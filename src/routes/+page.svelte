<script lang="ts">


	let age = $state('');

	const birthday = $state({
		month: '',
		day: '',
		year: '',
	})

	const ageBrokenDown = $derived({
		years: 0,
		month: 0,
		day: 0
	});

	console.log(age)

	function calculateAge(age: string)  {
		let year: string, month: string, day: string;
		year = age.substring(0, 4);
		month = age.substring(5, 7);
		day = age.substring(8, 10);
		return { year, month, day };
	}

	const newAge = calculateAge(age);
</script>


<div class="bg-blue-500 p-2 w-full h-dvh flex flex-col items-center justify-center">
	<h1 class="p-2 mb-24 text-5xl font-bold">Age Calculator</h1>
	<div class="w-11/12 h-1/2 bg-yellow-600 flex flex-col items-center justify-center">
		<div class="bg-green-400 w-full h-1/2 p-5 flex flex-col items-center justify-center">
			<p>This is my app now!!!!</p>
			<div class="w-full flex justify-around">
				<span>Birthday : <input type="date" name="date" bind:value={age} />
				</span>
			</div>
		</div>
		<div class="bg-purple-400 w-3/4 h-1/2 p-5 flex flex-col items-center justify-center">
			<span>Age : {newAge}</span>
			<span>{newAge.year} Years</span>
			<span>{newAge.month} Months</span>
			<span>{newAge.day} Days</span>
		</div>
	</div>

</div>