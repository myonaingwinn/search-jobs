<template>
  <div class="app">
    <JobList :jobs="jobs" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import Job from "types/Job";
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

    return { jobs };
  },
});
</script>
