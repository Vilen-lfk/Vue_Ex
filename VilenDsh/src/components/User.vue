<script>
	export default {
		props: ['names', 'surn'],
		data() {
			return {
				name1: 'john',
     		 	surn1: 'smith',
      			price1: '155555'
			}
		}
	}
</script>
<template>
	<div>

		{{ price1 }}
		{{ name1 }}
		{{ surn1 }}
	</div>
</template>
