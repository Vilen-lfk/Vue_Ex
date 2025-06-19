<template>
  <div class="employee">
    <p>Имя: {{ name }}</p>
    <p>Зарплата: {{ salary }}</p>
    <p>Возраст: {{ age }}</p>
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    salary: Number,
    age: Number
  }
}
</script>