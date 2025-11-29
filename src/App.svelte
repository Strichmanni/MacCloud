<script>
  import BootScreen from './BootScreen.svelte';
  import Desktop from './Desktop.svelte';
  import { writable } from 'svelte/store';
  let bootComplete = writable(false);

  function handleBootComplete() {
    bootComplete.set(true);
  }
</script>

{#if !$bootComplete}
  <BootScreen onBootComplete={handleBootComplete}/>
{:else}
  <Desktop/>
{/if}
