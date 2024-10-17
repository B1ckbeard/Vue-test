<template>
  <div class="container">
    <input type="text" v-model="userName" placeholder="Name">
    <input type="password" v-model="userPass" placeholder="Password">
    <input type="email" v-model="userEmail" placeholder="Email">
    <button @click="sendData()">Send data</button>
    <div v-if="users.length === 0" className="user">Список пуст</div>
    <User v-for="(el, index) in users" :key="index" :user="el" @click="deleteUser(index)"/>
  </div>
</template>

<script>
import User from './components/User.vue'

export default {
  components: {User},
  data() {
    return {
      users: [],
      userName: '',
      userPass: '',
      userEmail: ''
    }
  },
  methods: {
    sendData() {
      this.users.push({
        name: this.userName,
        pass: this.userPass,
        email: this.userEmail
      })
    },
    deleteUser(index){
      this.users.splice(index, 1)
    }
  }
}
</script>

<style scoped>
.container {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
</style>
