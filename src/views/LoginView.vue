<template>
  <form @submit.prevent="submit">
    <label for="">Email</label>
    <input type="text" v-model="form.email" required />
    <br /><br />
    <label for="">password</label>
    <input type="password" v-model="form.password" required />
    <br /><br />
    <button type="submit">Login</button>
    <br />
  </form>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
    submit() {
      this.$store.commit("login", this.form.email);
    },
  },
};
</script>
