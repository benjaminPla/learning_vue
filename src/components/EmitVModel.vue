<template>
  <input
    type='text'
    placeholder='Emit test...'
    @input='$emit("update:modelValue", $event.target.value)'>
</template>

<script>
export default {
  name: 'EmitVModel',
  props: ['modelValue'],
  emits: ['update:modelValue'],
};
</script>
