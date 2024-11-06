<script>

let contador = 0;
let boton = document.getElementById('boton');

boton.addEventListener('click', changeColor);

function changeColor(){
    
    let colores = ["red", "green", "purple", "orange"];

    if(contador >= colores.length){
        contador = 0;
    }
    
    contador++;
    boton.style.backgroundColor = colores[contador];

}

</script>

<div class="box">
    <button id="boton" on:click={changeColor}>Cambiar color</button>
</div>