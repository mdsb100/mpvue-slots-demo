<template>
  <alert ref="alert" :height="height" @showAnimationEnd="showAnimationEnd">
    <view class="shareContainer ytx-wxa">
      <view class="shareCanvasContainer">
        <image :src="shareImagePath" class="shareCanvasImage"/>
        <view class="closeImageContainer center-center" @tap="closeShare">
          <image class="closeButton" :src="closeButtonImageSrc"/>
        </view>
      </view>
      <button class="btn-middle-normal timelineSaveButton" :disabled="shareButtonDisabled" open-type="share">{{buttonText}}</button>
    </view>
    <canvas canvas-id="shareCanvas" class="shareCanvas"/>
  </alert>
</template>

<style scoped>
.shareContainer {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.shareCanvas {
  height: 512rpx; 
  width: 640rpx;
  background-color: white;
  visibility: hidden;
  position: absolute;
  top: 0;
  left: -1500rpx;
}

.shareCanvasContainer {
  display: flex;
  flex-direction: row;
  position:relative;
  height: 512rpx; 
  width: 640rpx;
}

.shareCanvasImage {
  height: 512rpx;
  width: 640rpx;
  background-color: white;
}

.closeImageContainer {
  width: 68rpx;
  height: 68rpx;
  right: 0rpx;
  top: 0rpx;
  position: absolute;
  flex-direction: column;
}

.closeButton {
  width: 32rpx;
  height: 32rpx;
}

.timelineSaveButton {
  margin-top: 60rpx;
  width: 480rpx;
}

</style>

<script>
import Alert from '@/components/WXAMpvueAlert'

export default {
  props: {
    shareImagePath: {
      type: String,
      default: ''
    },
    height: {
      type: Number,
      default: 0
    },
    shareButtonDisabled: {
      type: Boolean,
      default: true
    },
    buttonText: {
      type: String,
      default: '分享到微信'
    },
    closeButtonImageSrc: {
      type: String,
      default: ''
    }
  },
  data () {
    return {}
  },
  computed: {

  },
  components: {
    alert: Alert
  },

  methods: {
    show () {
      this.$refs.alert.show()
    },
    hide () {
      this.$refs.alert.hide()
    },
    setShareImagePath (path) {
      this.shareImagePath = path
      this.$emit('pathchanged', path)
    },
    showAnimationEnd (alert) {
      this.$emit('drawShareCanvas', 'shareCanvas')
    },
    closeShare () {
      this.shareButtonDisabled = true
      this.hideShareAlert()
    },
    hideShareAlert () {
      this.hide()
      this.setShareImagePath('')
    }
  }

}
</script>
