<template>
  <div id="app">
    <h1>Welcome to Bands</h1>
    <BandList></BandList>
  </div>
</template>

<script>
import BandList from './components/BandList.vue'

export default {
  name: 'app',
  components: {
    BandList
  }
}
</script>

<style>
</style>
