<template>
  <div class="invest">
    <el-card class="box-card">
      <el-col :span="18">
        <div>Meta:</div>
        <div>Interés anual en moneda local:</div>
        <div>Contribuido:</div>
      </el-col>
      <el-col :span="6">
        <div>{{ communityData.project.goal }}</div>
        <div>{{ communityData.project.interest }}</div>
        <div>{{ communityData.project.contributed }}</div>
      </el-col>
    </el-card>
  </div>
</template>

<script>
export default {
  name: 'InvestDetail',
  props: ['communityData'],
  data () {
    return {}
  },
  computed: {},
  methods: {},
  // created: async function () {
  //   let communitieResp = await axios.get(
  //     `${env.endpoint}/communities/${this.$route.params.communityID}`
  //   )
  //   this.communityData = communitieResp.data
  // },
  mounted () {},
  components: {}
}
</script>

<style lang="scss" scoped>
</style>
