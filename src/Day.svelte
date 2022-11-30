<script lang="ts">
import Dialog from './Dialog.svelte';
  export let date: Date;

  let dialog;
  let today = new Date();

  var day = today.getDate();

  function openDialog() {
    dialog.showModal()
    dialog.addEventListener('click', function (event) {
      if (event.target === dialog) {
        dialog.close()
      }
    })
  }

  function closeDialog() {
    dialog.close()
  }
</script>

<style>
  div {
    flex: 1;
    border: 1px solid #ccc;
  }
  button {
    margin: 5px;
  }
</style>

<div>
  {#if date.getDate() === 1}
    {#if date.getDate() === day}
    <button on:click={openDialog}>{date.getMonth() + 1}/{date.getDate()}</button>
    {:else}
    {date.getMonth() + 1}/{date.getDate()}
    {/if}
  {:else}
    {#if date.getDate() === day}
    <button>{date.getDate()}</button>
    {:else}
    {date.getDate()}
    {/if}
  {/if}
</div>

<Dialog
	bind:dialog
	on:closeDialog={closeDialog}
/>