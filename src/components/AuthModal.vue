<script setup>
import { ref, defineProps } from 'vue';

const props = defineProps(['isLogin'])
const visible = ref(false);

const showModal = () => {
  visible.value = true;
}; 

const handleOk = (e) => {
  console.log(e);
  visible.value = false;
};

const title = props.isLogin ? 'Login' : 'Sign up'
</script>
<template>
    <div>
      <a-button type="primary" @click="showModal" class="btn">{{title}}</a-button>
      <a-modal v-model:visible="visible" :title="title" @ok="handleOk">
        <a-input class="input" v-if="!isLogin" v-model:value="value" placeholder="Username" /> 
        <a-input class="input" v-model:value="value" placeholder="Email" /> 
        <a-input class="input" v-model:value="value" placeholder="Password" /> 
      </a-modal>
    </div>
  </template>
<style scoped>
.btn {
    margin-top: 10px;
}
.input {
    margin-top: 5px;
}

</style>
  
  
  