<template>
  <div class="header">
    <el-menu
      :default-active="activeIndex"
      class="el-menu-demo"
      mode="horizontal"
      @select="handleSelect"
    >
      <el-menu-item index="1">
        <Menu />
      </el-menu-item>
    </el-menu>
    <div class="line"></div>
  </div>
</template>

<script>
import Menu from './Menu';
export default {
  name: 'Header',
  data () {
    return {}
  },
  mounted () {},
  methods: {},
  components: {
    Menu
  }
}
</script>

<style lang="scss" scoped>
@import "~/assets/scss/element-variables.scss";

.header {
  border-bottom: solid 1px $--color-gray;
}
</style>
