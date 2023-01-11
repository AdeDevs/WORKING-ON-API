<template>
  <div class="main-container">
    <HomePage
      name="Adeyemi"
      title="This HomePage"
      msg="This homepage was built by"
    >
      <p>Hey This Works</p>
    </HomePage>
  </div>
</template>

<script>
import HomePage from "./components/HomePage.vue";

export default {
  name: "App",
  components: {
    HomePage,
  },
};
</script>

<style >
@import "./components/styles/app.css";
</style>
