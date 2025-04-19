<script>
/**
 * @name app
 * @description
 * This component is the main component of the application.
 * It manages the developer count and developer names.
 * It listens to developer-registered and later events from RegisterDeveloper.
 */

import RegisterDeveloper from "./greetings/components/register-developer.component.vue";
import GreetDeveloper from "./greetings/components/greet-developer.component.vue";
import ShowDeveloperCount from "./greetings/components/show-developer-count.component.vue";
import { Developer } from "./greetings/model/developer.entity.js";

export default {
  name: "app",
  components: {
    RegisterDeveloper,
    GreetDeveloper,
    ShowDeveloperCount,
  },
  data() {
    return {
      firstName: "",
      lastName: "",
      developerCount: 0,
      hasRegistered: false,
    };
  },
  methods: {
    onDeveloperRegistered(developer) {
      this.firstName = developer.firstName;
      this.lastName = developer.lastName;
      this.hasRegistered = true;
      console.log("Developer registered: ", developer);
      this.updateDeveloperCount(developer);
    },
    onLater(developer) {
      this.firstName = "";
      this.lastName = "";
      this.hasRegistered = false;
      console.log("Registration deferred");
    },
    updateDeveloperCount(developer) {
      const dev = new Developer(developer.firstName, developer.lastName);
      if (dev.fullName !== "Unknown") {
        this.developerCount++;
      }
    },
  },
};
</script>

<template>
  <h1>Hello Vue Developer Application</h1>
  <register-developer
      v-on:developer-registered="onDeveloperRegistered"
      v-on:later="onLater"
  />
  <greet-developer
      v-if="hasRegistered"
      :first-name="firstName"
      :last-name="lastName"
  />
  <show-developer-count :developer-count="developerCount" />
</template>

<style>
</style>