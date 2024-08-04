<template>
  <div class="conteiner">
    <div class="first__task">
      <MyButton 
        :class="{ 'btn-active': name === 'StepOne' }"
        @action="chouse('StepOne')"
      >
        one
      </MyButton>
      <MyButton 
        :class="{ 'btn-active': name === 'StepTwo' }" 
        @action="chouse('StepTwo')"
      >
        two
      </MyButton>
      <MyButton 
        :class="{ 'btn-active': name === 'StepThre' }" 
        @action="chouse('StepThre')"
      >
        thre
      </MyButton>
      <MyButton  
        :class="{ 'btn-active': name === 'StepFoure' }"
        @action = "chouse('StepFoure')"
      >
        четыре
      </MyButton>
    </div>
    <component :is="ComponentName"></component>

  </div>



</template>

<script lang="ts">
import { defineComponent, ref, computed } from 'vue';
import MyButton from '@/components/my-btn.vue';
import StepOne from '@/components/steps/step-one.vue';
import StepTwo from '@/components/steps/step-two.vue';
import StepThre from '@/components/steps/step-thre.vue';
import StepFoure from '@/components/steps/step-foure.vue';  

export default defineComponent({
  components: {
    MyButton,
    StepOne,
    StepTwo,
    StepThre,
    StepFoure
  },
  setup() {

    const name = ref<string>('StepOne');

    function chouse(text: string) {
      name.value = text;
    }
    const ComponentName = computed(() => {
      return name.value
    });
    return {
      name,
      chouse,
      ComponentName
    };
  }
});
</script>
<style >
.conteiner
{
  max-width: 1170px;
  margin: 0 auto;
}
.first__task
{
  display: flex;
  justify-content: space-around;
  width: 600px;

}


</style>