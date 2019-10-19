<template>
  <div class="map">
    <el-image :src="map" alt="mapa"></el-image>
  </div>
</template>

<script>
export default {
  name: 'Map',
  data () {
    return {
      map:
        'https://raw.githubusercontent.com/AcheZeta/FantasyHub/dev/src/assets/images/Map.jpg'
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
