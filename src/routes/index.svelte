<script>
  import { myStore } from "../myStores";
  import { crossfade } from "svelte/transition";
  import { flip } from "svelte/animate";

  let show = false;

  const [send, receive] = crossfade({ duration: 200 });
</script>

<style>
  main {
    padding: 50px 10%;
  }
  button {
    padding: 20px 50px;
  }
  .modal {
    position: fixed;
    top: 50%;
    left: 50%;

    background: white;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 12px rgba(0, 0, 0, 0.24);
    padding: 70px 100px;
    transform: translate(-50%, -50%);
    border-radius: 12px;
  }
</style>


<main>

  <div style="height:200px; overflow: auto">
    <pre>{JSON.stringify($myStore, 0, 2)}</pre>
  </div>

  {#if !show}
    <button
      in:receive={{ key: 'modal' }}
      out:send={{ key: 'modal' }}
      on:click={() => (show = true)}>
      Open me
    </button>
  {/if}

  {#if show}
    <div
      in:receive={{ key: 'modal' }}
      out:send={{ key: 'modal' }}
      on:click={() => (show = false)}
      class="modal">
      Close me
    </div>
  {/if}

</main>
