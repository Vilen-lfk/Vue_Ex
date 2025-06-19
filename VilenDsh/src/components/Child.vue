<template>
  <div>
    <h3>Дочерний компонент</h3>
    <button @click="handleFirst">Кнопка 1</button>
    <button @click="handleSecond">Кнопка 2</button>
  </div>
</template>

<script>
export default {
  emits: ['clickOne', 'clickTwo'],
  methods: {
    handleFirst() {
      this.$emit('clickOne');
    },
    handleSecond() {
      this.$emit('clickTwo');
    }
  }
}
</script>