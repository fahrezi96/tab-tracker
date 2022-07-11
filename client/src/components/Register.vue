<template>
  <div>
    <h2>Register</h2>
    <input type="email" name="email" placeholder="email" v-model="email" /> <br />
    <input type="password" name="password" placeholder="password" v-model="password" /> <br />
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '../services/AuthenticationService';
export default {
  data() {
    return {
      email: 'abc',
      password: '123',
    };
  },
  methods: {
    async register() {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password,
      });

      console.log(response.data);
    },
  },
  //   watch: {
  //     email(value) {
  //       console.log('email has changed', value);
  //     },
  //   },
  //   mounted() {
  //     setTimeout(() => {
  //       this.email = 'hello';
  //     }, 2000);
  //   },
};
</script>

<style scoped></style>
