<template>
  <div id="app">
    <Auth v-if="interfaces.auth.show" />
  </div>
</template>

<script>
import Auth from "./views/Authentication/AuthView";

export default {
  name: 'App',
  data() {
    return {
      interfaces: {
        "auth": {
          show: 0,
        }
      }
    }
  },
  components: {
    Auth
  },
  methods: {
    showInterface(name,toggle){
      this.interfaces[name].show = toggle;
    },
    
    hideAllInterfaces() {
      for (let el in this.interfaces) {
        this.interfaces[el] = 0;
      }
    }
  }
}
</script>
