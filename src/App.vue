<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/Movie">영화</router-link> |
      <router-link to="/TV">TV</router-link> |
      <router-link to="/Login">Login</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
html{
  background: black;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: aliceblue;
}

#nav a.router-link-exact-active {
  color: crimson;
}
</style>
