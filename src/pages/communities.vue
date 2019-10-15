<template>
  <eh-layout>
    <h1>{{ msg }}</h1>
  </eh-layout>
</template>

<script>
import BaseLayout from "@/layouts/BaseLayout.vue";
/**
 * Here goes the "main screen" with communitie's cards
 */

export default {
  name: "Communities",
  data() {
    return {
      msg: "Conectamos personas. Cosechamos Riquezas"
    };
  },
  mounted() {},
  methods: {},
  components: {
    "eh-layout": BaseLayout
  }
};
</script>

<style lang="scss" scoped>
</style>
