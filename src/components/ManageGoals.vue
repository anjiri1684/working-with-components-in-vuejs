<template>
  <div>
    <h2>Manage Goals</h2>
    <input type="text" ref="goal" />
    <button @click="addGoal">Add Goal</button>
    <error-alert v-if="inputIsInvalid">
      <p>Input is invalid</p>
      <p>Please enter at least few characters....</p>
      <button @click="confirmError">Okay</button>
    </error-alert>
  </div>
</template>

<script>
import ErrorAlert from "./ErrorAlert.vue";

export default {
  components: { ErrorAlert },
  data() {
    return {
      inputIsInvalid: false,
    };
  },
  methods: {
    addGoal() {
      const enteredValue = this.$refs.goal.value;

      if (enteredValue.trim() === "") {
        this.inputIsInvalid = true;
      }
    },
    confirmError() {
      this.inputIsInvalid = false;
    },
  },
};
</script>
