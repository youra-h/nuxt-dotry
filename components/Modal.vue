<!-- Модальное окно -->
<template>
    <div>
      <textarea v-model="localData"></textarea>
      <button @click="save">Сохранить</button>
      <button @click="cancel">Отмена</button>
    </div>
  </template>
  
  <script setup>
  import { ref, watchEffect } from 'vue';
  
  const props = defineProps(['data']);
  const emits = defineEmits(['save', 'cancel']);
  const localData = ref('');
  
  watchEffect(() => {
    localData.value = props.data;
  });
  
  const save = () => {
    emits('save', localData.value);
  };
  
  const cancel = () => {
    emits('cancel');
  };
  </script>
  