<script lang="ts">
    import Task from './Task.svelte';
    export let tasks: { id: string; name: string }[];
    export let deleteTask: (id: string) => void;
  </script>
  
  {#each tasks as task (task.id)}
    <Task {task} {deleteTask} />
  {/each}
  