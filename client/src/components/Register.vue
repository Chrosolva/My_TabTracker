<template>
  <div>
    <h1>Register</h1>

    <input type="email" v-model="email" name="email" placeholder="email"/>
    <br>
    <input type="password" v-model="password" name="password" placeholder="password"/>
    <br>
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationServices from '@/services/AuthenticationServices'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationServices.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<style scoped>

</style>
