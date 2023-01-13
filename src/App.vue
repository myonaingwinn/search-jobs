<template>
  <div class="app">
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
      { id: "2kjdk", title: "Farmer", location: "Myanmar", salary: 230000 },
      { id: "jasdk", title: "Farmer", location: "India", salary: 230000 },
      { id: "3sadk", title: "Farmer", location: "Philp", salary: 220000 },
      { id: "2bjdl", title: "Farmer", location: "Singapore", salary: 250000 },
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
