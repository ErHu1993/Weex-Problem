<template>
  <div class="wrapper">
    <image :src="logo" class="logo" @click="jump"></image>
    <text class="greeting">The environment is ready!</text>
    <text class="message">Now, let's use Vue.js to build your Weex app.</text>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        logo: 'https://gw.alicdn.com/tfs/TB1yopEdgoQMeJjy1XaXXcSsFXa-640-302.png',
      }
    },
    methods: {
      jump () {
        let path = weex.config.bundleUrl.split('index.js')[0]
        console.log(path)
        weex.requireModule('navigator').push({
        url: path + 'index-two.js',
        animated: 'true'
      })
      }
    }
  }
</script>

<style scoped>
  .wrapper {
    justify-content: center;
    align-items: center;
  }
  .logo {
    width: 424px;
    height: 200px;
  }
  .greeting {
    margin-top: 70px;
    font-size: 50px;
    color: #41B883;
  }
  .message {
    margin: 30px;
    font-size: 32px;
    color: #727272;
  }
</style>
