<template>
  <div class="invest">
    <el-card class="box-card">
      <el-col :span="12" class="left-text">
        <div class="rowtext">Meta:</div>
        <div class="rowtext">Interés anual en moneda local:</div>
        <div class="rowtext">Contribuido:</div>
      </el-col>
      <el-col :span="12" class="right-text">
        <div class="rowtext">{{ communityData.project.goal }}</div>
        <div class="rowtext">{{ communityData.project.interest }}</div>
        <div class="rowtext">{{ communityData.project.contributed }}</div>
      </el-col>
      <div class="selectInvest">
        <selectInvest />
      </div>
    </el-card>
  </div>
</template>

<script>
import selectInvest from '../components/Select'
export default {
  name: 'InvestDetail',
  props: ['communityData'],
  data () {
    return {}
  },
  computed: {},
  methods: {},
  created: {},
  mounted: {},
  components: {
    selectInvest
  }
}
</script>

<style lang="scss" scoped>
@import "~/assets/scss/element-variables.scss";
.box-card {
  text-align: justify;
}
.right-text {
  color: #062f4f;
  font-weight: 800;
}
.rowtext {
  height: 10vh;
}
.col-div {
  height: 5vh;
}
</style>
