<template>
  <button class="btn-acent" @click="action">
    <slot></slot>
  </button>
</template>

<script>
export default {
  setup(props, { emit }) {
    
    const action = () => {
      emit('action')
    };

    return {
      action
    };
  }
};
</script>
<style >

</style>