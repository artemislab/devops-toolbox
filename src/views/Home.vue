<template>
  <div class="home branding">
    <img alt="Megatron-Team" src="../assets/platform-team-logo.png" class="logo-size">
    <Hello msg="Welcome to our toolbox"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Hello from '@/components/Hello.vue'

export default {
  name: 'Home',
  components: {
    Hello
  }

}
</script>

<style>
.logo-size {
  width: 10%;
  height: auto;
  text-align: left;
}

.branding {
  padding-left: 10%;
  padding-top: 2%;
}
</style>