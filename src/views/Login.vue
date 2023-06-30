<template>
  <div class="login-container">
    <h1 class="login-title"> Login</h1>
    <div class="login-form-container">
      <form class="login-form" @submit.prevent="submitForm">
        <div class="form-group">
          <label for="email" class="form-label">Email address</label>
          <input type="email" class="form-control" v-model="email" id="email" placeholder="Enter email">
        </div>
        <div class="form-group">
          <label for="password" class="form-label">Password</label>
          <input type="password" class="form-control" v-model="password" id="password" placeholder="Password">
        </div>
        <button type="submit" class="login-button">Login</button>
      </form>
    </div>
  </div>
</template>

<script>
import firebase from 'firebase/app'
import 'firebase/auth'

export default {
  data() {
    return {
      email: '',
      password: ''
    };
  },
  methods: {
    submitForm() {
      firebase.auth().signInWithEmailAndPassword(this.email, this.password)
        .then(() => {
          console.log('User logged in successfully');
          
        })
        .catch((error) => {
          console.log('Error logging in:', error.message);
        });
    }
  }
}
</script>

<style scoped>
.login-container {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  background-color: #f8f8f8;
  border: 1px solid #ddd;
  border-radius: 5px;
}

.login-title {
  text-align: center;
  margin-bottom: 20px;
}

.login-form-container {
  display: flex;
  justify-content: center;
}

.login-form {
  width: 100%;
}

.form-group {
  margin-bottom: 15px;
}

.form-label {
  font-weight: bold;
}

.form-control {
  padding: 8px;
  border: 1px solid #ddd;
  border-radius: 4px;
  width: 100%;
}

.login-button {
  padding: 10px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  width: 100%;
}

.login-button:hover {
  background-color: #0056b3;
}
</style>