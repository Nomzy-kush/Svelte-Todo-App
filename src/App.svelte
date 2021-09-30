<script>
	import { Button } from 'svelte-mui/src'
	let tasks = [];
	const addTasks = () => {
		tasks = [...tasks, '']
	}
	
	const removeTask = (index) => {
		tasks = [...tasks.slice(0, index), ...tasks.slice(index+1)];
	}


</script>

<main>
	<article>

{#each tasks as task, index }
 <input bind:value={tasks[index]}>
 <Button on:click={()=>removeTask(index)} raised color="#737383">Remove</Button>
 <br>
 {/each}



 <Button on:click={addTasks} raised color="#ff4d14">Add
	</Button>

</article>
</main>


<style>

	main {
		display: flex;
		justify-content: center;
	}

	input {
		border-radius: 3px;
		width: 10em;
		height: 3em;
		color: #FFC0CB;
		background-color: #000;
	}

</style>