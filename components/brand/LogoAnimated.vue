<template>
  <div>
    <svg class="rotate outer" width="100%" height="100%" viewBox="0 0 590 591" xmlns="http://www.w3.org/2000/svg"
      xml:space="preserve" style="fill-rule: evenodd; clip-rule: evenodd; stroke-linejoin: round; stroke-miterlimit: 2">
      <sodipodi:namedview id="namedview30035" pagecolor="#ffffff" bordercolor="#999999" borderopacity="1"
        inkscape:pageshadow="0" inkscape:pageopacity="0" inkscape:pagecheckerboard="0" inkscape:document-units="mm"
        showgrid="true" inkscape:zoom="0.13134003" inkscape:cx="898.43135" inkscape:cy="689.05116"
        inkscape:window-width="1920" inkscape:window-height="1001" inkscape:window-x="-9" inkscape:window-y="-9"
        inkscape:window-maximized="1" inkscape:current-layer="layer1" inkscape:snap-bbox="true" inkscape:bbox-paths="true"
        inkscape:bbox-nodes="true" inkscape:snap-bbox-edge-midpoints="true" inkscape:snap-bbox-midpoints="true">
        <inkscape:grid type="xygrid" id="grid822" units="mm" spacingx="0.99999997" spacingy="0.99999997" />
      </sodipodi:namedview>
      <defs id="defs30030" />
      <g inkscape:label="Layer 1" inkscape:groupmode="layer" id="layer1">
        <path id="rect10006-4-4-0-6"
          style="font-variation-settings:normal;vector-effect:none;fill-opacity:1;fill-rule:evenodd;stroke:#000080;stroke-width:0;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;-inkscape-stroke:none;stop-color:#000000;fill:var(--color-brand)"
          d="M 85.332006,2.0967973e-7 A 85.333233,85.333383 0 0 0 2.0967973e-7,85.332006 V 426.66666 A 85.333233,85.333383 0 0 0 85.332006,511.99998 H 426.66798 a 85.333233,85.333383 0 0 0 85.332,-85.33332 V 85.332006 A 85.333233,85.333383 0 0 0 426.66798,2.0967973e-7 Z M 85.333362,85.334655 256.00002,256.00131 h 85.3333 V 85.334655 h 85.33334 V 426.66798 L 256,256.00131 H 170.66666 V 426.66798 H 85.333336 Z" />
      </g>
    </svg>
  </div>
</template>

<style lang="scss" scoped>
div {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 5rem;
  margin-top: 1rem;

  svg {
    width: 5rem;
    height: 5rem;
    position: absolute;

    @keyframes rotateAndBob {
      0% {
        transform: scale(1.0);
      }

      10% {
        transform: scale(1.2);
      }

      20% {
        transform: scale(1);
      }

      30% {
        transform: scale(1.2);
      }

      40% {
        transform: scale(1);
      }

      50% {
        transform: scale(1.2);
      }

      60% {
        transform: scale(1.0);
      }

      70% {
        transform: scale(1.2);
      }

      80% {
        transform: scale(1);
      }

      90% {
        transform: scale(1.2);
      }

      100% {
        transform: scale(1.0);
      }
    }

    &.rotate {
      //animation: rotate 1s infinite linear;
      animation: rotateAndBob 4s ease-in-out infinite;

      &.inner {
        animation: rotate 6s infinite linear reverse;
      }
    }

    @keyframes rotate {
      0% {
        transform: rotate(0);
      }

      100% {
        transform: rotate(360deg);
      }
    }
  }
}
</style>
