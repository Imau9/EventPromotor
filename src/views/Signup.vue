<template>
    <div class="signup-container">
      <h1 class="signup-title"> Signup</h1>
      <div class="signup-form-container">
        <form class="signup-form" @submit.prevent="submitForm">
          <div class="form-group">
            <label for="email" class="form-label">Email address</label>
            <input type="email" class="form-control" v-model="email" id="email" placeholder="Enter email">
          </div>
          <div class="form-group">
            <label for="password" class="form-label">Password</label>
            <input type="password" class="form-control" v-model="password" id="password" placeholder="Password">
          </div>
          <div class="form-group">
            <label for="repeatPassword" class="form-label">Repeat Password</label>
            <input type="password" class="form-control" v-model="repeatPassword" id="repeatPassword" placeholder="Repeat Password">
          </div>
          <button type="submit" class="signup-button">Sign up</button>
        </form>
      </div>
    </div>
  </template>
  
  <script>
  import firebase from 'firebase/compat/app'
  import 'firebase/compat/auth'
  
  export default {
    data() {
      return {
        email: '',
        password: '',
        repeatPassword: ''
      };
    },
    methods: {
      submitForm() {
        if (this.password !== this.repeatPassword) {
          console.log('Passwords do not match');
          return;
        }
  
        firebase.initializeApp({
          
        });
  
        firebase.auth().createUserWithEmailAndPassword(this.email, this.password)
          .then(() => {
            console.log('User signed up successfully');
           
          })
          .catch((error) => {
            console.log('Error signing up:', error.message);
          });
      }
    }
  }
  </script>
  
  <style scoped>
.signup-container {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  background-color: #f8f8f8;
  border: 1px solid #ddd;
  border-radius: 5px;
}

.signup-title {
  text-align: center;
  margin-bottom: 20px;
}

.signup-form-container {
  display: flex;
  justify-content: center;
}

.signup-form {
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

.signup-button {
  padding: 10px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  width: 100%;
}

.signup-button:hover {
  background-color: #0056b3;
}
</style>