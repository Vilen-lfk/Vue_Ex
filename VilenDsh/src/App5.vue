<template>
  <div class="checklist">
    <h1>Чеклист</h1>
    
    <form @submit.prevent="addTask">
      <input v-model="newTaskText" placeholder="Новое дело" />
      <button type="submit" :disabled="!newTaskText.trim()">Добавить</button>
    </form>
    
    <ul>
      <li v-for="task in tasks" :key="task.id">
        <input type="checkbox" v-model="task.done" />
        
        <template v-if="editId === task.id">
          <input
            v-model="editText"
            @keyup.enter="saveEdit"
            @keyup.esc="cancelEdit"
            @blur="cancelEdit"
            ref="editInput"
          />
          <button @click="saveEdit">Сохранить</button>
          <button @click="cancelEdit">Отмена</button>
        </template>
        
        <template v-else>
          <span
            :class="{ done: task.done }"
            @dblclick="startEdit(task)"
            style="cursor: pointer;"
            >{{ task.text }}</span
          >
          <button @click="deleteTask(task.id)">Удалить</button>
        </template>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTaskText: '',
      tasks: [
        { id: 1, text: 'Купить продукты', done: false },
        { id: 2, text: 'Сделать домашнее задание', done: true }
      ],
      editId: null,
      editText: ''
    };
  },
  methods: {
    addTask() {
      if (!this.newTaskText.trim()) return;
      this.tasks.push({
        id: Date.now(),
        text: this.newTaskText.trim(),
        done: false
      });
      this.newTaskText = '';
    },
    deleteTask(id) {
      this.tasks = this.tasks.filter(task => task.id !== id);
      if (this.editId === id) this.cancelEdit();
    },
    startEdit(task) {
      this.editId = task.id;
      this.editText = task.text;
      this.$nextTick(() => {
        this.$refs.editInput?.focus();
      });
    },
    saveEdit() {
      if (this.editId === null) return;
      const task = this.tasks.find(t => t.id === this.editId);
      if (task && this.editText.trim()) {
        task.text = this.editText.trim();
      }
      this.cancelEdit();
    },
    cancelEdit() {
      this.editId = null;
      this.editText = '';
    }
  }
};
</script>

<style scoped>
.done {
  text-decoration: line-through;
  color: grey;
}
ul {
  padding-left: 0;
  list-style: none;
}
li {
  margin-bottom: 0.5rem;
  display: flex;
  align-items: center;
  gap: 10px;
}
input[type="text"] {
  padding: 0.3rem;
  font-size: 1rem;
}
button {
  cursor: pointer;
}
</style>
