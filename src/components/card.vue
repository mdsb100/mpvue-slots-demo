<template>
  <div>
    <p class="card">
      {{text}}
    </p>
    <alert-share ref='kk' close-button-image-src="/static/static/icon_smallprogram_close_gray.png" @drawShareCanvas="drawShareSessionCanvas" @pathchanged="alertShareSessionPathChanged" :height="alertViewHeight"></alert-share>
  </div>
</template>

<script>
export default {
  props: ['text']
}
</script>

<style>
.card {
  padding: 10px;
}
</style>
