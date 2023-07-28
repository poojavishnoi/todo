<template>
  <div>
    <input type="text" v-model="text" class="task_input" />

    <button @click="addTask(text)">Add task</button>

    <div id="task" v-for="(item, index) in tasklist" :key="index">
      <div class="task_left">
        <h4 v-if="!item.isEditing" id="task_name">{{ item.task }}</h4>
        <input v-model="item.task" v-else class="task_input" id="edit_input" />
      </div>
      <div id="task_right">
        <button @click="editTask(index)">
          {{ item.isEditing ? "ok" : "edit" }}
        </button>
        <button @click="deleteTask(index)">Delete</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: "",
      tasklist: [],
      editingText: "",
    };
  },
  methods: {
    addTask(text) {
      this.tasklist.push({
        task: text,
        isEditing: false,
      });
      this.text = " ";
      console.log(this.tasklist);
    },
    deleteTask(index) {
      this.tasklist.splice(index, 1);
    },
    editTask(index) {
      const editingTask = this.tasklist[index];
      editingTask.isEditing = !editingTask.isEditing;
    },
  },
};
</script>

<style scoped>
#task_name {
  margin: 1rem;
  padding: 0.5rem 1rem;
}

#task_right {
  margin-left: 7rem;
}

#edit_input {
  width: min-content;
  font-size: 1rem;
  font-weight: bold;
}

#task {
  display: flex;
  border: 1px solid rgb(236, 187, 187);
  background-color: rgb(255, 240, 240);
  margin: 0.5rem 25%;
  border-radius: 1rem;
  padding: 1rem;
  justify-content: space-between;
  align-items: center;
}
</style>