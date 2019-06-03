<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <User
      v-on:kill="removeUser(user)"
      v-for="user in users"
      :user="user"
      :key="user.name"
    />
  </div>
</template>

<script>
import User from "./components/User.vue";

export default {
  name: "app",
  components: {
    User
  },
  data() {
    return {
      users: [
        {
          name: "James",
          age: 28
        },
        {
          name: "Corrie",
          age: 22
        },
        {
          name: "Mark",
          age: 39
        }
      ]
    };
  },
  methods: {
    removeUser(user) {
      this.users = this.users.filter(iterUser => {
        return user.name !== iterUser.name;
      });
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
