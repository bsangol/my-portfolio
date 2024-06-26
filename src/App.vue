<template>
  <div id="app" v-if="user.token">
    <md-app md-waterfall md-mode="fixed" :md-scrollbar="false">
      <md-app-content>
        <router-view/>
      </md-app-content>
    </md-app>
  </div>
  <div v-else id="app">
    <Login></Login>
  </div>
</template>

<script>
import Login from '@/components/Login.vue';

export default {
  name: 'App',
  components: {
    Login,
  },
  data() {
    return {
      user: this.$user,
    };
  },
}
</script>

<style scoped>
.md-content {
  padding: 0 !important;
}

.md-app {
  height: 100vh;
}
</style>
