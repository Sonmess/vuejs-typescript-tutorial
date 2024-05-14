<template>
  <section class="app">
    Hello, Hyrule
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('Zelda')">Change name</button>
    <button @click="changeAge(30)">Change Age</button>
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "App",
  components: {},
  data() {
    return {
      name: 'Link',
      age: 25 as number | string
    }
  },
  methods: {
    changeName(newName: string) {
      this.name = newName;
      return this.name;
    },

    changeAge(age: number | string) {
      this.age = age;
      return this.age;
    }
  }
});
</script>

<style></style>
