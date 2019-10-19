<template>
  <eh-layout>
    <el-row :gutter="20">
      <el-col :span="14">
        <div class="block">
          <Detail />
          <Map />
        </div>
      </el-col>
      <el-col :span="10">
        <div class="block">
          <Invest :communityData="communityData" />
        </div>
      </el-col>
    </el-row>
  </eh-layout>
</template>

<script>
import BaseLayout from '@/layouts/BaseLayout.vue'
import axios from 'axios'
import env from '../../config/env'
import Map from '../components/Map'
import Detail from '../components/DetailCard'
import Invest from '../components/InvestCard'
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
  },
  mounted () {},
  components: {
    'eh-layout': BaseLayout,
    Map,
    Detail,
    Invest
  }
}
</script>

<style lang="scss" scoped>
.communityData {
  width: 50vh;
  float: left;
  padding: 1em;
}
</style>
