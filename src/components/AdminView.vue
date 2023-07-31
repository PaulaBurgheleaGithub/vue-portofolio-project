<template>
  <div class="AdminView">
    <form @submit.prevent="handleSubmit">

      <label for="title">Project Title
        <input type="text" v-model="title"/>
      </label>

      <label for="image">Image URL 
        <input type="text" v-model="image">
      </label>

      <label for="description" class="span-2-cols">Project Details
        <input type="text" v-model="description">
      </label>

      <div class="span-2-cols" style="text-align: center">
        <button @click="handleSubmit">SUBMIT</button>
      </div>
      
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
      this.title = this.image = this.description = ""
    }
  }
};
</script>

<style>

form {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  text-align: left;
}

input,
textarea {
  display: block;
  width: 100%;
}

.span-2-cols {
  grid-column: 1 / span 2;
}

</style>
