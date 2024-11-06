<script>

function changeColor(){
    let boton = document.getElementById('boton');
    let contador = 0;
    let colores = ["red", "green", "purple", "orange"];

    if(contador >= colores.length){
        contador = 0;
    }
    else{
        contador++;
        boton.style.backgroundColor = colores[contador];
    }

boton.addEventListener('click', changeColor);

}

</script>

<div class="box">
    <button id="boton" on:click={changeColor}>Cambiar color</button>
</div>