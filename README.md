<!doctype html>
<html lang="fr">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<title>Stats au Comptoir</title>
<link rel="preconnect" href="https://fonts.googleapis.com"><link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,600;12..96,700;12..96,800&family=Figtree:wght@400;500;600;700&family=JetBrains+Mono:wght@500;600;700&display=swap">
<style>
html{color-scheme:light dark}body{margin:0}[hidden]{display:none!important}
:root{--bg:#EEF2EF;--surface:#FFFFFF;--ink:#12201C;--muted:#55645F;--line:#CBD5D0;--accent:#0B7A62;--on-accent:#FFFFFF;--soft:#E1EDE8;--gold:#E0A800;--warn:#9A6200;--good:#1C7C3E;--bad:#B93526;--shadow:0 1px 0 rgba(18,32,28,.06),0 8px 24px -12px rgba(18,32,28,.18);--fd:"Bricolage Grotesque",Georgia,serif;--fb:"Figtree",system-ui,sans-serif;--fm:"JetBrains Mono",ui-monospace,Menlo,monospace}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#0E1614;--surface:#16221F;--ink:#E7F0EC;--muted:#9BB0A8;--line:#2C3D38;--accent:#3FD1AE;--on-accent:#05211A;--soft:#1E2F2A;--gold:#F5C518;--warn:#F5C518;--good:#5FD38A;--bad:#FF8A7A;--shadow:0 8px 24px -12px rgba(0,0,0,.6);color-scheme:dark}}
:root[data-theme="dark"]{--bg:#0E1614;--surface:#16221F;--ink:#E7F0EC;--muted:#9BB0A8;--line:#2C3D38;--accent:#3FD1AE;--on-accent:#05211A;--soft:#1E2F2A;--gold:#F5C518;--warn:#F5C518;--good:#5FD38A;--bad:#FF8A7A;--shadow:0 8px 24px -12px rgba(0,0,0,.6);color-scheme:dark}
*{box-sizing:border-box}
body{background:var(--bg);color:var(--ink);font:16px/1.55 var(--fb);padding-block:0;padding-left:max(16px,env(safe-area-inset-left,0px));padding-right:max(16px,env(safe-area-inset-right,0px))}
#app{max-width:760px;margin:0 auto;padding-block:12px 48px}
button{font:inherit;color:inherit;cursor:pointer}
:focus-visible{outline:3px solid var(--accent);outline-offset:2px;border-radius:6px}
.mono{font-family:var(--fm);font-variant-numeric:tabular-nums}
.top{display:flex;justify-content:space-between;align-items:center;gap:12px;padding:6px 0 14px;flex-wrap:wrap}
.brand{display:flex;align-items:center;gap:10px;background:none;border:0;padding:0;font:800 19px var(--fd);letter-spacing:-.01em}
.logo{display:grid;place-items:center;width:32px;height:32px;border-radius:8px;background:var(--accent);color:var(--on-accent);font:700 18px var(--fm)}
.top-r{display:flex;align-items:center;gap:10px}
.pill{background:var(--soft);border-radius:99px;padding:4px 12px;font-size:14px;font-weight:600}
.btn{background:var(--accent);color:var(--on-accent);border:0;border-radius:10px;padding:11px 20px;font-weight:700;font-size:16px;min-height:44px}
.btn:hover{filter:brightness(1.07)}
.btn.ghost{background:transparent;color:var(--ink);border:1.5px solid var(--line)}
.btn.sm{padding:6px 12px;min-height:36px;font-size:14px}
.link{background:none;border:0;color:var(--accent);text-decoration:underline;text-underline-offset:3px;padding:6px 0;font-weight:600;font-size:15px}
.back{margin-bottom:10px;display:inline-block}
.eyebrow{font:700 12px var(--fb);letter-spacing:.09em;text-transform:uppercase;color:var(--muted);margin:0 0 6px}
h1{font:800 clamp(28px,6vw,40px)/1.1 var(--fd);letter-spacing:-.02em;margin:0 0 12px;text-wrap:balance}
.hero{padding:10px 0 8px}.lead{font-size:17px;color:var(--ink);max-width:62ch;margin:0 0 18px}
.status{display:flex;align-items:center;gap:20px;flex-wrap:wrap;background:var(--surface);border:1px solid var(--line);border-radius:12px;padding:14px 18px}
.grade{font:700 22px var(--fd)}.bar-wrap{flex:1;min-width:140px;height:10px;background:var(--soft);border-radius:99px;overflow:hidden}.bar-in{height:100%;background:var(--accent);border-radius:99px}
h2.sec{font:700 14px var(--fb);letter-spacing:.09em;text-transform:uppercase;color:var(--muted);margin:30px 0 12px}
.mlist{display:grid;gap:10px;margin-bottom:10px}
.mcard{display:flex;align-items:center;gap:16px;width:100%;text-align:left;background:var(--surface);border:1px solid var(--line);border-radius:12px;padding:14px 16px;box-shadow:var(--shadow)}
.mcard:hover:not(:disabled){border-color:var(--accent)}
.mnum{flex:none;display:grid;place-items:center;width:42px;height:42px;border-radius:10px;background:var(--soft);font-weight:700;font-size:19px;color:var(--accent)}
.mtxt{flex:1;min-width:0;display:flex;flex-direction:column}.mtxt b{font:700 17px var(--fd)}.mtxt small{color:var(--muted);font-size:14px}
.mst{flex:none;color:var(--muted);letter-spacing:2px;font-size:18px}.mst.on{color:var(--gold)}
.mcard.boss{margin-top:14px;border-style:dashed;border-color:var(--accent)}.mcard.locked{opacity:.6;cursor:not-allowed}
.foot-note{color:var(--muted);font-size:14px;margin-top:22px}
.ticket{background:var(--surface);border:1px solid var(--line);border-radius:6px;padding:0 20px 22px;box-shadow:var(--shadow);margin-top:8px;position:relative}
.ticket::after{content:"";position:absolute;left:0;right:0;bottom:-7px;height:8px;background:radial-gradient(circle at 6px 0,transparent 5px,var(--surface) 5.5px) 0 0/12px 8px repeat-x;filter:drop-shadow(0 1px 0 var(--line))}
.perf{margin:0 -20px 18px;padding:10px 20px;border-bottom:2px dashed var(--line);font-size:12px;letter-spacing:.1em;color:var(--muted)}
.ticket h1{font-size:clamp(24px,5vw,32px)}.qt{font-size:clamp(22px,4.5vw,28px)!important}
.sec2{font:700 16px var(--fd);margin:18px 0 8px;color:var(--accent)}
.course ul{padding-left:20px;margin:0 0 12px}.course li{margin:6px 0}.ex{background:var(--soft);border-radius:8px;padding:10px 14px;font-size:15px}
.actions{display:flex;gap:10px;flex-wrap:wrap;margin-top:20px}
.qbar{display:flex;align-items:center;gap:14px;padding:4px 0}.prog{flex:1;display:flex;gap:5px}.prog i{flex:1;height:7px;border-radius:99px;background:var(--line)}.prog i.d{background:var(--accent)}.prog i.c{background:var(--gold)}.sc{font-weight:700;font-size:14px}
.story{font-size:17px;margin:0 0 10px}.callout{background:var(--soft);border-radius:8px;padding:12px 16px;margin-top:8px;font-size:17px}
.data{margin:10px 0 14px;max-width:100%;overflow-x:auto}
.chips{display:flex;flex-wrap:wrap;gap:8px}.chip{font:600 16px var(--fm);background:var(--soft);padding:6px 12px;border-radius:8px}
.tw{overflow-x:auto}table{border-collapse:collapse;font-size:15px;min-width:60%}th,td{border:1px solid var(--line);padding:7px 12px;text-align:center;font-variant-numeric:tabular-nums}th{background:var(--soft);font-weight:700}
.note{color:var(--muted);font-size:14px;margin:8px 0 0}
.steps{display:grid;gap:12px;margin-top:6px}
.step{border-radius:10px;padding:12px 14px}.step.solved{display:flex;gap:12px;background:var(--soft)}.tick{color:var(--good);font-weight:800}.slabel{font-weight:600}.sans{font-size:17px;color:var(--ink)}.sans em{font:italic 13px var(--fb);color:var(--muted)}
.step.current{border:2px solid var(--accent);background:var(--surface)}
.ansrow{display:flex;gap:10px;align-items:center;margin-top:10px;flex-wrap:wrap}
.inp{flex:1;min-width:130px;max-width:240px;font-size:20px;padding:10px 14px;border:2px solid var(--line);border-radius:10px;background:var(--bg);color:var(--ink)}.inp:focus{border-color:var(--accent);outline:none}
.unit{font:600 16px var(--fm);color:var(--muted)}
.opts{display:grid;gap:8px;margin-top:10px}.opt{text-align:left;background:var(--bg);border:2px solid var(--line);border-radius:10px;padding:12px 14px;font-size:16px}.opt:hover:not(:disabled){border-color:var(--accent)}.opt.bad{border-color:var(--bad);opacity:.6;text-decoration:line-through}
.fb{min-height:1.4em;margin-top:8px;font-size:15px}.bad{color:var(--bad);font-weight:700}
.hint{background:var(--soft);border-left:4px solid var(--gold);border-radius:6px;padding:10px 14px;margin-top:8px;font-size:15px}
.tools{display:flex;gap:18px;flex-wrap:wrap}
.recap{margin-top:16px;border-top:2px dashed var(--line);padding-top:14px}.recap p{margin:8px 0}
.svg{width:100%;max-width:460px;height:auto;display:block}.svg .bar{fill:var(--accent)}.svg .t{fill:var(--ink);font:600 11px var(--fm)}.svg .t.s{fill:var(--muted);font-size:10px;font-weight:500}.svg .ax{stroke:var(--muted);stroke-width:1.5}.svg .box{fill:var(--soft);stroke:var(--accent);stroke-width:2}.svg .med{stroke:var(--warn);stroke-width:3}.svg .curve{fill:none;stroke-width:3;stroke-linejoin:round}.c1{stroke:var(--accent);background:var(--accent)}.c2{stroke:var(--ink);background:var(--ink)}.c3{stroke:var(--warn);background:var(--warn)}
.legend{display:flex;gap:16px;font-size:14px;flex-wrap:wrap}.legend .k{display:inline-block;width:18px;height:5px;border-radius:3px;margin-right:6px;vertical-align:middle}
.center{text-align:center}.bigstars{font-size:44px;color:var(--gold);letter-spacing:6px}.score{font-size:24px;font-weight:700;margin:0}
.rlist{text-align:left;margin:16px auto 0;max-width:520px}.rrow{display:flex;justify-content:space-between;gap:12px;padding:8px 0;border-bottom:1px dashed var(--line);font-size:15px}.g{color:var(--good)}.o{color:var(--warn)}.r{color:var(--bad)}
.center .actions{justify-content:center}
.overlay{position:fixed;inset:0;background:rgba(10,18,16,.55);display:grid;place-items:center;padding:16px;z-index:20}
.sheet{background:var(--surface);border-radius:14px;max-width:640px;width:100%;max-height:88vh;overflow:auto;padding:20px 22px}.sheet h2{font:800 24px var(--fd);margin:0 0 10px}.sheet h3{font:700 15px var(--fd);color:var(--accent);margin:0 0 4px}.sheet p{margin:4px 0 8px;font-size:15px}.hgrid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:6px 22px;margin-bottom:14px}
@media (prefers-reduced-motion:no-preference){.bar-in{transition:width .6s}.mcard{transition:border-color .15s}}

.trk{margin:18px 0 0}.nameform{background:var(--surface);border:1px solid var(--accent);border-radius:12px;padding:16px 18px}.nameform .inp{max-width:none}
.kpis{display:flex;flex-wrap:wrap;gap:10px}.kpi{background:var(--soft);border-radius:10px;padding:10px 16px;display:flex;flex-direction:column;min-width:84px}.kpi .mono{font-size:22px;font-weight:700}.kpi small{color:var(--muted)}
.wk{display:grid;grid-template-columns:minmax(0,1.3fr) minmax(70px,1fr) 52px;gap:12px;align-items:center;padding:6px 0;font-size:15px}.wbar{height:10px;background:var(--soft);border-radius:99px;overflow:hidden}.wbar i{display:block;height:100%;background:var(--warn)}
.tst{color:var(--gold);letter-spacing:1px;font-size:13px;white-space:nowrap}.ticket table td:first-child{text-align:left;white-space:nowrap}

.ansrow+.kpis{margin-top:16px}
.fl{display:block;font-weight:600;font-size:14px;margin:12px 0 4px}.inp.wide{max-width:none;width:100%}.fh{margin:0}select.inp{min-width:140px;font-size:16px}

</style>
</head>
<body>
<div id="app"></div>
<script>
// ===== Outils =====
const R=(a,b)=>Math.floor(Math.random()*(b-a+1))+a;
const pick=a=>a[R(0,a.length-1)];
const shuffle=a=>{a=a.slice();for(let i=a.length-1;i>0;i--){const j=R(0,i);[a[i],a[j]]=[a[j],a[i]]}return a};
const sum=a=>a.reduce((s,x)=>s+x,0);
const sample=(a,k)=>shuffle(a).slice(0,k);
const f=(n,d=2)=>{if(!isFinite(n))return"?";let s=Number.isInteger(n)?String(n):String(+n.toFixed(d));let neg=s[0]==="-";if(neg)s=s.slice(1);let [i,dec]=s.split(".");i=i.replace(/\B(?=(\d{3})+(?!\d))/g," ");return(neg?"−":"")+i+(dec?","+dec:"")};
const median=a=>{const b=[...a].sort((x,y)=>x-y),n=b.length;return n%2?b[(n-1)/2]:(b[n/2-1]+b[n/2])/2};
const sorted=a=>[...a].sort((x,y)=>x-y);
const chips=(a,u="")=>`<div class="chips">${a.map(x=>`<span class="chip">${f(x)}${u?" "+u:""}</span>`).join("")}</div>`;
const table=(head,rows)=>`<div class="tw"><table><thead><tr>${head.map(h=>`<th>${h}</th>`).join("")}</tr></thead><tbody>${rows.map(r=>`<tr>${r.map(c=>`<td>${c}</td>`).join("")}</tr>`).join("")}</tbody></table></div>`;
// étape numérique / choix
const num=(label,ans,o={})=>({type:"num",label,ans,unit:o.unit||"",tol:o.tol??0.011,hint:o.hint||"",traps:o.traps||[]});
function ch(label,correct,wrongs,hint=""){const opts=shuffle([correct,...wrongs]);return{type:"choice",label,options:opts,ans:opts.indexOf(correct),hint}}
const Q=(title,story,data,steps,recap)=>({title,story,data:data||"",steps,recap});

// ===== SVG =====
function svgHist(counts,labels,w=420,h=190){const m=Math.max(...counts),bw=(w-40)/counts.length;let s=`<svg viewBox="0 0 ${w} ${h}" class="svg" role="img" aria-label="Histogramme">`;
 counts.forEach((c,i)=>{const bh=(h-50)*c/m,x=30+i*bw,y=h-30-bh;s+=`<rect class="bar" x="${x+1}" y="${y}" width="${bw-2}" height="${bh}"/><text class="t" x="${x+bw/2}" y="${y-5}" text-anchor="middle">${c}</text><text class="t s" x="${x+bw/2}" y="${h-12}" text-anchor="middle">${labels[i]}</text>`});
 return s+`<line class="ax" x1="28" y1="${h-30}" x2="${w-8}" y2="${h-30}"/></svg>`}
function svgBox(min,q1,med,q3,max,w=440,h=110){const lo=Math.floor(min/5)*5-5,hi=Math.ceil(max/5)*5+5,X=v=>20+(w-40)*(v-lo)/(hi-lo);let s=`<svg viewBox="0 0 ${w} ${h}" class="svg" role="img" aria-label="Boîte à moustaches">`;
 s+=`<line class="ax" x1="${X(min)}" y1="45" x2="${X(q1)}" y2="45"/><line class="ax" x1="${X(q3)}" y1="45" x2="${X(max)}" y2="45"/><rect class="box" x="${X(q1)}" y="25" width="${X(q3)-X(q1)}" height="40"/><line class="med" x1="${X(med)}" y1="25" x2="${X(med)}" y2="65"/>`;
 [[min,"min"],[q1,"Q1"],[med,"méd."],[q3,"Q3"],[max,"max"]].forEach(([v,l],i)=>{const x=X(v);s+=`<line class="ax" x1="${x}" y1="${i==0||i==4?35:65}" x2="${x}" y2="${i==0||i==4?55:72}"/><text class="t s" x="${x}" y="${i%2?92:92}" text-anchor="middle">${l}</text><text class="t" x="${x}" y="${i%2?106:106}" text-anchor="middle">${f(v)}</text>`});
 return s+`</svg>`}
function svgCurves(ids,w=440,h=200){const xs=[];for(let x=-4;x<=4.001;x+=0.1)xs.push(x);
 const fn={A:x=>Math.exp(-Math.abs(x)*Math.SQRT2)/(Math.SQRT2/1)*1,B:x=>Math.exp(-x*x/2)/Math.sqrt(2*Math.PI),C:x=>{const a=Math.sqrt(3);return 1/(2*a)/(1+Math.pow(Math.abs(x)/a,28))}};
 const X=x=>20+(w-40)*(x+4)/8,Y=y=>h-25-(h-50)*y/0.75;let s=`<svg viewBox="0 0 ${w} ${h}" class="svg" role="img" aria-label="Trois courbes">`;
 const cls={A:"c1",B:"c2",C:"c3"};
 ids.forEach(id=>{const g=fn[id];const d=xs.map((x,i)=>(i?"L":"M")+X(x).toFixed(1)+" "+Y(g(x)).toFixed(1)).join(" ");s+=`<path class="curve ${cls[id]}" d="${d}"/>`});
 s+=`<line class="ax" x1="18" y1="${h-25}" x2="${w-18}" y2="${h-25}"/>`;
 return s+`</svg>`}
const legend3=`<div class="legend"><span><i class="k c1"></i>Courbe A</span><span><i class="k c2"></i>Courbe B</span><span><i class="k c3"></i>Courbe C</span></div>`;

// ===== MISSION 1 : vocabulaire =====
const VARS=[["Moyen de paiement (CB, espèces, chèque)","Qualitative","Ce sont des catégories, pas des nombres."],["Couleur du produit acheté","Qualitative","Une couleur est une catégorie."],["Niveau de satisfaction (insatisfait, neutre, satisfait)","Qualitative","Des catégories, même ordonnées."],["Ville de résidence du client","Qualitative","Des noms de villes : des catégories."],["Code postal du client","Qualitative","Piège : c'est un nombre, mais calculer une moyenne de codes postaux n'a aucun sens. C'est une catégorie."],["Nombre d'articles dans le panier","Quantitative discrète","On compte : 0, 1, 2, 3… Pas de valeur intermédiaire."],["Nombre de réclamations reçues dans le mois","Quantitative discrète","On compte des réclamations : valeurs entières."],["Nombre d'employés du magasin","Quantitative discrète","On compte des personnes : valeurs entières."],["Chiffre d'affaires mensuel du magasin (€)","Quantitative continue","Peut prendre n'importe quelle valeur dans un intervalle."],["Temps d'attente en caisse (minutes)","Quantitative continue","Une durée se mesure : 3 min, 3,5 min, 3,52 min…"],["Poids d'un colis (kg)","Quantitative continue","Un poids se mesure : toutes les valeurs sont possibles."],["Température du rayon frais (°C)","Quantitative continue","Une température se mesure."]];
const TYPES=["Qualitative","Quantitative discrète","Quantitative continue"];
function m1(){const qs=sample(VARS,4).map(([v,t,why])=>Q("Quel type de variable ?",`Un magasin étudie la variable suivante :<div class="callout"><b>${v}</b></div>`,"",[{type:"choice",label:"Cette variable est…",options:TYPES,ans:TYPES.indexOf(t),hint:"Se demande-t-on « quelle catégorie ? », « combien (on compte) ? » ou « combien (on mesure) ? »"}],`<p><b>${t}.</b> ${why}</p>`));
 const q5=pick([["200 clients d'une boutique, dont on note l'âge","les 200 clients","l'âge","un client"],["50 magasins d'une enseigne, dont on relève le chiffre d'affaires","les 50 magasins","le chiffre d'affaires","un magasin"]]);
 qs.push(Q("La population",`Une étude porte sur <b>${q5[0]}</b>.`,"",[ch("Que désigne la <b>population</b> ?",q5[1],[q5[2],q5[3],"le nombre 200 ou 50"],"La population, c'est l'ensemble de tous les individus étudiés."),ch("Que désigne la <b>variable</b> ?",q5[2],[q5[1],q5[3],"la moyenne des résultats"],"La variable, c'est la caractéristique observée sur chaque individu.")],`<p>Population : <b>${q5[1]}</b>. Individu : <b>${q5[3]}</b>. Variable : <b>${q5[2]}</b>.</p>`));
 qs.push(Q("Qualitative ou quantitative ?","Un étudiant dit : « Le numéro de rue du client est un nombre, donc c'est une variable quantitative. »","",[ch("A-t-il raison ?","Non : on ne peut pas calculer de moyenne sensée de numéros de rue, c'est une catégorie",["Oui : tout ce qui est un nombre est quantitatif","Oui : c'est une variable continue","Non : c'est une variable discrète"],"Une variable est quantitative si les opérations (somme, moyenne) ont un sens.")],"<p>Une variable est <b>quantitative</b> si la somme et la moyenne ont un sens. Un numéro de rue, un code postal ou un numéro de client sont des <b>codes</b> : variables qualitatives.</p>"));
 return qs}

// ===== MISSION 2 : effectifs et fréquences =====
const PRED=[["clients du magasin","ont utilisé la carte de fidélité"],["tickets de caisse","contiennent au moins un produit bio"],["commandes en ligne","ont été livrées en retard"],["visiteurs du site","ont ajouté un article au panier"]];
const freqTrap=(ni,N)=>[{val:ni/N,msg:"Tu as la fréquence en décimal. Multiplie par 100 pour l'exprimer en %."},{val:ni,msg:"Tu as redonné l'effectif. La fréquence est l'effectif ÷ l'effectif total."}];
function m2(){const qs=[];
 for(let t=0;t<2;t++){let N,k,ni;do{N=pick([20,25,40,50,100,200]);k=pick([5,10,15,20,25,30,35,40,45,60]);ni=N*k/100}while(!Number.isInteger(ni));const [s,p]=pick(PRED);
  qs.push(Q("Calculer une fréquence",`Sur <b>${N} ${s}</b>, <b>${ni}</b> ${p}.`,"",[num("Quelle est la fréquence, en % ?",k,{unit:"%",hint:"fréquence = effectif ÷ effectif total, puis × 100.",traps:freqTrap(ni,N)})],`<p>f = ${ni} ÷ ${N} = ${f(ni/N)} soit <b>${k} %</b>.</p>`))}
 {let N,k,ni;do{N=pick([40,50,80,200,500]);k=pick([10,15,20,25,30,40,45]);ni=N*k/100}while(!Number.isInteger(ni));const [s,p]=pick(PRED);
  qs.push(Q("Retrouver un effectif",`Parmi <b>${N} ${s}</b>, <b>${k} %</b> ${p}.`,"",[num("Combien de "+s+" cela représente-t-il ?",ni,{hint:"effectif = fréquence × effectif total (avec la fréquence en décimal : "+k+" % = "+f(k/100)+").",traps:[{val:k,msg:"Tu as redonné le pourcentage. Il faut le multiplier par l'effectif total."}]})],`<p>${f(k/100)} × ${N} = <b>${ni}</b>.</p>`))}
 {const N=pick([40,50]);const mods=sample(["Magasin","Site web","Application","Téléphone","Click & collect"],4);let c;do{c=[R(4,N/2),R(3,N/3),R(3,N/3),0];c[3]=N-sum(c.slice(0,3))}while(c[3]<3||c[3]>N/2);
  const big=Math.max(...c);const bi=c.indexOf(big);
  qs.push(Q("Lire un tableau d'effectifs",`Canal d'achat de <b>${N} clients</b>. L'effectif de la dernière modalité est caché.`,table(["Canal",...mods],[["Effectif",c[0],c[1],c[2],"?"]]),[num(`Quel est l'effectif de « ${mods[3]} » ?`,c[3],{hint:`La somme des effectifs doit valoir ${N}.`}),num("Quelle est la fréquence du canal « "+mods[bi]+" » (le plus utilisé), en % ?",big/N*100,{unit:"%",tol:0.06,hint:"fréquence = effectif ÷ "+N+" × 100",traps:freqTrap(big,N)}),num(`Quelle est la fréquence cumulée jusqu'à « ${mods[1]} » incluse, en % ?`,(c[0]+c[1])/N*100,{unit:"%",tol:0.06,hint:"Additionne les effectifs des deux premiers canaux, puis divise par "+N+"."})],`<p>Effectif manquant : ${N} − ${c[0]} − ${c[1]} − ${c[2]} = <b>${c[3]}</b>. Fréquence du plus utilisé : ${big} ÷ ${N} = ${f(big/N*100)} %. Cumulée : (${c[0]} + ${c[1]}) ÷ ${N} = ${f((c[0]+c[1])/N*100)} %.</p>`))}
 qs.push(Q("Somme des fréquences","Dans un tableau de fréquences, on additionne toutes les fréquences de la série.","",[ch("Que doit-on trouver ?","100 % (ou 1)",["Cela dépend de la série","L'effectif total","0 %"],"Les fréquences se partagent la totalité des individus.")],"<p>La somme des fréquences vaut toujours <b>100 %</b> (ou 1). C'est un excellent moyen de vérifier ses calculs.</p>"));
 qs.push(Q("Effectif ou fréquence ?","« 18 clients sur 60 ont acheté en promotion. »","",[ch("Quelle est la <b>fréquence</b> ?","30 %",["18","60","0,18 %"],"fréquence = 18 ÷ 60 = 0,3")],"<p>18 est l'effectif, 60 l'effectif total, et la fréquence est 18 ÷ 60 = 0,30 soit <b>30 %</b>.</p>"));
 return qs}

// ===== MISSION 3 : moyennes =====
function devs(n,span=8){let d;do{d=Array.from({length:n-1},()=>R(-span,span));d.push(-sum(d))}while(Math.abs(d[n-1])>span+3);return d}
function m3(){const qs=[];
 for(let t=0;t<2;t++){const n=pick([5,6]),m=R(12,40),v=shuffle(devs(n).map(d=>m+d));const [c,u]=pick([["ventes journalières d'un rayon","k€"],["paniers de clients","€"],["temps de préparation de commandes","min"]]);
  qs.push(Q("Moyenne simple",`${c[0].toUpperCase()+c.slice(1)} (${n} relevés) :`,chips(v,u),[num("Quelle est la <b>somme</b> des valeurs ?",n*m,{hint:"Additionne toutes les valeurs."}),num(`Quelle est la <b>moyenne</b> (en ${u}) ?`,m,{hint:`moyenne = somme ÷ nombre de valeurs (${n}).`,traps:[{val:n*m,msg:`Tu as donné la somme. Il reste à la diviser par ${n}.`}]})],`<p>Somme = ${v.map(f).join(" + ")} = ${f(n*m)}. Moyenne = ${f(n*m)} ÷ ${n} = <b>${f(m)} ${u}</b>.</p>`))}
 {const sets=[[4,3,2,1],[3,3,2,2],[5,2,2,1],[4,2,2,2],[3,3,3,1]];const co=pick(sets),no=co.map(()=>R(6,18)),mat=["Marketing","Statistiques","Anglais","Vente"],S=sum(no.map((x,i)=>x*co[i]));
  qs.push(Q("Moyenne pondérée",`Notes d'un étudiant et coefficients des matières :`,table(["Matière","Note /20","Coefficient"],mat.map((m,i)=>[m,no[i],co[i]])),[num("Calcule Σ (note × coefficient).",S,{hint:"Multiplie chaque note par son coefficient, puis additionne."}),num("Quelle est la somme des coefficients ?",10,{hint:"Additionne les coefficients."}),num("Quelle est la moyenne pondérée ?",S/10,{tol:0.06,hint:"moyenne pondérée = Σ(valeur × coef) ÷ Σ(coef)",traps:[{val:sum(no)/4,msg:"Tu as fait la moyenne simple. Ici les coefficients comptent."}]})],`<p>Σ(note × coef) = ${no.map((x,i)=>x+"×"+co[i]).join(" + ")} = ${S}. Σ coef = 10. Moyenne = ${S} ÷ 10 = <b>${f(S/10)}</b>.</p>`))}
 {let p,q,S,Qt,tries=0;do{p=sample([8,10,12,15,20,25,30],3);q=[pick([10,20,30,40]),pick([10,20,30,40]),pick([10,20,30])];S=sum(p.map((x,i)=>x*q[i]));Qt=sum(q);tries++}while(((S*10)%Qt!==0)&&tries<500);
  qs.push(Q("Prix moyen pondéré",`Ventes d'une gamme de produits :`,table(["Gamme","Prix (€)","Quantités vendues"],p.map((x,i)=>[["Entrée de gamme","Standard","Premium"][i],x,q[i]])),[num("Calcule Σ (prix × quantité), c'est le chiffre d'affaires total (€).",S,{hint:"Multiplie le prix par la quantité pour chaque gamme, puis additionne."}),num("Quel est le nombre total d'articles vendus ?",Qt,{hint:"Additionne les quantités."}),num("Quel est le prix moyen d'un article vendu (€) ?",S/Qt,{tol:0.06,hint:"prix moyen = CA total ÷ nombre d'articles",traps:[{val:sum(p)/3,msg:"Tu as fait la moyenne simple des 3 prix, sans tenir compte des quantités."}]})],`<p>CA = ${p.map((x,i)=>x+"×"+q[i]).join(" + ")} = ${f(S)} €. Articles = ${Qt}. Prix moyen = ${f(S)} ÷ ${Qt} = <b>${f(S/Qt)} €</b>.</p>`))}
 {const n=R(4,6),m=R(10,30),m2=m+R(1,4),v=m2*(n+1)-n*m;
  qs.push(Q("Une nouvelle valeur arrive",`La moyenne de ${n} ventes est de <b>${m} k€</b>. Une ${n+1}ᵉ vente est enregistrée : <b>${v} k€</b>.`,"",[num(`Quelle était la somme des ${n} premières ventes ?`,n*m,{hint:"somme = moyenne × nombre de valeurs"}),num("Quelle est la nouvelle somme ?",n*m+v,{hint:"Ajoute la nouvelle vente."}),num("Quelle est la nouvelle moyenne (k€) ?",m2,{hint:`nouvelle somme ÷ ${n+1}`})],`<p>Somme initiale ${n} × ${m} = ${n*m}. Nouvelle somme ${n*m} + ${v} = ${n*m+v}. Nouvelle moyenne ${n*m+v} ÷ ${n+1} = <b>${m2} k€</b>.</p>`))}
 qs.push(Q("Pourquoi pondérer ?","Un enseignant calcule la moyenne d'un module avec un examen (coef. 3) et un devoir (coef. 1).","",[ch("Pourquoi utiliser une moyenne pondérée ?","Parce que les valeurs n'ont pas toutes la même importance",["Parce qu'il y a moins de 10 valeurs","Pour trouver la valeur la plus fréquente","Parce que la moyenne simple est interdite"],"Pense à ce que signifie « coefficient 3 ».")],"<p>La moyenne pondérée sert quand chaque valeur a un <b>poids</b> différent (coefficients, quantités vendues, effectifs).</p>"));
 return qs}

// ===== MISSION 4 : médiane et quartiles =====
const distinct=(n,a=10,b=80)=>sample(Array.from({length:b-a+1},(_,i)=>a+i),n);
const showSorted=v=>"Valeurs triées : "+sorted(v).map(f).join(" · ");
function m4(){const qs=[];
 {const n=pick([7,9]),v=distinct(n),s=sorted(v),r=(n+1)/2;
  qs.push(Q("Médiane (série impaire)",`Délais de livraison en heures (<b>${n}</b> valeurs, dans le désordre) :`,chips(v,"h"),[num("Quel est le rang de la valeur centrale ?",r,{hint:"Avec n valeurs impaires, rang = (n + 1) ÷ 2. Pense à trier les valeurs d'abord."}),num("Quelle est la <b>médiane</b> (h) ?",s[r-1],{hint:showSorted(v)})],`<p>On trie : ${s.map(f).join(" · ")}. Rang ${r}. Médiane = <b>${s[r-1]} h</b>.</p>`))}
 {const n=pick([6,8]),v=distinct(n),s=sorted(v),a=s[n/2-1],b=s[n/2];
  qs.push(Q("Médiane (série paire)",`Paniers de <b>${n}</b> clients (€), dans le désordre :`,chips(v,"€"),[num("Quel est le rang de la première valeur centrale ?",n/2,{hint:`Avec ${n} valeurs, les valeurs centrales sont aux rangs ${n/2} et ${n/2+1}.`}),num("Quelle est la <b>médiane</b> (€) ?",(a+b)/2,{tol:0.06,hint:showSorted(v)+" — fais la moyenne des deux valeurs centrales.",traps:[{val:a,msg:"Avec un nombre pair de valeurs, la médiane est la moyenne des deux valeurs centrales."},{val:b,msg:"Avec un nombre pair de valeurs, la médiane est la moyenne des deux valeurs centrales."}]})],`<p>On trie : ${s.map(f).join(" · ")}. Valeurs centrales : ${a} et ${b}. Médiane = (${a} + ${b}) ÷ 2 = <b>${f((a+b)/2)} €</b>.</p>`))}
 for(const n of [8,12]){const v=distinct(n,10,90),s=sorted(v),h=n/2,q1=median(s.slice(0,h)),q3=median(s.slice(h)),md=median(s);
  qs.push(Q("Quartiles",`Ventes de <b>${n}</b> vendeurs (k€), dans le désordre :`,chips(v,"k€"),[num("Médiane (k€) ?",md,{tol:0.06,hint:showSorted(v)}),num(`<b>Q1</b> = médiane de la moitié inférieure (les ${h} plus petites valeurs) ?`,q1,{tol:0.06,hint:"Prends les "+h+" plus petites valeurs triées, puis leur médiane."}),num(`<b>Q3</b> = médiane de la moitié supérieure (les ${h} plus grandes valeurs) ?`,q3,{tol:0.06,hint:"Prends les "+h+" plus grandes valeurs triées, puis leur médiane."}),num("Écart interquartile Q3 − Q1 ?",q3-q1,{tol:0.06,hint:"Soustrais Q1 de Q3."})],`<p>${s.map(f).join(" · ")}<br>Médiane ${f(md)} ; Q1 ${f(q1)} ; Q3 ${f(q3)} ; écart interquartile ${f(q3-q1)}.</p>${svgBox(s[0],q1,md,q3,s[n-1])}<p class="note">Méthode des moitiés. Excel peut donner des quartiles légèrement différents selon la fonction utilisée.</p>`))}
 qs.push(Q("Que signifie Q1 ?","Pour des ventes de vendeurs, on lit : <b>Q1 = 24 k€</b>.","",[ch("Quelle phrase est correcte ?","25 % des vendeurs ont vendu 24 k€ ou moins",["24 % des vendeurs ont vendu moins de 25 k€","La plus petite vente est de 24 k€","La moyenne du premier quart est de 24 k€"],"Q1 est le premier quartile : il coupe la série à 25 %.")],"<p>Les quartiles découpent la série triée en 4 groupes de même effectif : 25 % des valeurs sont ≤ Q1, 50 % ≤ médiane, 75 % ≤ Q3.</p>"));
 {const a=sorted([R(5,20),R(5,20)])[0],mn=a,q1=mn+R(5,10),md=q1+R(4,10),q3=md+R(5,12),mx=q3+R(8,20);
  qs.push(Q("Lire une boîte à moustaches","Chiffres d'affaires mensuels de magasins (k€) :",svgBox(mn,q1,md,q3,mx),[num("Quelle est l'étendue (k€) ?",mx-mn,{hint:"étendue = max − min"}),num("Quel est l'écart interquartile (k€) ?",q3-q1,{hint:"Q3 − Q1 : la largeur de la boîte."}),ch("Quelle part des magasins est dans la boîte (entre Q1 et Q3) ?","50 %",["25 %","75 %","100 %"],"Entre Q1 et Q3, il y a la moitié centrale des valeurs.")],`<p>Étendue = ${mx} − ${mn} = ${mx-mn}. Écart interquartile = ${q3} − ${q1} = ${q3-q1}. La boîte contient les <b>50 %</b> centraux.</p>`))}
 return qs}

// ===== MISSION 5 : mode et choix de l'indicateur =====
const IND=["La moyenne simple","La moyenne pondérée","La médiane","Le mode"];
const SCEN=[["Un magasin de chaussures doit décider <b>quelle pointure commander en priorité</b>.","Le mode","La pointure la plus vendue, c'est la valeur la plus fréquente : le mode."],["Les salaires de la boutique : 1 800, 1 900, 2 000, 2 000 et <b>9 500 €</b> (le gérant). On veut le salaire typique.","La médiane","Une valeur extrême tire la moyenne vers le haut. La médiane n'est pas sensible à cette valeur."],["Le module de statistiques compte <b>l'examen pour 60 %</b> et les devoirs pour 40 %. On calcule la note finale.","La moyenne pondérée","Les composantes n'ont pas le même poids."],["Un rayon a vendu 120, 118, 122, 119 et 121 unités sur 5 jours très réguliers. On veut le niveau de ventes quotidien.","La moyenne simple","Données régulières, sans valeur extrême : la moyenne résume bien."],["Un restaurateur veut connaître <b>le plat le plus commandé</b>.","Le mode","Le plat le plus commandé est la modalité la plus fréquente. C'est le seul indicateur utilisable pour une variable qualitative."],["Le prix moyen d'un article, sachant que <b>les quantités vendues diffèrent selon les gammes</b>.","La moyenne pondérée","Chaque prix doit compter à hauteur des quantités vendues."]];
function m5(){const qs=[];
 {const sz=[38,39,40,41,42,43];let c;do{c=sz.map(()=>R(2,14));c[R(0,5)]+=0}while(sum(c)>50);let d=50-sum(c);c[R(0,5)]+=d;const mx=Math.max(...c);if(c.filter(x=>x===mx).length>1){c[c.indexOf(mx)]+=0;}
  // garantir mode unique
  const mxi=c.indexOf(Math.max(...c));if(c.filter(x=>x===c[mxi]).length>1){c[mxi]+=1;const j=c.findIndex((x,i)=>i!==mxi&&x>1);c[j]-=1}
  const big=Math.max(...c),bi=c.indexOf(big);
  qs.push(Q("Trouver le mode",`Pointures vendues en une semaine (<b>50 paires</b>) :`,table(["Pointure",...sz],[["Paires vendues",...c]]),[num("Quelle est la pointure modale (le mode) ?",sz[bi],{hint:"Le mode est la valeur qui a le plus grand effectif.",traps:[{val:big,msg:"Tu as donné l'effectif. Le mode est la pointure, pas le nombre de paires."}]}),num("Quelle part des ventes représente-t-elle, en % ?",big*2,{unit:"%",hint:"fréquence = effectif ÷ 50 × 100",traps:[{val:big/50,msg:"Multiplie par 100 pour obtenir un pourcentage."}]})],`<p>Le mode est <b>${sz[bi]}</b> (${big} paires). Fréquence = ${big} ÷ 50 = ${f(big*2)} %.</p>`))}
 {const m=R(14,20),base=[m-4,m-2,m,m+2,m+4],delta=5*R(6,12),nv=[...base.slice(0,4),base[4]+delta],nm=m+delta/5;
  qs.push(Q("Une valeur extrême",`Paniers de 5 clients (€) :`,chips(base,"€")+`<p class="note">Un client très aisé passe en caisse : le dernier panier devient <b>${nv[4]} €</b> (au lieu de ${base[4]} €).</p>`,[num("Moyenne initiale (€) ?",m,{hint:"somme ÷ 5"}),num("Nouvelle moyenne (€) ?",nm,{hint:"Recalcule la somme avec "+nv[4]+" puis divise par 5."}),num("Nouvelle médiane (€) ?",m,{hint:"Trie les 5 valeurs : la médiane est la 3ᵉ."})],`<p>La moyenne passe de ${m} à <b>${f(nm)} €</b> alors que la médiane reste à <b>${m} €</b>. La moyenne est sensible aux valeurs extrêmes, la médiane beaucoup moins.</p>`))}
 sample(SCEN,3).forEach(([s,a,w])=>qs.push(Q("Quel indicateur choisir ?",s,"",[ch("Quel indicateur est le plus adapté ?",a,IND.filter(x=>x!==a),"Demande-toi : y a-t-il des poids, des valeurs extrêmes, ou une catégorie ?")],`<p><b>${a}.</b> ${w}</p>`)));
 qs.push(Q("Sensibilité","Parmi la moyenne, la médiane et le mode, un seul indicateur bouge beaucoup quand une valeur extrême apparaît.","",[ch("Lequel ?","La moyenne",["La médiane","Le mode","Aucun des trois"],"Souviens-toi de l'exemple des paniers.")],"<p>La <b>moyenne</b> utilise toutes les valeurs, y compris les extrêmes. La médiane et le mode y sont peu sensibles.</p>"));
 return qs}

// ===== MISSION 6 : dispersion =====
function varSet(){for(let t=0;t<4000;t++){const d=Array.from({length:4},()=>R(-7,7));d.push(-sum(d));if(Math.abs(d[4])>8)continue;const S=sum(d.map(x=>x*x));if(S%5)continue;const v=S/5,s=Math.sqrt(v);if(Number.isInteger(s)&&s>=2&&s<=5&&new Set(d).size>=4)return d}return [-3,-1,0,1,3]}
function m6(){const qs=[];
 {const v=distinct(6,8,60);qs.push(Q("Étendue",`Nombre de visites par jour dans un magasin :`,chips(v),[num("Quelle est l'<b>étendue</b> ?",Math.max(...v)-Math.min(...v),{hint:"étendue = valeur max − valeur min"}),ch("Quel est le défaut de l'étendue ?","Elle ne dépend que de deux valeurs (la plus petite et la plus grande)",["Elle est toujours négative","Elle ne se calcule que pour des séries paires","Elle dépend de toutes les valeurs"],"Quelles valeurs entrent dans le calcul ?")],`<p>Étendue = ${Math.max(...v)} − ${Math.min(...v)} = <b>${Math.max(...v)-Math.min(...v)}</b>. Elle est facile à calculer mais très sensible aux valeurs extrêmes.</p>`))}
 for(let t=0;t<2;t++){const m=R(12,30),d=varSet(),v=shuffle(d.map(x=>m+x)),S=sum(d.map(x=>x*x)),va=S/5,sd=Math.sqrt(va);
  qs.push(Q("Variance et écart type",`Ventes de 5 vendeurs (k€) :`,chips(v,"k€")+`<p class="note">Formules de la population : on divise par n.</p>`,[num("Quelle est la moyenne ?",m,{hint:"somme ÷ 5"}),num("Calcule Σ (xᵢ − x̄)².",S,{hint:"Pour chaque valeur : écart à la moyenne, puis au carré. Additionne.",traps:[{val:0,msg:"La somme des écarts simples vaut 0. Il faut d'abord les mettre au carré."}]}),num("Quelle est la variance ?",va,{hint:"variance = Σ(xᵢ − x̄)² ÷ n",traps:[{val:S/4,msg:"Dans ce cours, on divise par n (population), pas par n − 1."}]}),num("Quel est l'écart type ?",sd,{hint:"écart type = √variance",traps:[{val:va,msg:"C'est la variance. L'écart type est sa racine carrée."}]})],`${table(["xᵢ","xᵢ − x̄","(xᵢ − x̄)²"],v.map((x,i)=>[x,f(x-m),f((x-m)**2)]))}<p>Σ = ${S}. Variance = ${S} ÷ 5 = <b>${f(va)}</b>. Écart type = √${f(va)} = <b>${f(sd)} k€</b>.</p>`))}
 {const sa=pick([3,4,5]),sb=sa+pick([3,4,5]),sw=Math.random()<.5;
  qs.push(Q("Quelle série est la plus régulière ?",`Deux magasins ont le même chiffre d'affaires moyen de 50 k€ par mois.`,table(["","Magasin A","Magasin B"],[["Écart type (k€)",sw?sa:sb,sw?sb:sa]]),[ch("Quel magasin a les ventes les plus régulières ?",sw?"Le magasin A":"Le magasin B",[sw?"Le magasin B":"Le magasin A","Ils sont identiques","On ne peut pas savoir"],"Plus l'écart type est petit, plus les valeurs sont proches de la moyenne."),num("Quelle est la variance du magasin le plus régulier ?",sa*sa,{hint:"variance = (écart type)²"})],`<p>L'écart type le plus faible (${sa}) indique les ventes les plus <b>regroupées autour de la moyenne</b>. Variance = ${sa}² = <b>${sa*sa}</b>.</p>`))}
 qs.push(Q("Tous les prix augmentent de 2 €","Une enseigne augmente tous ses prix de 2 €. Avant : moyenne 20 €, écart type 4 €.","",[ch("Que deviennent la moyenne et l'écart type ?","Moyenne : 22 € ; écart type : 4 € (inchangé)",["Moyenne : 22 € ; écart type : 6 €","Moyenne : 20 € ; écart type : 4 €","Moyenne : 22 € ; écart type : 8 €"],"Décaler toutes les valeurs de la même quantité change-t-il leur écartement ?")],"<p>Ajouter la même quantité à toutes les valeurs <b>décale</b> la moyenne mais ne change pas la dispersion.</p>"));
 qs.push(Q("Tous les prix doublent","Tous les prix sont multipliés par 2. Avant : moyenne 20 €, écart type 4 €.","",[ch("Que deviennent la moyenne et l'écart type ?","Moyenne : 40 € ; écart type : 8 €",["Moyenne : 40 € ; écart type : 4 €","Moyenne : 22 € ; écart type : 6 €","Moyenne : 40 € ; écart type : 16 €"],"Les écarts sont multipliés par 2 aussi.")],"<p>Multiplier toutes les valeurs par 2 multiplie la moyenne <b>et l'écart type</b> par 2 (et la variance par 4).</p>"));
 return qs}

// ===== MISSION 7 : forme =====
function skewQ(kind){const D={right:[[14,11,7,4,2,2],["0-20","20-40","40-60","60-80","80-100","100-120"],"montants de tickets de caisse (€)","À droite (skewness positif)","Moyenne > médiane","Les gros paniers étirent la distribution vers la droite et tirent la moyenne vers le haut."],left:[[1,2,4,8,14,11],["50-60","60-70","70-80","80-90","90-100","100-110"],"pourcentages d'objectif atteint par des vendeurs","À gauche (skewness négatif)","Moyenne < médiane","Quelques vendeurs très en retard étirent la distribution vers la gauche. L'indicateur est plafonné autour de 100 %."]}[kind];
 const sides=["À droite (skewness positif)","À gauche (skewness négatif)","Symétrique (skewness proche de 0)"];
 return Q("Lire l'asymétrie (skewness)",`Histogramme des ${D[2]} :`,svgHist(D[0],D[1]),[ch("Où se trouve la <b>queue</b> de la distribution ?",D[3],sides.filter(x=>x!==D[3]),"La queue est le côté où quelques valeurs s'étirent loin du gros des données."),ch("Que peut-on dire de la moyenne et de la médiane ?",D[4],["Moyenne > médiane","Moyenne < médiane","Moyenne = médiane"].filter(x=>x!==D[4]).concat(D[4]==="Moyenne = médiane"?[]:[]),"La moyenne est attirée par la queue.")],`<p>Queue : <b>${D[3]}</b>. ${D[4]}. ${D[5]}</p><p class="note">Le signe du skewness indique le côté de la queue, pas l'endroit où se trouve la majorité des valeurs.</p>`)}
function m7(){const qs=[skewQ("right"),skewQ("left")];
 qs.push(Q("Lire le kurtosis","Trois distributions ont la même moyenne et le même écart type.",svgCurves(["A","B","C"])+legend3,[ch("Laquelle produit <b>le plus souvent des valeurs extrêmes</b> ?","La courbe A",["La courbe B","La courbe C","Elles en produisent autant"],"Regarde les queues, loin du centre : laquelle reste au-dessus de la courbe B ?"),ch("Quelle courbe a un kurtosis <b>négatif</b> (Excel) ?","La courbe C",["La courbe A","La courbe B","Aucune"],"Le kurtosis est négatif quand il y a moins de valeurs extrêmes que la loi normale (courbe B).")],`<p>A : queues lourdes, kurtosis positif (pics ou creux exceptionnels, ex. Black Friday). B : loi normale (kurtosis 0). C : presque pas d'extrêmes, kurtosis négatif.</p><p class="note">« Pointu » ou « aplati » est une image trompeuse : c'est le poids des queues qui compte.</p>`));
 {const m=pick([100,200,500]),s=pick([10,20,25]);qs.push(Q("La loi normale : 95 %",`Les dépenses d'un client suivent une loi normale de moyenne <b>${m} €</b> et d'écart type <b>${s} €</b>.`,"",[num("Borne basse de l'intervalle contenant environ 95 % des clients (moyenne − 2σ) ?",m-2*s,{hint:`${m} − 2 × ${s}`}),num("Borne haute (moyenne + 2σ) ?",m+2*s,{hint:`${m} + 2 × ${s}`})],`<p>Environ <b>95 %</b> des valeurs sont dans [m − 2σ ; m + 2σ] = [${m-2*s} ; ${m+2*s}].</p><p class="note">Repères : 68 % dans m ± σ, 95 % dans m ± 2σ, 99,7 % dans m ± 3σ.</p>`))}
 {const m=pick([60,80,120]),s=pick([5,10,15]);qs.push(Q("La loi normale : 68 %",`Le temps de préparation d'une commande suit une loi normale de moyenne <b>${m} min</b> et d'écart type <b>${s} min</b>.`,"",[num("Borne basse de l'intervalle contenant environ 68 % des commandes ?",m-s,{hint:`${m} − ${s}`}),num("Borne haute ?",m+s,{hint:`${m} + ${s}`})],`<p>Environ <b>68 %</b> des commandes sont dans [m − σ ; m + σ] = [${m-s} ; ${m+s}] min.</p>`))}
 qs.push(Q("Interpréter une sortie Excel","Excel donne <b>COEFFICIENT.ASYMETRIE = 1,8</b> pour les délais de livraison d'une enseigne.","",[ch("Quelle phrase est correcte ?","Quelques livraisons très longues tirent la distribution vers la droite ; la médiane décrit mieux un délai typique",["La plupart des livraisons sont très longues","La distribution est parfaitement symétrique","1,8 % des livraisons sont en retard"],"Skewness positif : queue à droite.")],"<p>Skewness positif = queue à droite : <b>quelques délais très longs</b> font monter la moyenne au-dessus de la médiane.</p>"));
 return qs}

const MISSIONS=[
 {id:"m1",n:1,title:"Le vocabulaire du statisticien",short:"Population, variable, types de données",build:m1,intro:`<ul><li><b>Population</b> : tous les individus étudiés. <b>Individu</b> : un élément. <b>Variable</b> : la caractéristique observée.</li><li><b>Qualitative</b> : des catégories (couleur, ville, code postal).</li><li><b>Quantitative discrète</b> : on compte (valeurs entières). <b>Continue</b> : on mesure (toute valeur possible).</li></ul><p class="ex">Test rapide : peut-on faire une moyenne sensée ? Si oui, c'est quantitatif.</p>`},
 {id:"m2",n:2,title:"Effectifs et fréquences",short:"Compter, puis passer en pourcentage",build:m2,intro:`<ul><li><b>Effectif</b> nᵢ : nombre d'individus d'une modalité. <b>Effectif total</b> N.</li><li><b>Fréquence</b> fᵢ = nᵢ ÷ N (× 100 pour des %).</li><li>La somme des fréquences fait toujours 100 %.</li></ul><p class="ex">Exemple : 12 clients sur 48 → 12 ÷ 48 = 0,25 = 25 %.</p>`},
 {id:"m3",n:3,title:"Les moyennes",short:"Moyenne simple et moyenne pondérée",build:m3,intro:`<ul><li><b>Moyenne simple</b> = somme des valeurs ÷ nombre de valeurs.</li><li><b>Moyenne pondérée</b> = Σ(valeur × poids) ÷ Σ(poids).</li></ul><p class="ex">Exemple : notes 12 (coef. 3) et 16 (coef. 1) → (12×3 + 16×1) ÷ 4 = 13.</p>`},
 {id:"m4",n:4,title:"Médiane et quartiles",short:"Trier, couper en deux, couper en quatre",build:m4,intro:`<ul><li>D'abord, on <b>trie</b> les valeurs par ordre croissant.</li><li><b>Médiane</b> : la valeur du milieu (rang (n+1) ÷ 2 si n est impair ; moyenne des deux valeurs centrales si n est pair).</li><li><b>Q1</b> : médiane de la moitié inférieure. <b>Q3</b> : médiane de la moitié supérieure.</li><li>Écart interquartile = Q3 − Q1.</li></ul><p class="ex">Exemple : 3, 5, 8, 10 → médiane = (5 + 8) ÷ 2 = 6,5.</p>`},
 {id:"m5",n:5,title:"Mode et choix de l'indicateur",short:"Quel indicateur pour quelle situation ?",build:m5,intro:`<ul><li><b>Mode</b> : la valeur (ou modalité) la plus fréquente.</li><li><b>Moyenne</b> : sensible aux valeurs extrêmes. <b>Médiane</b> : résistante.</li><li>Poids différents → moyenne pondérée. Catégories → mode.</li></ul><p class="ex">Salaires 1 800 · 1 900 · 2 000 · 2 000 · 9 500 : la médiane (2 000) décrit mieux que la moyenne (3 440).</p>`},
 {id:"m6",n:6,title:"Mesurer la dispersion",short:"Étendue, variance, écart type",build:m6,intro:`<ul><li><b>Étendue</b> = max − min.</li><li><b>Variance</b> = Σ(xᵢ − x̄)² ÷ n.</li><li><b>Écart type</b> σ = √variance : plus il est petit, plus les valeurs sont regroupées.</li></ul><p class="ex">Exemple : 4, 6, 8 → x̄ = 6 ; écarts² : 4, 0, 4 ; variance = 8 ÷ 3 ≈ 2,67.</p>`},
 {id:"m7",n:7,title:"La forme d'une distribution",short:"Loi normale, skewness, kurtosis",build:m7,intro:`<ul><li><b>Loi normale</b> : courbe en cloche. Environ 68 % des valeurs dans m ± σ, 95 % dans m ± 2σ.</li><li><b>Skewness</b> : le signe indique le côté de la queue (+ à droite, − à gauche).</li><li><b>Kurtosis</b> : fréquence des valeurs extrêmes (0 = loi normale). Ces deux indicateurs se calculent sous Excel et s'interprètent.</li></ul>`}
];
function bossBuild(){const pool=MISSIONS.map(m=>m.build());const g=i=>pick(pool[i]);return [g(0),g(1),g(2),g(3),g(4),g(5),g(6),pick(pool[5])]}


// ===== CONFIGURATION (à modifier) =====
// Colle ici l'adresse de ton application web Google Apps Script (voir le guide). Laisse "" pour désactiver l'envoi des scores.
const ENDPOINT="https://script.google.com/macros/s/AKfycby3F8PtypAmtlR8OTYyM72tx-K_3Aa21N6BGEoi2g7Vnum6G_m91b0mCJxUjt7MguLIvQ/exec";
// Code de classe facultatif : doit être identique dans le script Google (laisser "" si inutile).
const CLASS_CODE="B1";
// Groupes proposés aux étudiants, par exemple ["B1-A","B1-B"]. Laisser [] pour un champ libre.
const GROUPS=[];
let UID="";try{UID=localStorage.getItem("stats-au-comptoir-id")||"";if(!UID){UID="s"+Math.random().toString(36).slice(2,10)+Date.now().toString(36);localStorage.setItem("stats-au-comptoir-id",UID)}}catch(e){UID="s"+Math.random().toString(36).slice(2,10)}
// ===== Interface =====
const KEY="stats-au-comptoir-v1";
let prog={best:{}};
try{prog=JSON.parse(localStorage.getItem(KEY))||{best:{}};if(!prog.best)prog.best={}}catch(e){prog={best:{}}}
const save=()=>{try{localStorage.setItem(KEY,JSON.stringify(prog))}catch(e){}};
const $app=document.getElementById("app");
const esc=s=>String(s).replace(/[&<>"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]));
const DB=ENDPOINT?{}:null,TEACHER=false;let DL=null,unsub=null;
const NKEY="stats-au-comptoir-name";let NAME="",GRP="",NOSYNC=false;
try{NAME=localStorage.getItem(NKEY)||"";GRP=localStorage.getItem(NKEY+"-grp")||"";NOSYNC=localStorage.getItem(NKEY+"-off")==="1"}catch(e){}

const S={rows:null,sync:"",view:"home",mid:null,qs:[],qi:0,si:0,att:0,hint:false,wrong:[],msg:"",done:false,steps:[],log:[],pts:0,max:0,reveal:false,confirmReset:false,help:false};
const BOSS={id:"boss",n:"★",title:"Le Rapport au directeur",short:"8 questions mêlant toutes les missions",build:bossBuild,intro:`<p>Dernière épreuve : une question de chaque mission, tirée au hasard. Tu as tout ce qu'il faut : l'aide-mémoire reste accessible en haut de l'écran.</p><p class="ex">Objectif : 3 étoiles pour devenir Directeur·rice des données.</p>`};
const starsFor=(s,m)=>{const p=m?s/m:0;return p>=.9?3:p>=.7?2:p>=.5?1:0};
const bestOf=id=>prog.best[id]||{score:0,max:0,stars:0};
const starStr=n=>"★".repeat(n)+"☆".repeat(3-n);
const total=()=>{let s=0,m=0;MISSIONS.forEach(x=>{const b=bestOf(x.id);s+=b.score;m+=b.max});const b=bestOf("boss");s+=b.score;m+=b.max;return{s,m}};
const doneCount=()=>MISSIONS.filter(x=>bestOf(x.id).stars>=1).length;
const LEVELS=["Stagiaire","Assistant·e analyste","Analyste","Responsable données","Directeur·rice des données"];
function level(){const all=MISSIONS.length*0+1;let pts=0,mx=0;MISSIONS.forEach(m=>{pts+=bestOf(m.id).stars});const bs=bestOf("boss").stars;const stars=pts+bs; // /24
 return stars>=22?4:stars>=16?3:stars>=9?2:stars>=3?1:0}
const parse=s=>{s=String(s).replace(/[\s  ]/g,"").replace(",",".").replace(/k€|min|[%€h]/g,"").replace("−","-");return /^-?\d*\.?\d+$/.test(s)?parseFloat(s):NaN};
const modOf=id=>id==="boss"?BOSS:MISSIONS.find(m=>m.id===id);

function header(){const t=total();return`<header class="top"><button class="brand" data-act="home" aria-label="Retour à l'accueil"><span class="logo" aria-hidden="true">€</span><span>Stats au Comptoir</span></button><div class="top-r">${TEACHER?`<button class="btn sm" data-act="teacher">Suivi de la classe</button>`:""}<span class="pill mono" title="Points de chiffre d'affaires">${t.s} pts</span><button class="btn ghost sm" data-act="help">Aide-mémoire</button></div></header>`}
function trackCard(){
 if(!DB)return`<p class="note trk">Tes scores sont gardés sur cet appareil.</p>`;
 if(!NAME&&!NOSYNC)return`<form class="trk nameform" data-form="name" autocomplete="off"><p class="fh"><b>Avant de commencer</b><br><span class="note">Indique ton prénom, ton nom et ton groupe. Ton enseignant verra ces informations et tes scores (personne d'autre).</span></p><label class="fl" for="nm">Prénom et nom</label><input id="nm" class="inp wide" maxlength="40" placeholder="Prénom Nom" value="${esc(NAME)}"/><label class="fl" for="grp">Groupe</label>${GROUPS.length?`<select id="grp" class="inp wide">${GROUPS.map(g=>`<option ${g===GRP?"selected":""}>${esc(g)}</option>`).join("")}</select>`:`<input id="grp" class="inp wide" maxlength="20" placeholder="Ex. B1-A" value="${esc(GRP)}"/>`}<div class="ansrow"><button class="btn" type="submit">Enregistrer</button><button type="button" class="link" data-act="nosync">Jouer sans transmettre mes scores</button></div></form>`;
 if(NOSYNC)return`<p class="note trk">Tes scores ne sont pas transmis à ton enseignant. <button class="link" data-act="enable">Les transmettre</button></p>`;
 return`<p class="note trk">Scores transmis à ton enseignant sous le nom <b>${esc(NAME)}</b>${GRP?" ("+esc(GRP)+")":""}${S.sync==="ok"?" (envoi effectué)":S.sync==="err"?" (envoi impossible pour l'instant)":""} · <button class="link" data-act="rename">Changer de nom</button></p>`}
function home(){const lv=level();const t=total();
 const cards=MISSIONS.map(m=>{const b=bestOf(m.id);return`<button class="mcard" data-act="intro" data-id="${m.id}"><span class="mnum mono">${m.n}</span><span class="mtxt"><b>${m.title}</b><small>${m.short}</small></span><span class="mst ${b.stars?"on":""}" aria-label="${b.stars} étoiles sur 3">${starStr(b.stars)}</span></button>`}).join("");
 const open=doneCount()>=4,bb=bestOf("boss");
 return`<section class="hero"><p class="eyebrow">Statistiques commerciales · Topics 1 et 2</p><h1>Bienvenue au Comptoir</h1><p class="lead">Tu es analyste stagiaire dans une enseigne de magasins. Chaque mission te fait gagner des points de chiffre d'affaires. Les calculs sont guidés étape par étape, et chaque erreur te montre comment corriger.</p>
 <div class="status"><div><span class="eyebrow">Ton grade</span><div class="grade">${LEVELS[lv]}</div></div><div class="bar-wrap" aria-hidden="true"><div class="bar-in" style="width:${Math.min(100,(doneCount()+(bb.stars?1:0))/8*100)}%"></div></div></div></section>
 ${trackCard()}<h2 class="sec">Les missions</h2><div class="mlist">${cards}</div>
 <button class="mcard boss ${open?"":"locked"}" ${open?`data-act="intro" data-id="boss"`:"disabled"}><span class="mnum mono">★</span><span class="mtxt"><b>${BOSS.title}</b><small>${open?BOSS.short:"Se débloque après 4 missions avec au moins 1 étoile ("+doneCount()+"/4)"}</small></span><span class="mst ${bb.stars?"on":""}">${starStr(bb.stars)}</span></button>
 <p class="foot-note">Les nombres changent à chaque partie : tu peux rejouer une mission autant de fois que tu veux pour t'entraîner. Ta progression est gardée sur cet appareil. ${ENDPOINT?`<button class="link" data-act="teacher">Espace enseignant</button> · `:""}${t.s?`<button class="link" data-act="reset">${S.confirmReset?"Cliquer à nouveau pour tout effacer":"Effacer ma progression"}</button>`:""}</p>`}
function intro(){const m=modOf(S.mid);return`<button class="link back" data-act="home">← Retour aux missions</button><section class="ticket"><div class="perf mono">MISSION ${m.n}</div><h1>${m.title}</h1><h2 class="sec2">Le cours en 30 secondes</h2><div class="course">${m.intro}</div><div class="actions"><button class="btn" data-act="start" data-id="${m.id}">Commencer la mission</button></div></section>`}
function quiz(){const q=S.qs[S.qi],m=modOf(S.mid);
 let steps="";
 S.steps.forEach((s,i)=>{steps+=`<div class="step solved"><span class="tick" aria-hidden="true">✓</span><div><div class="slabel">${q.steps[i].label}</div><div class="sans mono">${s.shown}${s.pts===0?" <em>(réponse révélée)</em>":""}</div></div></div>`});
 if(!S.done){const st=q.steps[S.si];
  steps+=`<div class="step current"><div class="slabel">${S.si+1}/${q.steps.length} · ${st.label}</div>`;
  if(st.type==="num")steps+=`<form class="ansrow" data-form="num" autocomplete="off"><input id="ans" class="inp mono" inputmode="decimal" aria-label="Ta réponse" placeholder="Ta réponse"/>${st.unit?`<span class="unit">${st.unit}</span>`:""}<button class="btn" type="submit">Vérifier</button></form>`;
  else steps+=`<div class="opts">${st.options.map((o,i)=>`<button class="opt ${S.wrong.includes(i)?"bad":""}" data-act="pick" data-i="${i}" ${S.wrong.includes(i)?"disabled":""}>${o}</button>`).join("")}</div>`;
  steps+=`<div class="fb" aria-live="polite">${S.msg}</div>`;
  if(S.hint&&st.hint)steps+=`<div class="hint"><b>Indice</b> ${st.hint}</div>`;
  steps+=`<div class="tools">${!S.hint&&st.hint?`<button class="link" data-act="hint">Afficher l'indice (réponse moins bien payée)</button>`:""}${S.att>=2?`<button class="link" data-act="reveal">Voir la réponse</button>`:""}</div></div>`}
 const recap=S.done?`<div class="recap"><b>Correction</b>${q.recap}</div><div class="actions"><button class="btn" data-act="next" id="nextbtn">${S.qi+1<S.qs.length?"Question suivante":"Voir mon résultat"}</button></div>`:"";
 return`<div class="qbar"><button class="link" data-act="home">← Quitter</button><div class="prog" aria-label="Question ${S.qi+1} sur ${S.qs.length}">${S.qs.map((_,i)=>`<i class="${i<S.qi?"d":i===S.qi?"c":""}"></i>`).join("")}</div><span class="mono sc">${S.pts} pts</span></div>
 <section class="ticket"><div class="perf mono">${m.id==="boss"?"RAPPORT":"MISSION "+m.n} · QUESTION ${S.qi+1}/${S.qs.length}</div><h1 class="qt">${q.title}</h1><p class="story">${q.story}</p>${q.data?`<div class="data">${q.data}</div>`:""}<div class="steps">${steps}</div>${recap}</section>`}
function result(){const m=modOf(S.mid),st=starsFor(S.pts,S.max),b=bestOf(S.mid);
 const msg=st===3?"Excellent travail. Tu maîtrises cette mission.":st===2?"Très bien. Encore un petit effort pour la 3ᵉ étoile.":st===1?"C'est un bon début. Relis le cours en 30 secondes et rejoue la mission.":"Pas de panique : relis le cours et rejoue, les nombres vont changer.";
 return`<section class="ticket center"><div class="perf mono">RÉSULTAT · ${m.id==="boss"?"RAPPORT":"MISSION "+m.n}</div><h1>${m.title}</h1><div class="bigstars" aria-label="${st} étoiles sur 3">${starStr(st)}</div><p class="score mono">${S.pts} / ${S.max} pts</p><p>${msg}</p>${S.pts>=b.score?`<p class="note">Meilleur score enregistré.</p>`:`<p class="note">Ton meilleur score reste ${b.score} pts.</p>`}
 <div class="rlist">${S.log.map((l,i)=>`<div class="rrow"><span>${S.qs[i].title}</span><span class="mono ${l.e===l.m?"g":l.e===0?"r":"o"}">${l.e}/${l.m}</span></div>`).join("")}</div>
 <div class="actions"><button class="btn" data-act="start" data-id="${m.id}">Rejouer (nouveaux nombres)</button><button class="btn ghost" data-act="home">Retour aux missions</button></div></section>`}
const HELP=`<h2>Aide-mémoire</h2><div class="hgrid"><div><h3>Données</h3><p>Fréquence = effectif ÷ effectif total (× 100 pour des %).</p><p>Qualitative : catégories. Quantitative discrète : on compte. Continue : on mesure.</p></div><div><h3>Position</h3><p>Moyenne = Σ valeurs ÷ n.</p><p>Moyenne pondérée = Σ(valeur × poids) ÷ Σ poids.</p><p>Médiane : valeur du milieu (valeurs triées). Mode : la plus fréquente.</p><p>Q1, Q3 : médianes des deux moitiés.</p></div><div><h3>Dispersion</h3><p>Étendue = max − min.</p><p>Variance = Σ(xᵢ − x̄)² ÷ n.</p><p>Écart type σ = √variance.</p></div><div><h3>Forme</h3><p>Loi normale : 68 % dans m ± σ, 95 % dans m ± 2σ.</p><p>Skewness &gt; 0 : queue à droite (moyenne &gt; médiane). &lt; 0 : queue à gauche.</p><p>Kurtosis &gt; 0 : extrêmes fréquents. &lt; 0 : extrêmes rares.</p></div></div>`;
function render(){let body=S.view==="home"?home():S.view==="intro"?intro():S.view==="quiz"?quiz():S.view==="teacher"?teacher():result();
 $app.innerHTML=header()+`<main>${body}</main>`+(S.help?`<div class="overlay" data-act="closehelp"><div class="sheet" role="dialog" aria-label="Aide-mémoire" data-stop="1">${HELP}<button class="btn" data-act="closehelp">Fermer</button></div></div>`:"");
 requestAnimationFrame(()=>{const a=document.getElementById("ans");if(a)a.focus();else if(S.done){const n=document.getElementById("nextbtn");if(n)n.focus()}})}
function go(v){if(v!=="teacher"&&unsub){unsub();unsub=null}S.view=v;S.help=false;window.scrollTo(0,0);render()}
function startMission(id){const m=modOf(id);S.mid=id;S.qs=m.build();S.qi=0;S.pts=0;S.max=S.qs.reduce((a,q)=>a+q.steps.length*10,0);S.log=[];resetQ();go("quiz")}
function resetQ(){S.si=0;S.att=0;S.hint=false;S.wrong=[];S.msg="";S.done=false;S.steps=[];S.qEarned=0}
function award(pts,shown){const q=S.qs[S.qi];S.steps.push({shown,pts});S.pts+=pts;S.qEarned+=pts;S.si++;S.att=0;S.hint=false;S.wrong=[];S.msg="";
 if(S.si>=q.steps.length){S.done=true;S.log.push({e:S.qEarned,m:q.steps.length*10})}}
const pointsFor=()=>S.att===0&&!S.hint?10:S.att<=1?5:3;
function shownOf(st){return st.type==="num"?f(st.ans)+(st.unit?" "+st.unit:""):st.options[st.ans]}
function finish(){const m=modOf(S.mid),b=bestOf(S.mid);if(S.pts>b.score){prog.best[S.mid]={score:S.pts,max:S.max,stars:starsFor(S.pts,S.max)}}else if(!prog.best[S.mid])prog.best[S.mid]={score:S.pts,max:S.max,stars:starsFor(S.pts,S.max)};
 const nb=prog.best[S.mid];nb.stars=Math.max(nb.stars,starsFor(S.pts,S.max));
 prog.plays=prog.plays||{};prog.plays[S.mid]=(prog.plays[S.mid]||0)+1;prog.weak=prog.weak||{};
 S.qs.forEach((q,i)=>{const l=S.log[i];if(!l)return;const k=(m.id==="boss"?"Boss":"M"+m.n)+" · "+q.title.replace(/[.\/]/g,"");const w=prog.weak[k]||[0,0];prog.weak[k]=[w[0]+l.e,w[1]+l.m]});
 save();push();go("result")}
$app.addEventListener("click",e=>{const t=e.target.closest("[data-act]");if(!t)return;if(t.classList.contains("overlay")&&e.target!==t)return;
 const a=t.dataset.act;const q=S.qs[S.qi];
 if(a==="home"){S.confirmReset=false;go("home")}
 else if(a==="intro"){S.mid=t.dataset.id;go("intro")}
 else if(a==="start")startMission(t.dataset.id);
 else if(a==="help"){S.help=true;render()}
 else if(a==="closehelp"){S.help=false;render()}
 else if(a==="reset"){if(S.confirmReset){prog={best:{}};save();S.confirmReset=false}else S.confirmReset=true;render()}
 else if(a==="teacher")openTeacher();
 else if(a==="csv")exportCsv();
 else if(a==="reload")loadTeacher();
 else if(a==="lock"){TCODE="";try{sessionStorage.removeItem("stats-au-comptoir-tcode")}catch(x){}S.rows=null;S.terr="";render()}
 else if(a==="grp"){}
 else if(a==="nosync"){NOSYNC=true;try{localStorage.setItem(NKEY+"-off","1")}catch(e){}render()}
 else if(a==="enable"){NOSYNC=false;try{localStorage.removeItem(NKEY+"-off")}catch(e){}render()}
 else if(a==="rename"){NAME="";render()}
 else if(a==="hint"){S.hint=true;render()}
 else if(a==="reveal"){const st=q.steps[S.si];award(0,shownOf(st));render()}
 else if(a==="pick"){const st=q.steps[S.si],i=+t.dataset.i;if(i===st.ans){award(pointsFor(),shownOf(st))}else{S.att++;S.wrong.push(i);S.msg=`<span class="bad">Pas tout à fait.</span> ${S.att>=2?"Tu peux voir la réponse ou réessayer.":"Relis la question ou affiche l'indice, puis réessaie."}`}render()}
 else if(a==="next"){if(S.qi+1<S.qs.length){S.qi++;resetQ();window.scrollTo(0,0);render()}else finish()}});
$app.addEventListener("submit",e=>{const nf=e.target.closest("[data-form=name]");if(nf){e.preventDefault();const v=document.getElementById("nm").value.trim().slice(0,40),g=(document.getElementById("grp").value||"").trim().slice(0,20);if(!v)return;NAME=v;GRP=g;NOSYNC=false;try{localStorage.setItem(NKEY,v);localStorage.setItem(NKEY+"-grp",g);localStorage.removeItem(NKEY+"-off")}catch(x){}push();render();return}
 const tf=e.target.closest("[data-form=tcode]");if(tf){e.preventDefault();TCODE=document.getElementById("tc").value.trim();try{sessionStorage.setItem("stats-au-comptoir-tcode",TCODE)}catch(x){}loadTeacher();return}
 const fm=e.target.closest("[data-form=num]");if(!fm)return;e.preventDefault();
 const st=S.qs[S.qi].steps[S.si],raw=document.getElementById("ans").value,v=parse(raw);
 if(isNaN(v)){S.msg=`<span class="bad">Écris un nombre, par exemple 12,5.</span>`;render();return}
 if(Math.abs(v-st.ans)<=st.tol){award(pointsFor(),shownOf(st));render();return}
 S.att++;let msg="";const tr=st.traps.find(t=>Math.abs(v-t.val)<=Math.max(st.tol,1e-9));
 if(tr)msg=tr.msg;else if(st.unit==="%"&&Math.abs(v*100-st.ans)<=Math.max(st.tol,.06)*1.5)msg="Tu as la bonne valeur en décimal. Exprime-la en pourcentage.";else if(Math.abs(Math.abs(v)-Math.abs(st.ans))<=st.tol&&v*st.ans<0)msg="Attention au signe.";else msg="Ce n'est pas la bonne valeur. Vérifie ton calcul ou affiche l'indice.";
 S.msg=`<span class="bad">Pas tout à fait.</span> ${msg}`;render()});

// ===== Suivi enseignant =====
const weakArr=()=>Object.entries(prog.weak||{}).map(([t,v])=>({t,e:v[0],m:v[1]}));
function push(){if(!ENDPOINT||!NAME||NOSYNC)return;const t=total(),stars=MISSIONS.concat([BOSS]).reduce((a,m)=>a+bestOf(m.id).stars,0);
 const payload={code:CLASS_CODE,id:UID,name:NAME,group:GRP,points:t.s,stars,best:prog.best,plays:prog.plays||{},weak:weakArr()};
 return fetch(ENDPOINT,{method:"POST",mode:"no-cors",headers:{"Content-Type":"text/plain;charset=utf-8"},body:JSON.stringify(payload)}).then(()=>{S.sync="ok";if(S.view==="home")render()}).catch(()=>{S.sync="err";if(S.view==="home")render()})}
let TCODE="";try{TCODE=sessionStorage.getItem("stats-au-comptoir-tcode")||""}catch(e){}
S.gf="";S.terr="";S.wk=[];
function openTeacher(){S.rows=null;S.terr="";S.gf="";go("teacher");if(TCODE)loadTeacher()}
async function loadTeacher(){S.rows=null;S.terr="";render();
 try{const r=await fetch(ENDPOINT+"?action=stats&code="+encodeURIComponent(TCODE));const d=await r.json();
  if(d.error){S.terr=d.error==="code"?"Code enseignant incorrect.":"Le service a répondu par une erreur.";S.rows=[];TCODE="";try{sessionStorage.removeItem("stats-au-comptoir-tcode")}catch(x){}}
  else S.rows=d.rows||[]}
 catch(e){S.terr="Impossible de lire les résultats. Vérifie l'adresse du script, ou ouvre directement la feuille Google Sheets.";S.rows=[]}
 if(S.view==="teacher")render()}
const IDS=()=>MISSIONS.map(m=>m.id).concat("boss");
const when=t=>{if(!t)return"–";const d=new Date(t);return d.toLocaleDateString("fr-FR",{day:"2-digit",month:"2-digit"})+" "+d.toLocaleTimeString("fr-FR",{hour:"2-digit",minute:"2-digit"})};
function teacher(){
 const back=`<button class="link back" data-act="home">← Retour aux missions</button>`;
 if(!TCODE)return back+`<section class="ticket"><div class="perf mono">ESPACE ENSEIGNANT</div><h1>Suivi de la classe</h1>${S.terr?`<p class="bad">${S.terr}</p>`:""}<form class="nameform" data-form="tcode" autocomplete="off"><label class="fl" for="tc">Code enseignant</label><div class="ansrow"><input id="tc" type="password" class="inp" autocomplete="off" aria-label="Code enseignant"/><button class="btn" type="submit">Ouvrir</button></div></form></section>`;
 const R0=S.rows;let body;
 if(R0===null)body=`<p>Chargement…</p>`;
 else if(!R0.length)body=`${S.terr?`<p class="bad">${S.terr}</p>`:`<p class="note">Aucun score pour l'instant. Les résultats apparaissent ici dès qu'un étudiant termine une mission avec son nom renseigné.</p>`}`;
 else{const groups=[...new Set(R0.map(r=>r.group||"").filter(Boolean))].sort();
  const R=S.gf?R0.filter(r=>(r.group||"")===S.gf):R0;
  const rows=[...R].sort((a,b)=>(b.points||0)-(a.points||0)),n=rows.length||1,avg=Math.round(rows.reduce((a,r)=>a+(r.points||0),0)/n);
  const cov=IDS().map((id,i)=>{const c=rows.filter(r=>((r.best||{})[id]||{}).stars>=1).length;return`<div class="kpi"><span class="mono">${c}/${rows.length}</span><small>${id==="boss"?"Boss":"M"+(i+1)}</small></div>`}).join("");
  const agg={};R.forEach(r=>(r.weak||[]).forEach(w=>{const a=agg[w.t]||(agg[w.t]=[0,0]);a[0]+=w.e;a[1]+=w.m}));
  const weak=Object.entries(agg).filter(([,v])=>v[1]>=20).map(([t,v])=>[t,Math.round(v[0]/v[1]*100)]).sort((a,b)=>a[1]-b[1]).slice(0,6);
  const tbl=table(["Étudiant","Groupe",...MISSIONS.map(m=>"M"+m.n),"Boss","Points","Activité"],rows.map(r=>[`<b>${esc(r.name||"?")}</b>`,esc(r.group||"–"),...IDS().map(id=>{const b=(r.best||{})[id];return b?`<span class="tst" title="${b.score}/${b.max} pts">${starStr(b.stars||0)}</span>`:"–"}),`<span class="mono">${r.points||0}</span>`,`<small>${when(r.updated)}</small>`]));
  body=`${groups.length?`<div class="ansrow"><label class="fl" for="gf">Groupe</label><select id="gf" class="inp" data-act="grp"><option value="">Tous</option>${groups.map(g=>`<option ${g===S.gf?"selected":""}>${esc(g)}</option>`).join("")}</select></div>`:""}
  <div class="kpis"><div class="kpi"><span class="mono">${rows.length}</span><small>étudiants</small></div><div class="kpi"><span class="mono">${avg}</span><small>points en moyenne</small></div></div><h2 class="sec">Missions réussies (au moins 1 étoile)</h2><div class="kpis">${cov}</div>
  <h2 class="sec">Notions les plus difficiles</h2>${weak.length?weak.map(([t,p])=>`<div class="wk"><span>${esc(t)}</span><span class="wbar"><i style="width:${p}%"></i></span><span class="mono">${p} %</span></div>`).join("")+`<p class="note">Part des points obtenus sur chaque notion (notions avec assez de réponses).</p>`:`<p class="note">Pas encore assez de réponses.</p>`}
  <h2 class="sec">Résultats par étudiant</h2>${tbl}`}
 const tools=`<div class="actions">${R0&&R0.length?`<button class="btn ghost" data-act="csv">Exporter en CSV</button>`:""}<button class="btn ghost" data-act="reload">Actualiser</button><button class="btn ghost" data-act="lock">Verrouiller</button></div>`;
 return back+`<section class="ticket"><div class="perf mono">ESPACE ENSEIGNANT</div><h1>Suivi de la classe</h1>${body}${tools}</section>`}
$app.addEventListener("change",e=>{if(e.target.id==="gf"){S.gf=e.target.value;render()}});
function exportCsv(){const R=(S.gf?(S.rows||[]).filter(r=>(r.group||"")===S.gf):S.rows)||[];if(!R.length)return;const ids=IDS();
 const q=s=>'"'+String(s).replace(/"/g,'""')+'"';
 const lines=[["Nom","Groupe",...MISSIONS.map(m=>"M"+m.n+" (pts)"),"Boss (pts)","Points","Etoiles","Derniere activite"].map(q).join(";")];
 [...R].sort((a,b)=>(b.points||0)-(a.points||0)).forEach(r=>lines.push([q(r.name||""),q(r.group||""),...ids.map(id=>((r.best||{})[id]||{}).score??""),r.points||0,r.stars||0,q(when(r.updated))].join(";")));
 const a=document.createElement("a");a.href=URL.createObjectURL(new Blob(["﻿"+lines.join("\r\n")],{type:"text/csv;charset=utf-8"}));a.download="scores-stats-au-comptoir.csv";document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(a.href),2000)}
render();
if(DB&&NAME&&!NOSYNC)push();

</script>
</body>
</html>
