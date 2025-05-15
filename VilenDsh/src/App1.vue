<script>
	export default {
	data() {
	return {
    //18
    hidden: true,
    //19
    visible: false,
    //20
    visible1:true,
    //21
    visible2:true,
    //22
    isAdmin: false,
    //23
    num: 2,
    //24
    age: 25,
    //27
    items: [1, 2, 3, 4, 5],
    //28
    arr: ['x', 'y', 'z'],
    
}
},
methods: {
	hide: function() {
		this.visible = true;
	},
    hide1: function() {
		this.visible = false;
	},
    toggle: function() {
	this.visible1 = !this.visible1;
    },
    toggle1: function() {
	this.visible2 = !this.visible2;
}
}
}



</script>
<template>
	<div>
    <H1>18</H1>
    <p v-if="!hidden">text</p>
    <p v-if="hidden">text</p>

    <h1>19</h1>
    <button @click="hide">открыть</button>
     <button @click="hide1">скрыть</button>
	<p v-if="visible">text</p>

    <h1>20</h1>
    <button @click="toggle">toggle</button>
	<p v-if="visible1">text</p>

    <h1>21</h1>
    <button @click="toggle1">
		{{ visible2 ? 'hide' : 'show' }}
	</button>

    <h1>22</h1>
    <p v-if="isAdmin">+++</p>
	<p v-else>---</p>

    <h1>23</h1>
    <p v-if="num === 1">one</p>
	<p v-if="num === 2">two</p>
	<p v-if="num === 3">three</p>

    <h1>24</h1>
    <p v-if="age < 18">подросток</p>
	<p v-else-if="19 >= age < 25">молодой человек</p>
	<p v-else-if="26 >= age <= 100">мужчина</p>

  <h1>27</h1>
  <p v-for="item in items" :key="item">{{ item }}</p>
  -----------
  <p v-for="item in items" :key="item">{{ item*item }}</p>

  <h1>28</h1>
   <li v-for="(elem, key) in arr" :key="key">
      {{ key }}
    </li>
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
