<template>
  <div>
    <h1>Create an Event</h1>
    <form @submit.prevent="submit">
      <input
        v-model="event.title"
        type="text"
        name="title"
        placeholder="Add a Title"
      />
    </form>
    <input type="submit" value="Create" />
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      event: {
        title: ""
      }
    };
  },
  methods: {
    async submit() {
      return await axios.post("http://localhost:3000/events", this.event);
    }
  }
};
</script>

<style scoped></style>
