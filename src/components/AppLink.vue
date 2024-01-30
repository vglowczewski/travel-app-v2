<template>
    <a v-if="isExternal" 
      target="_blank"
      rel="noopener"
      class="external-link"
      :href="to"><slot/></a>
    <router-link v-else v-bind="$props" class="internal-link"><slot/></router-link>
  </template>
  
  <script>
  import { computed } from 'vue';
  import { RouterLink } from 'vue-router';

  export default {
    props: {
      ...RouterLink.props
    },
    setup(props) {
      const isExternal = computed(() => typeof props.to === 'string' && props.to.startsWith('http'));
      return {isExternal};
    }
  };
  </script>