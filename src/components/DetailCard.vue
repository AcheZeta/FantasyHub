<template>
  <div>
    <div class="block">
      <el-image :src="communityData.image" :alt="communityData.name"></el-image>
      <span class="name">{{ communityData.name }}</span>
      <div class="description">{{ communityData.description }}</div>
      <Map />
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import env from '../../config/env';
/**
 * Here goes the detail cards
 */
export default {
  name: 'Detail',
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
  components: {}
}
</script>

<style lang="scss" scoped>
</style>
