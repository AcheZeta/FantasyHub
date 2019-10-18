<template>
  <el-select v-model="value" placeholder="Invertir">
    <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value"></el-option>
  </el-select>
</template>

<script>
export default {
  name: 'SelectInvest',
  data () {
    return {
      options: [
        {
          value: '25',
          label: '25'
        },
        {
          value: '50',
          label: '50'
        },
        {
          value: '100',
          label: '100'
        }
      ],
      value: ''
    }
  }
}
</script>
