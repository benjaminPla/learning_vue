<template>
  <emit-v-model :modelValue='emitTest' @update:modelValue='emitTest = $event' />
  <test-slot>Testing text... {{ testStlot }}</test-slot>
</template>

<script>
import { ref } from 'vue';
import EmitVModel from '../components/EmitVModel.vue';
import TestSlot from '../components/TestSlot.vue';

export default {
  name: 'Home',
  components: { EmitVModel, TestSlot },
  setup() {
    const emitTest = ref('');
    const testStlot = 'Another test slot text...';
    return { emitTest, testStlot };
  },
};
</script>
