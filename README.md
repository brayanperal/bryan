<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Construction Takeoff Sheet v2</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=IBM+Plex+Mono:wght@400;500;600&family=IBM+Plex+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
:root {
  --bg:#f7f4ef; --ink:#1a1a1a; --rule:#c4b89a; --light-rule:#e2d9c8;
  --accent:#d4401a; --accent2:#1a5fd4; --muted:#8a7d6b;
  --row-alt:#ede9e1; --green:#1a6b3c; --gold:#b8860b;
}
*{margin:0;padding:0;box-sizing:border-box;}
body{font-family:'IBM Plex Mono',monospace;background:var(--bg);color:var(--ink);font-size:13px;}

@media screen {
/* CONFIG PANEL */
.config-panel{
  background:var(--ink);color:white;
  padding:14px 20px;display:flex;flex-wrap:wrap;gap:16px;align-items:flex-end;
}
.cp-group{display:flex;flex-direction:column;gap:4px;min-width:130px;}
.cp-label{font-size:8px;text-transform:uppercase;letter-spacing:2px;color:#888;}
.cp-group select{
  font-family:'IBM Plex Mono',monospace;font-size:13px;font-weight:600;
  background:#2a2a2a;border:1.5px solid #444;color:white;
  padding:6px 10px;outline:none;cursor:pointer;
}
.cp-group select:focus{border-color:var(--accent);}
.cp-group select option{background:#1a1a1a;}
.cp-divider{width:1px;background:#333;align-self:stretch;margin:0 4px;}
.cp-hint{font-size:9px;color:#555;line-height:1.7;align-self:center;border-left:1px solid #333;padding-left:14px;}
.cp-hint span{color:#4ade80;}

/* PAGE */
.page{max-width:980px;margin:0 auto;padding:22px 20px 110px;}
.doc-header{
  display:grid;grid-template-columns:1fr auto;align-items:end;gap:20px;
  border-bottom:3px solid var(--ink);padding-bottom:14px;margin-bottom:20px;
}
.doc-title{font-family:'Bebas Neue',cursive;font-size:52px;line-height:.9;letter-spacing:2px;}
.doc-title em{color:var(--accent);font-style:normal;}
.doc-meta{display:flex;flex-direction:column;gap:5px;align-items:flex-end;}
.meta-field{display:flex;flex-direction:column;align-items:flex-end;gap:2px;}
.meta-label{font-size:8px;text-transform:uppercase;letter-spacing:2px;color:var(--muted);}
.meta-input{
  font-family:'IBM Plex Mono',monospace;font-size:12px;border:none;
  border-bottom:1px solid var(--rule);background:transparent;
  text-align:right;width:200px;padding:2px 4px;color:var(--ink);outline:none;
}
.meta-input:focus{border-bottom-color:var(--accent);}

/* TOOLBAR */
.toolbar{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:18px;align-items:center;}
.btn{
  font-family:'IBM Plex Mono',monospace;font-size:10px;font-weight:600;
  text-transform:uppercase;letter-spacing:1.5px;padding:7px 14px;
  border:1.5px solid var(--ink);background:transparent;cursor:pointer;
  transition:all .12s;white-space:nowrap;
}
.btn:hover{background:var(--ink);color:var(--bg);}
.btn-blue{background:var(--accent2);border-color:var(--accent2);color:white;}
.btn-blue:hover{background:#1448a8;}
.btn-green{background:var(--green);border-color:var(--green);color:white;}
.btn-green:hover{background:#135430;}
.btn-red{background:var(--accent);border-color:var(--accent);color:white;}
.btn-red:hover{background:#b3350f;}
.t-sep{width:1px;height:28px;background:var(--rule);margin:0 4px;}

/* SECTION */
.section{margin-bottom:18px;border:1.5px solid var(--ink);}
.sec-head{
  background:#1a1a1a;color:white;display:flex;align-items:center;
  justify-content:space-between;padding:9px 14px;gap:12px;
}
.sec-icon{font-size:16px;margin-right:8px;}
.sec-name-wrap{display:flex;align-items:center;flex:1;}
.sec-name{
  font-family:'Bebas Neue',cursive;font-size:18px;letter-spacing:2px;
  background:transparent;border:none;color:white;width:100%;outline:none;
}
.sec-name:focus{border-bottom:1px solid var(--accent);}
.sec-acts{display:flex;gap:6px;}
.secbtn{
  font-size:9px;font-family:'IBM Plex Mono',monospace;font-weight:600;
  text-transform:uppercase;letter-spacing:1px;padding:3px 8px;
  border:1px solid #555;background:transparent;color:#aaa;cursor:pointer;transition:all .12s;
}
.secbtn:hover{border-color:white;color:white;}
.secbtn.d:hover{border-color:var(--accent);color:var(--accent);}

.sec-body.collapsed{display:none;}
table{width:100%;border-collapse:collapse;}
thead th{
  background:#2e2e2e;color:#bbb;font-size:8px;text-transform:uppercase;
  letter-spacing:2px;padding:6px 10px;text-align:left;font-weight:500;border-bottom:1px solid #444;
}
thead th.c{text-align:center;}
tbody tr{border-bottom:1px solid var(--light-rule);}
tbody tr:nth-child(even){background:var(--row-alt);}
tbody tr:hover{background:#ddd6c8;}
td{padding:5px 10px;vertical-align:middle;}
td.c{text-align:center;}

.iname{
  font-family:'IBM Plex Sans',sans-serif;font-size:12px;border:none;
  background:transparent;width:100%;color:var(--ink);outline:none;padding:2px 0;
}
.iname:focus{border-bottom:1px solid var(--accent2);}

.type-sel{
  font-family:'IBM Plex Mono',monospace;font-size:11px;
  border:1px solid var(--rule);background:white;
  padding:3px 5px;outline:none;color:var(--ink);width:100%;cursor:pointer;
}
.type-sel:focus{border-color:var(--accent2);}
.type-sel.blank{background:transparent;border:none;border-bottom:1px dashed var(--light-rule);color:var(--muted);}

.qty{
  width:54px;font-family:'IBM Plex Mono',monospace;font-size:14px;font-weight:700;
  text-align:center;border:1.5px solid var(--rule);background:white;
  padding:4px 5px;outline:none;color:var(--ink);
}
.qty:focus{border-color:var(--accent2);background:#f0f4ff;}
.qty.auto{background:#e6f7ec;border-color:var(--green);color:var(--green);}

.uunit{
  width:50px;font-family:'IBM Plex Mono',monospace;font-size:11px;text-align:center;
  border:none;border-bottom:1px dashed var(--rule);background:transparent;
  padding:2px 3px;color:var(--muted);outline:none;
}
.uunit:focus{border-bottom-color:var(--accent);color:var(--ink);}

.nnotes{
  font-family:'IBM Plex Sans',sans-serif;font-size:11px;border:none;
  border-bottom:1px dashed var(--light-rule);background:transparent;
  width:100%;color:var(--muted);outline:none;padding:2px 0;font-style:italic;
}
.nnotes:focus{border-bottom-color:var(--accent);color:var(--ink);font-style:normal;}

.dbtn{
  background:none;border:none;color:#ccc;cursor:pointer;
  font-size:13px;padding:2px 4px;transition:color .12s;line-height:1;
}
.dbtn:hover{color:var(--accent);}

/* ADD ROW BAR */
.addbar{display:flex;border-top:1px dashed var(--rule);background:#f0ece3;}
.addbar input{
  font-family:'IBM Plex Mono',monospace;font-size:11px;border:none;
  border-right:1px solid var(--light-rule);background:transparent;
  padding:7px 10px;outline:none;color:var(--ink);
}
.addbar input::placeholder{color:#bbb;}
.addbar input:focus{background:#fff9f0;}
.addbar .an{flex:3;}.addbar .aq{width:78px;text-align:center;}
.addbar .au{width:68px;text-align:center;}.addbar .anotes{flex:2;}
.addbtn{
  font-family:'IBM Plex Mono',monospace;font-size:10px;font-weight:600;
  text-transform:uppercase;letter-spacing:1px;padding:0 14px;
  background:var(--green);border:none;color:white;cursor:pointer;
}
.addbtn:hover{background:#135430;}

/* ADD SECTION BAR */
.add-sec-bar{
  display:flex;gap:10px;align-items:center;margin-bottom:20px;
  padding:10px 14px;border:1.5px dashed var(--rule);
}
.add-sec-bar input{
  font-family:'Bebas Neue',cursive;font-size:20px;letter-spacing:2px;
  border:none;border-bottom:1.5px solid var(--rule);background:transparent;
  padding:2px 8px;outline:none;flex:1;color:var(--ink);
}
.add-sec-bar input:focus{border-bottom-color:var(--accent);}
.add-sec-bar select{font-size:20px;border:none;background:transparent;cursor:pointer;outline:none;}

/* FOOTER */
.footer{
  position:fixed;bottom:0;left:0;right:0;background:var(--ink);color:white;
  display:flex;align-items:center;justify-content:space-between;
  padding:10px 24px;z-index:100;
}
.footer-info{color:#888;font-size:9px;text-transform:uppercase;letter-spacing:2px;}
.fcounts{display:flex;gap:24px;}
.fcount{text-align:center;}
.fcount span{display:block;font-size:8px;text-transform:uppercase;letter-spacing:1px;color:#555;}
.fcount strong{font-family:'Bebas Neue',cursive;font-size:22px;letter-spacing:1px;color:#e8e0d0;}
.fcount strong.hi{color:var(--accent);}
} /* end screen */

@media print {
  body{background:white;color:#000;font-size:9pt;}
  .no-print,.footer,.toolbar,.addbar,.add-sec-bar,.dbtn,.secbtn,.sec-acts,.config-panel{display:none !important;}
  .page{padding:0;max-width:100%;}
  .doc-header{display:grid;grid-template-columns:1fr auto;border-bottom:2pt solid #000;padding-bottom:10pt;margin-bottom:14pt;gap:16pt;align-items:end;}
  .doc-title{font-family:'Bebas Neue',cursive;font-size:36pt;line-height:.9;}
  .doc-title em{color:#d4401a;}
  .doc-meta{display:flex;flex-direction:column;gap:4pt;align-items:flex-end;}
  .meta-field{display:flex;flex-direction:column;align-items:flex-end;}
  .meta-label{font-size:7pt;text-transform:uppercase;color:#666;}
  .meta-input{font-size:9pt;border:none;background:transparent;text-align:right;padding:0;}
  .section{border:1pt solid #000;margin-bottom:10pt;page-break-inside:avoid;}
  .sec-head{background:#111 !important;color:white !important;padding:5pt 10pt;}
  .sec-icon{font-size:12pt;}.sec-name{font-size:14pt;color:white !important;}
  .sec-body.collapsed{display:block !important;}
  table{width:100%;font-size:8.5pt;}
  thead th{background:#e8e8e8 !important;color:#000;font-size:7pt;padding:4pt 7pt;border-bottom:1pt solid #000;}
  tbody tr{border-bottom:.5pt solid #ccc;}
  tbody tr:nth-child(even){background:#f5f5f0 !important;}
  td{padding:3pt 7pt;}
  .iname,.qty,.uunit,.nnotes,.type-sel{border:none !important;background:transparent !important;font-size:inherit;padding:0;width:auto;}
  .qty{font-weight:700;font-size:10pt;}
}
</style>
</head>
<body>

<!-- CONFIG PANEL -->
<div class="config-panel no-print">
  <div class="cp-group">
    <span class="cp-label">Baños en casa</span>
    <select id="cfg-banos" onchange="smartFill()">
      <option value="1">1 Baño</option>
      <option value="2" selected>2 Baños</option>
      <option value="3">3 Baños</option>
      <option value="4">4 Baños</option>
      <option value="5">5 Baños</option>
    </select>
  </div>
  <div class="cp-group">
    <span class="cp-label">Vanity Baño 1</span>
    <select id="cfg-v1" onchange="smartFill()">
      <option value="single">Single (1 faucet)</option>
      <option value="double" selected>Double (2 faucets)</option>
      <option value="vessel">Vessel sink</option>
      <option value="pedestal">Pedestal</option>
    </select>
  </div>
  <div class="cp-group">
    <span class="cp-label">Vanity Baño 2</span>
    <select id="cfg-v2" onchange="smartFill()">
      <option value="single" selected>Single (1 faucet)</option>
      <option value="double">Double (2 faucets)</option>
      <option value="vessel">Vessel sink</option>
      <option value="pedestal">Pedestal</option>
    </select>
  </div>
  <div class="cp-divider"></div>
  <div class="cp-group">
    <span class="cp-label">Cuartos</span>
    <select id="cfg-cuartos" onchange="smartFill()">
      <option value="1">1 Cuarto</option>
      <option value="2">2 Cuartos</option>
      <option value="3" selected>3 Cuartos</option>
      <option value="4">4 Cuartos</option>
      <option value="5">5 Cuartos</option>
    </select>
  </div>
  <div class="cp-group">
    <span class="cp-label">Puertas Exterior</span>
    <select id="cfg-ext" onchange="smartFill()">
      <option value="1">1 Puerta</option>
      <option value="2">2 Puertas</option>
      <option value="3" selected>3 Puertas</option>
      <option value="4">4 Puertas</option>
    </select>
  </div>
  <div class="cp-group">
    <span class="cp-label">Cocina</span>
    <select id="cfg-kitchen" onchange="smartFill()">
      <option value="basic">Básica (sin DW)</option>
      <option value="full" selected>Completa (DW + nevera)</option>
    </select>
  </div>
  <div class="cp-divider"></div>
  <div class="cp-hint no-print">
    Cantidades en <span>verde</span> = auto-calculadas.<br>
    Puedes editarlas manualmente.<br>
    Cambia los selectores arriba para recalcular.
  </div>
</div>

<div class="page">
  <div class="doc-header">
    <div><div class="doc-title">MATERIAL<br><em>TAKEOFF</em></div></div>
    <div class="doc-meta">
      <div class="meta-field"><span class="meta-label">Proyecto</span><input class="meta-input" id="mp" type="text" placeholder="Nombre del proyecto"></div>
      <div class="meta-field"><span class="meta-label">Dirección</span><input class="meta-input" id="ma" type="text" placeholder="Dirección"></div>
      <div class="meta-field"><span class="meta-label">Contratista</span><input class="meta-input" id="mc" type="text" placeholder="Nombre"></div>
      <div class="meta-field"><span class="meta-label">Fecha</span><input class="meta-input" id="mf" type="text"></div>
    </div>
  </div>

  <div class="toolbar no-print">
    <button class="btn btn-blue" onclick="window.print()">🖨 Imprimir / PDF</button>
    <div class="t-sep"></div>
    <button class="btn" onclick="collapseAll()">▲ Colapsar</button>
    <button class="btn" onclick="expandAll()">▼ Expandir</button>
    <div class="t-sep"></div>
    <button class="btn btn-red" onclick="clearQty()">↺ Limpiar cantidades</button>
  </div>

  <div id="sections"></div>

  <div class="add-sec-bar no-print">
    <select id="ni">
      <option>🛁</option><option>🚿</option><option>🚽</option><option>🪞</option>
      <option>🍳</option><option>🚪</option><option>🏠</option><option>🧺</option>
      <option>💡</option><option>🔌</option><option>🔩</option><option>🪟</option>
      <option>🛏️</option><option>💧</option><option>🌡️</option><option>📦</option>
    </select>
    <input type="text" id="nn" placeholder="NOMBRE DE NUEVA SECCIÓN..." onkeydown="if(event.key==='Enter')addSec()">
    <button class="btn btn-green" onclick="addSec()">+ Agregar Sección</button>
  </div>
</div>

<div class="footer no-print">
  <div class="footer-info">Construction Takeoff Sheet</div>
  <div class="fcounts">
    <div class="fcount"><span>Secciones</span><strong id="cs">0</strong></div>
    <div class="fcount"><span>Total Ítems</span><strong id="ci">0</strong></div>
    <div class="fcount"><span>Completados</span><strong class="hi" id="cf">0</strong></div>
  </div>
</div>

<script>
// ═══════════════════════════════════════════════════
// DATA  — smartKey maps to computed values
// ═══════════════════════════════════════════════════
const SECS = [
  { icon:'🌡️', id:'wh', name:'WATER HEATER & CONEXIONES COMPLETAS',
    items:[
      { n:'Water heater 40 gal electric/gas',          q:'1',  u:'ea',    no:'',                       sk:'wh' },
      { n:'Drip pan / bandeja WH',                      q:'1',  u:'ea',    no:'Bajo el water heater',   sk:'wh' },
      { n:'Manguera TPR / discharge pipe 3/4"',         q:'1',  u:'ea',    no:'Tubo descarga válvula TPR', sk:'wh' },
      { n:'Nipple macho 3/4" NPT — entrada fría',       q:'1',  u:'ea',    no:'Macho entrada agua fría', sk:'wh' },
      { n:'Nipple macho 3/4" NPT — salida caliente',    q:'1',  u:'ea',    no:'Macho salida caliente',  sk:'wh' },
      { n:'Flex connectors 3/4" (par)',                  q:'1',  u:'set',   no:'Mangueras flex WH',      sk:'wh' },
      { n:'Expansion tank',                              q:'1',  u:'ea',    no:'',                       sk:'wh' },
      { n:'Shutoff valve 3/4" cierre WH',               q:'1',  u:'ea',    no:'Válvula de cierre entrada', sk:'wh' },
      { n:'Pressure relief valve TPR 3/4"',             q:'1',  u:'ea',    no:'',                       sk:'wh' },
      { n:'Escutcheon / tapa válvula 3/4" WH',          q:'2',  u:'ea',    no:'',                       sk:'wh' },
    ]
  },
  { icon:'🛁', id:'baths', name:'BAÑOS — BATHTUBS & SHOWERS',
    items:[
      { n:'Bañeras (bathtubs)',                 q:'', u:'ea',  no:'',                  sk:'banos' },
      { n:'Overflow & drain kit bañera',        q:'', u:'set', no:'1 por bañera',      sk:'banos' },
      { n:'Mortar bed / leveling compound',     q:'', u:'bag', no:'',                  sk:'banos' },
      { n:'Shower pans / bases',               q:'', u:'ea',  no:'',                  sk:'banos' },
      { n:'Shower drain 2"',                    q:'', u:'ea',  no:'1 por shower',      sk:'banos' },
      { n:'Shower walls / 3-piece surround',    q:'', u:'set', no:'',                  sk:'banos' },
      { n:'Shower doors / enclosures',          q:'', u:'ea',  no:'',                  sk:'banos' },
      { n:'Shower niches 12"x24"',              q:'', u:'ea',  no:'',                  sk:'banos' },
      { n:'Waterproofing membrane (RedGard)',   q:'', u:'gal', no:'',                  sk:'banos' },
      { n:'Tile backer / Schluter Kerdi board', q:'', u:'ea',  no:'',                  sk:'banos_x2' },
    ]
  },
  { icon:'🪞', id:'vanity', name:'BAÑOS — VANITY & PLOMERÍA',
    hasType: true,
    items:[
      { n:'Vanity cabinet baño 1',    q:'1', u:'ea', no:'', sk:'v1_label',
        opts:[{l:'Single 24-30"',v:'single'},{l:'Double 48-60"',v:'double'},{l:'Vessel sink',v:'vessel'},{l:'Pedestal',v:'pedestal'}] },
      { n:'Vanity cabinet baño 2',    q:'1', u:'ea', no:'', sk:'v2_label',
        opts:[{l:'Single 24-30"',v:'single'},{l:'Double 48-60"',v:'double'},{l:'Vessel sink',v:'vessel'},{l:'Pedestal',v:'pedestal'}] },
      { n:'Vanity mirrors',                          q:'', u:'ea',  no:'1 por baño',          sk:'banos' },
      { n:'Vanity light bar pared (encima espejo)',  q:'', u:'ea',  no:'1 por baño',          sk:'banos' },
      { n:'Bathroom faucets',                        q:'', u:'ea',  no:'',                    sk:'faucets' },
      { n:'Shower valve / trim kit pressure-balance',q:'', u:'set', no:'1 por shower',        sk:'banos' },
      { n:'Tub spout con diverter',                  q:'', u:'ea',  no:'1 por tub',           sk:'banos' },
      { n:'P-trap 1-1/2" drain (por sink)',          q:'', u:'ea',  no:'',                    sk:'sinks' },
      { n:'Angle stop valve 1/2" (hot+cold / sink)', q:'', u:'ea',  no:'2 por sink',          sk:'faucets_x2' },
      { n:'Supply lines flex 12" (hot+cold / sink)', q:'', u:'ea',  no:'2 por sink',          sk:'faucets_x2' },
      { n:'Escutcheon tapa válvula 1/2" vanity',     q:'', u:'ea',  no:'2 por sink',          sk:'faucets_x2' },
    ]
  },
  { icon:'🚽', id:'toilets', name:'BAÑOS — TOILETS & ACCESORIOS',
    items:[
      { n:'Toilets (WC)',                      q:'', u:'ea',  no:'',           sk:'banos' },
      { n:'Toilet supply line 12" braided',    q:'', u:'ea',  no:'1 por WC',   sk:'banos' },
      { n:'Angle stop valve 3/8" toilet',      q:'', u:'ea',  no:'1 por WC',   sk:'banos' },
      { n:'Escutcheon tapa 3/8" toilet',       q:'', u:'ea',  no:'',           sk:'banos' },
      { n:'Wax ring + bolts kit',              q:'', u:'ea',  no:'1 por WC',   sk:'banos' },
      { n:'Towel bar 24"',                     q:'', u:'ea',  no:'1 por baño', sk:'banos' },
      { n:'Toilet paper holder',               q:'', u:'ea',  no:'1 por baño', sk:'banos' },
      { n:'Robe hook (2-pack)',                q:'', u:'pk',  no:'',           sk:'banos' },
      { n:'Hand towel ring',                   q:'', u:'ea',  no:'1 por baño', sk:'banos' },
      { n:'Shower curtain rod + hooks',        q:'', u:'set', no:'',           sk:'banos' },
      { n:'Bath exhaust fan 110 CFM',          q:'', u:'ea',  no:'1 por baño', sk:'banos' },
      { n:'Exhaust fan duct 4" flex kit',      q:'', u:'kit', no:'',           sk:'banos' },
      { n:'Roof cap 4" duct termination',      q:'', u:'ea',  no:'',           sk:'banos' },
    ]
  },
  { icon:'🍳', id:'kitchen', name:'COCINA — SINK, FAUCET & GABINETES',
    items:[
      { n:'Kitchen sink double bowl stainless',          q:'1', u:'ea',     no:'' },
      { n:'Kitchen faucet',                              q:'1', u:'ea',     no:'' },
      { n:'Garbage disposal',                            q:'1', u:'ea',     no:'' },
      { n:'Sink drain strainer basket (par)',             q:'1', u:'set',    no:'' },
      { n:'P-trap 1-1/2" doble kitchen',                 q:'1', u:'ea',     no:'' },
      { n:'Angle stop valve 3/8" hot+cold cocina',       q:'2', u:'ea',     no:'' },
      { n:'Supply lines flex 16" kitchen',               q:'2', u:'ea',     no:'hot + cold' },
      { n:'Escutcheon tapas válvulas 3/8" cocina',       q:'4', u:'ea',     no:'' },
      { n:'Dishwasher dual outlet valve (hot+DW)',       q:'',  u:'ea',     no:'',  sk:'dw' },
      { n:'Dishwasher supply line 72" braided',          q:'',  u:'ea',     no:'',  sk:'dw' },
      { n:'Dishwasher drain air gap countertop',         q:'',  u:'ea',     no:'',  sk:'dw' },
      { n:'Refrigerator outlet box recessed (nevera)',   q:'',  u:'ea',     no:'',  sk:'fridge' },
      { n:'Ice maker supply line 1/4" 6ft',             q:'',  u:'ea',     no:'',  sk:'fridge' },
      { n:'Angle stop valve 1/4" nevera',               q:'',  u:'ea',     no:'',  sk:'fridge' },
      { n:'Escutcheon tapa válvula 1/4" nevera',        q:'',  u:'ea',     no:'',  sk:'fridge' },
      { n:'Base cabinets',                              q:'',  u:'ea',     no:'' },
      { n:'Wall cabinets (upper)',                      q:'',  u:'ea',     no:'' },
      { n:'Corner cabinet base',                        q:'',  u:'ea',     no:'' },
      { n:'Countertop',                                 q:'',  u:'lin ft', no:'' },
      { n:'Cabinet hardware (pulls/knobs)',             q:'',  u:'set',    no:'' },
      { n:'Cabinet hinges soft-close (pack)',           q:'',  u:'pk',     no:'' },
      { n:'Under-cabinet LED strip light',             q:'',  u:'kit',    no:'' },
    ]
  },
  { icon:'🧺', id:'laundry', name:'LAUNDRY — CAJAS Y CONEXIONES',
    items:[
      { n:'Laundry recessed outlet box (hot+cold+drain)', q:'1', u:'ea',  no:'' },
      { n:'Washing machine hoses braided (par)',           q:'1', u:'pr',  no:'' },
      { n:'Standpipe & trap 2" washing machine',          q:'1', u:'kit', no:'' },
      { n:'Angle stop valve 1/2" washer (hot+cold)',      q:'2', u:'ea',  no:'' },
      { n:'Escutcheon tapas válvula 1/2" laundry',       q:'4', u:'ea',  no:'' },
      { n:'Dryer 240V outlet NEMA 14-30',                q:'1', u:'ea',  no:'' },
      { n:'Dryer vent 4" transition hose kit',            q:'1', u:'kit', no:'' },
      { n:'Dryer wall/roof cap 4"',                       q:'1', u:'ea',  no:'' },
    ]
  },
  { icon:'🚪', id:'idoors', name:'PUERTAS INTERIORES',
    items:[
      { n:'Puertas cuartos (pre-hung)',            q:'', u:'ea', no:'',                  sk:'cuartos' },
      { n:'Puertas baños (pre-hung)',              q:'', u:'ea', no:'',                  sk:'banos' },
      { n:'Door knobs / passage (cuartos)',        q:'', u:'ea', no:'',                  sk:'cuartos' },
      { n:'Door knobs / privacy (baños)',          q:'', u:'ea', no:'',                  sk:'banos' },
      { n:'Door hinges 3.5" interior',             q:'', u:'ea', no:'3 por puerta',      sk:'intdoors_x3' },
      { n:'Door jamb / frame kit',                 q:'', u:'set',no:'',                  sk:'intdoors' },
      { n:'Door stoppers wall-mount',              q:'', u:'ea', no:'1 por puerta',      sk:'intdoors' },
      { n:'Door casing chimold 7" (2 lados)',      q:'', u:'pc', no:'2 piezas/puerta',   sk:'intdoors_x2' },
      { n:'Shims para instalación puertas',        q:'', u:'bag',no:'' },
      { n:'Spray foam gaps puertas',               q:'', u:'can',no:'' },
    ]
  },
  { icon:'🏠', id:'edoors', name:'PUERTAS EXTERIORES + LUCES & VÁLVULAS EXT.',
    items:[
      { n:'Puertas exteriores fiberglass',              q:'', u:'ea',  no:'',                     sk:'ext' },
      { n:'Deadbolt lockset exterior',                  q:'', u:'ea',  no:'',                     sk:'ext' },
      { n:'Handle set / lever exterior',               q:'', u:'ea',  no:'',                     sk:'ext' },
      { n:'Door hinges exterior 4" heavy duty',         q:'', u:'ea',  no:'3 por puerta',         sk:'ext_x3' },
      { n:'Door sweep bottom seal',                    q:'', u:'ea',  no:'',                     sk:'ext' },
      { n:'Weatherstrip kit foam+vinyl',               q:'', u:'set', no:'',                     sk:'ext' },
      { n:'Threshold exterior 36"',                    q:'', u:'ea',  no:'',                     sk:'ext' },
      { n:'Brick mold / exterior casing',              q:'', u:'set', no:'',                     sk:'ext' },
      { n:'Sill flashing / door pan',                  q:'', u:'ea',  no:'',                     sk:'ext' },
      { n:'— LUCES EXTERIOR —',                        q:'', u:'',    no:'─────────────────────' },
      { n:'Exterior wall lantern lights (pared)',       q:'', u:'ea',  no:'Lámpara muro exterior', sk:'ext' },
      { n:'Exterior GFCI outlet weatherproof',         q:'', u:'ea',  no:'Salida exterior',       sk:'ext' },
      { n:'Weatherproof outlet cover in-use',          q:'', u:'ea',  no:'Tapa salida ext.',      sk:'ext' },
      { n:'— VÁLVULAS EXTERIOR —',                     q:'', u:'',    no:'─────────────────────' },
      { n:'Hose bib / sillcock valve 3/4" exterior',   q:'2', u:'ea', no:'Válvula manguera jardín' },
      { n:'Vacuum breaker / anti-sifón hose bib',      q:'2', u:'ea', no:'Anti-backflow',  },
      { n:'Escutcheon / tapa hose bib exterior',       q:'2', u:'ea', no:'' },
    ]
  },
  { icon:'💡', id:'lights', name:'ILUMINACIÓN — RESET LIGHTS, FANS, VANITY',
    items:[
      { n:'Recessed lights 6" LED — Living Room',       q:'', u:'ea', no:'Reset lights' },
      { n:'Recessed lights 6" LED — Dining Room',       q:'', u:'ea', no:'Reset lights' },
      { n:'Recessed lights 6" LED — Hallway',           q:'', u:'ea', no:'Reset lights' },
      { n:'Recessed lights 6" LED — Kitchen',           q:'', u:'ea', no:'Reset lights' },
      { n:'Recessed lights 6" LED — Laundry',           q:'', u:'ea', no:'Reset lights' },
      { n:'Recessed lights 4" LED — Baños',             q:'', u:'ea', no:'',          sk:'banos_x2' },
      { n:'Ceiling fans c/ light kit (cuartos)',         q:'', u:'ea', no:'1/cuarto',  sk:'cuartos' },
      { n:'Ceiling fan brace / mounting box',           q:'', u:'ea', no:'',          sk:'cuartos' },
      { n:'Ceiling fan remote control kit',             q:'', u:'ea', no:'',          sk:'cuartos' },
      { n:'Vanity light bar pared baños',               q:'', u:'ea', no:'1/baño encima espejo', sk:'banos' },
      { n:'Wall sconces / lámparas pared interior',     q:'', u:'ea', no:'Hallway, dining' },
      { n:'Exterior wall lantern lights',               q:'', u:'ea', no:'Frente/atrás', sk:'ext' },
      { n:'Pendant lights cocina / dining',             q:'', u:'ea', no:'' },
      { n:'LED bulbs A19 60W equiv (6-pack)',            q:'', u:'pk', no:'' },
    ]
  },
  { icon:'🔌', id:'elec', name:'ELECTRICIDAD — OUTLETS & SWITCHES',
    items:[
      { n:'Outlets / receptacles 15A',            q:'', u:'ea', no:'' },
      { n:'GFCI outlets baños + cocina',          q:'', u:'ea', no:'',           sk:'gfci' },
      { n:'Exterior GFCI outlets weatherproof',   q:'', u:'ea', no:'',           sk:'ext' },
      { n:'Outlet covers / plates',               q:'', u:'ea', no:'' },
      { n:'Light switches single-pole',           q:'', u:'ea', no:'' },
      { n:'3-way switches entrada / pasillos',    q:'', u:'ea', no:'' },
      { n:'Dimmer switches',                      q:'', u:'ea', no:'' },
      { n:'Switch plate covers',                  q:'', u:'ea', no:'' },
      { n:'Wire nuts assortment bag',             q:'', u:'bag',no:'' },
    ]
  },
  { icon:'🔩', id:'valves', name:'PLOMERÍA — VÁLVULAS & ESCUTCHEONS (toda la casa)',
    items:[
      { n:'Main shutoff valve 3/4" ball (casa)',  q:'1', u:'ea',  no:'' },
      { n:'Angle stop valve 1/2" spare (lote)',   q:'',  u:'ea',  no:'Extra toda la casa' },
      { n:'Angle stop valve 3/8" spare (lote)',   q:'',  u:'ea',  no:'Extra toda la casa' },
      { n:'Escutcheon plate 1/2" chrome',         q:'',  u:'ea',  no:'' },
      { n:'Escutcheon plate 3/8" chrome',         q:'',  u:'ea',  no:'' },
      { n:'Supply lines flex 12" braided (general)',q:'', u:'ea', no:'' },
      { n:'Teflon tape (lote de 5)',              q:'',  u:'ea',  no:'' },
      { n:'Pipe joint compound / dope',           q:'1', u:'jar', no:'' },
      { n:'PEX crimp rings 1/2" (50pk)',          q:'',  u:'pk',  no:'' },
      { n:'PEX crimp rings 3/4" (25pk)',          q:'',  u:'pk',  no:'' },
      { n:'Plumber\'s putty',                     q:'1', u:'tub', no:'' },
    ]
  },
  { icon:'🪟', id:'trim', name:'TRIM OUT — BASEBOARD, CHIMOLD & MOLDURAS',
    items:[
      { n:'Baseboard 3.5" sticks 8\'',            q:'', u:'pc',     no:'Total lineal casa' },
      { n:'Base shoe / quarter round 8\'',        q:'', u:'pc',     no:'' },
      { n:'Door casing / chimold 7" (2 lados)',   q:'', u:'pc',     no:'',            sk:'alldoors_x2' },
      { n:'Window casing chimold',                q:'', u:'set',    no:'1 set/ventana' },
      { n:'Crown molding 8\'',                    q:'', u:'pc',     no:'' },
      { n:'Chair rail molding',                   q:'', u:'lin ft', no:'' },
      { n:'Shoe molding 8\'',                     q:'', u:'pc',     no:'' },
      { n:'Attic door / pull-down stairs',        q:'', u:'ea',     no:'' },
    ]
  },
  { icon:'📦', id:'misc', name:'MISCELÁNEOS & SUMINISTROS GENERALES',
    items:[
      { n:'Caulk paintable (tubes)',               q:'', u:'ea',  no:'' },
      { n:'Silicone sealant clear / white',       q:'', u:'ea',  no:'' },
      { n:'Construction adhesive',                q:'', u:'tube',no:'' },
      { n:'Spray foam gaps & cracks 12oz',        q:'', u:'can', no:'' },
      { n:'Painter tape 2" blue',                 q:'', u:'roll',no:'' },
      { n:'Drywall screws 1-5/8" (1lb box)',      q:'', u:'box', no:'' },
      { n:'Brad nails / finish nails',            q:'', u:'box', no:'' },
      { n:'Shims assorted bag',                   q:'', u:'bag', no:'' },
      { n:'Hydraulic cement',                     q:'', u:'bag', no:'Penetraciones / pipes' },
      { n:'Trash bags heavy duty 42 gal (box)',   q:'', u:'box', no:'' },
      { n:'Safety glasses + gloves pack',         q:'', u:'kit', no:'' },
    ]
  },
];

// ══════════════════════════════════════════════════════
//  SMART FILL
// ══════════════════════════════════════════════════════
function getVals() {
  const b  = +document.getElementById('cfg-banos').value   || 2;
  const cu = +document.getElementById('cfg-cuartos').value || 3;
  const ex = +document.getElementById('cfg-ext').value     || 3;
  const v1 = document.getElementById('cfg-v1').value;
  const v2 = document.getElementById('cfg-v2').value;
  const ck = document.getElementById('cfg-kitchen').value;
  const f1 = v1 === 'double' ? 2 : 1;
  const f2 = b >= 2 ? (v2 === 'double' ? 2 : 1) : 0;
  const totalF = f1 + f2;
  const intd = b + cu;
  return {
    banos: b, cuartos: cu, ext: ex, wh: 1,
    faucets: totalF, faucets_x2: totalF*2, sinks: b,
    banos_x2: b*2,
    gfci: b*2+3,
    intdoors: intd, intdoors_x2: intd*2, intdoors_x3: intd*3,
    alldoors_x2: (intd+ex)*2,
    ext_x3: ex*3,
    dw: ck==='full'?1:0, fridge: ck==='full'?1:0,
    v1_label: v1, v2_label: v2,
  };
}

function smartFill() {
  const V = getVals();
  document.querySelectorAll('[data-sk]').forEach(el => {
    const sk = el.dataset.sk;
    if (sk === 'v1_label' || sk === 'v2_label') {
      const sel = el.closest('tr')?.querySelector('.type-sel');
      if (sel) sel.value = sk === 'v1_label' ? document.getElementById('cfg-v1').value
                                              : document.getElementById('cfg-v2').value;
      return;
    }
    if (V[sk] !== undefined) {
      const v = V[sk];
      el.value = v === 0 ? '' : v;
      el.classList.toggle('auto', v > 0);
    }
  });
  updateCounts();
}

// ══════════════════════════════════════════════════════
//  RENDER
// ══════════════════════════════════════════════════════
function esc(s){ return (s||'').replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;'); }

let SC = 0;
function buildSec(data) {
  const sid = 'sec-'+(data.id||SC++);
  if (document.getElementById(sid)) return;
  const hasType = data.hasType || data.items.some(i=>i.opts);
  const div = document.createElement('div');
  div.className='section'; div.id=sid;
  const thType = hasType ? '<th style="width:148px;">Tipo / Modelo</th>' : '';
  const w = hasType ? '26%' : '42%';
  div.innerHTML=`
    <div class="sec-head">
      <div class="sec-name-wrap">
        <span class="sec-icon">${data.icon}</span>
        <input class="sec-name" type="text" value="${esc(data.name)}" spellcheck="false">
      </div>
      <div class="sec-acts no-print">
        <button class="secbtn" onclick="togSec('${sid}')">▼</button>
        <button class="secbtn d" onclick="delSec('${sid}')">✕</button>
      </div>
    </div>
    <div class="sec-body" id="b-${sid}">
      <table>
        <thead><tr>
          <th style="width:${w};">Ítem / Material</th>
          ${thType}
          <th class="c" style="width:72px;">Cantidad</th>
          <th class="c" style="width:56px;">Unidad</th>
          <th>Notas / Especificación</th>
          <th class="c no-print" style="width:26px;"></th>
        </tr></thead>
        <tbody id="tb-${sid}"></tbody>
      </table>
      <div class="addbar no-print">
        <input class="an" type="text" placeholder="Nuevo ítem...">
        <input class="aq" type="text" placeholder="Cant.">
        <input class="au" type="text" placeholder="Unidad" value="ea">
        <input class="anotes" type="text" placeholder="Notas...">
        <button class="addbtn" onclick="addRow('${sid}',this)">+ Row</button>
      </div>
    </div>`;
  const tb = div.querySelector(`#tb-${sid}`);
  data.items.forEach(it => addRowData(tb, it, hasType));
  document.getElementById('sections').appendChild(div);
  updateCounts();
}

function addRowData(tb, it, hasType) {
  const tr = document.createElement('tr');
  let typeCell = '';
  if (hasType) {
    if (it.opts) {
      const opts = it.opts.map(o=>`<option value="${o.v}">${o.l}</option>`).join('');
      typeCell = `<td><select class="type-sel">${opts}</select></td>`;
    } else {
      typeCell = `<td></td>`;
    }
  }
  const skAttr = it.sk ? `data-sk="${it.sk}"` : '';
  const autoCls = (it.sk && it.q) ? 'auto' : '';
  tr.innerHTML=`
    <td><input class="iname" type="text" value="${esc(it.n)}" placeholder="Ítem..." spellcheck="false"></td>
    ${typeCell}
    <td class="c"><input class="qty ${autoCls}" type="text" value="${it.q||''}" placeholder="—" ${skAttr}
        oninput="this.classList.remove('auto');updateCounts()"></td>
    <td class="c"><input class="uunit" type="text" value="${it.u||'ea'}"></td>
    <td><input class="nnotes" type="text" value="${esc(it.no||'')}" placeholder="Especificación..."></td>
    <td class="c no-print"><button class="dbtn" onclick="this.closest('tr').remove();updateCounts()">✕</button></td>`;
  tb.appendChild(tr);
}

function addRow(sid, btn) {
  const bar = btn.closest('.addbar');
  const n = bar.querySelector('.an').value.trim()||'Nuevo ítem';
  const q = bar.querySelector('.aq').value.trim();
  const u = bar.querySelector('.au').value.trim()||'ea';
  const no= bar.querySelector('.anotes').value.trim();
  const tb= document.getElementById(`tb-${sid}`);
  const hasType = !!tb.querySelector('.type-sel');
  addRowData(tb,{n,q,u,no},hasType);
  bar.querySelector('.an').value=''; bar.querySelector('.aq').value='';
  bar.querySelector('.au').value='ea'; bar.querySelector('.anotes').value='';
  bar.querySelector('.an').focus(); updateCounts();
}

function addSec() {
  const icon=document.getElementById('ni').value;
  const name=document.getElementById('nn').value.trim().toUpperCase()||'NUEVA SECCIÓN';
  const sid='sec-c'+Date.now();
  const div=document.createElement('div');
  div.className='section';div.id=sid;
  div.innerHTML=`
    <div class="sec-head">
      <div class="sec-name-wrap">
        <span class="sec-icon">${icon}</span>
        <input class="sec-name" type="text" value="${name}" spellcheck="false">
      </div>
      <div class="sec-acts no-print">
        <button class="secbtn" onclick="togSec('${sid}')">▼</button>
        <button class="secbtn d" onclick="delSec('${sid}')">✕</button>
      </div>
    </div>
    <div class="sec-body" id="b-${sid}">
      <table>
        <thead><tr>
          <th style="width:42%;">Ítem / Material</th>
          <th class="c" style="width:72px;">Cantidad</th>
          <th class="c" style="width:56px;">Unidad</th>
          <th>Notas / Especificación</th>
          <th class="c no-print" style="width:26px;"></th>
        </tr></thead>
        <tbody id="tb-${sid}"></tbody>
      </table>
      <div class="addbar no-print">
        <input class="an" type="text" placeholder="Nuevo ítem...">
        <input class="aq" type="text" placeholder="Cant.">
        <input class="au" type="text" placeholder="Unidad" value="ea">
        <input class="anotes" type="text" placeholder="Notas...">
        <button class="addbtn" onclick="addRow('${sid}',this)">+ Row</button>
      </div>
    </div>`;
  document.getElementById('sections').appendChild(div);
  const tb=div.querySelector(`#tb-${sid}`);
  for(let i=0;i<3;i++) addRowData(tb,{n:'',q:'',u:'ea',no:''},false);
  document.getElementById('nn').value='';
  updateCounts();
}

function delSec(sid){ if(confirm('Eliminar sección?')){ document.getElementById(sid).remove(); updateCounts(); } }
function togSec(sid){
  const b=document.getElementById('b-'+sid);
  const btn=document.querySelector(`#${sid} .secbtn`);
  b.classList.toggle('collapsed');
  btn.textContent=b.classList.contains('collapsed')?'▶':'▼';
}
function collapseAll(){ document.querySelectorAll('.sec-body').forEach(b=>b.classList.add('collapsed')); document.querySelectorAll('.secbtn:first-child').forEach(b=>b.textContent='▶'); }
function expandAll(){ document.querySelectorAll('.sec-body').forEach(b=>b.classList.remove('collapsed')); document.querySelectorAll('.secbtn:first-child').forEach(b=>b.textContent='▼'); }
function clearQty(){ if(!confirm('Limpiar todas las cantidades?'))return; document.querySelectorAll('.qty').forEach(i=>{i.value='';i.classList.remove('auto');}); updateCounts(); }
function updateCounts(){
  document.getElementById('cs').textContent=document.querySelectorAll('.section').length;
  const all=[...document.querySelectorAll('.qty')];
  document.getElementById('ci').textContent=all.length;
  document.getElementById('cf').textContent=all.filter(i=>i.value.trim()!=='').length;
}

// INIT
document.getElementById('mf').value=new Date().toLocaleDateString('es-US',{year:'numeric',month:'long',day:'numeric'});
SECS.forEach(buildSec);
smartFill();
</script>
</body>
</html>