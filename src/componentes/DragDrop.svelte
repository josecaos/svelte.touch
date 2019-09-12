<script>
  import interact from 'interactjs'
  import './DragDrop.css'
  //
  console.log("Start Scripts: ")
  const Drag = () => {
    interact('.dragall').draggable({
      inertia: true,
      modifiers: [
        interact.modifiers.restrictRect({
          restriction: 'body',
          endOnly: true
        })
      ],
      // autoScroll: true,
      onmove: dragMoveListener,
      onend: (e) => {
        console.log('drag')
      }

    })
  }
const dragMoveListener = (event) => {

    let target = event.target//svg

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
  //
  Drag()
</script>
<!--  -->
<section>
  <h2 class="info"></h2>
  <!--
  <div class="contenedores">

    <svg id="svg-circulo-area" class="drop-1 dropall" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
    preserveAspectRatio="xMidYMid meet"
    viewBox="178.6385542168675 77.43373493975895 357.0120481927711 357.01204819277126" width="353.01" height="353.01">
    <defs>
      <path
      d="M532.65 254.94C532.65 352.36 453.56 431.45 356.14 431.45C258.73 431.45 179.64 352.36 179.64 254.94C179.64 157.52 258.73 78.43 356.14 78.43C453.56 78.43 532.65 157.52 532.65 254.94Z"
      id="circulo-area"></path>
    </defs>
    <g>
      <g>
        <use xlink:href="#circulo-area" opacity="1" fill="#651e48" fill-opacity="1"></use>
      </g>
    </g>
  </svg>

  <svg id="svg-cuadrado-area" class="drop-2 dropall" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
  preserveAspectRatio="xMidYMid meet"
  viewBox="111.1686746987952 78.63855421686739 387.13253012048193 383.51807228915663" >
  <defs>
    <path d="M112.17 79.64L495.3 79.64L495.3 459.16L112.17 459.16L112.17 79.64Z" id="cuadrado-area"></path>
  </defs>
  <g>
    <g>
      <use xlink:href="#cuadrado-area" opacity="1" fill="#1d5299" fill-opacity="1"></use>
      <g>
        <use xlink:href="#cuadrado-area" opacity="1" fill-opacity="0" stroke="#6c40d2" stroke-width="0"
        stroke-opacity="1"></use>
      </g>
    </g>
  </g>
</svg>
<svg id="svg-irregular-area" class="drop-3 dropall" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
preserveAspectRatio="xMidYMid meet"
viewBox="206.34939759036146 65.38554216867462 270.26506024096386 293.15662650602405" width="266.27" height="289.16">
<defs>
  <path d="M473.61 66.39L437.47 172.41L433.86 219.4L324.22 239.88L403.73 272.41L349.52 285.66L339.88 342.29L282.05 304.94L274.82 355.54L236.27 300.12L207.35 219.4L232.65 133.86L473.61 66.39Z" id="irregular-area"></path>
</defs>
<g>
  <g>
    <use xlink:href="#irregular-area" opacity="1" fill="#b06508" fill-opacity="1"></use>
    <g>
      <use xlink:href="#irregular-area" opacity="1" fill-opacity="0" stroke="#000000" stroke-width="0"
      stroke-opacity="1"></use>
    </g>
  </g>
</g>
</svg>


<svg id="svg-triangulo-area" class="drop-4 dropall" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
preserveAspectRatio="xMidYMid meet"
viewBox="179.84337349397592 85.86746987951798 249.78313253012053 294.3614457831326" width="245.78" height="290.36">
<defs>
  <path width="200" height="200" d="M426.63 374.82L180.84 377.23L300.12 86.87L426.63 374.82Z" id="triangulo-area"></path>
</defs>
<g>
  <g>
    <use xlink:href="#triangulo-area" opacity="1" fill="#469216" fill-opacity="1"></use>
    <g>
      <use xlink:href="#triangulo-area" opacity="1" fill-opacity="0" stroke="#000000" stroke-width="0" stroke-opacity="1"></use>
    </g>
  </g>
</g>
</svg>

</div>

-->
<!--  -->
<!-- draggables -->
<div id="zonas_linguisticas">
  <!-- circulo -->
  <svg id="svg-circulo-drag" class="dragall" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
  preserveAspectRatio="xMidYMid meet"
  viewBox="178.6385542168675 77.43373493975895 357.0120481927711 357.01204819277126" width="353.01" height="353.01">
  <defs>
    <path
    d="M532.65 254.94C532.65 352.36 453.56 431.45 356.14 431.45C258.73 431.45 179.64 352.36 179.64 254.94C179.64 157.52 258.73 78.43 356.14 78.43C453.56 78.43 532.65 157.52 532.65 254.94Z"
    id="circulo-drag"></path>
  </defs>
  <g>
    <g>
      <use xlink:href="#circulo-drag" opacity="1" width="150" height="150" fill-opacity="1"></use>
    </g>
  </g>
</svg>

<!-- cuadrado -->
<svg id="svg-cuadrado-drag" class="dragall" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
preserveAspectRatio="xMidYMid meet"
viewBox="111.1686746987952 78.63855421686739 387.13253012048193 383.51807228915663" width="383.13" height="379.52">
<defs>
  <path d="M112.17 79.64L495.3 79.64L495.3 459.16L112.17 459.16L112.17 79.64Z" id="cuadrado-drag"></path>
</defs>
<g>
  <g>
    <use xlink:href="#cuadrado-drag" opacity="1" fill="#1d5299" fill-opacity="1"></use>
    <g>
      <use xlink:href="#cuadrado-drag" opacity="1" fill-opacity="0" stroke="#6c40d2" stroke-width="0"
      stroke-opacity="1"></use>
    </g>
  </g>
</g>
</svg>
<!-- irregular -->
<svg id="svg-irregular-drag" class="dragall" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
preserveAspectRatio="xMidYMid meet"
viewBox="206.34939759036146 65.38554216867462 270.26506024096386 293.15662650602405" width="266.27" height="289.16">
<defs>
  <path d="M473.61 66.39L437.47 172.41L433.86 219.4L324.22 239.88L403.73 272.41L349.52 285.66L339.88 342.29L282.05 304.94L274.82 355.54L236.27 300.12L207.35 219.4L232.65 133.86L473.61 66.39Z" id="irregular-drag"></path>
</defs>
<g>
  <g>
    <use xlink:href="#irregular-drag" opacity="1" fill="#b06508" fill-opacity="1"></use>
    <g>
      <use xlink:href="#irregular-drag" opacity="1" fill-opacity="0" stroke="#000000" stroke-width="0"
      stroke-opacity="1"></use>
    </g>
  </g>
</g>
</svg>

<!-- triangulo -->

<svg id="svg-triangulo-drag" class="dragall" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
preserveAspectRatio="xMidYMid meet"
viewBox="179.84337349397592 85.86746987951798 249.78313253012053 294.3614457831326" width="245.78" height="290.36">
<defs>
  <path d="M426.63 374.82L180.84 377.23L300.12 86.87L426.63 374.82Z" id="triangulo-drag"></path>
</defs>
<g>
  <g>
    <use xlink:href="#triangulo-drag" opacity="1" fill="#469216" fill-opacity="1"></use>
    <g>
      <use xlink:href="#triangulo-drag" opacity="1" fill-opacity="0" stroke="#000000" stroke-width="0" stroke-opacity="1"></use>
    </g>
  </g>
</g>
</svg>

</div>

</section>
