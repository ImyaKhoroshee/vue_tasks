<template>
  <!-- <Authentication :isAuth="isAuthenticated" />
  <UserList />
  <MortgageCalculator /> -->
  <Productdetails />
</template>

<script>
// import Authentication from "./components/Authentication.vue";
// import MortgageCalculator from "./components/MortgageCalculator.vue";
// import UserList from "./components/UserList.vue";
import Productdetails from "./components/Productdetails.vue";

export default {
  name: "App",
  components: {
    // Authentication,
    // UserList,
    // MortgageCalculator,
    Productdetails,
  },
  data() {
    return {
      // isAuthenticated: false,
    };
  },
};
</script>

<style lang="scss"></style>
