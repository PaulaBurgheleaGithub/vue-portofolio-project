<template>
  <div>
    <form @submit.prevent="handleSubmit">
    <label for="title">Project Title</label>
      <input type="text" v-model="title"/>
    <label for="image">Image URL</label>
      <input type="text" v-model="image">
    <label for="">Project Details</label>
      <input type="text" v-model="description">
    <button @click="handleSubmit">SUBMIT</button>
    </form>

  </div>
</template>

<script>
export default {
  name: "AdminView",

  data() {
    return {
      pageTitle: "Admin Page",
      title: "",
      image: "",
      description: "",
    };
  },

  //list all custom events to send to the parent
  emits:["createProject"],

  methods: {
    handleSubmit() {
      let project = {
        title: this.title,
        image: this.image,
        description: this.description,
      };
      this.$emit("createProject", project);
      //reset form data by setting all form filds to ""
    }
  }
};
</script>

<style></style>
