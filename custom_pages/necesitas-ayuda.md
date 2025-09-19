---
title: '¿Necesitas ayuda? '
fullscreen: false
hidden: false
---
<br />

<br />

<br />

<HTMLBlock>{`
<!-- Tipificación de consultas – SVG pastel/neutral -->
<svg viewBox="-640 -360 1280 720" width="100%" xmlns="http://www.w3.org/2000/svg" role="img" aria-labelledby="title desc">
  <title id="title">Tipificación de consultas</title>
  <desc id="desc">Diagrama radial con un nodo central y 16 categorías alrededor, colores pastel.</desc>

  <defs>
    <style type="text/css"><![CDATA[
      :root { color-scheme: light dark; }
      .node { stroke: #A8ADB5; stroke-width: 1.6; rx: 14; ry: 14; }
      .edge { stroke: #C9CDD3; stroke-width: 2; }
      .label { fill: #334155; font: 15px/1.3 -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial; dominant-baseline: middle; text-anchor: middle; }
      .center-label { font-weight: 700; font-size: 18px; }
      /* Paleta pastel/neutra */
      .p1 { fill:#E8F1FF; }  /* azul muy claro */
      .p2 { fill:#E8FFF4; }  /* verde menta claro */
      .p3 { fill:#FFF6E5; }  /* crema */
      .p4 { fill:#F4E9FF; }  /* lila claro */
      .p5 { fill:#FDEEEE; }  /* rosa pálido */
      .p6 { fill:#EDF2F7; }  /* gris azulado suave */
      .p7 { fill:#FFF0F6; }  /* rosado chalk */
      .p8 { fill:#EEFCEF; }  /* verde pastel */
      .shadow { filter:url(#s); }
    ]]></style>

    <!-- Sombra muy sutil -->
    <filter id="s" x="-20%" y="-20%" width="140%" height="140%">
      <feDropShadow dx="0" dy="1" stdDeviation="2" flood-color="#000000" flood-opacity="0.06"/>
    </filter>
  </defs>

  <!-- Centro -->
  <rect class="node p6 shadow" x="-190" y="-38" width="380" height="76" />
  <text class="label center-label" x="0" y="0">Tipificación de consultas</text>

  <!-- Líneas izquierda -->
  <!-- y targets: -220,-160,-100,-40,20,80,140,200 -->
  <g class="edge">
    <line x1="-190" y1="-18" x2="-390" y2="-220"/>
    <line x1="-190" y1="-12" x2="-390" y2="-160"/>
    <line x1="-190" y1="-6"  x2="-390" y2="-100"/>
    <line x1="-190" y1="0"   x2="-390" y2="-40"/>
    <line x1="-190" y1="6"   x2="-390" y2="20"/>
    <line x1="-190" y1="12"  x2="-390" y2="80"/>
    <line x1="-190" y1="18"  x2="-390" y2="140"/>
    <line x1="-190" y1="24"  x2="-390" y2="200"/>
  </g>

  <!-- Líneas derecha -->
  <g class="edge">
    <line x1="190" y1="-18" x2="390" y2="-220"/>
    <line x1="190" y1="-12" x2="390" y2="-160"/>
    <line x1="190" y1="-6"  x2="390" y2="-100"/>
    <line x1="190" y1="0"   x2="390" y2="-40"/>
    <line x1="190" y1="6"   x2="390" y2="20"/>
    <line x1="190" y1="12"  x2="390" y2="80"/>
    <line x1="190" y1="18"  x2="390" y2="140"/>
    <line x1="190" y1="24"  x2="390" y2="200"/>
  </g>

  <!-- Nodos izquierda -->
  <g>
    <rect class="node p1 shadow" x="-500" y="-242" width="220" height="44"/><text class="label" x="-390" y="-220">Webinars</text>
    <rect class="node p2 shadow" x="-500" y="-182" width="220" height="44"/><text class="label" x="-390" y="-160">Consultas generales</text>
    <rect class="node p3 shadow" x="-500" y="-122" width="220" height="44"/><text class="label" x="-390" y="-100">Abonos</text>
    <rect class="node p4 shadow" x="-500" y="-62"  width="220" height="44"/><text class="label" x="-390" y="-40">Felicitaciones</text>
    <rect class="node p5 shadow" x="-500" y="-2"   width="220" height="44"/><text class="label" x="-390" y="20">Balance de comercio</text>
    <rect class="node p8 shadow" x="-500" y="58"   width="220" height="44"/><text class="label" x="-390" y="80">Portal de servicios</text>
    <rect class="node p7 shadow" x="-500" y="118"  width="220" height="44"/><text class="label" x="-390" y="140">PayOut</text>
    <rect class="node p1 shadow" x="-500" y="178"  width="220" height="44"/><text class="label" x="-390" y="200">Incidencias técnicas</text>
  </g>

  <!-- Nodos derecha -->
  <g>
    <rect class="node p2 shadow" x="280" y="-242" width="220" height="44"/><text class="label" x="390" y="-220">Liquidación</text>
    <rect class="node p3 shadow" x="280" y="-182" width="220" height="44"/><text class="label" x="390" y="-160">Mantención</text>
    <rect class="node p4 shadow" x="280" y="-122" width="220" height="44"/><text class="label" x="390" y="-100">Mejoras</text>
    <rect class="node p5 shadow" x="280" y="-62"  width="220" height="44"/><text class="label" x="390" y="-40">Métodos de pago</text>
    <rect class="node p8 shadow" x="280" y="-2"   width="220" height="44"/><text class="label" x="390" y="20">Pay4U</text>
    <rect class="node p7 shadow" x="280" y="58"   width="220" height="44"/><text class="label" x="390" y="80">PayIn</text>
    <rect class="node p1 shadow" x="280" y="118"  width="220" height="44"/><text class="label" x="390" y="140">Success Rate</text>
    <rect class="node p2 shadow" x="280" y="178"  width="220" height="44"/><text class="label" x="390" y="200">Sugerencias</text>
  </g>
</svg>
`}</HTMLBlock>

<br />
