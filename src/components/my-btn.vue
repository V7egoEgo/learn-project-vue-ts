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
    border: 1px solid #297410;
    color: white ;
  }
}
.btn-active
{
  cursor: pointer;
  background-color: #3c941e;
  border: 1px solid #297410;
  &:hover
  {
    padding: 10px;
    background-color: #297410;
    border: 1px solid #4ed421;
    border-radius: 16px;
  }
}
</style>