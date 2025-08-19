<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Carta Especial</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: "Segoe UI", sans-serif;
      background: linear-gradient(135deg, #ffe1f2, #e0c3fc);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      overflow: hidden;
    }
    .carta {
      width: 250px;
      height: 180px;
      background: #fff0f6;
      border: 2px solid #b197fc;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.2);
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      transition: all 0.4s ease;
      position: relative;
      z-index: 2;
    }
    .carta:hover {
      transform: scale(1.05);
    }
    .libro {
      display: none;
      position: absolute;
      width: 90%;
      max-width: 600px;
      height: 400px;
      background: #fff;
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
      overflow: hidden;
      z-index: 3;
    }
    .pagina {
      display: none;
    }
    .pagina.activa {
      display: block;
      animation: aparecer 0.5s ease forwards;
    }
    @keyframes aparecer {
      from { opacity: 0; transform: scale(0.95); }
      to { opacity: 1; transform: scale(1); }
    }
    .indicacion {
      position: absolute;
      bottom: 10px;
      font-size: 0.85em;
      color: #888;
    }
    video {
      max-width: 100%;
      margin-top: 20px;
      border-radius: 10px;
    }
  </style>
</head>
<body>

<div class="carta" onclick="abrirCarta()">
  💌 Toca para abrir
</div>

<div class="libro" id="libro" onclick="siguientePagina()">
  <div class="pagina activa">Hola ana, primero que nada felicitaciones por llegar a los 200 días de racha de tiktok conmigo </div>
  <div class="pagina">No cualquiera la verdad y esta racha empezó por un descuido xD.creo q recuerdas muy bien ese dia que te mande el tiktok del chabubu que nunca se compro, y ahí te apareció mi perfil pero bueno<br><br>200 días aguantándonos y que sean más (eso espero) 😅</div>
  <div class="pagina">Muchas cosas se hablaron en este chat xD aqui un pequeño resumen:como recuerdos, desgracias, arrepentimientos, reflexiones, risas, inseguridades...</div>
  <div class="pagina">Story time, regla 📏, desveladas, chismes, onvrez, actualizaciones, códigos de uber xD, verdades, autocorrector humillando...</div>
  <div class="pagina">¿Te sientes muy onichan?, agradecimientos, apoyo en malos momentos, apuestas (siempre perdia), invitaciones a jugar...</div>
  <div class="pagina">Doxxeadas, gustos culposos, chat gpt, tlou (ya sabes 🍑), recetas (todavía sigo haciendo esa receta de los rollos jiji) y te debo la carne, capítulos de la Rosa, África 🗣, coca, Montoya 🗣</div>
  <div class="pagina">Compartir buena música (esclava), ni en un psicólogo se habla tanto XD y de lo más importante: tiktoks good, ahh y stickers tmb muy good, bueno, es importante pero<br><br>Lo importante es que siempre se disfrutó. Eso creo. y espero</div>
  <div class="pagina">Pero gracias pq sigues estando aquí aguantándome, se que hablo mucho osea escribo mucho ps y siento q aveces molesto o enfado y por metiche XD solo dime si eso llega a pasar, a afectar y molestar para calmarme, ok? y sabes lo q pienso de eso? que me vale XD seguire estando ahi, ntp, psicólogo ricolin a la orden pero enserió ty. 😁</div>
  <div class="pagina">
    chale, me desvelo mucho haciendo esto pero bueno, 🎥 ahí te va un video un poco revelador, ty por todo 🫶:<br><br>
    <video controls>
      <source src="video_demo.mp4" type="video/mp4">
      Tu navegador no soporta video.
    </video>
  </div>
  <div class="indicacion">Toca para pasar la página 📖</div>
</div>

<script>
  let paginaActual = 0;
  let paginas;

  function abrirCarta() {
    document.querySelector(".carta").style.display = "none";
    const libro = document.getElementById("libro");
    libro.style.display = "block";
    paginas = libro.querySelectorAll(".pagina");
  }

  function siguientePagina() {
    if (!paginas) return;
    paginas[paginaActual].classList.remove("activa");
    paginaActual++;
    if (paginaActual >= paginas.length) paginaActual = 0;
    paginas[paginaActual].classList.add("activa");
  }
</script>

</body>
</html>
