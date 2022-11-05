<script lang="ts">
	import { onMount } from 'svelte';

	let second: string | number;
	let minute: string | number;
	let hour: string | number;
	let day: number;

	const countdown = () => {
		let currentDate: Date = new Date();
		let christmasDate: Date = new Date(2022, 11, 25);

		let currentTime: number = currentDate.getTime();
		let christmasTime: number = christmasDate.getTime();

		let countdownTime: number = christmasTime - currentTime;

		let s = Math.floor(countdownTime / 1000);
		let m = Math.floor(s / 60);
		let h = Math.floor(m / 60);
		day = Math.floor(h / 24);

		h %= 24;
		m %= 60;
		s %= 60;

		hour = h < 10 ? '0' + h : h;
		minute = m < 10 ? '0' + m : m;
		second = s < 10 ? '0' + s : s;
	};

	onMount(() => {
		setInterval(countdown, 1000);
		countdown();
	});
</script>

<style lang="scss">
</style>
