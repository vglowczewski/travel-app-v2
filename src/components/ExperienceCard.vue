<template>
    <div class="card">
        <img :src="`/images/${experience.image}`" :alt="experience.name">
        <span class="card__text">
            {{ experience.name }}
        </span>
    </div>
</template>
<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  props: {
    experience: { type: Object, required: true },
  },
  setup(props) {
    return {experience: props.experience};
  },
});
// export default{
//     props:{
//         experience:{type: Object, required: true,}
//     }
// }
</script>