 <template>
  <div class="container mx-auto">
    <TaskList :tasks="tasks" :editTask="editTask" />
    <EditTaskPopup v-if="editingTask" :editedTask="editedTask" :onSubmit="updateTask" :onCancel="cancelEdit" />
  </div>
</template>

<script>
import { ref } from 'vue';
import TaskList from './components/TaskList.vue';
import EditTaskPopup from './components/EditTaskPopup.vue';

export default {
  components: {
    TaskList,
    EditTaskPopup
  },
  data() {
    return {
      tasks: [
        { name: 'Task 1', time: 30 },
        { name: 'Task 2', time: 40 },
        { name: 'Task 3', time: 60 },
        { name: 'Task 4', time: 45 },
        { name: 'Task 5', time: 50 }
      ],
      editingTask: false,
      editedTask: {}
    };
  },
  methods: {
    editTask(task) {
      this.editingTask = true;
      this.editedTask = { ...task };
    },
    updateTask(updatedTask) {
      const index = this.tasks.findIndex(task => task.name === updatedTask.name);
      if (index !== -1) {
        this.tasks[index] = updatedTask;
      }
      this.editingTask = false;
    },
    cancelEdit() {
      this.editingTask = false;
    }
  }
};
</script>

<style>
/* Include Tailwind CSS */
</style> 


