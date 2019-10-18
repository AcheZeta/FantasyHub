<template>
  <div class="header">
    <el-menu class="el-menu-demo" mode="horizontal">
      <el-menu-item>
        <router-link to="/">
          <Logo />
        </router-link>
      </el-menu-item>
      <el-menu-item>
        <Menu />
      </el-menu-item>
    </el-menu>
    <div class="line"></div>
  </div>
</template>

<script>
import Menu from './Menu'
import Logo from './Logo'

export default {
  name: 'Header',
  data () {
    return {}
  },
  mounted () {},
  methods: {},
  components: {
    Menu,
    Logo
  }
}
</script>

<style lang="scss" scoped>
@import "~/assets/scss/element-variables.scss";

.header {
  border-bottom: solid 1px $--color-gray;
}
</style>
