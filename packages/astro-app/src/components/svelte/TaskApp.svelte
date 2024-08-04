<script lang="ts">
	import { v4 as uuidv4 } from 'uuid';
	import TaskList from "./TaskList.svelte";
	import TaskInput from './TaskInput.svelte';

  
	let tasks: { id: string; name: string }[] = [];
  
	const addTask = (event: CustomEvent) => {
	  tasks = [...tasks, { id: uuidv4(), name: event.detail.name }];
	};
  
	const deleteTask = (id: string) => {
	  tasks = tasks.filter((task) => task.id !== id);
	};
  </script>
  
  <div class="flex items-center justify-center"> 
	<div class="p-4 max-w-sm mx-auto bg-white rounded-xl shadow-md">

		<h1 class="text-xl font-bold">To-Do List</h1>
		<TaskInput on:addtask={addTask} />
		<TaskList {tasks} {deleteTask} />
	</div>
</div>
  