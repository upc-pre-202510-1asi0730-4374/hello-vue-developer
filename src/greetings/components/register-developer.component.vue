<script>
/**
 * @name app
 * @description
 * This component is the main component of the application
 * xyz
 */
export default {
  name: "register-developer",
  data() {
    return {
      firstName: "",
      lastName: "",
      errorMessage: "",
    }
  },
  methods: {
    onRegister() {
      if (this.firstName.trim() || this.lastName.trim()) {
        console.log("Registering developer");
        this.$emit("developer-registered", {
          eventFirstName: this.firstName,
          eventLastName: this.lastName
        });
        this.clearForm();
      } else {
        console.log("Cannot register");
        this.errorMessage = "Please provide a valid firs name and last name.!";
      }
    },
    clearForm() {
      this.firstName = "";
      this.lastName = "";
      this.errorMessage = "";
    }
  }
}
</script>

<template>
  <div>
    <h2>New Developer</h2>
    <div>
      <form v-on:submit.prevent="onRegister">
        <div>
          <label for="firstName">First Name</label>
          <input type="text" id="firstName" v-model="firstName">
        </div>
        <div>
          <label for="lastName">Last Name</label>
          <input type="text" id="lastName" v-model="lastName">
        </div>
        <div>
          <button type="submit">Register</button>
          <button type="button">Later</button>
          <button type="button" v-on:click="clearForm">Clear</button>
        </div>
      </form>
      <p role="alert">{{ errorMessage }}</p>
    </div>
  </div>
</template>

<style scoped>
  button {
    margin-right: 10px;
    padding: 8px 16px;
    cursor: pointer;
  }

  .error {
    color: #d32f2f;
    margin-top: 10px;
    font-size: 14px;
  }
</style>