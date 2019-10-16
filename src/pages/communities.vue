<template>
  <eh-layout>
    <mainText />
    <commCard />
  </eh-layout>
</template>

<script>
import BaseLayout from '@/layouts/BaseLayout.vue';
import axios from 'axios';
import env from '../../config/env';
import commCard from '../components/CommCard';
import mainText from '../components/MainText';

/**
 * Here goes the "main screen" with communitie's cards
 */

export default {
  name: 'Communities',
  data () {
    return {
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
    'eh-layout': BaseLayout,
    commCard,
    mainText
  }
}
</script>

<style>
.bottom {
  margin-top: 13px;
  line-height: 12px;
}

.button {
  padding: 0;
  float: right;
}

.image {
  width: 100%;
  height: 30vh;
  display: block;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}

.clearfix:after {
  clear: both;
}
</style>
