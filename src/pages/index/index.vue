<template>
  <view class="index">
    <NumberDisplay/>
    <NumberSubmit/>
    <button @tap="toWebView('https://daxigua-xi-jade.vercel.app')">
      test btn
    </button>
  </view>
</template>

<script>
import NumberDisplay from '../../components/NumberDisplay.vue'
import NumberSubmit from '../../components/NumberSubmit.vue'
import {onMounted} from 'vue'
import Taro from '@tarojs/taro'
export default {
  name: 'Index',
  components: {
    NumberDisplay,
    NumberSubmit
  },


  // data() {
  // },
  // methods: {
  //   toWebView (e) {
  //     console.log(e)
  //   }
  // }



  setup() {
    const toWebView = (src) => {
      console.log(src)
      Taro.navigateTo({
        url: `/pages/web-view/web-view?src=${src}`,
      })
    }
    onMounted(() => {
      console.log('onMounted00')
    })
    return {
      toWebView
    }
  }
}
</script>

<style>
.index {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
