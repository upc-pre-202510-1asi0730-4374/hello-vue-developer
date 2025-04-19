<script>
import GreetDeveloper from "@/greetings/components/greet-developer.component.vue";
import RegisterDeveloper from "@/greetings/components/register-developer.component.vue";

export default {
  name: "app",
  components: {
    RegisterDeveloper,
    GreetDeveloper
  },
  data() {
    return {
      appfirstName: "",
      applastName: ""
    };
  },
  methods: {
    onDeveloperRegistered(developerParameter) {
      this.appfirstName = developerParameter.eventFirstName;
      this.applastName = developerParameter.eventLastName;
    }
  }
}
</script>

<template>
  <h1>Hello Vue Developer Application</h1>
  <register-developer
      v-on:developer-registered="onDeveloperRegistered"
  ></register-developer>

  <greet-developer :first-name="appfirstName" :last-name="applastName"></greet-developer>
</template>

<style scoped>
</style>
