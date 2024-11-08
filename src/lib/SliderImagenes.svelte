<script>
      const imagenes = ["/caraJuan.png", "/caraMarcos.png", "/caraPaco.png", "/caraRafa.png"];
      let imagenActual = 0;
      let btnAnterior = true;
      let btnSiguiente = false;

      function imagenSiguiente(){
            if(imagenActual<imagenes.length-2){
                  btnSiguiente = false;
                  btnAnterior = false;
                  imagenActual += 1;
            }else if(imagenActual<imagenes.length-1){
                  btnSiguiente = true;
                  imagenActual += 1;
            }
            else{
                  btnSiguiente = true;
            }
      }

      function imagenAnterior(){
            if(imagenActual>1){
                  btnSiguiente = false;
                  btnAnterior = false;
                  imagenActual -= 1;
            }else if(imagenActual>0){
                  btnAnterior = true;
                  imagenActual -= 1;
            }
            else{
                  btnAnterior = true;
            }
      }

      function actualizarImagen(){
            return imagenes[imagenActual];
      }

</script>

<div class="slider">
      
      <!-- svelte-ignore a11y_consider_explicit_label -->
      <button on:click={imagenAnterior} disabled={btnAnterior}>
            <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M10 22L0 12L10 2l1.775 1.775L3.55 12l8.225 8.225z"/></svg>
      </button>

      <img src="{imagenes[imagenActual]}" alt="imagenesSlider" class="imgSlider">


      <!-- svelte-ignore a11y_consider_explicit_label -->
      <button class="pasarImagen" on:click={imagenSiguiente} disabled={btnSiguiente}>
            <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M8.025 22L6.25 20.225L14.475 12L6.25 3.775L8.025 2l10 10z"/></svg>
      </button>
</div>

<style>
      .slider{
            display: flex;
            flex-wrap: wrap;
            flex-direction: row;
            align-content: center;
            justify-content: center;

      }
      .imgSlider{
            width: 250px;
      }

</style>