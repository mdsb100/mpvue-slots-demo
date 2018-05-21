<template>
  <view @transitionend="animationEnd" :animation="shareContainerAnimation" :style="{height: height+'px',marginTop:(-height*0.5)+'px',left: shareContainerLeft+'rpx', transform: 'scale(0.7)', backgroundColor: 'rgba(0,0,0,0.7)'}" class="alertContainer" >
    <slot></slot>
  </view>
</template>

<style scoped>
.alertContainer {
  width: 750rpx;
  position: fixed;
  top: 50%;
  left: -750rpx;
  background-color: red;
}
</style>

<script>
export default {
  props: {
    height: {
      type: Number,
      default: 0
    }
  },
  data () {
    return {
      shareContainerAnimation: {},
      shareContainerLeft: -750,
      isShow: false
    }
  },
  methods: {
    show () {
      setTimeout(() => {
        this.isShow = true
        this.shareContainerLeft = 0
      }, 0)

      var animation = wx.createAnimation({
        transformOrigin: '50% 50%',
        duration: 200,
        timingFunction: 'ease',
        delay: 0
      })

      animation.scale(1, 1).step()
      setTimeout(() => {
        this.shareContainerAnimation = animation.export()
      }, 0)
    },
    hide () {
      setTimeout(() => {
        this.isShow = false
        this.shareContainerLeft = -750
      }, 0)
      var animation = wx.createAnimation({
        transformOrigin: '50% 50%',
        duration: 0,
        timingFunction: 'ease',
        delay: 0
      })
      animation.scale(0.7, 0.7).step()
      setTimeout(() => {
        this.shareContainerAnimation = animation.export()
      }, 0)
    },
    animationEnd (e) {
      this.$emit(this.isShow ? 'showAnimationEnd' : 'hideAnimationEnd', this)
    }
  }
}
</script>
