<script>
	export default {
	data() {
	return {
		name: 'john',
		surn: 'smit',
    // 5
    text: 'page',
		href: 'page.html',
	}
}
}
</script>
<template>
	<div>
		Hello World
    <p> My name is Vilen</p>

    <div>
      <h1>4 задание</h1>
      {{ name }}
      {{ surn }}
    </div>
      <h1>5 задание</h1>
      <a href="page.html">page</a>
    </div>
</template>

<style scoped>
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
