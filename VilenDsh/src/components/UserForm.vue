<!-- components/UserForm.vue -->
<template>
  <div>
    <input v-model="newName" placeholder="Имя" />
    <input v-model="newSurn" placeholder="Фамилия" />
    <button @click="save">Сохранить</button>
  </div>
</template>

<script>
export default {
  emits: ['add'],
  data() {
    return {
      newName: '',
      newSurn: ''
    };
  },
  methods: {
    save() {
      if (this.newName.trim() && this.newSurn.trim()) {
        this.$emit('add', this.newName, this.newSurn);
        this.newName = '';
        this.newSurn = '';
      } else {
        alert('Пожалуйста, введите имя и фамилию');
      }
    }
  }
};
</script>

