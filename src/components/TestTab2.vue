<template>
  <h2>test tab 2</h2>
  <button @click='toggle'>Click me!</button>
  <p v-if='active'>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'TestTab2',
  setup() {
    const active = ref(false);
    const toggle = () => {
      active.value = !active.value;
    };
    return { active, toggle };
  },
};
</script>
