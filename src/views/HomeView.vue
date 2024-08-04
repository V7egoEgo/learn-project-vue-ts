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
        ref="myBtn"
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
    <keep-alive>
      <component :is="ComponentName"></component> 
    </keep-alive>

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
    const myBtn = ref<HTMLElement | null>()
    const name = ref<string>('StepOne');

    function chouse(step: string) {
      name.value = step;
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