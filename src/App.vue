<template>
  <div id="app">
    <show-button
      :backgroundColor="backgroundColor"
      size="small"
      :text="buttonText"
      @click.native="doSomething"
      >I am awesome</show-button
    >
  </div>
</template>

<script>
import showButton from "./showButton.vue";

export default {
  components: {
    "show-button": showButton,
  },

  data() {
    return {
      loading: false,
      backgroundColor: "#eee",
      buttonText: 'Click Me'
    };
  },

  computed: {
    showLoading() {
      return this.loading;
    },
  },

  methods: {
    simulateAsyncFunction: function () {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          const randomNum = Math.floor(Math.random() * 2) + 1;
          if (randomNum === 1) resolve("success");
          else reject("failed");
        }, 1000);
      });
    },
    doSomething: function () {
      this.buttonText = 'loading...'

      // reset the background color to the default anytime u are making a request
      this.backgroundColor = '#eee'
      
      this.simulateAsyncFunction()
        .then((res) => {
          this.backgroundColor = "green";
          this.buttonText = 'success'
        })
        .catch((error) => {
          this.backgroundColor = "red"
          this.buttonText = 'failed, retry'
        })
    },
  },
};
</script>