<template>
  <el-container>
    <!-- 头部 -->
    <el-header>
      <div>
        <img src="../assets/logo.png" alt="图片加载失败..." />
        <span>技术分享</span>
      </div>
    </el-header>
    <el-container>
      <!-- 菜单栏 -->
      <el-aside :width="isCollapse?'64px' :'200px'">
        <div class="toggle-button" @click="toggleCollapse">|||</div>
        <el-menu background-color="#333744" text-color="#fff" active-text-color="#409eff" :unique-opened="true" :collapse="isCollapse" :collapse-transition="false" router :default-active="activeMenu">
          <el-submenu :index="item.id+''" v-for="item in menuList" :key="item.id">
            <!-- 一级菜单模板区 -->
            <template slot="title">
              <i :class="iconsObj[1]"></i>
              <span>{{ item.authName }}</span>
            </template>
            <el-menu-item :index="'/'+item1.path" v-for="item1 in item.children" :key="item1.id">
              <template slot="title">
                <!-- <i class="el-icon-menu"></i> -->
                <span>{{item1.authName}}</span>
              </template>
            </el-menu-item>
          </el-submenu>
        </el-menu>
      </el-aside>
      <!-- 主体区 -->
      <el-main>
        <router-view></router-view>
      </el-main>
    </el-container>
  </el-container>
</template>
<script>
export default {
  name: 'Home',
  data () {
    return {
      provideData: 'provideData',
      parent: 'parent',
      eventBusData: 'eventBusData',
      menuList: [
        {
          id: 1,
          authName: '高胜钰',
          children: [{
            id: 2,
            authName: '下拉多选',
            path: 'drop-list'
          }]
        },
        {
          id: 3,
          authName: '黄贯中',
          children: [
            {
              id: 4,
              authName: 'siuma编号',
              path: 'siuma-number'
            },
            {
              id: 5,
              authName: '目录记住',
              path: 'remember-list'
            }
          ]
        },
        {
          id: 6,
          authName: '汪健',
          children: [
            {
              id: 7,
              authName: '报错不关闭',
              path: 'error-no-close'
            },
            {
              id: 8,
              authName: '预验证',
              path: 'pretest'
            }
          ]
        }
      ],
      iconsObj: {
        1: 'el-icon-user-solid',
        2: 'el-icon-s-tools',
        3: 'el-icon-s-goods',
        4: 'el-icon-s-claim',
        5: 'el-icon-s-marketing'
      },
      // 是否折叠
      isCollapse: false,
      // 当前激活的目录
      activeMenu: ''
    }
  },
  created () {
    this.defaultActive()
  },
  // beforeUpdate () {
  //   this.defaultActive()
  // },
  methods: {
    toggleCollapse () {
      this.isCollapse = !this.isCollapse
    },
    defaultActive () {
      const nowHash = this.$route.path
      this.activeMenu = nowHash
    }
  }
}
</script>
<style lang="less" scoped>
.el-container {
  width: 100%;
  height: 100%;
}
.el-header {
  background-color: #373d41;
  display: flex;
  justify-content: space-between;
  padding-left: 0;
  align-items: center;
  div {
    display: flex;
    align-items: center;
  }
  img {
    width: 50px;
    height: 50px;
    display: inline-block;
  }
  span {
    color: white;
    font-size: 20px;
    margin-left: 15px;
  }
}
.el-aside {
  background-color: #333744;
  .el-menu {
    border-right: 0;
  }
  .toggle-button {
    background-color: #4a5064;
    font-size: 10px;
    line-height: 24px;
    color: #fff;
    text-align: center;
    letter-spacing: 0.2em;
    cursor: pointer;
    user-select: none;
  }
}
.el-main {
  background-color: #eaedf1;
}
</style>
