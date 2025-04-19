<script>
import {Developer} from "@/greetings/model/developer.entity.js";

export default {
  name: "greet-developer",
  props: {
    firstName: String,
    lastName: String,
  },
  methods: {
    getGreeting() {
      if (!this.firstName?.trim() || !this.lastName?.trim())
        return "Welcome Anonymous Developer";

      const developer = new Developer(this.firstName, this.lastName);

      return "Congrats " + developer.fullName + "! Now your are Vue Developer!";
    }
  }
}
</script>

<template>
  <p>{{ getGreeting() }}</p>
</template>

<style scoped>

</style>