<script>
	export default {
	data() {
    return{
        hrefs: [
        {href: '1.html', text: 'text1'},
        {href: '2.html', text: 'text2'},
        {href: '3.html', text: 'text3'},
      ],
      //33
        items: [1, -2, 3, -4, 5 , 6],
      //35
        arr: ['a', 'b', 'c'],  
    }
},
methods: {
	add: function() {
		this.arr.push('xxx');
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

    <h1>33</h1>
    <ul>
		<template v-for="elem in items">
			<li v-if="elem > 0" :key="elem.items">
				{{ elem }}
			</li>
		</template>
	</ul>

    <h1>35</h1>
	<p v-for="elem in arr" :key = "elem.arr">
		{{ elem }}
	</p>
	<button @click="add">add</button>

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
