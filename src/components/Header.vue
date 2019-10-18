<template>
  <div class="header">
    <div class="logo-right">
      <Menu />
    </div>
    <div class="logo-left">
      <router-link to="/">
        <Logo />
      </router-link>
    </div>
    <div class="line"></div>
  </div>
</template>

<script>
import Menu from './Menu';
import Logo from './Logo';

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
  position: absolute;
  top: 0;
  width: 100%;
  display: block;
}

.header > .logo-left {
  float: left;
}

.header > .logo-right {
  float: right;
}
</style>
