<template>
  <div class="employee">
    <p>Имя: {{ name }}</p>
    <button @click="send">Передать имя</button>
  </div>
</template>

<script>
export default {
  props: {
    name: String
  },
  methods: {
    send() {
      this.$emit('sendName', this.name);
    }
  }
}
</script>
