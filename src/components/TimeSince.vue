<template>
	<div>{{ data }}</div>
</template>

<script>
	export default {
		data () {
			return {
				data: ''
			}
		},
		props: {
			date: String
		},
		mounted () {
			if (this.date.length > 0) {
				const 	today = new Date(),
						todaysMonth = today.getMonth() + 1,
						todaysYear = today.getFullYear(),
						todaysDay = today.getDate()
				let difference = 0;
				if (this.date == '0' + (todaysMonth).toString() + (todaysDay).toString() + (todaysYear).toString()) {
					this.data = '0 days ago'
				} else {
					if ((this.date[2] + this.date[3] < todaysDay) && 
						(this.date[0] + this.date[1] == todaysMonth) && 
						(this.date[4] + this.date[5] + this.date[6] + this.date[7] == todaysYear)) {
						difference = todaysDay - (this.date[2] + this.date[3])
						if (difference > 1) {
							this.data = difference + ' days ago'
						} else {
							this.data = difference + ' day ago'
						}
					} else if ((this.date[0] + this.date[1] < todaysMonth) &&
						(this.date[4] + this.date[5] + this.date[6] + this.date[7] == todaysYear)) {
						difference = todaysMonth - (this.date[0] + this.date[1])
						if (difference > 1) {
							this.data = difference + ' months ago'
						} else {
							this.data = difference + ' month ago'
						}
					} else if ((this.date[4] + this.date[5] + this.date[6] + this.date[7]) < todaysYear) {
						difference = todaysYear - (this.date[4] + this.date[5] + this.date[6] + this.date[7])
						if (difference > 1) {
							this.data = difference + ' years ago'
						} else {
							this.data = difference + ' year ago'
						}
					}
				}
			}
		}
	}
</script>