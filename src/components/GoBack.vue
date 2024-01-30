<template>
    <span class="go-back">
      <button @click="goBack">go back</button>
    </span>
  </template>
  
  <script>
  import { useRoute, useRouter } from 'vue-router';
  
  export default {
    setup() {
      const router = useRouter();
      const goBack = () => {
        router.back();
      };
      return {goBack};
    },
  };
  </script>