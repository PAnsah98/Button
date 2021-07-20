<template>
  <div id="show-button">
   <button v-bind:class="{'red':clicked, 'blue':clicked}" v-on:click="clicked = !clicked">{{loading}}</button>
    </div>
</template>

<script>
export default {
    props: ['loading'],
    data(){
        return{
      clicked: true
    }
    },
    methods: {
 
    }
    
}
</script>

<style>
.red {
    background-color: red;
    width: 200px;
    height: 20px;
}

.blue {
    background-color: blue;
    width: 100px;
    height: 30px;
    color: white;
}

</style>