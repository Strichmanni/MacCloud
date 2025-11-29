<script>
  export let title = "";
  export let visible = true;
  export let onClose = () => {};
</script>

<style>
  .window {
    position:absolute;
    top:100px;
    left:100px;
    width:400px;
    height:300px;
    background:#f0f0f5;
    border-radius:10px;
    box-shadow:0 10px 30px rgba(0,0,0,0.4);
    display:flex;
    flex-direction:column;
  }
  .titlebar {
    height:30px;
    background:#ddd;
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding:0 10px;
    cursor:move;
  }
  .buttons div {
    width:15px; height:15px; border-radius:50%; cursor:pointer;
  }
  .close { background:#ff5f57; }
</style>

{#if visible}
<div class="window">
  <div class="titlebar">
    <span>{title}</span>
    <div class="buttons">
      <div class="close" on:click={onClose}></div>
    </div>
  </div>
  <div class="window-content">
    <slot></slot>
  </div>
</div>
{/if}
