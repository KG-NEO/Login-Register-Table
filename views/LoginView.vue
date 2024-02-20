<template>
  <div>
    <input v-model="correo" type="correo" placeholder="Correo Electronico" />
    <input v-model="password" type="password" placeholder="Contraseña" />
    <button @click="login">Login</button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const correo = ref('')
    const password = ref('')

    const login = () => {
      if (correo.value === 'utcancun@gmail.com' && password.value === 'ut2024') {
        alert(' Inicio de sesion correcto ')
      } else {
        alert('Contraseña o Correo invalidos')
      }
    }

    return { correo, password, login }
  }
}
</script>

<style scoped>
.correo{
  width: auto;
}
</style>
