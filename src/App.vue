<template>
	<TimeSince :date="'09262021'" />
</template>

<script>
	import TimeSince from '@/components/TimeSince.vue'
	export default {
		name: 'App',
		components: {
			TimeSince
		}
	}
</script>
