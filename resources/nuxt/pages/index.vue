<template>
    <div>
      <h1>Hello {{ user.name }}!</h1>
      <h3>This is from {{ user.description }}</h3>
    </div>
  </template>

  <script>
  export default {
    data() {
      return {
        user: null
      };
    },
    async created() {
      try {
        const response = await this.$axios.get('api/me');
        this.user = response.data;
      } catch (error) {
        console.error(error);
      }
    }
  };
  </script>