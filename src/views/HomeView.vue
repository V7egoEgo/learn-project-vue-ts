<template>
  <div class="conteiner">
    <div class="first__task">
      <MyButton
        class="btn-acent" 
        :class="{ 'btn-active': name === 'one' }"
        @action="chouse('one')"
      >
        one
      </MyButton>
      <MyButton 
        class="btn-acent"
        :class="{ 'btn-active': name === 'two' }" 
        @action="chouse('two')"
      >
        two
      </MyButton>
      <MyButton 
        class="btn-acent"
        :class="{ 'btn-active': name === 'thre' }" 
        @action="chouse('thre')"
      >
        thre
      </MyButton>
      <MyButton 
        class="btn-acent" 
        :class="{ 'btn-active': name === 'thour' }"
        @action = "chouse('thour')"
      >
        четыре
      </MyButton>
    </div>
  </div>



</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import MyButton from '@/components/my-btn.vue';
import StepOne from '@/components/steps/step-one.vue';
import StepTwo from '@/components/steps/step-two.vue'
import Stepthre from '@/components/steps/step-three.vue'
import StepFoure from '@/components/steps/step-foure.vue'

export default defineComponent({
  components: {
    MyButton
  },
  setup() {

    const name = ref<string>('');

    function chouse(text: string) {
      name.value = text;
      console.log(text)
    }

    return {
      name,
      chouse
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

.btn-active
{
  cursor: pointer;
  background-color: #4ed421;
  color: white;
  border: 1px solid #297410;
  &:hover
  {
    padding: 10px;
    background-color: white;
    border: 1px solid #4ed421;
    border-radius: 16px;
    color: black;
  }
}
.btn-acent
{
  padding: 10px;
  background-color: white;
  border: 1px solid #4ed421;
  border-radius: 16px;
  &:hover
  {
    cursor: pointer;
    background-color: #4ed421;
    color: white;
    border: 1px solid #297410;
  }
}
</style>