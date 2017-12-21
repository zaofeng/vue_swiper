<template>
  <div>
    <banner :bannerList="bannerList" v-if="flag"></banner>
    <div class="loading" v-else>
      <img :src="img">
    </div>
  </div>
</template>
<script>
import Banner from './HelloWorld'
export default {
  components: {
    Banner
  },
  data () {
    return {
      bannerList: [],
      flag: false,
      img: require('../assets/loading.svg')
    }
  },
  mounted () {
    setTimeout(() => {
      this.bannerList = [{
        url: '//ascdn.baidu.com/0df2e2444e6024f08398a07ed497384c71be9a82d.jpeg'
      }, {
        url: '//ascdn.baidu.com/00295a56ab1a744f601da8650d998481d6b4ad59c.jpeg'
      }, {
        url: '//ascdn.baidu.com/09e754fe0e0098e8a299c35a164589bead740cd4c.jpeg'
      }]
      this.flag = true
    }, 2000)
  }
}
</script>
<style lang="scss">
.loading {
    height: 160px;
    width: 100%;
    position: relative;
    background: #999;
    img{
      position: absolute;
      transform: translate(-50%, -50%);
      top: 50%;
      left: 50%;
    }
  }
  
</style>


