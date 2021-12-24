<template>
  <button @click='show = !show'>Toggle transition</button>
  <transition name='fade'>
    <p v-if='show'>Hello World!</p>
  </transition>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'TestTransition',
  setup() {
    const show = ref(false);
    return { show };
  },
};
</script>

<style scoped lang='scss'>
.fade-enter-active,
.fade-leave-active {
  transition: opacity .5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>

<!-- https://v3.vuejs.org/guide/transitions-enterleave.html#transition-classes -->
