<script lang="ts">
  export let date: Date;
</script>

<style>
  div {
    flex: 1;
    border: 1px solid #ccc;
  }
</style>

<div>
  {#if date.getDate() === 1}
    <a href="#">{date.getMonth() + 1}/{date.getDate()}</a>
  {:else}
    <a href="#">{date.getDate()}</a>
  {/if}
</div>