<template>
  <div>
    <table>
      <tr v-for="user in users" :key="user.id">
        <td>{{ user.email }}</td>
        <td>{{ user.password }}</td>
        <td><button @click="deleteUser(user.id)">Delete</button></td>
      </tr>
    </table>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const users = ref([
      { id: 1, email: 'john@example.com', password: 'password' },
      { id: 2, email: 'jane@example.com', password: 'password' }
      // More users...
    ])

    const deleteUser = (id) => {
      users.value = users.value.filter((user) => user.id !== id)
    }

    return { users, deleteUser }
  }
}
</script>

<style scoped></style>
