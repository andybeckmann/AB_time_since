# AB_time_since

AB_time_since is a Vue component that accepts a timestamp as a string, in the form of MMDDYYYY, and returns the total time elapsed since the provided date, in days, months, or years.

## Demo

```vue
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
```

### Output

"1 day ago"

#### Setup
```
npm install
```

#### Compiles and hot-reloads for development
```
npm run serve
```

#### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```
