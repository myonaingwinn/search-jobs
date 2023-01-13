<template>
  <div class="app">
    <h1 class="heading">Grab Your Job Here</h1>
    <header>
      <div class="order">
        <button @click="handleClick('title')">Order by Title</button>
        <button @click="handleClick('salary')">Order by Salary</button>
        <button @click="handleClick('location')">Order by Location</button>
      </div>
    </header>
    <JobList :jobs="jobs" :order="orderTerm" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import Job from "types/Job";
import OrderTerm from "types/OrderTerm";
import JobList from "./components/JobList.vue";

export default defineComponent({
  name: "App",
  components: {
    JobList,
  },
  setup() {
    /* const state = reactive({
      name: "Bohemian Rhapsody",
      age: 23 as number | string,
    }); 
    return { ...toRefs(state) }; */

    const jobs = ref<Job[]>([
      {
        id: "2kjdk",
        title: "MC Enginner",
        location: "Myanmar",
        salary: 2350000,
      },
      { id: "jasdk", title: "Farmer", location: "India", salary: 2300000 },
      { id: "3sadk", title: "DevOps", location: "Philp", salary: 2200000 },
      {
        id: "2bjdl",
        title: "Cloud Engineer",
        location: "Singapore",
        salary: 3400000,
      },
      {
        id: "2bjdl",
        title: "Infrastructure Engineer",
        location: "North America",
        salary: 2100000,
      },
      {
        id: "2bjdl",
        title: "Network Engineer",
        location: "China",
        salary: 5000000,
      },
      {
        id: "2bjdl",
        title: "Security Administrator",
        location: "Thailand",
        salary: 3000000,
      },
    ]);

    const orderTerm = ref<OrderTerm>("title");

    const handleClick = (term: OrderTerm) => {
      orderTerm.value = term;
      console.log(orderTerm.value);
    };

    return { jobs, handleClick, orderTerm };
  },
});
</script>
