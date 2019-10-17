<template>
  <eh-layout>
    <img :src="communityData.image" alt="altText" />
    <span>{{ communityData.name }}</span>
    <div>{{ communityData.description }}</div>
  </eh-layout>
</template>

<script>
import BaseLayout from '@/layouts/BaseLayout.vue';
import axios from 'axios';
import env from '../../config/env';
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
      communityData: [],
      idComm: this.$route.params.id
    }
  },
  computed: {},
  methods: {},
  created: async function () {
    let communitieResp = await axios.get(
      `${env.endpoint}/communities/${this.$route.params.communityID}`
    )
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
