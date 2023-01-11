<template>
  <div class="container">
    <form @submit.prevent="submit">
      <label for="">Email</label>
      <input type="text" v-model="form.email" required />
      <br /><br />
      <label for="">Password</label>
      <input type="password" v-model="form.password" required />
      <br /><br />
      <div class="buttons">
        <button type="submit">Login</button>
        <button type="reset">Reset</button>
      </div>
      <br />
    </form>
  </div>
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
<style scoped>
form {
  background-color: #52baff;
  width: 500px;
  text-align: center;
  padding-top: 20px;
  padding-bottom: 20px;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
  border-radius: 9px;
}
.container {
  display: flex;
  justify-content: center;
}
.buttons{

  margin-top: 20px;
}
.buttons > button {
  padding-top: 15px;
  padding-bottom: 15px;
  padding-left: 25px;
  padding-right: 25px;
  margin: 5px;
}

button[type="submit"] {
  background-color: rgb(16, 133, 57);
  border-radius: 9px;
  cursor: pointer;
  font-weight: bold;
  border: none;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.3);
  font-size: 14px;
}
button[type="submit"]:hover {
  background-color: rgb(14, 91, 41);
  color: white;
  border-radius: 9px;
  cursor: pointer;
  font-weight: bold;
}
button[type="reset"] {
  background-color: rgb(255, 160, 64);
  border-radius: 9px;
  cursor: pointer;
  font-weight: bold;
  border: none;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.3);
  font-size: 14px;
}
button[type="reset"]:hover {
  background-color: rgb(255, 119, 0);
  color: white;
  border-radius: 9px;
  cursor: pointer;
  font-weight: bold;
}
input {
  padding: 5px;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.3);
  font-size: 14px;
  font-weight: 600;
  width: 300px;
}
label {
  color: #ffffff;
  font-weight: bold;
  display: block;
  margin-top: 20px;
  margin-bottom: 5px;
}
label:after { content: ": " }
</style>
