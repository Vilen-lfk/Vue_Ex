<script>
import User from './components/User.vue'

export default {
  components: {
    User
  },
  data() {
    return {
      
    }
  }
}
</script>


<template>
    <div>
        <User />
    </div>
</template>

<style scoped>
p.done {
	text-decoration: line-through;
}
p{
    color: green;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
