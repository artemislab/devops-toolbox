<template>
  <div class="ui secondary pointing menu" id="nav">
    <img alt="Megatron-Team" src="./assets/platform-team-logo.png" class="small-logo-size">
    <router-link class="item active" to="/">Home</router-link> |
    <router-link class="item" to="/Featureflag">Featureflag</router-link>
  </div>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
.small-logo-size {
  width: 2%;
  height: auto;
  text-align: left;
  margin-right: 20px;

}
</style>
