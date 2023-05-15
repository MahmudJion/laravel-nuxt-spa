<template>
    <div>
      <h1>Hello {{ user.name }}!</h1>
      <h3>This is from {{ user.description }}</h3>
    </div>
  </template>

  <script>
  export default {
    async asyncData({ $axios }) {
      const { data: user } = await $axios.get('api/me');
      return { user };
    },
  };
  </script>