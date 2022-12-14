<template>
  <div id="app">
    <HeaderView/>
    <!-- <div className="container-fluid position-relative d-flex p-0"> -->
      <FormBindings msg="Form Bindings"/>
      <!-- <SideBar /> -->
      <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
      <HelloWorld msg="Welcome to Our Page"/>
    <!-- </div> -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import HeaderView from './components/HeaderView.vue';
import FormBindings from './components/FormBindings.vue'

const routes = {
  '/home': HelloWorld,
  '/form-bindings': FormBindings
}

export default {
  name: 'App',
  components: {
    HelloWorld,
    HeaderView,
    FormBindings
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/'] || HelloWorld
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
