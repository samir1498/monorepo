<script lang="ts">
    import Icon from '@iconify/svelte';
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
  
    let newTaskName: string = '';
  
    const submitForm = () => {
      if (newTaskName.trim()) {
        dispatch('addtask', { name: newTaskName });
        newTaskName = '';
      }
    };
  </script>
  
  <form on:submit|preventDefault={submitForm} class="flex items-center space-x-2">
    <input
      class="border p-2 rounded"
      type="text"
      bind:value={newTaskName}
      placeholder="Add a new task"
    />
    <button type="submit" class="bg-blue-500 text-white p-2 rounded">
      <Icon icon="mdi:plus-circle" />
    </button>
  </form>
  