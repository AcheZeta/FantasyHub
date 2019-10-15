<template>
  <eh-layout>
    <h1>{{ msg }}</h1>
    <div>
    <div v-for="item in community" :key="item.name">
      {{ item.name }}
    </div>
    </div>
  </eh-layout>
</template>

<script>
import BaseLayout from '@/layouts/BaseLayout.vue'
import axios from 'axios'
import env from '../../config/env'

/**
 * Here goes the "main screen" with communitie's cards
 */

export default {
  name: 'Communities',
  data () {
    return {
      msg: 'Conectamos personas. Cosechamos Riquezas',
      community: []
    }
  },
  created: async function () {
    let communitieResp = await axios.get(`${env.endpoint}/communities/`)
    this.community = communitieResp.data
    console.log(this.community)
  },
  mounted () {},
  methods: {},
  components: {
    'eh-layout': BaseLayout
  }
}
</script>

<style lang="scss" scoped>
</style>
