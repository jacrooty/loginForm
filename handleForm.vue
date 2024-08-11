<template>
  <form @submit.prevent="register">
    <!-- form fields remain the same -->
  </form>
</template>

<script>
import axios from 'axios';

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
      phoneNumber: '',
      errors: {}
    }
  },
  methods: {
    register() {
      // ... (validation logic remains the same)

      if (Object.keys(this.errors).length === 0) {
        const userData = {
          firstName: this.firstName,
          lastName: this.lastName,
          email: this.email,
          password: this.password,
          companyName: this.companyName,
          jobTitle: this.jobTitle,
          phoneNumber: this.phoneNumber
        };

        axios.post('/api/register', userData)
          .then(response => {
            console.log('User registered successfully!');
            // Redirect to login page or dashboard
          })
          .catch(error => {
            console.error('Error registering user:', error);
          });
      }
    }
  }
}
</script>