<script>
    let width = 300;
    let height = 200;
  
    function aumentarTamaño() {
      width = 400;
      height = 300;
    }
  
    function reducirTamaño() {
      width = 200;
      height = 100;
    }
  </script>
  
  <style>

.all{
  width: 700px;
  height: 400px;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: space-between;
  border: 1px white solid;
  border-radius: 20px;
}

.cont-foto{
  margin-top: 20px;
}

    .botones {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: flex-end;
      margin: 10px;
    }
  </style>
  
  <div class="all">
    <div class= "cont-foto">
      <img id="foto" src="./public/Skylanders_Logo.webp" alt="" style="width: {width}px; height: {height}px;">
    </div>
    <div class="botones">
      <!-- svelte-ignore a11y_click_events_have_key_events -->
      <!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
      <button on:click={aumentarTamaño}>+</button>
      <button on:click={reducirTamaño}>-</button>
      <!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
      <!-- svelte-ignore a11y_click_events_have_key_events -->
      
    </div>
  </div>