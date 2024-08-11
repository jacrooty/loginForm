<template>
  <form @submit.prevent="register">
    <div>
      <label>Full Name:</label>
      <input type="text" v-model="firstName" required>
      <input type="text" v-model="lastName" required>
    </div>

    <div>
      <label>Email Address:</label>
      <input type="email" v-model="email" required>
    </div>

    <div>
      <label>Password:</label>
      <input type="password" v-model="password" required>
      <input type="password" v-model="confirmPassword" required>
    </div>

    <div>
      <label>Company/Organization:</label>
      <input type="text" v-model="companyName">
    </div>

    <div>
      <label>Role/Job Title:</label>
      <input type="text" v-model="jobTitle">
    </div>

    <div>
      <label>Phone Number:</label>
      <input type="tel" v-model="phoneNumber">
    </div>

    <button type="submit">Register</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      firstName: '',
      lastName: '',
      email: '',
      password: '',
      confirmPassword: '',
      companyName: '',
      jobTitle: '',
      phoneNumber: ''
    }
  },
  methods: {
    register() {
      // Form submission logic here
      console.log('Registering user...');
    }
  }
}
</script>