<template>
  <div class="App">
    <nav>
    <button @click="isAdmin = true" :class="{active: isAdmin}" >ADMIN</button>
    <button @click="isAdmin = false" :class="{active : !isAdmin}" >USER</button>
    </nav>

    <h1>{{ title }}</h1>

    <section>
      <adminView v-if="isAdmin" @createProject="addProject" />
      <userView v-else :projects="allProjects"/>
    </section>

  </div>
</template>

<script>
import AdminView from "./components/AdminView.vue";
import UserView from "./components/UserView.vue";

export default {
  name: "app",
  components: {
    userView: UserView,
    adminView: AdminView
  },
  data() {
    return {
      title: "NEEDS TO CHANGE",
      isAdmin: true,
      allProjects: [],
    };
  },
  methods: {
    addProject(project) {
      //add id to each project
      project.id = this.allProjects.length;
      //push a project in the projects array
      this.allProjects.push(project);
    }
  }
};
</script>

<style>

* {
  box-sizing: border-box;
}

.App {
  width: 800px;
  font-family: Geneva, sans-serif;
  text-align: center;

  width: 600px;
  margin: 20px auto;
}

nav {
  border: 2px solid blue;
  padding: 20px;
  
  display: flex;
  justify-content: end;
  gap: 10px;
}

nav bottom {
  font-size: 120%;
  margin-left: 10px;
}

.active {
  color: red;
}

</style>
