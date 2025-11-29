<script>
  import { onMount } from 'svelte';
  import { writable } from 'svelte/store';
  export let onBootComplete;
  
  let progress = 0;
  
  onMount(() => {
    const interval = setInterval(() => {
      progress += 1;
      if (progress >= 100) {
        clearInterval(interval);
        onBootComplete();
      }
    }, 30);
  });
</script>

<style>
  .bootscreen {
    position: absolute;
    top:0; left:0;
    width: 100%;
    height:100%;
    background: black;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    color:white;
    font-family: -apple-system, BlinkMacSystemFont, sans-serif;
  }
  img {
    width: 100px;
    margin-bottom:20px;
  }
  .progress {
    width: 200px;
    height: 5px;
    background: #333;
    border-radius: 2px;
    overflow:hidden;
  }
  .bar {
    height: 100%;
    background:#fff;
    width: 0%;
  }
</style>

<div class="bootscreen">
  <img src="/apple-logo.png" alt="Apple Logo">
  <div class="progress">
    <div class="bar" style="width:{progress}%"></div>
  </div>
</div>
