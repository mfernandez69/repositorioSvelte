<script>
  import { Button, Spinner } from 'flowbite-svelte';
  let loading = false;

  function handleClick() {
    loading = true;
    setTimeout(() => {
      loading = false;
    }, 2000); // Simula una carga de 2 segundos
  }
</script>

<Button on:click={handleClick} disabled={loading}>
  {#if loading}
    <Spinner class="mr-3" size="4" color="white" />
  {/if}
  {loading ? 'Cargando...' : 'Clic aquí'}
</Button>