<template>
  <div>
    <el-card class="box-card">
      <div class="text item">
        {{data}}
      </div>
    </el-card>
  </div>
</template>

<script>
export default {
  data () {
    return {
      data: '技术分享'
    }
  }
}
</script>

<style lang="less" scoped>
.el-card {
  div {
    display: flex;
    justify-content: center;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size: 70px;
    color: darkturquoise;
  }
}
</style>
