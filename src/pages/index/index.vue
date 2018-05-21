<template>
  <div :style="{height: scrollViewHeight}" class="container ytx-wxa">
    <button class="btn-big-normal top" @click="showShareAlertSession">弹窗分享好友</button>
    <div class="userinfo" @click="clickHandle">
      <card :text="foo"></card>
      <CompA></CompA>
    </div>
    <alert-share ref='alertShare' close-button-image-src="/static/static/icon_smallprogram_close_gray.png" @drawShareCanvas="drawShareSessionCanvas" @pathchanged="alertShareSessionPathChanged" :height="alertViewHeight"></alert-share>
  </div>
</template>

<script>
import wxp from 'minapp-api-promise'

import card from '@/components/card'
import CompA from '@/components/CompA'

import AlertShare from '@/components/WXAMpvueAlertShareSessionComponent'

const systemInfo = wx.getSystemInfoSync()

function rpxToPx (rpx) {
  return systemInfo.windowWidth / 750 * parseInt(rpx)
}

export default {
  data () {
    return {
      motto: 'Hello World',
      userInfo: {},
      foo: Date.now(),
      shareSessionImagePath: '',
      alertViewHeight: systemInfo.windowHeight
    }
  },

  components: {
    card,
    CompA,
    'alert-share': AlertShare
  },

  methods: {
    clickHandle (msg, ev) {
      console.log('clickHandle:', msg, ev)
      this.foo = Date.now()
    },
    showShareAlertSession () {
      this.shareSessionImagePath = ''
      this.$refs.alertShare.show()
    },
    alertShareSessionPathChanged (path) {
      this.shareSessionImagePath = path
    },
    async drawShareSessionCanvas (cavansId) {
      this.$refs.alertShare.shareButtonDisabled = true
      const tempFilePath = await this.drawShareSession(cavansId)
      this.$refs.alertShare.shareButtonDisabled = false
      this.$refs.alertShare.setShareImagePath(tempFilePath)
    },
    async drawShareSession (canvasId) {
      return new Promise((resolve, reject) => {
        wx.showLoading({title: '生成中...'})
    // this.shareButtonDisabled = true
        const ctx = wx.createCanvasContext(canvasId)
        const canvasW = rpxToPx(640)
        const canvasH = rpxToPx(512)
    // 背景
        ctx.setFillStyle('red')
        ctx.fillRect(0, 0, canvasW, canvasH)
        ctx.draw(true, () => {
      // this.shareButtonDisabled = false
          setTimeout(async () => {
            const {tempFilePath} = await wxp.canvasToTempFilePath({
              x: 0,
              y: 0,
              width: canvasW,
              height: canvasH,
              quality: 1,
              canvasId: canvasId
            })
      // this.setShareImagePath(tempFilePath)
            resolve(tempFilePath)
            wx.hideLoading()
          }, 200)
        })
      })
    }
  }
}
</script>

<style scoped>
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}

</style>
