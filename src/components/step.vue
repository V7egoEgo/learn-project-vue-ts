<template lang="">
    <div>
        
    </div>
</template>
<script>
import { defineComponent, ref } from 'vue';
export default {

    setup() {
    const name = ref<string>('');

    function chouse(text: string) {
      name.value = text;
    }

    return {
      name,
      chouse
    };
  }
}
</script>
<style lang="">
    
</style>