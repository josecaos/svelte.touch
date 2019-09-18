<script>
import interact from 'interactjs'
import './DragDrop.css'
//
let width = window.innerWidth
let height = window.innerHeight
const itemDrag = '.dragall'

const Drag = () => {
  interact(itemDrag).draggable({
    inertia: true,
    cursorChecker: (action, interatable, element, interacting) => {
      switch (action.axis) {
        case 'x': return 'ew-resize'
        case 'y': return 'ns-resize'
        default: return interacting ? 'grabbing' : 'grab'
      }
    },
    modifiers: [
      interact.modifiers.restrictRect({
        restriction: 'body',
        endOnly: true
      })
    ],
    // autoScroll: true,
    onmove: dragMoveListener,
    onend: (e) => {
      console.log('Fin')
    }

  })
}

const dragMoveListener = (event) => {

  let target = event.target
  console.log("Moviendo: ")
  // aplica los valores en los atributos data-
  var x = (parseFloat(target.getAttribute('data-x')) || 0) + event.dx
  var y = (parseFloat(target.getAttribute('data-y')) || 0) + event.dy
  // translate the element
  target.style.webkitTransform =
  target.style.transform =
  'translate(' + x + 'px, ' + y + 'px)'

  // update the position attributes
  target.setAttribute('data-x', x)
  target.setAttribute('data-y', y)
}

const Drop = (interactObj, acceptObj) => {
  // DEBUG: refactorizar
  // const obj = document.querySelector(acceptObj)
  // const contObj = document.querySelector(interactObj)
  // const pathObj = document.querySelector(acceptObj).querySelector('path')
  //
  // pathObj.style.fill = colorObj
  //
  // //
  // const info = document.querySelector('.info')
  // //
  // interact(interactObj).dropzone({
  //   accept: acceptObj,
  //   // Requiere el 15% del elemento para ejercer el 'drop'
  //   overlap: 0.15,
  //   // Eventos relacionados al 'drop':
  //   ondropactivate: (event) => {
  //     event.target.querySelector('path').style.fill = colorAreaActive
  //     event.relatedTarget.querySelector('path').style.fill = colorAreaActive
  //     info.innerHTML = "DEBUG: ondropactive"
  //   },
  //   //al entrar en zona de 'drop'
  //   ondragenter: (event) => {
  //     event.target.querySelector('path').style.fill = colorObjDropped
  //     info.innerHTML = "DEBUG: ondragenter"
  //   },
  //   //al soltarlo dentro de la zona de 'drop'
  //   ondrop: (event) => {
  //     let dropzone = event.target.getBoundingClientRect()
  //     // // snap
  //     obj.style.webkitTransform =
  //     obj.style.transform =
  //     'translate(' + dropzone.x + 'px, ' + dropzone.y    + 'px)'
  //     //
  //     obj.setAttribute('data-x', dropzone.x)
  //     obj.setAttribute('data-y', dropzone.y)
  //
  //     info.innerHTML = "DEBUG: ondrop"
  //   },
  //   //Al salir del 'dropzone'
  //   ondragleave: (event) => {
  //     event.target.querySelector('path').style.fill = colorAreaActive
  //     info.innerHTML = "DEBUG: ondragleave"
  //   },
  //   // Al dejar fuera de la zona de 'drop'
  //   ondropdeactivate: (event) => {
  //     event.target.querySelector('path').style.fill = colorArea
  //     event.relatedTarget.querySelector('path').style.fill = colorObj
  //     info.innerHTML = "DEBUG: ondropdeactivate"
  //   }
  // })
  //
  // }
  console.log("Dropn'")
}
//llamadas
Drag()
// Drop()
</script>
<!--  -->
<section>

<div id="contenedores">
<svg id="svg-contenedor" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
preserveAspectRatio="xMidYMid meet"
viewBox="178.6385542168675 77.43373493975895 357.0120481927711 357.01204819277126" width="353.01" height="353.01">
<!-- circulo drop -->
<path
d="M532.65 254.94C532.65 352.36 453.56 431.45 356.14 431.45C258.73 431.45 179.64 352.36 179.64 254.94C179.64 157.52 258.73 78.43 356.14 78.43C453.56 78.43 532.65 157.52 532.65 254.94Z"
id="circulo-area"
class="drop-1 dropall"
opacity="1"
fill="#651e48"
></path>
<path d="M112.17 79.64L495.3 79.64L495.3 459.16L112.17 459.16L112.17 79.64Z"
id="cuadrado-area"
class="drop-2 dropall"
opacity="1"
fill="#1d5299"
></path>

<svg id="svg-irregular-area" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
preserveAspectRatio="xMidYMid meet"
viewBox="206.34939759036146 65.38554216867462 270.26506024096386 293.15662650602405" width="266.27" height="289.16">
<defs>
<path d="M473.61 66.39L437.47 172.41L433.86 219.4L324.22 239.88L403.73 272.41L349.52 285.66L339.88 342.29L282.05 304.94L274.82 355.54L236.27 300.12L207.35 219.4L232.65 133.86L473.61 66.39Z"
id="irregular-area"
class="drop-3 dropall"
opacity="1"
fill="#b06508"
></path>



<svg id="svg-triangulo-area"  version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
preserveAspectRatio="xMidYMid meet"
viewBox="179.84337349397592 85.86746987951798 249.78313253012053 294.3614457831326" width="245.78" height="290.36">
<defs>
<path width="200" height="200" d="M426.63 374.82L180.84 377.23L300.12 86.87L426.63 374.82Z"
id="triangulo-area"
class="drop-4 dropall"
opacity="1"
fill="#469216"
></path>
</div>

<!--  -->
<!-- draggables -->
<div id="zonas_linguisticas">

<svg id="svg-contenedor" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
preserveAspectRatio="xMidYMid meet"
viewBox={`0 0 ${width} ${height}`}
width={`${width}px`}
height={`${height}px`}
>
<!-- circulo -->
<path
d="M532.65 254.94C532.65 352.36 453.56 431.45 356.14 431.45C258.73 431.45 179.64 352.36 179.64 254.94C179.64 157.52 258.73 78.43 356.14 78.43C453.56 78.43 532.65 157.52 532.65 254.94Z"
id="circulo-drag"
class="dragall"
opacity="1"
fill= "#1c5a35"
></path>
<!-- cuadrado -->
<path d="M112.17 79.64L495.3 79.64L495.3 459.16L112.17 459.16L112.17 79.64Z"
id="cuadrado-drag"
class="dragall"
opacity="1"
fill="#1d5299"
></path>
<!-- irregular -->
<path d="M473.61 66.39L437.47 172.41L433.86 219.4L324.22 239.88L403.73 272.41L349.52 285.66L339.88 342.29L282.05 304.94L274.82 355.54L236.27 300.12L207.35 219.4L232.65 133.86L473.61 66.39Z"
id="irregular-drag"
class="dragall"
opacity="1"
fill="#b06508"
></path>
<!-- triangulo -->
<path d="M426.63 374.82L180.84 377.23L300.12 86.87L426.63 374.82Z"
id="triangulo-drag"
class="dragall"
opacity="1"
fill="#469216"
></path>
</svg>

</div>

</section>
