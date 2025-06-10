<!DOCTYPE html>
<html>
<head>
<title>Te Amo Cayendo</title>
<style>
body {
  height: 100vh;
  margin: 0;
  background-color: #222; /* Fondo oscuro */
  overflow: hidden; /* Evita scroll */
}

#teamo-grande {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 4em;
  color: #ff69b4; /* Rosa brillante */
  text-shadow: 0 0 10px #ff69b4, 0 0 20px #ff69b4; /* Brillo */
}

.teamo-pequeno {
  position: absolute;
  color: #ff69b4; /* Rosa brillante */
  text-shadow: 0 0 5px #ff69b4; /* Brillo */
  font-size: 1em;
  opacity: 0.8; /* Ligera transparencia */
}
</style>
</head>
<body>

<div id="teamo-grande">Te amo</div>

<script>
function crearTeAmoPequeno() {
  const teamo = document.createElement('div');
  teamo.classList.add('teamo-pequeno');
  teamo.textContent = 'Te amo';
  teamo.style.left = Math.random() * 100 + '%';
  teamo.style.top = '-20px';
  document.body.appendChild(teamo);

  const velocidad = Math.random() * 3 + 1; // Velocidad aleatoria (ajustada)
  let top = parseInt(teamo.style.top);

  const intervalo = setInterval(() => {
    top += velocidad;
    teamo.style.top = top + 'px';
    if (top > window.innerHeight) {
      clearInterval(intervalo);
      document.body.removeChild(teamo);
    }
  }, 20);
}

setInterval(crearTeAmoPequeno, 100); // Crea un nuevo "Te amo" cada 100 milisegundos
</script>

</body>
</html>
