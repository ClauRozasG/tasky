<template>
  <div>
    <h2>Tasky</h2>
    <h3>Task Management</h3>
    <ul>
      <li v-for="task in tasks"
        v-bind:key="task.id">
        <task-item v-bind:task="task"
        v-on:delete-task="$emit('delete-task', task.id)"></task-item> <!--lo escala a un nivel superior -->
      </li>
    </ul>
  </div>
</template>

<script>
import TaskItem from "@/components/task-item.component.vue";
export default {
  name: "task-list",
  components: {TaskItem},

  props: [
      "tasks"
  ]
}
</script>

<style scoped>

</style>