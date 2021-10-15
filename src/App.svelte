


<script>
	import { Button } from 'svelte-mui/src';
	import Header from "./components/Header.svelte";
	import {MDCTextField} from '@material/textfield';

	
	let tasks = [];
	const addTasks = () => {
		tasks = [...tasks, '']
	}
	
	const removeTask = (index) => {
		tasks = [...tasks.slice(0, index), ...tasks.slice(index+1)];
	}


</script>

<style>

	main {
		display: flex;
		justify-content: center;
	}
 

	.grid {
		display: grid;
		grid-template-columns: 1fr 1fr;
        grid-gap: 20px;
		padding: 3em 3em
	}

	.add-btn {
		display: flex;
		justify-content: center;
		padding-bottom: 1em;
	}

	.container {
		width: 500px;
		background: #C0C0C0;
	}

	:global( .container *) {
		font-family: Georgia, 'Times New Roman', Times, serif;
	}






</style>




<main>
	<head>
		<link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">
	  </head>
	<div class="container">
		<Header />

		<div class="grid">

{#each tasks as task, index }
<div class="grid-1">
	<label class="mdc-text-field mdc-text-field--outlined">
		<span class="mdc-notched-outline">
		  <span class="mdc-notched-outline__leading"></span>
		  <span class="mdc-notched-outline__notch">
			<span class="mdc-floating-label" id="my-label-id"></span>
		  </span>
		  <span class="mdc-notched-outline__trailing"></span>
		</span>
		<input type="text" class="mdc-text-field__input" aria-labelledby="my-label-id">
	  </label>
</div>

<div class="grid-2">
 
 <Button on:click={()=>removeTask(index)} > <span class="material-icons" >
	delete
	</span> </Button>
</div>
 {/each}

</div>


<div class="add-btn">
 <Button on:click={addTasks} raised color="#ff4d14" >Add
	</Button>
</div>

	

	

</div>
</main>


