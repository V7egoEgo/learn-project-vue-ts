<template>
  <div class="conteiner">
    <div class="first__task">
      <button class="btn-acent" :class="{ 'btn-active': name === 'one' }" @click="chouse('one')">one</button>
      <button class="btn-acent" :class="{ 'btn-active': name === 'two' }" @click="chouse('two')">two</button>
      <button class="btn-acent" :class="{ 'btn-active': name === 'thre' }" @click="chouse('thre')">thre</button>
      <button class="btn-acent" :class="{ 'btn-active': name === 'thour' }" @click="chouse('thour')">thour</button>
    </div>
  </div>
  <div v-if="name === 'one'" >
    <h2>first block</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit distinctio assumenda fugit corrupti fuga, laboriosam soluta laudantium, quidem consequatur sit doloribus, ex omnis veniam? Sed praesentium officia asperiores deleniti mollitia.</p>
  </div>
  <div v-if="name === 'two'">
    <h2>two block</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit distinctio assumenda fugit corrupti fuga, laboriosam soluta laudantium, quidem consequatur sit doloribus, ex omnis veniam? Sed praesentium officia asperiores deleniti mollitia.</p>
  </div>
  <div v-if="name === 'thre'">
    <h2>foure block</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit distinctio assumenda fugit corrupti fuga, laboriosam soluta laudantium, quidem consequatur sit doloribus, ex omnis veniam? Sed praesentium officia asperiores deleniti mollitia.</p>
  </div>
  <div v-if="name === 'thour'">
    <h2>five block</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit distinctio assumenda fugit corrupti fuga, laboriosam soluta laudantium, quidem consequatur sit doloribus, ex omnis veniam? Sed praesentium officia asperiores deleniti mollitia.</p>
  </div>

</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const name = ref<string>('');

    function chouse(text: string) {
      name.value = text;
      console.log(text);
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
</style>