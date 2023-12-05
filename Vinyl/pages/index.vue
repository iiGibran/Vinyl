<template>
  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
  </template>

<script>
export default {
  name: 'IndexPage',
  async asyncData({ $http }) {
    // Fetch data from Strapi
    const response = await $http.get('/home'); // Replace with your Strapi endpoint
    const data = response.data;

    return { data };
  },
}
</script>
