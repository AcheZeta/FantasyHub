<template>
  <eh-layout>
    <h1>{{ msg }}</h1>
  </eh-layout>
</template>

<script>
import BaseLayout from "@/layouts/BaseLayout.vue";
import axios from "axios";
import env from "../../config/env";
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
  created: async function() {
    let communitieResp = await axios.get(`${env.endpoint}/communities/`);
    console.log(communitieResp);
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
