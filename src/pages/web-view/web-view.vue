<template>
  <web-view :src='src' onMessage={this.handleMessage} ></web-view>
</template>

<script>

export default {
  name: 'WebView',
  components: {
  },
  data () {
    return {
      src: ''
    }
  },
  methods: {
    handleMessage() {
    }
  },
  onLoad (e) {
    console.log(e)
    this.src = e.src
  }
}
</script>

<style>
</style>
