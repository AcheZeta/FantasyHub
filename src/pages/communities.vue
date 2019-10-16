<template>
  <eh-layout>
    <h1>{{ msg }}</h1>
    <div class="c-card">
      <el-row>
        <el-col
          :span="8"
          v-for="community in community"
          :key="community.name"
          :offset="index > 0 ? 2 : 0"
        >
          <el-card :body-style="{ padding: '0px' }">
            <img :src="community.image" class="image" />
            <div style="padding: 14px;">
              <span>{{ community.name }}</span>
              <div class="bottom clearfix">
                <el-button type="text" class="button">Operating</el-button>
              </div>
            </div>
          </el-card>
        </el-col>
      </el-row>
    </div>
  </eh-layout>
</template>

<script>
import BaseLayout from '@/layouts/BaseLayout.vue';
import axios from 'axios';
import env from '../../config/env';

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
