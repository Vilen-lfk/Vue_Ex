<script>
	export default {
	data() {
    return{
        hrefs: [
        {href: '1.html', text: 'text1'},
        {href: '2.html', text: 'text2'},
        {href: '3.html', text: 'text3'},
      ],
    }
}
}



</script>
<template>
	<div>
        <h1>31</h1>
         <ul>
        <li v-for="ss in hrefs" :key="ss.href">
        <a :href="ss.href">{{ ss.text }}</a>
    </li>
  </ul>
  <h1>32</h1>
    <p v-for="num in 20" :key="num">		
        {{ num }}
	</p>
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
