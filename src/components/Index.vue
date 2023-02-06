<template>
  <div class="main_index">
    <LeafletMap :zoom="15" :center="[0, 0]" :locations="[{lat : -1, long : 0}, {lat : 0, long : 0}, {lat : 1, long : 0}]"/>
  </div>
</template>

<script>
export default {
  name: 'MainIndex',
  components: {
    LeafletMap
  }
}

import LeafletMap from '@/components/LeafletMap.vue'
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
