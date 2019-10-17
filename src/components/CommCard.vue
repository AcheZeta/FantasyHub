<template>
  <div>
    <el-row :gutter="20" class="c-card">
      <el-col
        :span="6"
        v-for="community in community"
        :key="community.name"
        :offset="community > 0 ? 2 : 0"
      >
        <span>{{ community.name }}</span>
        <el-card :body-style="{ padding: '0px' }">
          <img :src="community.image" class="image" />
          <div style="padding: 14px;">
            <span>{{ community.name }}</span>
            <div class="bottom clearfix">
              <router-link :to="'/communities/'+ community.id">
                <el-button type="text" class="button">Invertir</el-button>
              </router-link>
            </div>
          </div>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import axios from 'axios';
import env from '../../config/env';

/**
 * Here goes the "main screen" with communitie's cards
 */

export default {
  name: 'CommunitiesCard',
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
  components: {}
}
</script>
