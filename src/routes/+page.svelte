<script lang="ts">

	const age = 32

	const ageBrokenDown = $derived({
		years: 0,
		month: 0,
		day: 0,
	})




</script>





<div class="bg-blue-500 p-2 w-full h-dvh flex flex-col items-center justify-center">
	<h1 class="p-2 mb-24 text-5xl font-bold">Age Calculator</h1>
	<div class="w-3/4 h-1/2 bg-yellow-600 flex flex-col items-center justify-center">

		<div class="bg-green-400 w-3/4 h-1/2 p-5 flex flex-col items-center justify-center">
			<p>This is my app now!!!!</p>
			<span>
			this will be a form
		</span>
		</div>
		<div class="bg-purple-400 w-3/4 h-1/2 p-5 flex flex-col items-center justify-center">
			<span>Age : {age}</span>
			<span>{ageBrokenDown.years} Years</span>
			<span>{ageBrokenDown.month} Months</span>
			<span>{ageBrokenDown.day} Days</span>
		</div>
	</div>

</div>