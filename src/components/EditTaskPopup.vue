 <template>
  <div class="fixed top-0 left-0 w-full h-full bg-gray-800 bg-opacity-50 flex justify-center items-center">
    <div class="bg-white p-4 rounded shadow-lg">
      <h2 class="text-lg font-semibold mb-2">Edit Task</h2>
      <form @submit.prevent="handleSubmit">
        <div class="mb-4">
          <label for="name" class="block mb-1">Name:</label>
          <input type="text" v-model="editedTask.name" id="name" class="w-full border-gray-300 rounded-md">
        </div>
        <div class="mb-4">
          <label for="time" class="block mb-1">Time:</label>
          <input type="number" v-model="editedTask.time" id="time" class="w-full border-gray-300 rounded-md">
        </div>
        <div class="flex justify-between">
          <button type="submit" class="bg-blue-500 text-white px-4 py-2 rounded">Submit</button>
          <button type="button" @click="handleCancel" class="bg-gray-300 text-gray-800 px-4 py-2 rounded">Cancel</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    editedTask: Object,
    onSubmit: Function,
    onCancel: Function
  },
  methods: {
    handleSubmit() {
      this.onSubmit(this.editedTask);
    },
    handleCancel() {
      this.onCancel();
    }
  }
};
</script> 



