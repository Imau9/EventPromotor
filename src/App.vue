<template>
  <div id="app">
    <nav class="navbar">
      <div class="logo">
        <img src="@/assets/logo_event.png" alt="Logo" class="logo-image" />
        
      </div>
      <ul>
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/login">Login</router-link></li>
        <li><router-link to="/signup">Signup</router-link></li>
      </ul>
      <div class="search-bar">
        <input type="text" placeholder="Search..." />
        <button>Search</button>
      </div>
    </nav>
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: Arial, sans-serif;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  background-color: #f5f5f5;
}

.logo {
  display: flex;
  align-items: center;
}

.logo-image {
  width: 150px;
  height: 40px;
  margin-right: 5px;
}

.logo-text {
  font-size: 20px;
  font-weight: bold;
}

ul {
  list-style: none;
  display: flex;
  gap: 20px;
}

.search-bar {
  display: flex;
  gap: 10px;
}

input[type="text"] {
  padding: 5px;
  border: 1px solid #ccc;
}

button {
  padding: 5px 10px;
  background-color: #007bff;
  color: #fff;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

.content {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.content h1 {
  font-size: 24px;
  margin-bottom: 20px;
}

.login-form {
  max-width: 400px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.login-form label {
  display: block;
  margin-bottom: 10px;
  font-weight: bold;
}

.login-form input[type="email"],
.login-form input[type="password"] {
  width: 100%;
  padding: 5px;
  border: 1px solid #ccc;
  border-radius: 5px;
  margin-bottom: 10px;
}

.login-form button {
  padding: 5px 10px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.login-form button:hover {
  background-color: #0056b3;
}

.signup-form {
  max-width: 400px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.signup-form label {
  display: block;
  margin-bottom: 10px;
  font-weight: bold;
}

.signup-form input[type="email"],
.signup-form input[type="password"] {
  width: 100%;
  padding: 5px;
  border: 1px solid #ccc;
  border-radius: 5px;
  margin-bottom: 10px;
}

.signup-form button {
  padding: 5px 10px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.signup-form button:hover {
  background-color: #0056b3;
}
</style>