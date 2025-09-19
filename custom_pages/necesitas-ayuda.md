---
title: ¿Necesitas ayuda?
fullscreen: false
hidden: false
---
<HTMLBlock>{`
<!-- Tipificación de consultas – Estilo ProntoPaga (centro #FF1F55, ramas blancas) -->
<svg viewBox="-700 -380 1400 760" width="100%" xmlns="http://www.w3.org/2000/svg" role="img" aria-labelledby="title desc">
  <title id="title">Tipificación de consultas</title>
  <desc id="desc">Diagrama radial con centro #FF1F55 y ramas blancas con borde #FF1F55.</desc>

  <defs>
    <style type="text/css"><![CDATA[
      .center-box { fill:#FF1F55; stroke:#FF1F55; stroke-width:2; rx:16; ry:16; }
      .leaf-box   { fill:#FFFFFF; stroke:#FF1F55; stroke-width:2; rx:14; ry:14; }
      .edge       { stroke:#FF1F55; stroke-width:3; }
      .label      { font: 18px/1.35 -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial; fill:#0F2A5A; dominant-baseline: middle; text-anchor: middle; }
      .center-text{ fill:#FFFFFF; font-weight:700; font-size:22px; }
      .shadow { filter:url(#s); }
    ]]></style>

    <!-- Sombra sutil -->
    <filter id="s" x="-20%" y="-20%" width="140%" height="140%">
      <feDropShadow dx="0" dy="2" stdDeviation="3" flood-color="#0b1220" flood-opacity="0.12"/>
    </filter>
  </defs>

  <!-- Centro (subido un poco) -->
  <rect class="center-box shadow" x="-240" y="-75" width="480" height="110"/>
  <text class="label center-text" x="0" y="-20">Tipificación de consultas</text>

  <!-- Líneas izquierda -->
  <g class="edge">
    <line x1="-240" y1="-48" x2="-520" y2="-300"/>
    <line x1="-240" y1="-42" x2="-520" y2="-240"/>
    <line x1="-240" y1="-36" x2="-520" y2="-180"/>
    <line x1="-240" y1="-30" x2="-520" y2="-120"/>
    <line x1="-240" y1="-24" x2="-520" y2="-60"/>
    <line x1="-240" y1="-18" x2="-520" y2="0"/>
    <line x1="-240" y1="-12" x2="-520" y2="60"/>
    <line x1="-240" y1="-6"  x2="-520" y2="120"/>
  </g>

  <!-- Líneas derecha -->
  <g class="edge">
    <line x1="240" y1="-48" x2="520" y2="-300"/>
    <line x1="240" y1="-42" x2="520" y2="-240"/>
    <line x1="240" y1="-36" x2="520" y2="-180"/>
    <line x1="240" y1="-30" x2="520" y2="-120"/>
    <line x1="240" y1="-24" x2="520" y2="-60"/>
    <line x1="240" y1="-18" x2="520" y2="0"/>
    <line x1="240" y1="-12" x2="520" y2="60"/>
    <line x1="240" y1="-6"  x2="520" y2="120"/>
  </g>

  <!-- Nodos izquierda -->
  <g>
    <rect class="leaf-box shadow" x="-640" y="-322" width="240" height="44"/><text class="label" x="-520" y="-300">Webinars</text>
    <rect class="leaf-box shadow" x="-640" y="-262" width="240" height="44"/><text class="label" x="-520" y="-240">Consultas generales</text>
    <rect class="leaf-box shadow" x="-640" y="-202" width="240" height="44"/><text class="label" x="-520" y="-180">Abonos</text>
    <rect class="leaf-box shadow" x="-640" y="-142" width="240" height="44"/><text class="label" x="-520" y="-120">Felicitaciones</text>
    <rect class="leaf-box shadow" x="-640" y="-82"  width="240" height="44"/><text class="label" x="-520" y="-60">Balance de comercio</text>
    <rect class="leaf-box shadow" x="-640" y="-22"  width="240" height="44"/><text class="label" x="-520" y="0">Portal de servicios</text>
    <rect class="leaf-box shadow" x="-640" y="38"   width="240" height="44"/><text class="label" x="-520" y="60">PayOut</text>
    <rect class="leaf-box shadow" x="-640" y="98"   width="240" height="44"/><text class="label" x="-520" y="120">Incidencias técnicas</text>
  </g>

  <!-- Nodos derecha -->
  <g>
    <rect class="leaf-box shadow" x="400" y="-322" width="240" height="44"/><text class="label" x="520" y="-300">Liquidación</text>
    <rect class="leaf-box shadow" x="400" y="-262" width="240" height="44"/><text class="label" x="520" y="-240">Mantención</text>
    <rect class="leaf-box shadow" x="400" y="-202" width="240" height="44"/><text class="label" x="520" y="-180">Mejoras</text>
    <rect class="leaf-box shadow" x="400" y="-142" width="240" height="44"/><text class="label" x="520" y="-120">Métodos de pago</text>
    <rect class="leaf-box shadow" x="400" y="-82"  width="240" height="44"/><text class="label" x="520" y="-60">Pay4U</text>
    <rect class="leaf-box shadow" x="400" y="-22"  width="240" height="44"/><text class="label" x="520" y="0">PayIn</text>
    <rect class="leaf-box shadow" x="400" y="38"   width="240" height="44"/><text class="label" x="520" y="60">Success Rate</text>
    <rect class="leaf-box shadow" x="400" y="98"   width="240" height="44"/><text class="label" x="520" y="120">Sugerencias</text>
  </g>
</svg>
`}</HTMLBlock>

<br />

```html
<div style="position: relative; width: 100%; height: 0; padding-top: 100.0000%;
 padding-bottom: 0; box-shadow: 0 2px 8px 0 rgba(63,69,81,0.16); margin-top: 1.6em; margin-bottom: 0.9em; overflow: hidden;
 border-radius: 8px; will-change: transform;">
  <iframe loading="lazy" style="position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; padding: 0;margin: 0;"
    src="https://www.canva.com/design/DAGzcE0BDLY/K3rG6WZU5x1GyCciyeSHfQ/view?embed" allowfullscreen="allowfullscreen" allow="fullscreen">
  </iframe>
</div>
<a href="https:&#x2F;&#x2F;www.canva.com&#x2F;design&#x2F;DAGzcE0BDLY&#x2F;K3rG6WZU5x1GyCciyeSHfQ&#x2F;view?utm_content=DAGzcE0BDLY&amp;utm_campaign=designshare&amp;utm_medium=embeds&amp;utm_source=link" target="_blank" rel="noopener">Sitemap Whiteboard in Green Purple Basic Style</a> by tahbitareategui
```

<br />
