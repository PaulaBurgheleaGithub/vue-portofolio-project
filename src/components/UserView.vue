<template>
  <div>User View</div>
  <section>
    <ul>
      <li v-for="p in projects" :key="p.id">
          {{ p.title }}, {{ p.image }}
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: "UserView",

  props: ["projects"]
};

</script>

<style></style>
