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
