<template>
  <div>
    <ShareTech :src="src" :url="url"></ShareTech>
  </div>
</template>

<script>
import ShareTech from '../selfComponents/shareTech'
export default {
  data () {
    return {
      src: 'logo.png',
      url: 'http://www.baidu.com'
    }
  },
  components: {
    ShareTech
  }
}
</script>

<style lang="less" scoped>
</style>
