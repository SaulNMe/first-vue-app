<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <PrimaryBtn 
      v-bind:text="state" 
      :changeState="changeState"
      v-bind:disabled="disable"
    />
    <HelloWorld msg="Welcome to Your Vue.js App jojojo" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import PrimaryBtn from "@/components/PrimaryBtn.vue";

export default {
  name: "home",
  components: {
    HelloWorld,
    PrimaryBtn
  },
  data() {
    return {
      state: 'Click me!',
      disable: false
    }
  },
  methods: {
    changeState() {
      this.disable = true;
    }
  },
};
</script>
