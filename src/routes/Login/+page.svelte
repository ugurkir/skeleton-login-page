<script>
	import { LightSwitch } from '@skeletonlabs/skeleton';

	let email = '';
	let password = '';
	let dark = false;

	function handleLogin() {
		console.log(`Email: ${email}, Password: ${password}`);
	}

	function darkMode() {

		dark = !dark;
	
	}
</script>

<main class={`${dark? "dark" : "light"} flex flex-col justify-center items-center h-screen`}>
	
	<h1 class={`${dark? "darkText" : "lightText"} text-xl sm:text-xl md:text-2xl lg:text-2xl xl:text-3xl`}>Login</h1>
	<form class={`${dark? "darkForm" : "lightForm"} flex flex-col gap-4 p-8 rounded-xl shadow-md`} on:submit|preventDefault={handleLogin}>
		<label for="email" class="text-lg">Email:</label>
		<input id="email" type="email" bind:value={email} required class="p-2 rounded-md" />

		<label for="password" class="text-lg">Password:</label>
		<input id="password" type="password" bind:value={password} required class="p-2 rounded-md" />

		<button type="submit" class="p-2 rounded-md bg-blue-500 text-white cursor-pointer hover:bg-blue-700">Login</button>
	</form>
	<p class={`${dark? "darkText" : "lightText"} text-sm sm:text-sm md:text-base lg:text-base xl:text-lg`}>Don't have an account?<a href="./Signup" class="signup-link">Signup!</a></p>
	<LightSwitch on:click={darkMode}/>
</main>


<style>

	.signup-link {
		color: #007BFF;
	}

	.dark {
		background-color: #222222;
		color: #222222;
	}

	.light {
		background-color: #dddada;
		color: #dddada;
	}

	.darkText{
		color: #dddada;
	}

	.lightText{
		color: #222222;
	}

	.darkForm {
		background-color: #dddada;
	}

	.lightForm {
		background-color: #222222; ;
	}

	main {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100vh;
	}

	form {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		padding: 2rem;
		border-radius: 1rem;
		box-shadow: 0px 0px 10px rgba(0,0,0,0.1);
	}

	input, button {
		padding: 1rem;
		border-radius: .5rem;
	}

	button {
		background-color: #007BFF;
		color: white;
		cursor: pointer;
	}

	button:hover {
		background-color: #0056b3;
	}

</style>