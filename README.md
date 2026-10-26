
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>AIRLAB | Purificador de aire</title>
<style>
:root{--bg:#07131f;--panel:#102535;--cyan:#5ef0dc;--blue:#68a9ff;--text:#eaf8ff;--muted:#a7c1d0}
*{box-sizing:border-box}
body{margin:0;background:radial-gradient(circle at 50% 0,#163a4c 0,#07131f 48%,#030910 100%);color:var(--text);font-family:system-ui,-apple-system,Segoe UI,sans-serif}
main{max-width:1000px;margin:auto;padding:24px 16px 48px}
header{text-align:center;margin:10px auto 24px}
.kicker{color:var(--cyan);letter-spacing:.22em;font-size:.76rem;font-weight:800}
h1{font-size:clamp(2.3rem,8vw,4.5rem);letter-spacing:.08em;margin:7px 0;background:linear-gradient(90deg,#fff,var(--cyan),var(--blue));color:transparent;background-clip:text}
header p{color:var(--muted);max-width:580px;margin:0 auto;line-height:1.6}
.layout{display:grid;grid-template-columns:minmax(0,1fr) minmax(0,1fr);gap:18px;align-items:stretch}
.panel{background:linear-gradient(145deg,#102838ed,#081824f2);border:1px solid #285065;border-radius:22px;padding:18px;box-shadow:0 18px 45px #0004}
.panel h2{font-size:1.05rem;margin:0 0 12px}
.bottle-area{min-height:430px;display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden}
.bottle{width:min(260px,75%);height:390px;position:relative;border:4px solid #9ee8ef;border-top:0;border-radius:32px 32px 46px 46px;background:linear-gradient(90deg,#b9f4ff20,#e7ffff08,#8ed5ff24);box-shadow:inset 0 0 25px #6ce7f333,0 0 28px #36d9ef20;overflow:hidden}
.neck{position:absolute;top:-4px;left:33%;width:34%;height:43px;border:4px solid #9ee8ef;border-bottom:0;border-radius:12px 12px 0 0;background:#102838}
.cap{position:absolute;top:0;left:30%;width:40%;height:17px;border-radius:5px;background:#5ef0dc;box-shadow:0 0 14px #5ef0dc66;z-index:3}
.air{position:absolute;top:45px;left:0;right:0;text-align:center;color:var(--cyan);font-size:.72rem;font-weight:800;letter-spacing:.1em;animation:pulse 1.4s infinite}
.layers{position:absolute;top:86px;bottom:26px;left:13px;right:13px;display:flex;flex-direction:column;gap:8px}
.layer{border:1px solid #ffffff70;border-radius:8px;min-height:40px;display:flex;align-items:center;justify-content:center;font-weight:800;font-size:.82rem;text-shadow:0 1px 4px #0009;cursor:pointer;transition:.2s;position:relative}
.layer:after{content:"";position:absolute;left:10px;right:10px;top:7px;height:2px;background:#ffffff50;border-radius:50%}
.layer:active,.layer.selected{outline:3px solid white;transform:scale(1.025);filter:brightness(1.25)}
.l1{background:repeating-linear-gradient(45deg,#8b9eaa,#8b9eaa 5px,#6f8492 5px,#6f8492 10px)}
.l2{background:repeating-linear-gradient(0deg,#b7d8c2,#b7d8c2 4px,#679e82 4px,#679e82 8px);color:#09241c}
.l3{background:radial-gradient(circle,#171f26 2px,#35434c 3px,#1c2933 7px)}
.l4{background:repeating-linear-gradient(45deg,#d6dbe0,#d6dbe0 4px,#aab7c2 4px,#aab7c2 8px);color:#17232d}
.l5{background:linear-gradient(90deg,#66c7bc,#298a8d,#66c7bc);color:#062c30}
.airout{position:absolute;bottom:7px;left:0;right:0;text-align:center;font-size:.72rem;color:#c8faff;letter-spacing:.1em}
.controls{display:flex;gap:8px;flex-wrap:wrap;margin:14px 0}
button{border:1px solid #3e7589;background:#17394b;color:var(--text);padding:11px 14px;border-radius:12px;font-weight:750;cursor:pointer}
button.primary{background:var(--cyan);color:#05232a;border-color:var(--cyan)}
button:focus-visible,.layer:focus-visible{outline:3px solid white;outline-offset:3px}
.info-tag{display:inline-block;font-size:.72rem;letter-spacing:.12em;color:var(--cyan);font-weight:800;margin-bottom:6px}
#detail h3{font-size:1.45rem;margin:4px 0 10px}
#detail p{color:#c6d9e5;line-height:1.65;margin:0 0 14px}
.stat{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-top:16px}
.stat div{padding:12px;background:#0b1b27;border:1px solid #234658;border-radius:12px}
.stat strong{display:block;color:var(--cyan);font-size:.85rem;margin-bottom:4px}
.stat span{font-size:.82rem;color:var(--muted)}
.note{font-size:.8rem;color:#93adbb;line-height:1.5;margin-top:16px}
.flowing .air{animation:pulse .55s infinite}
.flowing .layer{animation:glow 1.3s infinite alternate}
@keyframes pulse{50%{opacity:.35;transform:translateY(-3px)}}
@keyframes glow{to{box-shadow:0 0 18px #5ef0dc40}}
footer{text-align:center;color:#7294a7;font-size:.75rem;margin-top:22px}
@media(max-width:700px){.layout{grid-template-columns:1fr}.bottle-area{min-height:420px}.panel{padding:16px}main{padding:18px 12px 34px}}
</style>
</head>
<body>
<main>
<header>
<div class="kicker">PROYECTO STEAM · EQUIPO 1</div>
<h1>AIRLAB</h1>
<p>Explora un prototipo conceptual de purificador de aire. Toca cada capa para conocer su función y activa el flujo para observar el recorrido del aire.</p>
</header>
<div class="layout">
<section class="panel">
<h2>01 / Corte del purificador</h2>
<div class="bottle-area" id="bottleArea">
<div class="neck"></div>
<div class="bottle" id="bottle">
<div class="cap"></div>
<div class="air">↓ AIRE ENTRANTE</div>
<div class="layers">
<div class="layer l1 selected" tabindex="0" role="button" data-layer="0">1 · Prefiltro</div>
<div class="layer l2" tabindex="0" role="button" data-layer="1">2 · Fibra</div>
<div class="layer l3" tabindex="0" role="button" data-layer="2">3 · Carbón activado</div>
<div class="layer l4" tabindex="0" role="button" data-layer="3">4 · Filtro fino</div>
<div class="layer l5" tabindex="0" role="button" data-layer="4">5 · Salida</div>
</div>
<div class="airout">↓ AIRE HACIA LA SALIDA</div>
</div>
</div>
<div class="controls">
<button class="primary" id="flowBtn">▶ Activar flujo</button>
<button id="resetBtn">↺ Reiniciar</button>
</div>
<p class="note">Modelo visual ilustrativo: la eficacia real depende de los materiales, el sellado y el movimiento del aire. No mide la calidad del aire.</p>
</section>
<section class="panel" id="detail">
<div class="info-tag" id="tag">CAPA 01 / 05</div>
<h3 id="name">Prefiltro</h3>
<p id="desc">La primera capa representa una barrera que retiene parte del polvo y las partículas más grandes antes de que el aire avance.</p>
<div class="stat">
<div><strong>FUNCIÓN</strong><span id="function">Retención inicial</span></div>
<div><strong>RECORRIDO</strong><span id="route">Entrada del aire</span></div>
</div>
<div style="margin-top:18px;border-top:1px solid #285065;padding-top:16px">
<h2>¿Cómo se usa?</h2>
<p>Selecciona una capa de la botella. La explicación cambia según la parte elegida. Pulsa “Activar flujo” para ver la animación conceptual.</p>
</div>
</section>
</div>
<footer>AIRLAB · Prototipo educativo interactivo · No es un dispositivo certificado</footer>
</main>
<script>
const layers=[
{name:"Prefiltro",desc:"La primera capa representa una barrera que retiene parte del polvo y las partículas más grandes antes de que el aire avance.",func:"Retención inicial",route:"Entrada del aire"},
{name:"Fibra filtrante",desc:"Una capa de fibra puede ayudar a atrapar partículas suspendidas. En el prototipo se representa como una malla fibrosa.",func:"Captura de partículas",route:"Después del prefiltro"},
{name:"Carbón activado",desc:"El carbón activado tiene una superficie muy porosa que puede adsorber ciertos gases y olores. Su rendimiento depende del tipo de carbón, la cantidad y el tiempo de contacto.",func:"Adsorción de ciertos gases",route:"Zona central del filtro"},
{name:"Filtro fino",desc:"Esta capa simboliza una barrera adicional para partículas pequeñas. El resultado real depende del material y de cómo esté instalado.",func:"Filtración adicional",route:"Antes de la salida"},
{name:"Salida de aire",desc:"El aire recorre las capas y sale por el extremo indicado. El prototipo muestra el recorrido, pero no demuestra por sí solo que el aire quede purificado.",func:"Salida del sistema",route:"Final del recorrido"}
];
const layerEls=[...document.querySelectorAll(".layer")];

function selectLayer(i){
layerEls.forEach((el,j)=>el.classList.toggle("selected",i===j));
document.getElementById("tag").textContent=`CAPA ${String(i+1).padStart(2,"0")} / 05`;
document.getElementById("name").textContent=layers[i].name;
document.getElementById("desc").textContent=layers[i].desc;
document.getElementById("function").textContent=layers[i].func;
document.getElementById("route").textContent=layers[i].route;
}

layerEls.forEach(el=>{
el.addEventListener("click",()=>selectLayer(Number(el.dataset.layer)));
el.addEventListener("keydown",e=>{
if(e.key==="Enter"||e.key===" "){
e.preventDefault();
selectLayer(Number(el.dataset.layer));
}
});
});

const bottle=document.getElementById("bottle");
const flowBtn=document.getElementById("flowBtn");

flowBtn.addEventListener("click",()=>{
const on=bottle.classList.toggle("flowing");
flowBtn.textContent=on?"■ Detener flujo":"▶ Activar flujo";
});

document.getElementById("resetBtn").addEventListener("click",()=>{
bottle.classList.remove("flowing");
flowBtn.textContent="▶ Activar flujo";
selectLayer(0);
});
</script>
</body>
</html>
