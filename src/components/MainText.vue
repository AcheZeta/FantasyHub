<template>
  <div class="container">
    <h1>{{ msg }}</h1>
    <p>{{ description }}</p>
  </div>
</template>

<script>
export default {
  name: 'MainText',
  data () {
    return {
      msg: 'Conectamos personas. Cosechamos Riquezas',
      description:
        'Inversiones desde ‎50 € en comunidades agrícolas productivas y rentables en todo el mundo'
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  padding: 1em;
  text-align: left;
}
</style>
