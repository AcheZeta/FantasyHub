<template>
  <eh-layout>
    <h1>{{ msg }}</h1>
    <el-row>
      <el-col :xs="24" :sm="12" :md="8" :lg="8" :xl="8" v-for="item in community" :key="item.name">
        <el-card :body-style="{ padding: '0px' }">
          <img :src="item.image" class="image" />
          <div>
            <span>{{ item.name }}</span>
            <span>{{ item.location }}</span>
            <div class="bottom clearfix">
              <!-- <time class="time">{{ currentDate }}</time> -->
              <el-button type="text" class="button">Operating</el-button>
            </div>
          </div>
        </el-card>
      </el-col>
    </el-row>
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
.image {
  width: 100%;
  height: 50vh;
  display: block;
}
/*
  .bottom {
    margin-top: 13px;
    line-height: 12px;
  }

  .button {
    padding: 0;
    float: right;
  }

  .clearfix:before,
  .clearfix:after {
      display: table;
      content: "";
  }

  .clearfix:after {
      clear: both
  } */
</style>
