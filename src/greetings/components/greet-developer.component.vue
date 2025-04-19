<script>/**
 * @name greet-developer
 * @description
 * This component greets a developer based on their name.
 * Displays 'Welcome Anonymous Developer' if names are empty, otherwise congratulates the developer.
 * @prop firstName {String} - The first name of the developer.
 * @prop lastName {String} - The last name of the developer.
 */
import {Developer} from "../model/developer.entity.js";


export default {
  name: "greet-developer",
  props: {
    firstName: String,
    lastName: String,
  },
  methods: {
    getGreeting() {
      if (!this.firstName?.trim() || !this.lastName?.trim()) {
        return "Welcome Anonymous Developer";
      }
      const developer = new Developer(this.firstName, this.lastName);
      return `Congrats ${developer.fullName}! Now you are a Vue Developer`;
    },
  },
};
</script>

<template>
  <p>{{ getGreeting() }}</p>
</template>

<style scoped>
</style>