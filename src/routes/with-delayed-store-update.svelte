<script>
  import { myStore } from "../myStores";
  setTimeout(() => {
    myStore.update(store => store);
  }, 0);
</script>

<h1>Delayed store update here</h1>
