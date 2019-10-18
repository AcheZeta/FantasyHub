<template>
  <div>
    <el-row :gutter="20" class="c-card">
      <el-col
        :span="6"
        v-for="community in community"
        :key="community.name"
        :offset="community > 0 ? 2 : 0"
      >
        <span class="color-succes txt">{{ community.name }}</span>
        <el-card :body-style="{ padding: '0px' }">
          <router-link :to="'/communities/'+ community.id">
            <img :src="community.image" class="image" />
          </router-link>
          <el-col :span="24">
            <el-card shadow="always" class="main txt">
              {{ community.project.name }}
              <div style="padding: 14px;">
                <div class="bottom clearfix">
                  <selectInvest />
                </div>
              </div>
              <span>
                Recibirás +
                <b>{{ community.project.interest }}%</b>
                <br />Interes anual en moneda local
              </span>
            </el-card>
          </el-col>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import axios from 'axios';
import env from '../../config/env';
import selectInvest from '../components/Select';

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
  components: {
    selectInvest
  }
}
</script>

<style lang="scss" scoped>
@import "~/assets/scss/element-variables.scss";
@import url("https://fonts.googleapis.com/css?family=Nunito&display=swap");

.button {
  border-color: $--color--button;
  color: $--color-text-q;
  background-color: $--color--button;
  font-size: $--button-font-size;
  border-radius: $--button-border-radius;
  font-weight: $--button-font-weight;
}

.main {
  font-weight: 800;
}

.txt {
  font-family: Nunito;
  font-size: $--font-display;
  letter-spacing: 1.32px;
  width: 100%;
}
</style>
