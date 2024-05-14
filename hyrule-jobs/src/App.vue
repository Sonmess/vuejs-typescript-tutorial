<template>
  <section class="app">
    <header>
      <h1 class="title">
        <img src="./assets//heart.svg" alt="Heart" />
        Hyrule Jobs
      </h1>
      <div class="order">
        <button @click="handleClick('title')">order by title</button>
        <button @click="handleClick('location')">order by location</button>
        <button @click="handleClick('salary')">order by salary</button>
      </div>
    </header>
    <JobsList :jobs="jobs" :order="order" />
  </section>
</template>

<script lang="ts">
import { defineComponent, ref, reactive, toRefs } from "vue";
import Job from "./types/job";
import JobsList from "./components/JobsList.vue";
import OrderTerm from "./types/orderTerm";

export default defineComponent({
  name: "App",
  components: { JobsList },
  setup() {
    //   const state = reactive({
    //       name: 'Link',
    //       age: 25 as string | number
    //   });

    //   return {
    //       ...toRefs(state)
    //   }

    // const name = ref('Link');
    // const age = ref<number | string>(25);
    // return {name, age};

    const jobs = ref<Job[]>([
      {
        title: "Farm worker",
        location: "Lon ranch",
        salary: 30000,
        id: 1,
      },
      {
        title: "Quarry man",
        location: "Death mountain",
        salary: 50000,
        id: 2,
      },
      {
        title: "Flute player",
        location: "The lost woods",
        salary: 20000,
        id: 3,
      },
      {
        title: "Fisherman",
        location: "Lake Hylia",
        salary: 21000,
        id: 4,
      },
      {
        title: "Prison guard",
        location: "Gerudo valley",
        salary: 32000,
        id: 5,
      },
    ]);

    const order = ref<OrderTerm>("title");

    const handleClick = (term: OrderTerm) => {
      order.value = term;
    };

    return { jobs, handleClick, order };
  },
});
</script>

<style>
header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
header .title {
  display: flex;
  justify-content: center;
}

header img {
  width: 60px;
  margin-right: 20px;
}

header h1 {
  font-size: 3em;
}
</style>
