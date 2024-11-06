<script>

let foto = document.getElementById('foto');

let aumento = document.getElementById('aumento');
let reduccion = document.getElementById('reduccion');

aumento.addEventListener('click', aumentarTamaño);
reduccion.addEventListener('click', reducirTamaño);

foto.style.width = '200px';
foto.style.height = '200px';

function aumentarTamaño(){

foto.style.width = '300px';
foto.style.height = '300px';

}

function reducirTamaño(){

foto.style.width = '100px';
foto.style.height = '100px';

}

</script>

<style>
    .botones{
        display: flex;
        flex-direction: row;
        justify-content: center;
    }
</style>

<div class="divImagen">
    <img id="foto" src="./public/Skylanders_Logo.webp" alt="">
    <div class="botones">
        <img id="aumento" src="./public/SimpleLineIconsPlus.png" alt="">
        <img id="reduccion" src="./public/EiMinus.png" alt="">
    </div>
</div>