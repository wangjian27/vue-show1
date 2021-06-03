<template>
  <div id="shareTech">
    <div>
      <img :src="setSrc" alt="图片加载失败...">
      <br>
      <br>
      <el-button type="primary" @click="openLink">打开链接</el-button>
      <br>
      <span><strong>账号：</strong>{{user}}</span>
      <br>
      <span><strong>密码：</strong>{{password}}</span>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {

    }
  },
  props: ['src', 'url', 'user', 'password'],
  computed: {
    setSrc () {
      return require(`../../assets/${this.src}`)
    }
  },
  methods: {
    openLink () {
      window.open(this.url)
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
