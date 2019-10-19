<template>
  <eh-layout>
    <el-col :span="14">
      <div class="block">
        <el-image :src="communityData.image" :alt="communityData.name"></el-image>
        <span class="name">{{ communityData.name }}</span>
        <div class="description">{{ communityData.description }}</div>
        <div class="map">
          <el-image :src="map" :alt="communityData.name"></el-image>
        </div>
      </div>
    </el-col>
    <el-col :span="10">
      <div class="block">
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Dicta, eaque, facere atque quidem quam deleniti molestiae hic eum iure recusandae deserunt libero perferendis magnam harum? Nihil repudiandae error officia rerum!</p>
      </div>
    </el-col>
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
      idComm: this.$route.params.id,
      map:
        'https://raw.githubusercontent.com/AcheZeta/FantasyHub/dev/src/assets/images/Map.jpg'
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
.communityData {
  width: 50vh;
  float: left;
  padding: 1em;
}
</style>
