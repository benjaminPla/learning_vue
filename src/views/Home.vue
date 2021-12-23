<template>
  <emit-v-model :modelValue='emitTest' @update:modelValue='emitTest = $event' />
  <test-slot>Testing text... {{ testSlot }}</test-slot>
  <button
    v-for='tab in tabs'
    :key='tab'
    @click='currentTab = tab'
  >
    {{ tab }}
  </button>
  <keep-alive>
    <component :is='currentTabComputed' />
  </keep-alive>
</template>

<script>
import { ref, computed } from 'vue';
import EmitVModel from '../components/EmitVModel.vue';
import TestSlot from '../components/TestSlot.vue';
import TestTab1 from '../components/TestTab1.vue';
import TestTab2 from '../components/TestTab2.vue';
import TestTab3 from '../components/TestTab3.vue';

export default {
  name: 'Home',
  components: {
    EmitVModel,
    TestSlot,
    TestTab1,
    TestTab2,
    TestTab3,
  },
  setup() {
    const emitTest = ref('');
    const testSlot = 'Another test slot text...';
    const tabs = ['TestTab1', 'TestTab2', 'TestTab3'];
    const currentTab = ref('TestTab1');
    const currentTabComputed = computed(() => currentTab.value);
    return {
      emitTest,
      testSlot,
      tabs,
      currentTab,
      currentTabComputed,
    };
  },
};
</script>
