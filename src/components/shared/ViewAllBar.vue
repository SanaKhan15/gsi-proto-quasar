<template>
  <p class="text-right q-mr-md" >
    <span class="text-weight-bolder ">{{count}}</span>
    of {{ total}}
    <span>
      <q-btn flat color="red-10">View all</q-btn>
    </span>
  </p>
</template>

<script>
export default {
  name: 'ViewAllBar',
  props: {
    count: Number,
    total: Number
  }
};
</script>

<style>
</style>
