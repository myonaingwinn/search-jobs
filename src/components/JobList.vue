<template>
  <div class="job-list">
    <h1>JobList</h1>
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
          <p>{{ job.salary }} kyats</p>
        </div>
        <div class="description">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Iusto
          corrupti nam totam officia autem facere. Error ullam sapiente,
          corporis dicta, labore esse eligendi sequi laborum expedita dolorum
          rem ipsa aliquam!
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import Job from "types/Job";
import { defineComponent, PropType } from "vue";

export default defineComponent({
  //   setup() {},
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>,
    },
  },
});
</script>
