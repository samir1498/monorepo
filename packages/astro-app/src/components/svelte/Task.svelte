<script lang="ts">
import Icon from '@iconify/svelte';
  export let task: { id: string; name: string };
  export let deleteTask: (id: string) => void;
</script>

<div class="flex items-center justify-between p-2 border-b">
  <span>{task.name}</span>
  <button on:click={() => deleteTask(task.id)}>
    <Icon icon="mdi:delete" class="text-red-500" />
  </button>
</div>
