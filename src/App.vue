<script>
export default {
  created () {
    // 调用API从本地缓存中获取数据
    const logs = wx.getStorageSync('logs') || []
    logs.unshift(Date.now())
    wx.setStorageSync('logs', logs)

    console.log('app created and cache logs by setStorageSync')
  }
}
</script>

<style>
.container {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  padding: 200rpx 0;
  box-sizing: border-box;
}
/* this rule will be remove */
* {
  transition: width 2s;
  -moz-transition: width 2s;
  -webkit-transition: width 2s;
  -o-transition: width 2s;
}

.ytx-wxa .pt36 {
  font-size: 72rpx;
  line-height: 100rpx;
  font-weight: bold;
}
.ytx-wxa .pt27 {
  font-size: 54rpx;
  line-height: 76rpx;
  font-weight: bold;
}
.ytx-wxa .pt24 {
  font-size: 48rpx;
  line-height: 68rpx;
  font-weight: bold;
}
.ytx-wxa .pt19 {
  font-size: 38rpx;
  line-height: 54rpx;
  font-weight: bold;
}
.ytx-wxa .pt17-title,
.ytx-wxa .btn-big-normal,
.ytx-wxa .btn-big-press,
.ytx-wxa .btn-big-ghost-normal,
.ytx-wxa .btn-big-ghost-press,
.ytx-wxa .btn-big-ghost-gray,
.ytx-wxa .btn-big-disabled {
  font-size: 34rpx;
  line-height: 48rpx;
  font-weight: bold;
}
.ytx-wxa .pt17-content {
  font-size: 34rpx;
  line-height: 48rpx;
  font-weight: normal;
  line-height: 27rpx;
}
.ytx-wxa .pt15-content {
  font-size: 30rpx;
  line-height: 42rpx;
  font-weight: normal;
  line-height: 24rpx;
}
.ytx-wxa .pt15-stockname,
.ytx-wxa .btn-middle-normal,
.ytx-wxa .btn-middle-press,
.ytx-wxa .btn-middle-ghost-normal,
.ytx-wxa .btn-middle-ghost-press,
.ytx-wxa .btn-middle-ghost-gray,
.ytx-wxa .btn-middle-disabled,
.ytx-wxa .btn-small-normal,
.ytx-wxa .btn-small-press,
.ytx-wxa .btn-small-ghost-normal,
.ytx-wxa .btn-small-ghost-press,
.ytx-wxa .btn-small-ghost-gray,
.ytx-wxa .btn-small-disabled {
  font-size: 30rpx;
  line-height: 42rpx;
  font-weight: bold;
}
.ytx-wxa .pt15 {
  font-size: 30rpx;
  line-height: 42rpx;
  font-weight: normal;
}
.ytx-wxa .pt14 {
  font-size: 28rpx;
  line-height: 40rpx;
  font-weight: normal;
}
.ytx-wxa .pt13 {
  font-size: 26rpx;
  line-height: 36rpx;
  font-weight: normal;
}
.ytx-wxa .pt13-button,
.ytx-wxa .btn-mini-normal,
.ytx-wxa .btn-mini-press,
.ytx-wxa .btn-mini-ghost-normal,
.ytx-wxa .btn-mini-ghost-press,
.ytx-wxa .btn-mini-ghost-gray,
.ytx-wxa .btn-mini-disabled {
  font-size: 26rpx;
  line-height: 36rpx;
  font-weight: bold;
}
.ytx-wxa .pt11 {
  font-size: 22rpx;
  line-height: 30rpx;
  font-weight: normal;
}
.ytx-wxa .pt10 {
  font-size: 20rpx;
  line-height: 28rpx;
  font-weight: normal;
}
.ytx-wxa .pt8 {
  font-size: 16rpx;
  line-height: 22rpx;
  font-weight: normal;
}
.ytx-wxa .btn-big-normal {
  width: 600rpx;
  height: 88rpx;
  line-height: 88rpx;
  border-radius: 44rpx;
  color: #fff;
  background-image: linear-gradient(to right, #f33, #ff794c);
}
.ytx-wxa .btn-big-press {
  width: 600rpx;
  height: 88rpx;
  line-height: 88rpx;
  border-radius: 44rpx;
  color: #fff;
  background-image: linear-gradient(to right, #e62e2e, #e66d45);
}
.ytx-wxa .btn-big-ghost-normal {
  width: 600rpx;
  height: 88rpx;
  line-height: 88rpx;
  border-radius: 44rpx;
  color: #f33;
  border: 2rpx #f33 solid;
  background-color: #fff;
}
.ytx-wxa .btn-big-ghost-press {
  width: 600rpx;
  height: 88rpx;
  line-height: 88rpx;
  border-radius: 44rpx;
  color: #f33;
  border: 2rpx #f33 solid;
  background-color: rgba(255,51,51,0.098);
}
.ytx-wxa .btn-big-ghost-gray {
  width: 600rpx;
  height: 88rpx;
  line-height: 88rpx;
  border-radius: 44rpx;
  color: #666;
  border: 2rpx #666 solid;
  background-color: #fff;
}
.ytx-wxa .btn-big-disabled {
  width: 600rpx;
  height: 88rpx;
  line-height: 88rpx;
  border-radius: 44rpx;
  color: #fff;
  background-color: #ccc;
  border: 0;
}
.ytx-wxa .btn-middle-normal {
  width: 500rpx;
  height: 64rpx;
  line-height: 64rpx;
  border-radius: 32rpx;
  color: #fff;
  background-image: linear-gradient(to right, #f33, #ff794c);
}
.ytx-wxa .btn-middle-press {
  width: 500rpx;
  height: 64rpx;
  line-height: 64rpx;
  border-radius: 32rpx;
  color: #fff;
  background-image: linear-gradient(to right, #e62e2e, #e66d45);
}
.ytx-wxa .btn-middle-ghost-normal {
  width: 500rpx;
  height: 64rpx;
  line-height: 64rpx;
  border-radius: 32rpx;
  color: #f33;
  border: 2rpx #f33 solid;
  background-color: #fff;
}
.ytx-wxa .btn-middle-ghost-press {
  width: 500rpx;
  height: 64rpx;
  line-height: 64rpx;
  border-radius: 32rpx;
  color: #f33;
  border: 2rpx #f33 solid;
  background-color: rgba(255,51,51,0.098);
}
.ytx-wxa .btn-middle-ghost-gray {
  width: 500rpx;
  height: 64rpx;
  line-height: 64rpx;
  border-radius: 32rpx;
  color: #666;
  border: 2rpx #666 solid;
  background-color: #fff;
}
.ytx-wxa .btn-middle-disabled {
  width: 500rpx;
  height: 64rpx;
  line-height: 64rpx;
  border-radius: 32rpx;
  color: #fff;
  background-color: #ccc;
  border: 0;
}
.ytx-wxa .btn-small-normal {
  width: 280rpx;
  height: 56rpx;
  line-height: 56rpx;
  border-radius: 28rpx;
  color: #fff;
  background-image: linear-gradient(to right, #f33, #ff794c);
}
.ytx-wxa .btn-small-press {
  width: 280rpx;
  height: 56rpx;
  line-height: 56rpx;
  border-radius: 28rpx;
  color: #fff;
  background-image: linear-gradient(to right, #e62e2e, #e66d45);
}
.ytx-wxa .btn-small-ghost-normal {
  width: 280rpx;
  height: 56rpx;
  line-height: 56rpx;
  border-radius: 28rpx;
  color: #f33;
  border: 2rpx #f33 solid;
  background-color: #fff;
}
.ytx-wxa .btn-small-ghost-press {
  width: 280rpx;
  height: 56rpx;
  line-height: 56rpx;
  border-radius: 28rpx;
  color: #f33;
  border: 2rpx #f33 solid;
  background-color: rgba(255,51,51,0.098);
}
.ytx-wxa .btn-small-ghost-gray {
  width: 280rpx;
  height: 56rpx;
  line-height: 56rpx;
  border-radius: 28rpx;
  color: #666;
  border: 2rpx #666 solid;
  background-color: #fff;
}
.ytx-wxa .btn-small-disabled {
  width: 280rpx;
  height: 56rpx;
  line-height: 56rpx;
  border-radius: 28rpx;
  color: #fff;
  background-color: #ccc;
  border: 0;
}
.ytx-wxa .btn-mini-normal {
  width: 144rpx;
  height: 42rpx;
  line-height: 42rpx;
  border-radius: 21rpx;
  color: #fff;
  background-image: linear-gradient(to right, #f33, #ff794c);
}
.ytx-wxa .btn-mini-press {
  width: 144rpx;
  height: 42rpx;
  line-height: 42rpx;
  border-radius: 21rpx;
  color: #fff;
  background-image: linear-gradient(to right, #e62e2e, #e66d45);
}
.ytx-wxa .btn-mini-ghost-normal {
  width: 144rpx;
  height: 42rpx;
  line-height: 42rpx;
  border-radius: 21rpx;
  color: #f33;
  border: 2rpx #f33 solid;
  background-color: #fff;
}
.ytx-wxa .btn-mini-ghost-press {
  width: 144rpx;
  height: 42rpx;
  line-height: 42rpx;
  border-radius: 21rpx;
  color: #f33;
  border: 2rpx #f33 solid;
  background-color: rgba(255,51,51,0.098);
}
.ytx-wxa .btn-mini-ghost-gray {
  width: 144rpx;
  height: 42rpx;
  line-height: 42rpx;
  border-radius: 21rpx;
  color: #666;
  border: 2rpx #666 solid;
  background-color: #fff;
}
.ytx-wxa .btn-mini-disabled {
  width: 144rpx;
  height: 42rpx;
  line-height: 42rpx;
  border-radius: 21rpx;
  color: #fff;
  background-color: #ccc;
  border: 0;
}
.ytx-wxa .center-center {
  display: flex;
  align-items: center;
  justify-content: center;
}
.ytx-wxa .line-horizontal {
  height: 1rpx;
  background-color: #e6e6e6;
}
.ytx-wxa .line-vertical {
  width: 1rpx;
  background-color: #e6e6e6;
}

</style>
