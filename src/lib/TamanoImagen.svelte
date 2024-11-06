<script>
    let width = 200;
    let height = 200;
  
    function aumentarTamaño() {
      width = 300;
      height = 300;
    }
  
    function reducirTamaño() {
      width = 100;
      height = 100;
    }
  </script>
  
  <style>
    .botones {
      display: flex;
      flex-direction: row;
      justify-content: center;
      
    }
  </style>
  
  <div class="divImagen">
    <img 
      id="foto" 
      src="./public/Skylanders_Logo.webp" 
      alt="" 
      style="width: {width}px; height: {height}px;"
    >
    <div class="botones">
      <!-- svelte-ignore a11y_click_events_have_key_events -->
      <!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
      <button on:click={aumentarTamaño}>+</button>
      <button on:click={reducirTamaño}>-</button>
      <!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
      <!-- svelte-ignore a11y_click_events_have_key_events -->
      
    </div>
  </div>