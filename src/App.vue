<template>
  <div id="app">
    <show-button :loading="loading">I am awesome</show-button>
  </div>
</template>

<script>
import showButton from './showButton.vue';

export default {
  components: {
      'show-button': showButton
  },
 
  data () {
    return {
      loading: "Loading..."
    
    }
  }
}
</script>

<style>

</style>
