<div align="center">

# SILENT HILL · A Tale of Birds Without a Voice

### Un acertijo de Midwich Elementary, convertido en un piano interactivo

*Una pequeña visita a la niebla de Silent Hill (1999).*

</div>

---

## El proyecto

Este sitio recrea, como homenaje interactivo, el acertijo del piano que Harry
Mason encuentra en Midwich Elementary School, en el primer
Silent Hill, publicado para PlayStation en 1999 por Konami y desarrollado
por Team Silent.

En el juego, un poema habla de cinco pájaros y de una recompensa. El desafío
consiste en interpretar sus pistas para descubrir qué teclas del piano no
tienen voz y en qué orden hay que tocarlas. Esta página lleva esa idea al
navegador: se pueden probar las teclas, escuchar sus sonidos y consultar el
poema desde el botón de pistas.

No es una reproducción oficial ni incluye el juego original: es un proyecto
de fans inspirado en uno de sus acertijos más recordados.

## Cómo jugar

1. Abrí la página en un navegador en https://luzrubini.github.io/sh-puzzle/ (si lo queres descargar local vas a necesitar un .bat y no directo desde el index o el envio del mail no va a funcionar)
2. Tocá las teclas y prestá atención a cuáles suenan y cuáles permanecen
   silenciosas.
3. Si necesitás una pista, usá Leer las pistas para mostrar el poema.
4. Encontrá la secuencia correcta para resolver el acertijo y desbloquear la
   recompensa.
5. Si querés registrar el resultado, ingresá tu nombre en el formulario que
   aparece al resolverlo.

> Aviso de spoiler: el orden correcto se verifica dentro del código fuente
> de `index.html`.

## Sonido y registro del resultado

- `piano_sound.ogg` se reproduce durante un segundo al tocar una tecla con
  sonido.
- Las teclas silenciosas generan un breve sonido de estática.
- Al completar el acertijo, `tears_of.mp3` se reproduce como recompensa.
- El formulario envía el nombre a través de FormSubmit, sin salir de la página.
  La primera vez, FormSubmit puede solicitar que se confirme la dirección de
  correo configurada en `index.html`.

El registro depende de una conexión a Internet y del servicio externo
FormSubmit. La página no tiene un servidor propio ni almacena los nombres.

## Ejecutarlo en tu computadora

No abras `index.html` directamente como archivo (`file://`): algunos
navegadores restringen desde ahí la carga del audio y el envío del formulario.

### Windows

Hacé doble clic en [`iniciar_juego.bat`](./iniciar_juego.bat). El archivo inicia
un servidor local y abre el sitio en el navegador. Necesitás tener Python
instalado.

### Cualquier sistema con Python

Desde la carpeta del proyecto, ejecutá:

```bash
python -m http.server 8000
```

Después abrí <http://localhost:8000>.

## Publicarlo con GitHub Pages

1. Subí `index.html`, `piano_sound.ogg` y `tears_of.mp3` a la raíz de un
   repositorio de GitHub.
2. En el repositorio, entrá a **Settings → Pages**.
3. En **Build and deployment**, elegí **Deploy from a branch**, seleccioná
   `main` y la carpeta `/(root)`, y guardá.
4. Cuando GitHub termine la publicación, abrí la URL que aparece en esa misma
   sección de Pages.

GitHub Pages sirve el sitio por HTTPS; no hace falta usar el archivo `.bat`
cuando se visita la versión publicada. No subas `.venv` al repositorio: no es
necesario para este sitio estático.

## Archivos principales

| Archivo | Para qué sirve |
| --- | --- |
| `index.html` | Interfaz, poema, lógica del acertijo y formulario |
| `piano_sound.ogg` | Sonido de las teclas con voz |
| `tears_of.mp3` | Audio de recompensa |
| `iniciar_juego.bat` | Servidor local sencillo para Windows |

## Créditos y contexto

**Silent Hill** es una obra de Konami y Team Silent. Este proyecto es un
homenaje hecho por fans y no está afiliado ni respaldado por sus titulares.
Los nombres de la saga y del juego pertenecen a sus respectivos propietarios.
