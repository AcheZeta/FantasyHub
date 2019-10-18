<template>
  <div class="header">
    <router-link to="/">
      <Logo />
    </router-link>
    <span></span>
    <Menu />
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
}
</style>
