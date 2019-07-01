<template>
  <div id="q-app">
    <!-- <app-nav :main-app-name="appName" :sub-app-name="appSubName"></app-nav> -->
    <router-view />
  </div>
</template>

<script>
//import AppNav from './components/shared/AppNav.vue';
export default {
  name: "App",
  // components: {
  //   AppNav
  // },
  //  data() {
  //   return {
  //     role: {
  //       careManager: true,
  //     },
  //     appName: 'GSI',
  //     appSubName: 'Health',
  //   };
  // },
};
</script>

<style></style>
