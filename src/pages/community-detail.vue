<template>
  <eh-layout>Detail</eh-layout>
</template>

<script>
import BaseLayout from '@/layouts/BaseLayout.vue';
import axios from 'axios';
/**
 * Here goes the detail cards
 */
export default {
  name: 'CommunityDetail',
  props: {
    communityID: {
      type: [String, Number],
      required: true
    }
  },
  data () {
    return {
      community: null,
      communityData: []
    }
  },
  computed: {},
  methods: {},
  created: async function () {
    let communitieResp = await axios.get(`${env.endpoint}/communities/`)
    this.communityData = communitieResp.data
    console.log(this.communityData)
  },
  mounted () {},
  components: {
    'eh-layout': BaseLayout
  }
}
</script>

<style lang="scss" scoped>
</style>
