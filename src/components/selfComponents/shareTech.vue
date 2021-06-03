<template>
  <div id="shareTech">
    <div>
      <img :src="setSrc" alt="图片加载失败...">
      <br>
      <br>
      <el-button type="primary" @click="openLink">打开链接</el-button>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      childSrc: this.src,
      childUrl: this.url
    }
  },
  props: ['src', 'url'],
  computed: {
    setSrc () {
      return require(`../../assets/${this.childSrc}`)
    }
  },
  methods: {
    openLink () {
      window.open(this.childUrl)
    }
  }
}
</script>

<style lang="less" scoped>
#shareTech {
  display: flex;
  justify-content: center;
  div {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}
</style>
