<template>
  <div class="job-list">
    <i>Ordered by {{ order }}</i>
    <ul>
      <li v-for="job in orderedJobs" :key="job.id">
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
import OrderTerm from "types/OrderTerm";
import { computed, defineComponent, PropType } from "vue";

export default defineComponent({
  //   setup() {},
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>,
    },
    order: {
      required: true,
      type: String as PropType<OrderTerm>,
    },
  },
  setup(props) {
    const orderedJobs = computed(() => {
      return [...props.jobs].sort((a: Job, b: Job) => {
        return a[props.order] > b[props.order] ? 1 : -1;
      });
    });

    return { orderedJobs };
  },
});
</script>
