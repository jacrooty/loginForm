<template>
  <form @submit.prevent="login">
    <input
      type="text"
      v-model="username"
      placeholder="Username"
      required
      pattern="[a-zA-Z0-9_]+"
    >
    <input
      type="password"
      v-model="password"
      placeholder="Password"
      required
      pattern="^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$"
    >
    <button type="submit">Login</button>
    <p v-if="error" class="error">{{ error }}</p>
  </form>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
      error: null
    }
  },
  methods: {
    login() {
      if (!this.username || !this.password) {
        this.error = 'Please fill in all fields';
        return;
      }
      // Additional validation logic can be added here
      // ...
      // Login logic remains the same
    }
  }
}
</script>