<template>
  <div>
    <ShareTech :src="src" :url="url" :user="user" :password="password"></ShareTech>
  </div>
</template>

<script>
import ShareTech from '../selfComponents/shareTech'
export default {
  data () {
    return {
      src: 'logo.png',
      url: 'http://www.baidu.com',
      user: 'J08',
      password: 'amebiz'
    }
  },
  components: {
    ShareTech
  }
}
</script>

<style lang="less" scoped>
</style>
