<script>
  import Window from './Window.svelte';
  import { writable } from 'svelte/store';

  let filesVisible = writable(false);
  let notesVisible = writable(false);
</script>

<div id="desktop">
  <div class="icon" on:click={() => filesVisible.set(true)}>Dateien</div>
  <div class="icon" on:click={() => notesVisible.set(true)}>Notizen</div>

  <Window title="Dateien" bind:visible={$filesVisible}>
    <p>Dateien hier...</p>
  </Window>

  <Window title="Notizen" bind:visible={$notesVisible}>
    <p>Notizen hier...</p>
  </Window>
</div>

<style>
  #desktop {
    width:100%;
    height:100%;
    background:#007aff;
    display:flex;
    padding:20px;
  }
  .icon {
    width:80px;
    text-align:center;
    color:white;
    cursor:pointer;
    margin-right:10px;
  }
</style>
