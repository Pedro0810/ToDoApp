<template>
  <div class="taskList">
    <template v-if="tasks.length">
        <Task
          v-for="(task, i) in tasks" :key="task.name"
          :task="task"
          @taskDeleted="$emit('taskDeleted', i)"
          @taskStateChanged="$emit('taskStateChanged', i)"
        />
    </template>
    <p v-else class="no-task">Sua vida está em dia :)</p>
  </div>
</template>

<script>
/* eslint-disable no-console */
import Task from "@/components/Task.vue";
export default {
  props: {
    tasks: {
      type: Array,
      required: true,
    },
  },

  components: {
    Task,
  },

  methods: {
    delTask(task) {
      const index = this.tasks.indexOf(task["task"]);
      if (index != -1) this.tasks.splice(index, 1);
    },
  },
};
</script>

<style>
.taskList {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
.taskList .card {
  margin: 10px;
}
.no-task {
  color: #aaa;
  font-size: 1.7rem;
}
</style>
