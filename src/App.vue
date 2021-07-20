<template>
  <div id="app">
    <show-button :loading="showLoading" size="small" @click.native="doSomething">I am awesome</show-button>
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
      loading:  false

    }
  },

  computed:{
    showLoading(){
      return this.loading
    }
  },

  methods:{
   async doSomething(){
     this.loading = true
     await setTimeout( () => {
      this.loading = false
    }, 1000);
   }
 }
};
</script>
