<template>
  <div class="hello">
    <h3>Your name is: {{ properCase }}!</h3>
    <h5>You are: {{ user.age }}</h5>
    <label for="checkbox">Uppercase</label>
    <input type="checkbox" id="checkbox" v-model="uppercase" />
    <button
      v-on:click="
        {
          {
            younger();
          }
        }
      "
    >
      Make me younger yo!
    </button>
    <button v-on:click="$emit('kill')">
      Kill me
    </button>
  </div>
</template>

<script>
export default {
  name: "User",
  props: {
    user: Object
  },
  data() {
    return {
      uppercase: false
    };
  },
  computed: {
    properCase() {
      return this.uppercase
        ? this.user.name.toUpperCase()
        : this.user.name.toLowerCase();
    }
  },
  methods: {
    younger() {
      if (this.user.age > 0) this.user.age -= 1;
    }
  }
};
</script>

