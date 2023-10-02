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
  
  


  <div class={dark? "dark all" : "light all"}>
	
	<h1 class={dark? "darkText" : "lightText"}>SIGNUP</h1>
	
	<form class={dark? "darkForm loginForm" : "lightForm loginForm"} on:submit|preventDefault={handleLogin}>
	  <label for="email" >Email:</label>
	  <input id="email" type="email" bind:value={email} required />
  
	  <label for="password" >Password:</label>
	  <input id="password" type="password" bind:value={password} required />
  
	  <button type="submit">Login</button>
	</form>

	<LightSwitch on:click={darkMode}/>
  
</div>
  

  <style>
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
		background-color:#222222; ;
	}
	.all {
	  display: flex;
	  flex-direction: column;
	  justify-content: center;
	  align-items: center;
	  height: 100vh;
	  
		
	}
  
	.loginForm {
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
  