<template>
  <div>
<h1>Register</h1>

<input
type="text" 
name="email" 
v-model="email"
placeholder="email"
>
<br>
<input 
type="password" 
name="password" 
placeholder="password" 
v-model="password">
<br>

<button @click="register"> Register</button>
  </div>
</template>

<script>
import Authentication from '@/services/Authentication'
export default {
  data () {
    return {
      email: null,
      password: null

    }
  },

  methods: {
   async register () {
     await Authentication.register({
        email: this.email,
        password: this.password
      })
      console.log('clicked register')
    }
    
  },

}
</script>

<style>

</style>