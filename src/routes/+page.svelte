<script lang="ts">
	type Birthday = {
		year: number | string | null;
		month: number | string | null;
		day: number | string | null;
	};

	type bdayInput = string;

	let age = $state<Birthday>();

	let birthday = $derived(age);

	function calculateAge(age: bdayInput | Birthday | undefined) : Birthday | undefined {
		let year: string, month: string, day: string;
		if (typeof age === 'string' ) {
			year = age.substring(0, 4);
			month = age.substring(5, 7);
			day = age.substring(8, 10);
			console.log(year, month, day);
			birthday = {year, month, day}
			return { year, month, day };
		}
	}
</script>

<div class="flex h-dvh w-full flex-col items-center justify-center bg-blue-500 p-2">
	<h1 class="mb-24 p-2 text-5xl font-bold">Age Calculator</h1>
	<div class="flex h-1/2 w-11/12 flex-col items-center justify-center bg-yellow-600">
		<div class="flex h-1/2 w-full flex-col items-center justify-evenly bg-green-400 p-5">
			<p>This is my app now!!!!</p>
			<div class="flex w-full justify-around">
				<span>Birthday : <input type="date" name="date" bind:value={age} /> </span>
			</div>
			<button class="rounded-3xl border p-3 hover:bg-blue-600" onclick={() => calculateAge(age)}>Calculate</button>
		</div>
		<div class="flex h-1/2 w-3/4 flex-col items-center justify-center bg-purple-400 p-5">
			<span>Age : {age}</span>
			<span> {birthday ? birthday.year : "no value"} Years</span>
			<span>{birthday ? birthday.month : "no value"} Months</span>
			<span>{birthday ? birthday.day : "no value"} Days</span>
		</div>
	</div>
</div>
