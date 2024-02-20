<template>
    <div>
      <input v-model="newUsu.correo" type="correo" placeholder="correo">
      <input v-model="newUsu.password" type="contraseña" placeholder="contraseña">
      <button @click="registro">registro</button>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    setup() {
      const usuario = ref([]);
      const newUsu = ref({ correo: '', password: '' });
  
      const registro = () => {
        if(usuario.value.find(user => user.correo === newUsu.value.correo)) {
          alert('correo registrado');
        } else {
          usuario.value.push({ ...newUsu.value });
          newUsu.value = { correo: '', password: '' };
          alert('Registro Completado ');
        }
      };
  
      return { usuario, newUsu, registro };
    }
  };
  </script>
  
<style scoped> </style>