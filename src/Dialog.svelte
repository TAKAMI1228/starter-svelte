<script>
    import { createEventDispatcher } from 'svelte'; // 子から親への値の受け渡し

	export let dialog;

	const dispatch = createEventDispatcher()
    function clickClose() {
        dispatch('closeDialog');
    }
</script>

<dialog bind:this={dialog}>
  <div class='inner'>
	<p>本日は</p>
	<h2>
		チョコレート
    </h2>
	<button on:click={clickClose}>
		close
	</button>
  </div>
</dialog>