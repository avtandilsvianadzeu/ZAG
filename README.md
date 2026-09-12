<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<style>body{margin:0}</style>
</head>
<body>
<title>ZAG Structures Slovenia</title>
<meta name="apple-mobile-web-app-capable" content="yes">
<style>
/* ============================== design tokens ============================== */
:root{
  --blue:#0B6BCB; --blue2:#2E8BE0; --green:#2E9E5B; --orange:#E08600; --red:#D33A2C;
  --purple:#7A45C7; --teal:#1C8FA3;
  --gray:#7C7F86; --gray3:#C9CBD1; --gray4:#DCDEE3; --gray5:#EAECF0; --gray6:#F4F5F7;

  --bg:#F1F2F5; --card:#FFFFFF; --panel:#FFFFFF;
  --sep:rgba(22,26,34,.10); --sep2:rgba(22,26,34,.16);
  --label:#12151A; --label2:#5B6068; --label3:#8A8F98;
  --fill:rgba(22,26,34,.05); --fill2:rgba(22,26,34,.09);
  --mat:rgba(255,255,255,.88); --mat-b:rgba(22,26,34,.10);
  --shadow:0 1px 2px rgba(16,20,28,.05),0 10px 30px rgba(16,20,28,.11);
  --shadow-s:0 1px 2px rgba(16,20,28,.07),0 2px 8px rgba(16,20,28,.07);

  --d-bridge:#1273D4; --d-ai:#7B4BD8; --d-build:#C77A0E; --d-mat:#1E9A57;
  --d-fire:#D9453A; --d-geo:#96602A; --d-energy:#0E93A6; --d-herit:#C0398C;
  --d-inst:#60687A;

  --m-out:#E3DFD5; --m-land:#F3F1E7; --m-mun:rgba(30,26,18,.08);
  --m-reg:rgba(30,26,18,.18); --m-coast:rgba(30,26,18,.42);
  --m-riv:#A6D6F1; --m-mot:#FFD87B; --m-mot-c:#E0AF4E; --m-rail:#BCB7AC;
  --m-grat:rgba(30,26,18,.05); --m-hl:rgba(18,115,212,.12);
  --m-lab:#3B3B40;

  --r:10px; --r-l:14px; --r-xl:20px;
  --safe-b:env(safe-area-inset-bottom,0px);
  --safe-t:env(safe-area-inset-top,0px);
  --panelw:432px;
  color-scheme:light dark;
}
@media (prefers-color-scheme:dark){ :root:not([data-theme="light"]){
  --blue:#4DA3FF; --blue2:#7CBEFF; --green:#41C97A; --orange:#FFAE3D; --red:#FF6B5E;
  --purple:#B889FF; --teal:#4FC4D8;
  --bg:#0D0F12; --card:#171A1F; --panel:#12151A;
  --sep:rgba(255,255,255,.10); --sep2:rgba(255,255,255,.18);
  --label:#F2F4F7; --label2:#A2A8B3; --label3:#787F8B;
  --fill:rgba(255,255,255,.07); --fill2:rgba(255,255,255,.12);
  --mat:rgba(23,26,31,.88); --mat-b:rgba(255,255,255,.12);
  --shadow:0 1px 2px rgba(0,0,0,.5),0 12px 36px rgba(0,0,0,.55);
  --shadow-s:0 1px 3px rgba(0,0,0,.5);
  --d-bridge:#57AEFF; --d-ai:#BC9BFF; --d-build:#F0B357; --d-mat:#45CC85;
  --d-fire:#FF7A6E; --d-geo:#D79C5C; --d-energy:#48C9DC; --d-herit:#F27BC4;
  --d-inst:#9BA3B4;
  --m-out:#131417; --m-land:#23252A; --m-mun:rgba(255,255,255,.08);
  --m-reg:rgba(255,255,255,.20); --m-coast:rgba(255,255,255,.40);
  --m-riv:#2D5872; --m-mot:#7A6432; --m-mot-c:#9C8145; --m-rail:#5C5F66;
  --m-grat:rgba(255,255,255,.05); --m-hl:rgba(87,174,255,.16);
  --m-lab:#E8E8EC;
}}
:root[data-theme="dark"]{
  --blue:#4DA3FF; --blue2:#7CBEFF; --green:#41C97A; --orange:#FFAE3D; --red:#FF6B5E;
  --purple:#B889FF; --teal:#4FC4D8;
  --bg:#0D0F12; --card:#171A1F; --panel:#12151A;
  --sep:rgba(255,255,255,.10); --sep2:rgba(255,255,255,.18);
  --label:#F2F4F7; --label2:#A2A8B3; --label3:#787F8B;
  --fill:rgba(255,255,255,.07); --fill2:rgba(255,255,255,.12);
  --mat:rgba(23,26,31,.88); --mat-b:rgba(255,255,255,.12);
  --shadow:0 1px 2px rgba(0,0,0,.5),0 12px 36px rgba(0,0,0,.55);
  --shadow-s:0 1px 3px rgba(0,0,0,.5);
  --d-bridge:#57AEFF; --d-ai:#BC9BFF; --d-build:#F0B357; --d-mat:#45CC85;
  --d-fire:#FF7A6E; --d-geo:#D79C5C; --d-energy:#48C9DC; --d-herit:#F27BC4;
  --d-inst:#9BA3B4;
  --m-out:#131417; --m-land:#23252A; --m-mun:rgba(255,255,255,.08);
  --m-reg:rgba(255,255,255,.20); --m-coast:rgba(255,255,255,.40);
  --m-riv:#2D5872; --m-mot:#7A6432; --m-mot-c:#9C8145; --m-rail:#5C5F66;
  --m-grat:rgba(255,255,255,.05); --m-hl:rgba(87,174,255,.16);
  --m-lab:#E8E8EC;
}

*{box-sizing:border-box; -webkit-tap-highlight-color:transparent}
html{height:100%}
body{margin:0;min-height:100vh;min-height:100dvh;background:var(--bg);color:var(--label);
  font:400 15px/1.45 -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",system-ui,sans-serif;
  -webkit-font-smoothing:antialiased;overscroll-behavior:none}
button,input,select,textarea{font:inherit;color:inherit}
button{border:0;background:none;cursor:pointer;margin:0;padding:0}
a{color:var(--blue);text-decoration:none}
a:hover{text-decoration:underline}
:focus{outline:none}
:focus-visible{outline:2px solid var(--blue);outline-offset:2px;border-radius:6px}
.sr{position:absolute;width:1px;height:1px;overflow:hidden;clip:rect(0 0 0 0);white-space:nowrap}
.skip{position:absolute;left:12px;top:-90px;z-index:999;background:var(--card);color:var(--label);
  padding:11px 15px;border-radius:var(--r);box-shadow:var(--shadow);transition:top .18s}
.skip:focus{top:12px}

/* ---- ranked rows, bars, programme tag ---- */
.row.rank{align-items:flex-start;padding:11px 12px}
.rn{flex:0 0 auto;width:19px;text-align:center;font-size:12px;font-weight:700;color:var(--label3);
  font-variant-numeric:tabular-nums;padding-top:5px}
.row .two .bar{display:block;height:5px;border-radius:3px;background:var(--fill);margin-top:7px;
  overflow:hidden;max-width:190px}
.row .two .bar span{display:block;height:100%;border-radius:3px}
.row.rank>s{text-align:right;line-height:1.3;font-size:11.5px;padding-top:2px;max-width:34%}
.lg .lgr .rn{padding-top:0}
.tagp{font-style:normal;font-size:10px;font-weight:700;letter-spacing:.5px;text-transform:uppercase;
  color:var(--label2);background:var(--fill);border-radius:4px;padding:2px 5px;margin-left:5px;
  vertical-align:1px}
.maplegend b2{font-variant-numeric:tabular-nums;font-weight:700;color:var(--label2);font-size:10.5px}
.row .two s+s{margin-top:2px;color:var(--label3);font-size:11.5px}

/* ================================= layout ================================= */
#app{position:relative;width:100%;height:100vh;height:100dvh;min-height:540px;overflow:hidden;
  display:grid;grid-template-columns:1fr var(--panelw);grid-template-rows:minmax(0,1fr);
  background:var(--bg)}
.mapwrap{position:relative;overflow:hidden;background:var(--m-out);min-width:0;min-height:0}
#map{position:absolute;inset:0;width:100%;height:100%;display:block;touch-action:none;cursor:grab}
#map.drag{cursor:grabbing}

/* =============================== map layers =============================== */
#l-land{fill:var(--m-land)}
.peak{pointer-events:none}
.peak .tri{fill:none;stroke:var(--m-lab);stroke-width:1.4;stroke-linejoin:round;opacity:.75}
.peak text{font:600 10px/1 -apple-system,system-ui,sans-serif;fill:var(--m-lab);opacity:.85;
  paint-order:stroke;stroke:var(--m-land);stroke-width:2.6;stroke-linejoin:round}
#l-coast{fill:none;stroke:var(--m-coast);stroke-width:1;vector-effect:non-scaling-stroke;
  stroke-linejoin:round;pointer-events:none}
#l-mun{fill:none;stroke:var(--m-mun);stroke-width:.7;vector-effect:non-scaling-stroke;pointer-events:none}
#l-grat path{fill:none;stroke:var(--m-grat);stroke-width:.7;vector-effect:non-scaling-stroke}
.regfill{fill:transparent;stroke:var(--m-reg);stroke-width:.9;vector-effect:non-scaling-stroke;
  cursor:pointer}
.regfill.shade{fill:var(--blue)}
.regfill.on{fill:var(--blue);fill-opacity:.2!important;stroke:var(--blue);stroke-width:2.2}
.riv{fill:none;stroke:var(--m-riv);stroke-width:2.8;vector-effect:non-scaling-stroke;
  stroke-linecap:round;stroke-linejoin:round;pointer-events:none}
.rivhit{fill:none;stroke:transparent;stroke-width:16;vector-effect:non-scaling-stroke;cursor:pointer}
#l-mot2{fill:none;stroke:var(--m-mot-c);stroke-width:5;vector-effect:non-scaling-stroke;
  stroke-linecap:round;stroke-linejoin:round;pointer-events:none}
#l-mot{fill:none;stroke:var(--m-mot);stroke-width:3.4;vector-effect:non-scaling-stroke;
  stroke-linecap:round;stroke-linejoin:round;pointer-events:none}
.rail{fill:none;stroke:var(--m-rail);stroke-width:1;stroke-dasharray:6 5;
  vector-effect:non-scaling-stroke;pointer-events:none}
.off{display:none}

.mk{cursor:pointer}
.mk .hit{fill:transparent;stroke:none}
.mk .pulse{fill:none}
.mk .ring{fill:#fff;stroke:none;filter:url(#mkshadow)}
.mk .core{fill:var(--dc)}
.mk .glyph{fill:none;stroke:#fff;stroke-width:1.75;stroke-linecap:round;stroke-linejoin:round;
  pointer-events:none}
.mk .glyph.f{fill:#fff;stroke:none}
.mk .inner{fill:none;stroke:none}
.mk .approx{fill:none;stroke:none}
.mk[data-p="approx"] .approx{stroke:var(--dc);stroke-width:1.3;stroke-dasharray:2.6 2.6;opacity:.85;
  vector-effect:non-scaling-stroke}
.mk[data-d="bridge"]{--dc:var(--d-bridge)} .mk[data-d="ai"]{--dc:var(--d-ai)}
.mk[data-d="energy"]{--dc:var(--d-energy)} .mk[data-d="geo"]{--dc:var(--d-geo)}
.mk[data-d="fire"]{--dc:var(--d-fire)} .mk[data-d="mat"]{--dc:var(--d-mat)}
.mk[data-d="inst"]{--dc:var(--d-inst)} .mk[data-d="build"]{--dc:var(--d-build)}
.mk[data-d="herit"]{--dc:var(--d-herit)}
/* ZAG or partner site: filled disc with a white inner ring */
.mk[data-c="inst"] .inner{stroke:#fff;stroke-width:1.6;vector-effect:non-scaling-stroke}
/* context only: hollow disc, domain coloured ring and glyph */
.mk[data-c="ctx"] .core{fill:#fff;stroke:var(--dc);stroke-width:2.6}
.mk[data-c="ctx"] .glyph{stroke:var(--dc)}
.mk[data-c="ctx"] .glyph.f{fill:var(--dc)}
.mk .lab{font:590 11.5px/1 -apple-system,BlinkMacSystemFont,system-ui,sans-serif;fill:var(--m-lab);
  paint-order:stroke;stroke:var(--m-land);stroke-width:3.2;stroke-linejoin:round;
  opacity:0;transition:opacity .15s;pointer-events:none;letter-spacing:-.1px}
.mk.named .lab,.mk:hover .lab,.mk.sel .lab{opacity:1}
.mk.sel .lab{font-weight:700}
.mk.hide{display:none}
.mk.dim{opacity:.18}
.mk.sel .ring{stroke:var(--dc);stroke-width:2.8}
.mk.sel .pulse{fill:var(--dc);opacity:.16;animation:pl 2.2s ease-out infinite}
@keyframes pl{0%{r:12;opacity:.3}100%{r:36;opacity:0}}
.cl{cursor:pointer}
.cl .cbg{fill:var(--blue);stroke:#fff;stroke-width:2;vector-effect:non-scaling-stroke;filter:url(#mkshadow)}
.cl:hover .cbg{fill:var(--blue2)}
.cl .chit{fill:transparent;stroke:none}
.cl text{fill:#fff;font:700 12px/1 -apple-system,system-ui,sans-serif;text-anchor:middle;pointer-events:none}
@media (prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important}}

/* ============================ floating map chrome ========================= */
.titlecard{position:absolute;left:14px;top:14px;z-index:26;max-width:330px;
  background:var(--mat);-webkit-backdrop-filter:saturate(180%) blur(20px);backdrop-filter:saturate(180%) blur(20px);
  border:1px solid var(--mat-b);border-radius:var(--r-l);padding:10px 14px;box-shadow:var(--shadow-s)}
.titlecard b{display:block;font-size:14px;font-weight:650;letter-spacing:-.1px}
.titlecard s{display:block;text-decoration:none;font-size:11.5px;color:var(--label2);margin-top:2px}

.chipbar{position:absolute;left:14px;top:84px;right:64px;z-index:25;display:flex;flex-wrap:wrap;gap:7px;
  align-items:center;pointer-events:none}
.chipbar>*{pointer-events:auto}
.chip{display:inline-flex;align-items:center;gap:7px;height:34px;padding:0 13px;border-radius:17px;
  background:var(--mat);-webkit-backdrop-filter:saturate(180%) blur(20px);backdrop-filter:saturate(180%) blur(20px);
  border:1px solid var(--mat-b);box-shadow:var(--shadow-s);
  font-size:13px;font-weight:600;color:var(--label);white-space:nowrap;transition:background .15s}
.chip:hover{background:var(--card)}
.chip i{width:10px;height:10px;border-radius:5px;flex:0 0 auto;box-sizing:border-box}
.chip u{text-decoration:none;color:var(--label2);font-variant-numeric:tabular-nums;font-weight:500}
.chip[aria-pressed="true"]{background:var(--blue);color:#fff;border-color:transparent}
.chip[aria-pressed="true"] u{color:rgba(255,255,255,.78)}
.chip[aria-pressed="true"] i{box-shadow:0 0 0 1.5px rgba(255,255,255,.8)}

.search{display:flex;align-items:center;gap:7px;height:34px;padding:0 12px;min-width:190px;
  background:var(--mat);-webkit-backdrop-filter:saturate(180%) blur(20px);backdrop-filter:saturate(180%) blur(20px);
  border:1px solid var(--mat-b);border-radius:17px;box-shadow:var(--shadow-s)}
.search svg{width:14px;height:14px;flex:0 0 auto;color:var(--label2)}
.search input{flex:1;height:34px;border:0;background:none;font-size:13.5px;min-width:0;padding:0}
.search input::placeholder{color:var(--label2)}
.search .clr{width:30px;height:30px;margin-right:-8px;display:none;align-items:center;justify-content:center;
  position:relative;flex:0 0 auto}
.search .clr::before{content:"";position:absolute;width:18px;height:18px;border-radius:9px;background:var(--gray3)}
.search .clr svg{position:relative;width:9px;height:9px;color:var(--card)}
.search.has .clr{display:flex}

.iconbtn{width:34px;height:34px;flex:0 0 auto;border-radius:17px;
  background:var(--mat);-webkit-backdrop-filter:saturate(180%) blur(20px);backdrop-filter:saturate(180%) blur(20px);
  border:1px solid var(--mat-b);box-shadow:var(--shadow-s);
  display:flex;align-items:center;justify-content:center;color:var(--blue)}
.iconbtn:hover{background:var(--card)}
.iconbtn svg{width:17px;height:17px}

.ctl{position:absolute;right:14px;bottom:16px;z-index:25;display:flex;flex-direction:column;gap:9px;align-items:flex-end}
.stack{display:flex;flex-direction:column;border-radius:var(--r-l);overflow:hidden;
  background:var(--mat);-webkit-backdrop-filter:saturate(180%) blur(20px);backdrop-filter:saturate(180%) blur(20px);
  border:1px solid var(--mat-b);box-shadow:var(--shadow-s)}
.stack button{width:40px;height:40px;display:flex;align-items:center;justify-content:center;color:var(--blue)}
.stack button+button{border-top:1px solid var(--sep)}
.stack button:hover{background:var(--fill)}
.stack button svg{width:18px;height:18px}

.scalebar{position:absolute;left:14px;bottom:18px;z-index:20;display:flex;align-items:center;gap:7px;
  font-size:11px;font-weight:600;color:var(--label2);pointer-events:none}
.scalebar .bar{height:5px;border-bottom:2px solid var(--label2);border-left:2px solid var(--label2);
  border-right:2px solid var(--label2);width:70px}

.maplegend{position:absolute;right:14px;bottom:160px;z-index:20;display:flex;flex-direction:column;gap:6px;
  padding:9px 12px;border-radius:var(--r-l);background:var(--mat);
  -webkit-backdrop-filter:saturate(180%) blur(20px);backdrop-filter:saturate(180%) blur(20px);
  border:1px solid var(--mat-b);box-shadow:var(--shadow-s);font-size:11px;font-weight:500;
  pointer-events:none;max-width:196px;gap:4px}
.maplegend strong{font-size:10.5px;font-weight:700;letter-spacing:.5px;text-transform:uppercase;color:var(--label2)}
.maplegend i{display:flex;align-items:center;gap:7px;color:var(--label);font-style:normal;line-height:1.25}
.maplegend b{width:11px;height:11px;border-radius:6px;flex:0 0 auto;box-sizing:border-box}

.maplegend .ramp{display:flex;height:8px;border-radius:4px;overflow:hidden;margin:1px 0 2px}
.maplegend .ramp span{flex:1}
.maplegend .rlab{display:flex;justify-content:space-between;color:var(--label2);font-size:10.5px}

/* hover tooltip on the map */
.tip{position:absolute;z-index:30;pointer-events:none;opacity:0;transform:translate(-50%,-140%);
  background:var(--label);color:var(--bg);padding:5px 9px;border-radius:7px;font-size:12px;font-weight:600;
  white-space:nowrap;box-shadow:var(--shadow-s);transition:opacity .12s}
.tip.on{opacity:1}

/* ================================= panel ================================== */
.sheet{position:relative;z-index:40;display:flex;flex-direction:column;min-width:0;min-height:0;
  background:var(--panel);border-left:1px solid var(--sep)}
.grab{display:none}
.tabs{flex:0 0 auto;display:flex;gap:4px;padding:12px 12px 10px;overflow-x:auto;scrollbar-width:none;
  border-bottom:1px solid var(--sep)}
.tabs::-webkit-scrollbar{display:none}
.tabs button{flex:1 1 0;min-width:0;height:36px;padding:0 6px;border-radius:9px;font-size:13px;font-weight:600;
  color:var(--label2);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;
  border:1px solid transparent;transition:background .15s,color .15s}
.tabs button:hover{background:var(--fill);color:var(--label)}
.tabs button[aria-selected="true"]{background:var(--card);color:var(--label);font-weight:650;
  border-color:var(--sep2);box-shadow:var(--shadow-s)}
.shead{flex:0 0 auto;display:none;align-items:center;gap:8px;padding:10px 16px 0}
.shead.on{display:flex}
.shead .back{display:inline-flex;align-items:center;gap:4px;height:32px;padding:0 11px 0 8px;border-radius:8px;
  color:var(--blue);font-size:13.5px;font-weight:560;background:var(--fill)}
.shead .back:hover{background:var(--fill2)}
.shead .back svg{width:10px;height:16px}
.shead .ht{flex:1;min-width:0;font-size:13px;color:var(--label2);overflow:hidden;
  text-overflow:ellipsis;white-space:nowrap}
.shead .ht b{font-weight:600;color:var(--label)}
.shead .ht s{display:none}
.sbody{flex:1;min-height:0;overflow-y:auto;overscroll-behavior:contain;padding:4px 16px 40px;touch-action:pan-y}
.sbody::-webkit-scrollbar{width:10px}
.sbody::-webkit-scrollbar-thumb{background:var(--gray4);border-radius:5px;border:3px solid var(--panel)}
:root[data-theme="dark"] .sbody::-webkit-scrollbar-thumb,
@media (prefers-color-scheme:dark){.sbody::-webkit-scrollbar-thumb{background:#333}}

/* =============================== panel content ============================ */
.eyebrow{margin:14px 0 3px;font-size:11.5px;font-weight:700;letter-spacing:.7px;color:var(--label2);
  text-transform:uppercase}
h1.lt{margin:0 0 3px;font-size:30px;line-height:1.12;font-weight:700;letter-spacing:-.7px}
h1.lt.sm{font-size:25px;letter-spacing:-.5px}
p.sub{margin:5px 0 0;font-size:14px;color:var(--label2)}
p.lede{margin:13px 0 0;font-size:15px;line-height:1.5}
p.body{margin:0;font-size:15px;line-height:1.55}
.sec{margin:24px 0 8px;font-size:11.5px;font-weight:700;color:var(--label2);
  text-transform:uppercase;letter-spacing:.7px}
.grp{background:var(--card);border:1px solid var(--sep);border-radius:var(--r);overflow:hidden}
.grp+.grp{margin-top:12px}
.row{display:flex;align-items:center;gap:11px;width:100%;min-height:46px;padding:9px 12px;text-align:left;
  background:none;position:relative;transition:background .13s}
.row:hover{background:var(--fill)}
.row+.row{border-top:1px solid var(--sep)}
.row .dot{width:11px;height:11px;border-radius:6px;flex:0 0 auto;border:2px solid transparent;box-sizing:border-box}
.row .mkic{flex:0 0 auto;width:26px;height:26px;display:flex;align-items:center;justify-content:center}
.row .mkic svg{display:block}
.tagrow{margin:12px 0 0;display:flex;gap:8px;flex-wrap:wrap;align-items:center}
.badge svg{flex:0 0 auto}
.citedby{margin-top:7px;font-size:12.5px;color:var(--label2);line-height:1.4}
.row .ic{width:28px;height:28px;border-radius:8px;flex:0 0 auto;display:flex;align-items:center;
  justify-content:center;background:var(--blue);color:#fff}
.row .ic svg{width:16px;height:16px}
.row b{flex:1;min-width:0;font-size:15px;font-weight:500;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.row .two{flex:1;min-width:0;display:block}
.row .two b{display:block;white-space:normal;line-height:1.3}
.row .two s{display:block;text-decoration:none;font-size:12.5px;color:var(--label2);margin-top:1px;line-height:1.3}
.row>s{text-decoration:none;font-size:14px;color:var(--label2);flex:0 0 auto;
  font-variant-numeric:tabular-nums;max-width:44%;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.cv{width:7px;height:12px;color:var(--label3);flex:0 0 auto}
.fr{display:flex;gap:12px;align-items:flex-start;padding:10px 12px;position:relative}
.fr+.fr{border-top:1px solid var(--sep)}
.fr .k{flex:0 0 38%;font-size:14px;color:var(--label2)}
.fr .v{flex:1;font-size:14.5px;text-align:right}
.mono{font-family:ui-monospace,SFMono-Regular,Menlo,monospace;font-size:13px;font-variant-numeric:tabular-nums}
.plain{margin:0;padding:0;list-style:none;background:var(--card);border:1px solid var(--sep);
  border-radius:var(--r);overflow:hidden}
.plain li{padding:10px 12px;font-size:14.5px}
.plain li+li{border-top:1px solid var(--sep)}
.note{margin:14px 0 0;font-size:12.5px;line-height:1.5;color:var(--label2)}
.badge{display:inline-flex;align-items:center;gap:6px;height:25px;padding:0 10px;border-radius:13px;
  font-size:12.5px;font-weight:600;background:var(--fill);color:var(--label)}
.badge i{width:8px;height:8px;border-radius:4px;border:2px solid transparent;box-sizing:border-box}
.badge.ev i{background:var(--label2)}
.badge.ev.doc i{background:currentColor}
.badge svg{width:15px;height:15px}
.callout{margin:12px 0 0;padding:13px 14px;border:1px solid var(--sep);border-radius:var(--r);
  background:var(--card);font-size:14.5px;line-height:1.5}
.callout p{margin:0} .callout p+p{margin-top:9px}
.callout.warn{background:color-mix(in srgb,var(--orange) 11%,var(--card));
  border-color:color-mix(in srgb,var(--orange) 32%,var(--sep))}
.btn{display:inline-flex;align-items:center;justify-content:center;min-height:40px;border-radius:9px;
  background:var(--blue);color:#fff;font-size:14.5px;font-weight:600;padding:0 16px;width:100%}
.btn:hover{filter:brightness(1.08)}
.btn:disabled{background:var(--gray3);color:var(--card);cursor:default}
.btn.ghost{background:var(--card);color:var(--blue);border:1px solid var(--sep2)}
.btn.ghost:hover{background:var(--fill)}
.btnrow{display:flex;flex-wrap:wrap;gap:9px;margin-top:16px}
.btnrow .btn{width:auto;flex:1 1 46%}
.seg{display:flex;gap:3px;padding:3px;background:var(--fill);border-radius:9px;margin:12px 0 0}
.seg button{flex:1;min-height:34px;border-radius:7px;font-size:12.5px;font-weight:600;color:var(--label2)}
.seg button:hover{color:var(--label)}
.seg button[aria-selected="true"]{background:var(--card);color:var(--label);box-shadow:var(--shadow-s)}
.field{margin-top:11px}
.field label{display:block;font-size:12.5px;color:var(--label2);margin:0 2px 5px}
.field input,.field select,.field textarea{width:100%;min-height:42px;border-radius:9px;
  border:1px solid var(--sep2);background:var(--card);padding:10px 11px;font-size:14.5px;
  -webkit-appearance:none;appearance:none}
.field input:focus,.field select:focus,.field textarea:focus{border-color:var(--blue)}
.field textarea{min-height:92px;resize:vertical;line-height:1.45}
.two{display:flex;gap:10px}.two>*{flex:1;min-width:0}
.chkrow{display:flex;align-items:center;gap:11px;background:var(--card);border:1px solid var(--sep);
  border-radius:9px;padding:11px;margin-top:11px;font-size:14.5px}
.chkrow input{width:18px;height:18px;flex:0 0 auto;accent-color:var(--blue)}
.msg{margin-top:11px;padding:11px 12px;border-radius:9px;font-size:14px}
.msg.ok{background:color-mix(in srgb,var(--green) 16%,var(--card))}
.msg.err{background:color-mix(in srgb,var(--red) 14%,var(--card))}
.cite{padding:12px;position:relative;font-size:13.5px;line-height:1.5}
.cite+.cite{border-top:1px solid var(--sep)}
.cite .ti{font-style:italic}
.cite .me{color:var(--label2)}
.cite .acts{display:flex;gap:8px;margin-top:9px;flex-wrap:wrap}
.cite .acts a,.cite .acts button{display:inline-flex;align-items:center;height:31px;padding:0 12px;
  border-radius:8px;background:var(--fill);font-size:12.5px;font-weight:560;color:var(--blue)}
.cite .acts a:hover,.cite .acts button:hover{background:var(--fill2);text-decoration:none}
.kind{display:block;font-size:10px;font-weight:700;letter-spacing:.6px;text-transform:uppercase;
  color:var(--label2);margin-bottom:4px}
.lg .lgr{display:flex;align-items:center;gap:11px;padding:9px 12px;position:relative;font-size:14.5px}
.lg .lgr+.lgr{border-top:1px solid var(--sep)}
.lg .lgr svg{width:24px;height:24px;flex:0 0 auto}
.lg .lgr s{text-decoration:none;color:var(--label2);font-size:12.5px;margin-left:auto;text-align:right;
  max-width:50%;line-height:1.3}
.pill{display:inline-flex;align-items:center;height:25px;padding:0 10px;border-radius:13px;
  font-size:12px;font-weight:600;background:color-mix(in srgb,var(--orange) 20%,transparent);color:var(--label)}
.pill.ok{background:color-mix(in srgb,var(--green) 20%,transparent)}
.stats{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-top:14px}
.stats>div{background:var(--card);border:1px solid var(--sep);border-radius:var(--r);padding:13px 14px}
.stats b{display:block;font-size:27px;font-weight:700;letter-spacing:-.8px;line-height:1.05;color:var(--blue);
  font-variant-numeric:tabular-nums}
.stats s{display:block;text-decoration:none;font-size:12.5px;color:var(--label2);margin-top:4px}
.switch{position:relative;width:44px;height:26px;flex:0 0 auto}
.switch input{position:absolute;opacity:0;width:100%;height:100%;margin:0;cursor:pointer;z-index:2}
.switch i{position:absolute;inset:0;border-radius:13px;background:var(--gray4);transition:background .2s}
.switch i::after{content:"";position:absolute;top:2px;left:2px;width:22px;height:22px;border-radius:11px;
  background:#fff;box-shadow:0 1px 3px rgba(0,0,0,.25);transition:transform .2s}
.switch input:checked+i{background:var(--green)}
.switch input:checked+i::after{transform:translateX(18px)}
kbd{display:inline-block;min-width:22px;text-align:center;padding:2px 6px;border-radius:5px;
  background:var(--fill);border:1px solid var(--sep);font:600 12px/1.4 ui-monospace,SFMono-Regular,Menlo,monospace}
.toast{position:absolute;left:50%;bottom:18px;transform:translate(-50%,18px);z-index:60;
  background:var(--label);color:var(--bg);border-radius:9px;padding:9px 16px;font-size:13.5px;font-weight:560;
  box-shadow:var(--shadow);opacity:0;pointer-events:none;transition:opacity .22s,transform .22s;max-width:80%}
.toast.on{opacity:1;transform:translate(-50%,0)}

/* ============================== narrow desktop ============================ */
@media (max-width:1180px){ :root{--panelw:380px} }
@media (max-width:1000px){ :root{--panelw:340px}
  .titlecard{max-width:260px}
  h1.lt{font-size:26px} .stats{grid-template-columns:1fr 1fr}
}
/* ================================== phone ================================= */
@media (max-width:820px){
  #app{display:block}
  .mapwrap{position:absolute;inset:0}
  .titlecard{left:10px;top:calc(10px + var(--safe-t));max-width:calc(100% - 74px)}
  .chipbar{left:10px;right:10px;top:calc(70px + var(--safe-t));flex-wrap:nowrap;overflow-x:auto;
    scrollbar-width:none;padding-bottom:2px}
  .chipbar::-webkit-scrollbar{display:none}
  .chipbar>*{flex:0 0 auto}
  .search{min-width:170px}
  .ctl{top:calc(118px + var(--safe-t));bottom:auto;right:10px}
  .scalebar{left:10px;bottom:auto;top:calc(120px + var(--safe-t))}
  .maplegend{display:none}
  .tip{display:none}

  .sheet{position:absolute;left:0;right:0;bottom:0;top:auto;
    height:calc(100% - 112px - var(--safe-t));
    border-left:0;border-radius:var(--r-xl) var(--r-xl) 0 0;box-shadow:var(--shadow);
    will-change:transform}
  .sheet.anim{transition:transform .38s cubic-bezier(.32,.72,0,1)}
  .grab{display:flex;height:22px;flex:0 0 auto;align-items:center;justify-content:center;
    cursor:grab;touch-action:none}
  .grab i{width:38px;height:5px;border-radius:3px;background:var(--gray3)}
  .tabs{padding:4px 10px 9px;touch-action:none}
  .tabs button{flex:0 0 auto;padding:0 14px;font-size:14px}
  .shead{padding:9px 14px 0;touch-action:none}
  .sbody{padding:4px 14px calc(40px + var(--safe-b))}
  .toast{bottom:auto;top:calc(170px + var(--safe-t))}
}
</style>

<a class="skip" href="#pane">Skip the map, go to the panel</a>
<div id="app">

<div class="mapwrap" id="mapwrap">
  <svg id="map" role="application" aria-label="Map of Slovenia with ZAG engineering structures. Drag to move, scroll or pinch to zoom, click a marker or a region.">
    <defs>
      <filter id="mkshadow" x="-60%" y="-60%" width="220%" height="220%">
        <feDropShadow dx="0" dy="0.6" stdDeviation="0.9" flood-color="#000" flood-opacity="0.28"/>
      </filter>
    </defs>
    <g id="cam">
      <g id="l-grat" aria-hidden="true"></g>
      <path id="l-land"></path>
      <g id="l-peaks" aria-hidden="true"></g>
      <path id="l-mun"></path>
      <g id="l-reg"></g>
      <g id="l-rail" aria-hidden="true"></g>
      <g id="l-riv"></g>
      <path id="l-mot2" aria-hidden="true"></path>
      <path id="l-mot" aria-hidden="true"></path>
      <path id="l-coast" aria-hidden="true"></path>
      <g id="l-mk"></g>
      <g id="l-cl"></g>
    </g>
  </svg>

  <div class="titlecard">
    <b>ZAG structures and sites</b>
    <s id="brandsub">Loading</s>
  </div>

  <div class="chipbar" id="chipbar" role="group" aria-label="Filters and search">
    <div class="search" id="searchbox">
      <svg viewBox="0 0 16 16" aria-hidden="true"><path d="M7 1a6 6 0 104.2 10.2l3.3 3.3a1 1 0 001.4-1.4l-3.3-3.3A6 6 0 007 1zm0 2a4 4 0 110 8 4 4 0 010-8z" fill="currentColor"/></svg>
      <input id="q" type="search" placeholder="Search" aria-label="Search the register" autocomplete="off">
      <button class="clr" id="qclr" aria-label="Clear search">
        <svg viewBox="0 0 12 12" aria-hidden="true"><path d="M1 1l10 10M11 1L1 11" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"/></svg>
      </button>
    </div>
    <span id="filters" style="display:contents"></span>
    <button class="iconbtn" id="layersbtn" aria-label="Map layers and legend">
      <svg viewBox="0 0 22 22" aria-hidden="true"><path d="M11 2l9 5-9 5-9-5 9-5zM3.5 11.2L2 12l9 5 9-5-1.5-.8L11 15.2 3.5 11.2z" fill="currentColor"/></svg>
    </button>
  </div>

  <div class="maplegend" id="maplegend" aria-hidden="true"></div>
  <div class="scalebar"><span class="bar"></span><span id="scaletxt">50 km</span></div>

  <div class="ctl">
    <div class="stack">
      <button id="zin"  aria-label="Zoom in"><svg viewBox="0 0 20 20" aria-hidden="true"><path d="M10 3v14M3 10h14" stroke="currentColor" stroke-width="2.1" stroke-linecap="round"/></svg></button>
      <button id="zout" aria-label="Zoom out"><svg viewBox="0 0 20 20" aria-hidden="true"><path d="M3 10h14" stroke="currentColor" stroke-width="2.1" stroke-linecap="round"/></svg></button>
      <button id="zres" aria-label="Show the whole of Slovenia"><svg viewBox="0 0 20 20" aria-hidden="true"><path d="M2 7V3.4A1.4 1.4 0 013.4 2H7M13 2h3.6A1.4 1.4 0 0118 3.4V7M18 13v3.6a1.4 1.4 0 01-1.4 1.4H13M7 18H3.4A1.4 1.4 0 012 16.6V13" fill="none" stroke="currentColor" stroke-width="1.9" stroke-linecap="round"/></svg></button>
    </div>
  </div>

  <div class="tip" id="tip"></div>
  <div class="toast" id="toast" role="status" aria-live="polite"></div>
</div>

<aside class="sheet" id="sheet" aria-label="Register panel">
  <div class="grab" id="grab" role="separator" aria-label="Drag to resize the panel" tabindex="0"><i></i></div>
  <nav class="tabs" id="tabs" role="tablist" aria-label="Sections"></nav>
  <div class="shead" id="shead">
    <button class="back" id="backbtn"><svg viewBox="0 0 12 20" aria-hidden="true"><path d="M10 1L2 10l8 9" fill="none" stroke="currentColor" stroke-width="2.6" stroke-linecap="round" stroke-linejoin="round"/></svg>Back</button>
    <span class="ht" id="sheadt"></span>
  </div>
  <div class="sbody" id="pane" tabindex="-1"></div>
</aside>

<p class="sr" id="live" role="status" aria-live="polite"></p>
</div>

<script>
const D = {"vb":[1000,671.6],"mpu":259.8,"crs":"EPSG:3794 D96/TM","country":"M121.63 571.41L128.55 570.14L133.89 573.56L134.95 573.57L135.01 574.04L138.69 576.26L140.52 576.78L143.16 577.18L143.95 576.88L144.70 577.40L147.42 577.72L156.12 577.26L159.29 576.30L159.03 576.09L159.76 576.27L159.65 574.40L160.50 573.09L164.21 571.15L165.30 565.80L167.88 565.12L171.56 562.82L172.93 561.28L175.00 560.43L180.22 556.65L180.33 555.66L175.73 551.73L172.72 550.63L166.24 545.80L162.22 541.57L158.56 535.15L155.15 532.38L154.47 529.89L154.77 528.68L155.90 527.76L155.36 523.79L153.13 520.54L148.53 516.81L146.84 514.04L145.32 509.43L143.76 507.83L140.74 505.98L137.84 505.70L135.16 504.78L134.21 502.49L129.31 502.80L127.11 500.89L126.23 500.93L125.63 500.29L126.79 499.98L126.13 499.26L124.61 497.95L118.68 494.62L109.63 485.83L108.20 487.34L106.69 483.44L103.32 483.10L97.20 483.94L97.16 482.57L93.11 484.77L93.05 483.01L90.28 481.72L89.32 481.89L87.20 481.27L84.77 479.46L85.21 478.35L84.90 478.00L85.24 474.55L83.84 472.92L82.78 467.77L78.66 464.71L78.62 464.27L79.29 464.29L78.83 463.41L79.37 461.02L78.92 459.94L80.34 458.71L81.70 454.02L82.66 452.39L84.48 450.97L82.52 447.84L84.69 444.27L84.55 443.81L85.33 443.80L85.49 442.28L89.35 440.56L90.66 437.31L91.43 436.95L92.18 433.59L93.59 431.30L94.17 431.67L94.87 430.85L94.84 429.83L96.14 427.58L98.30 425.32L96.87 419.26L98.59 412.50L98.53 410.71L99.36 410.43L99.03 406.38L100.13 404.93L97.37 402.21L96.45 403.05L95.85 402.97L92.81 404.67L91.84 404.19L91.90 403.73L89.85 404.17L88.32 402.76L84.61 401.58L84.06 402.18L82.75 402.28L83.04 403.02L80.64 404.47L80.02 407.24L77.81 410.61L72.80 409.73L71.75 409.94L70.98 411.76L69.95 412.14L66.48 411.45L65.73 411.09L65.28 408.68L63.78 408.51L62.70 407.68L61.56 405.53L57.95 405.22L54.11 399.31L53.43 396.96L51.63 395.60L50.57 394.11L52.03 392.63L51.64 391.80L53.25 391.37L54.47 390.42L56.08 390.56L56.84 389.78L60.48 381.94L60.99 378.88L60.38 378.36L60.52 377.23L56.92 376.16L57.41 374.77L57.06 371.80L57.97 371.53L58.93 370.10L59.40 370.07L60.15 371.02L60.85 370.08L62.88 370.28L65.75 368.12L67.14 368.54L67.03 366.99L68.15 367.34L68.39 365.88L69.47 365.18L69.76 364.34L70.90 364.08L71.08 362.04L71.55 361.54L73.27 362.10L73.64 360.97L74.43 361.29L76.25 360.57L76.79 359.74L78.13 359.84L79.04 359.06L80.00 359.40L81.19 356.81L82.24 355.31L83.04 355.04L83.18 354.29L84.51 354.42L85.42 353.37L87.14 352.64L87.20 351.65L88.30 351.11L88.22 350.30L88.88 349.88L88.68 349.16L90.51 347.73L91.80 347.59L92.00 346.67L93.29 345.74L94.00 345.75L95.46 344.42L96.30 342.42L96.93 342.29L97.37 341.14L98.74 339.88L100.07 340.14L101.70 338.74L104.87 332.86L105.23 331.42L104.54 329.78L104.61 328.63L107.21 325.96L108.57 323.27L106.51 319.12L105.28 318.09L98.87 315.50L93.16 318.60L92.27 318.07L92.97 317.43L92.65 316.47L85.84 316.78L86.99 315.21L86.54 314.73L85.05 316.47L84.77 315.75L82.27 317.97L81.64 317.67L80.82 318.43L80.25 317.84L80.34 317.19L79.92 317.12L79.03 317.73L78.47 316.60L78.83 313.76L77.47 311.98L77.67 309.81L72.84 306.29L70.91 305.69L68.09 306.23L68.02 303.35L65.88 303.77L63.95 304.99L60.24 304.59L58.55 303.77L59.22 303.05L58.50 301.91L54.95 300.73L51.42 300.32L49.16 300.98L46.63 299.85L43.41 299.94L42.83 300.08L43.99 304.03L43.38 305.52L40.30 306.03L36.52 308.24L36.15 307.01L33.03 305.72L32.36 304.30L32.82 303.34L34.17 302.79L34.67 301.08L33.14 299.05L34.09 298.49L35.08 298.63L36.42 297.52L36.14 296.63L36.62 296.06L34.81 294.54L32.84 293.64L31.59 291.97L30.53 288.33L29.52 287.80L29.50 286.24L28.99 285.58L29.32 285.27L28.81 284.92L29.02 284.19L28.19 282.42L28.60 281.89L27.92 280.77L27.99 275.38L26.79 273.99L26.32 271.80L24.37 272.52L23.69 271.46L23.10 268.75L31.25 267.87L32.36 265.50L35.68 265.65L35.75 264.78L35.12 263.82L35.27 260.89L38.15 258.42L41.25 258.92L42.14 258.59L43.68 255.21L44.97 254.87L45.35 253.30L43.93 250.95L43.87 249.20L43.06 248.26L43.37 247.35L41.82 244.89L42.39 242.46L46.41 241.23L48.86 241.35L50.86 242.38L51.58 242.21L53.46 241.21L55.20 239.02L56.55 238.25L57.33 238.59L60.07 238.20L63.31 235.66L65.69 235.73L66.01 235.32L65.73 233.08L68.90 230.93L70.66 232.15L72.20 231.87L73.09 229.58L76.68 228.97L78.44 226.62L79.67 226.51L80.24 226.93L82.61 224.06L83.06 222.46L83.99 222.40L83.68 220.05L84.31 215.53L85.43 213.72L85.48 212.83L86.22 213.09L87.11 212.65L88.26 210.61L90.09 209.38L90.85 209.88L92.23 209.10L92.87 209.43L93.92 208.48L95.58 209.53L97.27 208.07L97.69 208.37L98.46 207.86L99.90 208.55L101.05 208.46L101.72 207.70L103.19 207.62L105.32 206.51L106.78 207.80L106.92 209.64L110.04 209.14L111.91 209.67L113.35 209.35L115.60 210.64L115.98 209.76L117.17 209.59L118.51 207.96L118.71 205.54L120.12 202.44L119.45 199.93L118.67 199.04L118.66 197.67L120.39 196.33L120.87 194.92L122.75 193.32L123.64 191.80L121.59 190.48L122.34 187.41L121.49 184.51L121.91 183.31L125.72 181.15L125.91 177.95L125.09 174.19L128.56 174.18L128.67 174.67L131.93 176.84L136.88 176.50L140.47 178.07L140.88 177.61L142.84 177.47L143.45 176.79L143.95 176.89L144.53 179.16L147.34 181.08L148.00 181.01L148.80 182.13L151.72 181.45L153.96 181.83L155.50 180.18L156.54 180.02L156.91 179.10L158.41 178.73L159.04 178.03L158.88 177.31L159.68 176.58L160.57 176.70L161.62 177.74L166.74 178.74L168.84 178.25L171.54 176.52L173.71 176.59L174.68 175.04L180.33 176.82L183.52 175.87L186.81 176.98L188.22 179.07L192.62 180.12L194.26 181.61L195.42 181.92L195.42 182.38L197.55 183.85L197.93 184.80L200.42 186.50L202.20 185.90L206.05 188.25L206.25 190.21L208.72 190.82L211.23 193.25L215.49 193.19L216.53 192.46L217.02 191.35L218.51 190.99L219.52 189.24L221.36 188.39L224.55 188.37L226.58 189.74L228.66 189.97L230.17 190.98L236.40 191.72L238.69 193.29L238.64 194.14L239.40 194.63L240.53 194.22L245.20 195.69L244.85 196.73L246.04 197.67L247.51 200.07L247.13 200.57L249.13 203.39L249.13 206.76L250.64 207.88L251.05 208.76L252.96 210.11L253.85 210.16L254.19 212.61L254.81 213.31L257.36 214.22L261.29 214.09L262.57 212.19L263.27 212.27L265.20 211.29L265.74 209.89L267.11 211.13L270.52 211.92L271.96 211.66L272.64 210.36L273.96 210.27L275.27 211.43L276.22 213.45L279.21 215.04L282.58 214.10L284.94 212.18L286.49 212.09L287.32 212.52L289.48 211.08L292.87 210.34L296.16 212.13L298.28 212.60L300.20 215.91L302.72 215.54L305.54 215.79L307.32 215.42L310.85 213.12L313.20 213.17L314.51 212.57L316.91 212.81L318.08 212.13L322.10 212.46L326.96 210.21L328.65 210.19L330.26 209.42L331.06 209.81L334.38 209.88L336.18 209.18L337.69 211.02L338.75 210.95L338.86 211.88L336.91 212.46L336.31 213.86L337.77 215.97L339.84 217.32L339.96 219.46L341.18 220.10L342.59 219.74L344.46 220.35L347.10 219.98L349.07 220.98L349.95 220.92L350.64 223.63L352.31 222.81L354.61 223.90L356.20 221.37L357.71 220.76L357.88 219.64L358.59 219.09L359.93 218.36L363.39 217.82L363.49 219.29L366.40 223.25L367.61 223.41L368.71 224.56L369.36 227.97L371.87 231.22L373.66 235.90L373.66 239.58L375.45 241.32L376.10 241.35L376.40 240.25L380.01 239.35L381.01 237.42L380.13 236.44L382.36 232.91L382.78 231.39L382.51 227.79L383.36 225.49L383.15 223.44L381.56 222.80L381.35 221.83L382.53 216.86L385.19 215.39L385.37 213.85L387.95 213.81L388.77 212.90L390.44 212.61L393.12 213.09L395.88 212.77L398.66 211.27L402.07 210.44L404.22 210.66L405.26 209.93L406.29 208.33L407.59 207.86L408.71 208.03L410.05 204.98L408.98 203.27L409.86 202.89L411.22 200.67L413.03 202.17L416.00 202.49L416.89 200.94L416.53 199.10L415.48 197.87L416.84 195.33L418.94 195.15L419.69 191.51L419.36 190.11L420.16 189.14L420.60 186.99L422.70 187.73L424.43 190.07L424.62 191.12L426.62 188.05L427.38 185.66L428.45 184.77L429.58 185.62L430.52 188.03L433.98 185.08L438.95 185.06L439.82 186.86L440.16 186.42L441.50 187.26L447.57 183.81L451.30 183.05L451.16 179.65L451.51 178.72L451.01 177.66L452.33 176.54L452.47 175.40L453.26 174.33L452.52 173.23L452.60 171.84L455.24 170.25L454.02 168.98L452.63 168.56L452.65 167.42L453.38 167.49L453.54 166.51L455.38 166.31L455.28 165.18L456.05 164.71L457.07 162.22L456.92 161.06L456.04 160.02L456.58 158.95L457.72 158.88L457.05 157.98L457.55 156.39L458.80 154.08L460.09 152.92L461.23 152.57L461.26 151.76L462.46 149.96L462.56 147.66L464.02 146.92L465.00 147.17L465.79 144.87L465.76 142.29L466.69 141.20L469.11 140.76L469.58 140.12L469.40 139.50L471.55 138.84L474.33 139.96L475.66 139.16L475.46 140.24L476.62 141.26L476.72 142.23L479.39 142.50L479.43 141.60L480.30 142.15L480.97 143.51L481.89 143.10L482.36 142.29L481.81 141.48L482.07 139.61L481.42 137.25L482.15 135.38L483.74 136.12L484.61 137.77L486.31 135.70L487.17 135.95L487.72 135.45L491.80 130.34L495.18 132.42L496.27 133.93L497.18 137.00L497.45 140.72L498.79 143.74L500.34 142.78L501.03 141.64L500.96 140.71L503.39 138.40L503.76 137.55L503.24 136.67L503.31 135.25L506.16 131.99L507.20 130.03L508.35 129.48L509.65 126.86L513.62 125.10L514.91 123.39L516.98 122.18L524.07 122.06L525.70 122.97L526.93 123.03L529.17 125.00L531.12 122.33L530.79 122.07L534.01 121.45L534.46 120.33L536.55 118.77L537.48 118.78L539.11 119.93L538.67 120.36L539.85 121.30L540.69 120.35L540.63 120.98L542.14 121.63L542.12 122.54L542.77 122.90L543.54 122.65L544.50 119.99L545.50 119.58L546.19 120.17L546.78 119.83L547.07 118.87L547.71 118.69L549.85 119.37L550.83 120.47L552.67 119.58L553.36 119.76L554.11 121.15L558.59 120.25L560.68 121.68L561.44 123.47L563.04 124.69L565.63 124.91L569.17 126.19L570.98 125.65L574.41 127.38L576.01 127.08L576.79 126.35L579.58 126.20L582.25 125.07L586.63 125.53L588.06 124.83L588.60 123.66L590.20 123.02L591.52 121.71L593.60 121.39L596.61 121.84L599.01 123.67L599.67 123.59L601.53 121.37L602.67 121.73L604.41 121.37L605.22 122.29L606.31 122.36L607.33 121.15L609.11 120.57L609.70 122.08L613.36 122.13L614.59 122.79L615.65 121.87L617.87 122.02L619.35 121.40L621.08 121.83L626.89 120.25L628.74 120.51L629.62 121.45L629.16 123.79L631.65 124.02L632.69 125.83L634.37 126.92L637.40 125.84L639.53 127.27L639.03 131.06L640.39 132.74L641.12 132.83L641.58 134.08L641.14 137.41L644.87 138.76L646.28 138.01L647.50 135.86L648.81 135.02L652.19 136.09L652.42 137.57L652.99 137.91L653.51 137.75L653.65 137.01L655.79 136.74L655.28 135.25L655.77 134.51L656.85 133.83L658.25 134.60L659.84 132.42L661.00 131.69L661.20 130.92L663.20 129.28L664.25 129.31L664.78 130.97L665.70 129.59L665.82 127.94L666.94 127.30L667.30 126.54L666.08 125.46L665.68 125.62L665.16 124.06L666.01 122.92L667.39 123.36L667.98 121.76L666.48 118.59L666.31 116.00L665.74 116.08L665.96 115.16L665.03 114.13L665.79 113.76L666.07 114.14L667.19 112.70L667.77 113.30L667.84 112.71L669.60 113.33L669.81 112.28L670.67 111.59L672.00 111.50L672.19 109.37L672.62 109.53L672.79 109.11L673.71 109.48L674.13 108.85L675.12 109.08L674.98 108.12L676.38 108.63L677.55 107.64L678.64 108.05L678.60 106.85L680.12 105.16L681.61 105.13L682.74 105.93L684.08 106.13L683.05 106.58L682.73 107.77L683.16 108.93L684.40 108.12L684.94 108.51L685.46 107.93L685.62 108.45L687.44 109.46L687.99 109.08L688.35 109.56L690.41 109.34L691.60 108.84L691.04 107.39L691.69 105.78L692.94 104.45L693.68 104.02L694.29 104.98L695.45 104.33L697.06 104.53L697.34 104.13L697.45 100.98L696.22 98.29L703.96 97.81L709.72 101.14L717.32 102.36L722.54 100.55L726.80 101.38L729.22 100.73L731.27 100.85L740.54 93.87L746.67 91.70L751.60 90.66L757.61 90.64L761.29 91.18L763.95 92.04L767.66 94.07L773.23 95.69L775.86 97.43L781.66 103.15L783.75 104.55L794.54 106.32L798.90 107.99L800.46 109.70L801.49 113.07L802.65 114.66L803.89 115.38L806.11 115.73L810.74 118.30L811.46 112.98L810.93 111.50L811.05 109.69L811.87 105.55L810.07 101.62L807.75 99.20L807.92 97.82L807.28 97.16L807.99 94.59L807.49 94.32L805.51 94.94L803.43 92.40L802.67 92.12L801.58 92.76L800.24 92.32L799.69 91.40L800.22 89.82L797.14 86.35L796.63 83.67L795.57 82.26L795.72 80.75L794.52 77.50L795.95 74.99L795.48 73.44L796.03 68.68L795.54 67.04L797.02 59.69L796.47 55.59L798.13 52.94L796.06 49.19L795.10 48.54L794.29 45.26L795.53 44.31L795.96 42.83L797.44 41.75L799.00 43.39L800.82 43.74L802.51 41.48L803.91 41.27L806.54 39.18L808.48 41.58L808.01 41.84L808.06 42.77L808.86 41.81L810.26 41.27L810.55 39.61L811.13 39.27L813.57 40.75L814.55 39.33L815.67 40.12L817.85 36.92L817.75 35.28L818.89 34.83L819.42 33.89L821.73 34.00L822.46 32.67L824.20 31.13L824.72 29.45L825.36 28.89L826.54 29.06L827.19 30.58L827.75 30.51L828.10 29.61L829.71 28.56L831.03 26.84L831.78 26.88L832.66 27.70L832.74 29.20L835.01 29.43L835.58 32.03L838.60 32.14L839.55 32.85L842.03 32.90L842.60 32.30L844.26 33.27L846.09 30.83L846.95 30.51L850.21 31.64L852.84 28.00L856.40 27.42L858.13 26.39L859.76 26.19L861.68 26.69L864.44 25.17L864.87 25.54L865.16 24.51L866.83 23.10L869.36 23.23L870.57 23.99L872.22 23.98L876.20 25.03L883.84 24.47L884.96 25.45L885.90 28.81L886.31 28.66L886.91 30.12L889.01 30.13L888.99 31.42L891.83 31.38L892.80 33.36L894.72 35.14L895.25 36.35L897.05 35.43L898.40 35.34L898.07 36.96L899.27 36.88L900.61 37.94L901.61 42.48L899.78 42.66L899.58 46.01L898.57 46.06L898.52 49.10L898.96 50.62L898.58 53.69L896.86 54.55L892.13 55.23L891.43 56.48L890.66 56.68L890.23 61.89L890.62 64.95L893.84 65.20L895.75 64.81L896.04 66.05L895.67 66.14L894.85 69.38L893.65 70.64L893.60 73.32L892.68 75.13L893.97 75.66L893.99 76.39L894.69 76.39L894.63 76.80L896.79 77.44L897.49 79.61L899.05 80.30L899.96 82.34L901.09 82.72L902.22 85.97L901.32 87.65L903.18 87.51L902.96 88.70L904.29 92.01L904.77 90.83L905.88 90.90L908.36 88.49L908.95 89.87L909.64 90.04L909.54 90.68L910.98 91.40L910.85 93.33L907.85 96.33L911.66 98.81L917.85 98.96L921.50 99.75L924.13 99.53L925.51 100.31L923.97 103.65L923.47 106.15L923.61 106.59L924.73 106.73L923.36 107.92L923.22 108.84L924.69 109.88L924.73 110.40L924.15 111.87L922.70 112.96L923.40 113.82L923.20 115.54L919.77 115.11L918.27 115.48L918.33 114.45L916.10 113.01L914.82 113.45L915.47 114.13L915.33 115.38L914.84 115.43L914.75 117.12L913.68 117.80L913.04 117.69L913.31 121.81L915.15 123.22L914.53 123.53L914.43 124.34L915.17 125.34L915.11 126.28L917.43 126.05L918.29 126.90L919.79 127.41L920.14 128.40L921.27 128.77L922.74 131.88L925.02 134.91L927.61 134.85L931.15 135.74L933.18 140.10L933.61 140.08L934.23 141.30L935.97 141.66L938.23 146.37L939.55 145.59L942.56 149.38L942.14 151.17L942.55 154.75L944.69 154.88L945.54 155.35L945.55 156.19L946.75 155.83L947.95 156.18L950.05 154.94L953.20 160.24L953.45 162.96L952.55 165.20L953.04 165.45L953.02 167.26L953.72 167.81L954.74 167.50L956.07 167.81L956.39 168.72L957.47 169.29L956.77 170.45L957.03 171.96L956.41 172.19L956.43 172.83L955.15 174.38L955.59 174.85L955.61 176.14L957.30 176.14L957.79 176.54L956.88 179.49L955.26 178.99L955.03 180.47L957.54 182.48L959.21 182.75L963.84 185.90L968.69 187.66L968.95 189.03L971.69 190.57L972.19 191.77L976.90 192.67L972.69 194.43L970.53 194.73L967.36 193.90L966.39 192.14L963.42 192.97L963.12 192.23L961.30 192.83L960.52 192.42L959.61 193.04L959.36 191.33L958.38 190.70L955.48 191.82L952.94 190.95L952.96 189.97L953.52 189.50L952.82 188.52L953.58 187.55L953.30 186.43L952.68 185.92L950.40 186.24L950.74 184.86L946.03 184.00L945.40 182.87L944.39 182.66L943.78 181.80L944.56 179.45L942.35 179.22L941.95 178.76L942.33 178.44L941.62 177.60L939.21 178.34L939.58 176.61L939.18 175.54L938.42 175.49L937.79 176.13L938.13 177.69L936.87 177.09L936.73 176.26L937.73 174.68L937.32 173.96L936.59 174.18L936.02 176.16L933.47 175.52L932.70 176.22L930.44 176.82L929.61 175.83L929.51 174.94L929.59 173.57L930.45 172.47L929.38 171.08L928.66 171.77L927.67 171.64L927.44 169.89L926.35 169.18L925.45 169.81L925.85 171.42L924.90 171.34L923.68 171.00L922.73 169.62L921.24 168.84L920.69 169.12L921.92 170.85L921.40 171.90L920.45 171.98L920.09 170.79L918.79 169.65L919.40 168.46L919.15 166.68L918.45 166.52L917.20 168.05L915.33 168.25L914.39 168.06L913.66 165.52L912.94 165.34L912.10 166.17L910.49 165.68L909.49 164.93L909.17 163.69L912.13 163.07L912.88 162.27L912.87 161.58L912.37 161.09L910.57 161.02L908.55 160.16L907.99 161.04L908.49 162.78L908.13 163.67L906.70 163.68L905.66 164.46L905.08 164.08L904.97 162.94L904.21 162.73L903.92 164.12L906.04 165.41L906.10 167.21L905.05 167.22L905.17 165.62L904.46 164.97L902.03 165.71L899.73 165.53L901.59 166.04L902.10 166.79L902.04 167.62L900.83 168.80L901.17 170.81L900.33 171.88L899.34 172.12L898.55 170.95L895.64 171.48L892.88 173.38L893.17 175.32L892.04 175.20L891.16 176.55L891.19 178.01L888.88 178.93L887.43 178.40L887.59 177.67L886.89 178.35L886.69 177.23L886.20 177.12L885.81 177.67L884.72 177.31L884.44 177.85L884.09 177.04L883.63 177.49L882.53 177.30L881.53 178.02L881.40 176.97L880.58 176.93L881.13 176.32L880.60 176.48L880.26 177.54L878.86 177.55L879.41 180.01L879.22 182.03L878.16 182.05L877.29 183.73L875.71 183.79L875.48 184.18L875.94 184.75L874.90 183.99L873.14 185.12L871.77 184.94L872.00 189.46L871.62 190.79L874.85 192.11L876.05 195.54L876.86 195.88L877.35 197.43L877.23 200.89L878.11 201.72L879.20 204.76L878.63 206.88L879.47 209.39L879.33 210.31L880.63 212.99L881.87 214.31L881.52 214.64L881.89 215.15L881.73 216.97L882.34 217.40L882.35 218.74L881.46 219.51L881.81 220.08L881.45 220.32L882.06 220.66L884.37 220.45L886.01 221.72L887.05 223.27L888.66 223.44L889.52 224.28L890.23 226.30L891.97 227.78L891.91 228.96L890.97 229.30L890.69 231.58L891.30 232.58L890.32 236.03L881.63 236.14L879.83 237.02L874.43 235.88L874.45 235.51L873.13 235.49L871.73 236.13L870.45 233.01L869.09 232.32L867.72 232.81L867.37 235.01L866.12 236.25L865.24 234.08L864.50 233.43L863.03 233.85L861.08 235.57L857.00 236.76L856.64 235.61L857.28 234.39L857.25 233.14L856.20 232.80L854.37 233.73L852.97 233.53L852.43 232.61L852.46 231.37L850.57 230.17L847.03 226.48L844.09 225.26L841.14 225.63L827.14 232.60L818.15 230.57L816.89 232.82L817.42 233.51L816.61 234.05L816.56 234.93L815.92 235.51L816.53 236.28L817.43 236.32L817.53 237.07L819.06 238.02L819.13 238.82L819.97 239.18L822.55 242.75L824.17 250.87L823.86 251.59L822.92 252.03L822.64 253.03L821.66 253.54L820.99 252.65L819.45 252.67L817.01 255.60L815.59 255.65L813.87 254.57L811.99 254.84L811.45 255.77L809.45 257.24L809.21 258.23L809.83 258.91L809.73 259.48L807.83 260.24L806.66 261.73L807.35 261.68L808.08 263.35L807.87 264.61L805.59 267.02L804.39 266.56L801.88 267.69L800.79 266.86L800.84 266.21L799.93 266.02L798.40 264.56L798.09 266.39L797.34 266.37L796.60 267.09L796.24 266.03L795.45 266.18L794.57 265.62L794.31 267.08L793.45 267.15L792.46 268.44L791.63 271.29L790.86 272.07L788.76 272.44L788.10 273.52L786.15 273.56L784.41 275.30L781.94 275.32L781.41 275.94L780.36 275.92L779.11 276.86L778.40 276.55L776.94 277.38L776.45 277.27L775.66 275.56L772.94 276.74L772.18 275.76L771.51 276.17L771.70 276.80L771.12 278.12L767.16 279.87L765.29 279.59L764.13 279.97L762.03 281.59L762.53 282.50L762.35 283.78L761.06 285.15L756.59 286.22L754.08 286.01L751.10 287.60L745.57 287.74L742.60 288.75L739.78 288.93L740.08 290.67L741.51 292.37L741.64 293.82L742.85 296.05L742.20 297.00L742.27 298.14L740.57 298.73L740.76 302.35L739.47 303.75L739.21 305.82L738.25 307.31L737.09 307.76L736.16 309.02L733.22 310.10L733.01 310.62L729.63 311.38L727.94 310.56L728.26 310.08L727.79 309.22L729.10 307.16L728.51 305.89L724.97 305.15L723.51 305.76L723.41 306.65L721.71 307.56L720.52 306.28L721.43 305.52L721.18 304.72L719.34 305.18L719.16 304.76L717.66 305.15L715.65 304.55L713.30 305.01L709.45 304.23L707.24 302.91L704.98 303.15L703.91 304.91L703.03 304.81L701.80 305.55L701.99 306.20L700.94 305.96L700.64 306.77L699.07 306.48L698.77 307.31L698.05 307.20L697.88 307.72L697.10 307.36L696.72 309.27L695.58 309.95L695.84 310.63L695.35 311.51L695.89 312.09L695.91 311.60L696.48 311.70L696.60 312.37L697.44 312.73L697.41 313.53L696.90 313.57L697.23 314.01L696.91 315.20L697.69 316.63L697.30 317.04L697.71 318.46L696.82 319.13L696.51 320.42L695.28 320.75L695.17 320.25L694.99 320.68L693.88 320.81L694.49 322.39L693.40 324.16L692.98 323.82L692.65 324.11L693.10 324.70L689.39 326.91L687.49 326.97L687.19 327.75L685.65 328.68L685.48 329.07L686.04 329.58L684.54 330.70L684.26 331.52L686.15 332.32L687.58 334.79L683.36 336.46L682.17 337.77L682.77 338.50L682.61 339.01L684.61 340.02L684.48 340.68L685.91 340.64L686.11 341.21L685.35 341.05L685.37 341.54L686.42 341.44L686.82 341.98L686.70 343.19L687.51 343.35L687.52 344.02L686.73 344.39L686.95 345.15L686.18 346.02L686.81 346.12L686.57 347.60L686.15 348.03L685.87 347.50L685.51 347.63L686.44 348.32L685.88 349.37L686.11 350.08L684.95 350.75L685.37 351.99L684.78 352.35L686.66 354.25L686.47 354.81L687.25 354.31L687.73 354.55L687.26 356.37L687.60 357.38L688.26 357.11L688.07 357.86L691.01 357.60L690.28 360.28L689.11 361.09L689.97 361.49L689.80 362.07L691.00 362.46L691.63 363.55L692.51 363.56L693.26 364.57L693.92 363.89L694.15 364.68L695.75 364.27L696.45 362.98L696.16 362.64L697.96 362.97L697.98 363.93L698.49 364.13L698.16 364.61L697.85 364.33L698.00 364.77L699.21 364.95L699.84 364.13L700.31 365.64L701.08 365.85L700.61 368.64L700.94 369.76L702.15 370.15L703.40 368.81L704.57 368.57L705.36 368.84L704.49 369.35L705.65 370.02L706.25 369.63L707.06 370.09L707.00 369.58L707.46 369.61L707.81 370.99L707.88 370.17L708.27 370.15L708.79 370.66L708.09 371.12L708.32 371.58L709.30 371.26L709.45 370.25L709.77 371.06L710.59 371.04L710.33 371.40L709.26 371.31L709.78 371.98L709.54 372.66L710.59 372.43L710.54 373.36L712.33 373.85L712.78 373.58L716.41 375.19L717.67 374.56L718.06 375.61L720.50 377.76L720.36 378.57L720.81 378.70L720.31 379.47L721.53 379.35L722.35 379.90L722.08 380.42L723.12 381.00L722.48 382.06L722.53 382.97L722.22 382.42L720.72 382.00L720.19 383.39L720.51 383.54L719.29 384.22L719.00 383.86L718.28 385.02L718.87 386.06L718.48 386.44L718.55 387.88L719.06 387.55L719.53 388.25L718.04 388.37L717.28 390.21L717.98 390.94L717.51 391.58L718.22 391.59L717.67 392.22L717.09 391.80L716.89 392.54L717.50 392.74L715.90 392.78L715.32 393.98L716.42 394.48L717.06 393.89L717.24 394.53L716.58 395.04L717.79 395.44L718.19 396.07L716.99 396.10L717.53 397.06L717.17 398.41L715.98 398.56L715.37 399.40L715.54 400.21L715.03 399.92L715.12 400.60L714.22 399.74L713.72 400.39L714.32 401.01L713.58 401.41L714.77 401.74L715.47 402.61L715.07 402.80L714.34 401.92L713.82 402.19L714.85 404.10L715.56 403.99L715.73 404.63L714.11 404.48L713.83 404.85L714.01 405.42L714.93 405.50L714.45 406.30L714.76 406.83L715.28 406.46L714.86 407.69L715.00 408.55L715.42 408.24L715.49 408.58L714.94 409.06L715.67 410.45L716.74 416.37L716.56 420.90L716.92 421.64L716.17 422.17L716.62 422.44L716.26 422.75L716.51 425.01L717.27 425.37L717.40 426.02L716.93 426.62L716.68 426.08L716.16 426.29L716.71 427.86L716.24 427.78L716.11 428.52L716.88 428.82L716.56 429.68L716.11 429.34L715.38 429.89L715.68 430.57L716.13 430.43L715.70 430.74L715.87 431.36L715.39 431.04L714.88 431.35L716.07 431.97L715.68 432.65L716.18 432.99L716.08 433.56L715.58 434.47L714.81 433.88L713.92 434.42L713.64 435.47L714.16 435.65L714.11 436.16L712.26 436.66L711.84 437.36L711.03 437.22L711.64 437.78L711.31 438.29L709.50 439.34L709.20 440.26L707.84 441.05L708.07 442.47L708.66 442.38L708.26 444.56L708.94 444.47L708.75 445.98L709.27 446.35L709.20 447.23L708.26 446.64L708.12 447.10L709.19 447.79L709.86 449.11L710.21 449.06L710.18 448.25L710.50 449.40L711.68 449.29L711.15 450.20L710.61 449.94L710.81 451.48L710.34 451.15L709.87 451.54L710.09 450.80L709.20 451.06L708.45 450.43L708.72 451.85L709.47 452.36L709.29 452.87L708.55 452.46L708.62 453.11L708.21 452.46L707.95 452.78L708.13 453.58L709.00 454.22L708.17 455.16L708.97 455.76L707.38 456.30L709.64 458.97L711.90 459.57L713.53 460.60L717.00 465.81L715.25 466.47L714.24 465.92L713.92 464.77L713.06 464.59L712.44 465.32L712.68 466.77L711.27 467.66L709.65 467.28L706.38 468.37L703.81 468.10L702.70 469.81L699.51 472.61L698.71 475.10L697.01 477.12L695.58 475.34L694.64 474.94L694.44 473.00L693.03 471.80L692.13 472.38L689.61 471.32L689.28 470.64L688.16 470.89L688.51 469.94L687.24 469.21L686.97 468.55L682.46 466.77L681.77 465.97L678.97 465.69L676.06 463.09L675.39 464.97L673.21 467.25L673.00 469.70L672.18 471.38L671.70 470.25L670.03 468.88L669.64 466.61L665.91 465.72L665.57 467.34L666.16 470.61L665.02 472.39L665.24 473.56L664.18 474.11L662.82 475.93L661.13 476.26L660.49 477.09L658.72 476.27L657.64 477.23L656.68 476.68L654.83 476.74L655.30 473.94L653.28 473.63L652.25 472.47L648.13 474.43L647.70 476.32L647.99 477.88L645.84 478.81L644.27 478.35L644.89 480.39L645.73 481.40L645.83 484.57L647.31 487.04L645.93 487.97L643.34 488.99L641.92 488.37L639.45 488.49L638.07 488.04L636.50 488.23L635.74 488.88L634.72 488.26L632.72 488.51L631.22 487.89L630.06 488.61L628.36 488.41L626.99 490.08L625.93 489.44L624.44 489.72L621.73 491.87L619.23 495.27L616.98 494.59L615.61 496.37L613.15 496.31L612.58 497.63L610.19 498.00L604.28 502.24L601.86 503.44L599.64 503.69L596.92 505.79L594.72 506.02L593.32 507.47L593.21 508.83L591.80 509.78L590.47 509.92L589.67 510.77L588.79 510.74L588.30 511.28L588.31 512.42L587.20 512.13L587.43 513.42L582.05 518.79L582.58 518.93L581.83 521.22L583.41 520.96L583.85 521.64L585.02 522.03L584.85 523.14L585.37 523.76L585.68 526.18L587.06 526.56L589.12 524.65L590.05 525.16L591.15 526.83L591.58 528.94L590.97 530.08L591.27 532.48L592.69 532.92L594.77 535.22L595.67 534.39L595.00 534.80L594.74 534.05L593.75 533.62L593.87 532.23L594.12 533.41L594.49 533.40L595.06 532.40L596.47 532.08L596.49 531.36L596.02 530.73L595.76 531.92L595.75 531.15L594.56 532.69L594.13 531.95L594.75 532.43L594.42 531.72L594.95 532.04L594.53 530.44L595.29 530.36L595.50 529.66L596.30 529.70L596.58 530.45L597.10 530.49L597.40 529.80L598.10 530.25L597.48 533.45L596.53 534.03L597.29 534.62L597.38 535.29L598.09 535.13L598.15 536.02L600.11 538.49L600.31 540.15L601.70 540.40L602.84 539.62L601.98 536.40L600.93 534.92L600.44 531.26L604.59 528.38L605.41 526.96L605.30 525.61L605.99 525.37L605.67 524.79L606.71 522.97L607.78 522.95L608.29 523.89L609.85 523.00L611.91 523.20L612.78 525.41L612.01 529.64L612.62 530.28L613.54 529.48L613.94 529.77L614.16 532.17L613.16 533.75L612.91 535.64L611.55 535.35L611.43 534.94L611.47 535.31L609.87 536.31L610.29 536.53L609.72 537.49L609.88 538.30L609.26 538.63L609.73 539.49L609.31 541.53L610.27 542.34L610.25 541.54L611.49 540.54L611.02 539.21L612.36 539.75L612.06 539.05L612.81 538.81L612.82 539.58L613.72 538.55L613.64 534.64L615.46 533.36L615.16 532.92L615.58 531.99L616.41 532.80L615.81 533.24L615.44 535.38L617.45 537.35L617.95 539.11L619.90 539.90L620.22 541.52L620.88 541.76L621.71 543.11L622.36 543.12L622.27 545.09L623.28 545.76L623.49 548.98L624.67 550.14L626.77 550.49L626.83 551.41L625.61 552.07L624.45 554.21L621.92 555.88L620.53 555.50L619.75 554.49L616.64 553.90L616.23 552.27L614.35 553.10L610.61 552.00L607.91 552.35L607.57 553.26L608.09 554.16L609.97 554.28L610.58 554.88L610.70 555.70L610.11 556.48L606.92 557.96L602.58 557.14L596.56 558.30L595.43 559.43L595.44 561.98L596.76 563.86L597.38 565.96L596.50 566.65L592.71 566.72L589.41 568.67L588.08 570.14L590.43 574.25L592.94 576.41L594.69 579.02L595.05 581.99L594.49 587.11L594.97 590.56L594.79 594.70L595.50 596.63L595.34 598.68L595.71 599.57L596.93 601.02L599.29 601.21L599.11 603.80L599.60 604.99L602.69 606.07L603.51 608.83L604.67 610.16L610.97 613.91L613.87 616.87L614.86 616.85L616.39 615.70L617.22 617.42L620.94 619.64L620.71 620.64L618.30 621.32L613.19 624.51L612.12 626.26L611.88 627.83L609.96 630.23L609.00 633.42L606.42 633.31L603.43 635.06L600.96 633.57L594.44 632.27L588.62 629.53L587.31 629.38L578.08 635.11L573.73 642.02L573.62 644.89L572.84 646.36L570.85 646.85L566.06 646.49L563.30 641.97L561.69 643.33L562.09 645.05L561.80 645.73L559.52 647.84L558.44 648.52L556.88 647.78L555.12 648.21L551.30 646.52L549.41 644.65L548.62 642.18L547.48 640.91L546.63 638.78L542.18 637.66L536.36 631.14L533.06 630.44L530.68 628.97L530.27 628.12L530.18 624.97L530.83 622.30L528.33 622.55L526.26 620.24L522.92 620.00L522.05 618.01L521.04 617.37L519.35 617.76L517.76 620.16L513.25 621.17L512.36 620.67L511.72 618.88L509.85 617.91L508.57 616.05L504.62 616.61L500.95 616.40L498.00 614.58L495.41 610.88L493.51 610.14L488.06 604.98L484.18 602.44L481.21 603.13L480.65 605.31L478.85 607.12L478.74 610.40L479.81 613.21L478.30 614.51L478.40 615.76L479.55 617.51L477.90 619.99L478.33 622.84L477.05 624.76L475.51 625.47L472.35 625.09L469.13 626.70L467.31 626.81L466.16 628.99L465.38 629.48L463.04 629.16L461.67 630.08L458.13 631.10L449.98 632.24L449.50 627.03L446.22 623.92L446.57 622.94L446.34 620.73L444.84 619.42L444.41 618.34L445.79 616.68L444.86 616.00L443.40 613.47L441.60 614.87L440.74 614.43L441.45 613.34L440.63 612.02L436.47 611.61L435.21 612.32L434.75 611.35L435.36 609.65L432.57 610.41L431.35 608.43L426.30 604.57L425.22 602.06L423.85 602.48L420.89 600.22L419.37 600.56L418.72 599.97L418.00 600.66L416.94 599.91L415.68 600.04L415.10 600.90L415.36 603.27L414.78 603.92L413.27 603.54L412.61 602.90L411.84 603.41L410.59 601.60L410.22 599.95L411.25 597.84L410.89 596.94L411.36 596.08L410.91 595.28L411.98 593.95L411.33 592.22L411.93 591.02L413.34 590.92L414.80 587.98L413.96 586.32L414.08 585.44L412.91 584.33L412.60 581.71L411.80 581.09L411.85 580.28L409.88 579.28L409.97 578.36L409.10 577.99L409.00 577.17L408.06 576.47L406.29 576.20L405.51 576.61L404.95 576.18L404.12 576.50L401.77 575.51L400.16 575.46L397.78 571.63L396.91 571.51L397.21 570.72L396.62 570.79L396.15 570.07L394.88 570.70L394.02 569.94L393.82 568.48L392.99 567.19L392.99 565.85L391.69 566.22L390.48 564.88L388.69 564.74L387.61 563.75L387.30 562.77L386.29 562.55L383.54 560.30L385.41 557.31L385.25 553.21L386.31 552.01L387.24 547.27L387.80 546.80L387.31 546.18L386.89 546.43L387.09 545.66L386.65 545.10L387.27 544.44L386.70 543.72L386.70 544.42L386.33 544.32L386.17 543.56L385.19 543.11L385.09 543.56L384.58 543.51L384.02 542.14L383.24 542.99L382.59 542.85L381.42 543.65L380.72 543.40L379.91 544.20L378.43 543.92L378.86 543.57L378.39 543.13L378.52 542.00L378.32 541.77L377.96 542.67L377.45 541.02L375.92 540.64L375.06 545.07L375.25 547.51L373.86 551.67L373.10 552.19L372.26 554.55L369.73 557.81L368.44 561.43L365.28 565.83L362.66 567.41L360.06 567.62L359.06 568.70L355.15 568.38L356.83 574.18L356.89 576.36L356.26 579.33L354.38 582.13L354.84 585.79L353.99 586.77L353.84 589.07L354.41 591.96L353.95 592.39L354.74 593.46L353.50 594.51L351.70 598.34L347.23 600.01L341.77 605.38L336.97 607.35L334.98 610.32L333.95 610.32L332.65 611.40L332.39 610.72L331.17 610.15L330.87 610.49L329.08 610.08L328.81 610.92L326.75 612.30L325.54 612.25L323.91 613.07L324.44 613.97L322.65 616.83L321.63 616.59L320.45 617.02L318.01 619.36L313.23 620.81L312.91 620.55L312.55 621.03L309.39 620.36L306.88 622.59L305.77 622.89L302.69 626.01L301.04 626.77L300.21 625.70L299.23 621.38L296.02 622.55L291.53 620.49L290.17 618.15L289.06 618.52L288.20 618.11L287.05 618.57L284.57 621.56L283.55 621.31L280.75 616.13L279.16 614.97L277.76 611.61L274.71 611.49L271.23 613.25L270.18 616.67L268.47 617.00L267.82 618.73L267.31 618.50L266.02 621.46L266.90 622.46L266.08 623.00L266.37 626.94L255.97 622.43L250.28 621.74L249.18 622.12L247.01 624.27L245.00 624.26L239.51 621.54L237.58 621.06L231.56 621.20L226.02 619.98L221.86 616.02L221.05 616.06L218.92 613.89L217.16 614.07L216.74 613.74L213.30 610.34L212.13 608.53L207.45 604.64L204.77 604.53L203.38 606.41L204.66 609.64L200.36 608.92L197.61 606.70L196.78 606.58L194.69 607.74L193.96 609.25L192.70 610.40L193.67 614.60L195.60 614.91L198.45 616.71L201.63 620.58L199.79 620.57L202.93 624.95L200.98 625.87L200.27 625.70L199.34 626.49L199.86 627.32L199.40 629.47L199.95 630.60L199.42 630.85L199.26 631.86L195.53 634.34L194.94 635.41L190.85 631.95L187.72 631.50L187.00 632.48L181.43 632.53L181.47 633.10L180.85 633.26L178.08 632.64L176.42 633.63L176.66 634.42L175.88 635.50L172.81 637.58L172.92 639.09L171.39 639.24L169.66 642.67L169.63 644.36L166.84 643.95L166.76 644.64L166.52 643.92L162.79 643.58L162.60 644.06L162.00 643.35L161.04 644.12L159.76 644.31L160.05 643.05L158.77 641.98L158.76 641.35L151.46 640.00L147.98 640.41L147.75 637.59L144.38 636.04L145.07 634.94L145.06 632.90L146.02 631.50L145.84 630.74L142.95 628.22L139.48 626.57L138.85 626.90L137.91 626.55L136.52 627.63L135.67 626.89L134.47 627.15L133.43 626.17L131.27 628.27L128.81 628.96L125.50 628.52L122.90 629.59L121.45 629.09L120.82 629.46L121.05 630.91L120.41 630.67L115.91 632.22L115.63 630.05L114.35 630.53L113.85 631.54L112.60 631.47L107.96 635.58L106.35 635.29L106.64 635.95L105.95 636.33L103.63 634.30L102.69 634.23L101.88 632.25L100.03 632.04L98.88 631.21L98.44 629.94L95.71 628.72L92.52 628.13L91.66 627.44L86.13 626.44L83.90 625.22L79.23 620.50L78.64 617.13L76.90 615.49L80.46 616.02L81.13 614.21L80.44 610.55L82.57 606.19L82.62 603.52L79.69 602.90L77.44 601.19L75.73 598.33L74.55 594.34L80.84 595.94L130.06 589.44L130.10 586.79L126.99 582.16L117.96 571.99L118.92 570.58L120.06 571.38L121.63 571.41ZM711.36 179.08L711.60 179.05L711.61 178.96L711.36 179.08Z","regions":[{"id":"SI031","na":"Pomurska","nm":27,"d":"M804.5 179.7L801.1 177.7L799.8 172.5L797.0 170.5L793.5 163.2L790.1 161.1L789.4 157.4L792.0 153.7L792.2 148.7L784.7 148.0L781.8 145.7L777.2 144.4L773.7 139.5L773.8 136.1L772.1 132.9L776.5 131.6L776.6 129.9L778.6 129.6L780.4 127.4L780.1 125.6L778.3 126.3L775.8 125.2L773.3 126.9L770.6 124.9L768.1 125.0L765.9 123.6L767.7 119.3L767.4 115.3L762.8 114.2L760.5 116.3L759.6 113.2L758.3 114.4L755.3 112.6L753.3 113.1L751.1 109.3L748.0 109.2L746.0 107.0L748.1 105.1L745.0 100.2L740.4 101.9L736.4 97.2L740.5 93.9L749.3 91.0L762.0 91.4L774.5 96.4L783.8 104.5L798.7 107.8L802.7 114.7L810.7 118.3L811.9 105.6L807.8 99.2L808.0 94.6L805.5 94.9L803.4 92.4L800.2 92.3L800.2 89.8L797.1 86.4L794.5 77.5L796.0 75.0L796.5 55.6L798.1 52.9L794.3 45.3L795.9 42.9L797.4 41.8L800.8 43.7L806.5 39.2L808.5 41.6L808.1 42.8L811.1 39.3L813.6 40.7L814.6 39.3L815.7 40.1L817.8 35.3L819.4 33.9L821.7 34.0L825.4 28.9L827.7 30.5L831.0 26.8L832.7 27.7L832.7 29.2L835.0 29.4L835.6 32.0L844.3 33.3L846.1 30.8L850.2 31.6L852.8 28.0L858.1 26.4L861.7 26.7L864.9 25.5L866.8 23.1L876.2 25.0L883.8 24.5L886.9 30.1L891.9 31.4L895.2 36.3L898.4 35.3L898.1 37.0L900.5 37.8L901.5 41.5L901.5 42.6L899.8 42.7L899.6 46.0L898.6 46.1L898.6 53.7L892.1 55.2L890.7 56.7L890.6 64.9L895.8 64.8L896.0 66.1L892.7 75.1L896.8 77.4L897.5 79.6L901.1 82.7L902.2 86.0L901.3 87.7L903.2 87.5L904.3 92.0L908.4 88.5L911.0 91.4L910.9 93.3L907.9 96.3L911.7 98.8L925.5 100.3L923.5 106.1L924.7 106.7L923.2 108.8L924.7 110.4L922.7 113.0L923.2 115.5L918.3 115.5L916.1 113.0L914.8 113.4L914.8 117.1L913.0 117.7L915.1 126.3L919.8 127.4L925.0 134.9L931.1 135.7L938.2 146.4L939.6 145.6L942.6 149.4L942.5 154.8L944.7 154.9L945.5 156.2L950.1 154.9L953.2 160.2L953.0 167.3L957.5 169.3L955.1 174.4L955.6 176.1L957.8 176.5L956.9 179.5L955.3 179.0L955.0 180.5L968.7 187.7L972.2 191.8L976.9 192.7L970.5 194.7L967.4 193.9L966.4 192.1L959.6 193.0L958.4 190.7L955.5 191.8L952.9 191.0L953.3 186.4L946.0 184.0L943.8 181.8L944.6 179.4L942.3 179.2L941.6 177.6L939.2 178.3L939.2 175.5L937.8 176.1L938.1 177.7L936.9 177.1L937.3 174.0L936.0 176.2L933.5 175.5L930.6 176.8L929.5 174.9L930.4 172.3L929.2 171.0L927.7 171.6L926.8 169.3L925.6 169.5L925.2 171.4L920.9 168.9L922.0 170.5L920.6 172.0L918.8 169.7L919.1 166.6L915.3 168.2L913.7 165.5L912.1 166.2L909.5 164.9L909.3 163.6L912.9 161.9L908.9 160.1L908.0 163.7L905.7 164.5L904.2 162.7L903.9 164.1L906.0 165.4L906.2 167.2L905.0 167.2L904.4 164.9L899.7 165.5L902.1 166.8L901.0 171.1L899.5 172.2L898.6 171.0L895.9 171.4L894.0 172.6L891.0 178.1L888.9 178.9L884.1 177.0L881.5 178.0L881.1 176.3L878.9 177.6L879.2 182.0L875.7 183.8L875.9 184.8L871.8 184.9L872.0 188.5L865.9 189.8L863.6 191.9L864.4 195.6L862.2 196.5L861.0 193.9L856.9 192.9L859.1 198.9L856.4 197.8L856.3 195.6L854.6 196.5L852.3 194.0L854.2 190.0L852.7 188.6L849.7 189.8L847.4 184.3L845.3 187.3L843.0 186.5L842.6 190.1L841.0 191.4L835.6 189.4L832.6 184.4L829.3 185.3L821.1 184.3L819.3 185.4L812.7 181.2L807.5 182.1L803.7 180.8L804.5 179.7Z","c":[867.7,111.0]},{"id":"SI032","na":"Podravska","nm":41,"d":"M707.1 283.4L699.5 283.1L698.1 281.9L694.0 283.0L694.8 280.7L691.2 277.4L684.8 278.9L682.3 276.4L677.6 279.1L673.6 277.5L670.8 283.6L669.4 281.6L666.5 282.2L669.1 278.2L666.9 276.4L668.6 271.3L666.5 268.7L667.0 264.9L666.0 258.7L664.0 255.7L664.4 251.5L662.8 250.3L655.3 253.2L653.7 251.4L653.5 247.4L652.0 246.6L649.2 249.3L646.7 247.3L644.2 248.9L641.4 248.0L639.2 248.9L639.1 247.9L636.9 247.5L637.5 245.2L632.4 244.4L629.7 242.6L630.0 240.5L625.9 239.9L622.4 237.2L626.7 236.8L627.4 233.9L628.8 234.1L627.0 230.9L624.6 230.2L622.9 227.9L624.1 227.0L626.4 227.5L626.8 221.4L628.9 219.2L624.3 216.3L622.9 213.3L619.9 215.9L615.3 213.4L613.7 209.4L609.3 209.9L606.0 208.7L606.4 204.6L603.7 201.6L603.6 197.4L599.9 197.8L597.7 195.7L597.4 187.2L601.3 181.3L600.2 179.1L604.0 177.7L605.7 174.6L604.5 173.9L605.7 171.3L605.0 170.1L607.0 167.7L606.4 164.5L607.1 163.6L609.5 165.2L610.6 160.0L611.7 161.1L614.1 159.9L613.4 157.6L614.8 154.8L613.8 155.4L612.2 152.6L615.2 150.4L621.9 151.4L630.0 159.4L634.6 157.9L634.4 152.8L636.6 150.3L635.7 148.9L633.1 150.7L631.6 148.7L632.7 147.5L632.2 144.9L635.8 141.1L635.1 139.0L636.6 138.5L636.9 136.4L632.9 136.0L631.8 128.9L628.1 126.3L626.5 126.6L626.1 124.2L623.3 121.1L628.7 120.5L629.2 123.8L631.7 124.0L634.4 126.9L637.4 125.8L639.5 127.3L639.0 131.1L641.1 132.8L641.4 137.6L645.2 138.7L648.8 135.0L652.2 136.1L653.0 137.9L655.8 136.7L655.8 134.5L658.2 134.6L663.2 129.3L664.8 131.0L666.9 127.3L665.2 124.1L666.0 122.9L667.4 123.4L668.0 121.8L665.0 114.1L667.2 112.7L669.6 113.3L672.0 111.5L672.2 109.4L675.1 109.1L675.0 108.1L678.6 108.0L680.5 105.0L684.1 106.1L683.0 106.6L683.2 108.9L685.5 107.9L687.4 109.5L691.6 108.8L691.0 107.4L692.9 104.5L697.3 104.1L696.2 98.3L704.0 97.8L709.7 101.1L717.3 102.4L722.5 100.6L731.4 100.8L736.4 97.2L740.4 101.9L744.4 99.8L748.1 105.1L746.0 107.0L748.0 109.2L751.1 109.3L753.3 113.1L755.3 112.6L758.3 114.4L759.6 113.2L760.5 116.3L762.8 114.2L767.4 115.3L767.7 119.3L765.9 123.6L773.3 126.9L775.8 125.2L778.3 126.3L780.1 125.6L780.4 127.4L778.6 129.6L776.6 129.9L776.5 131.6L772.1 132.9L773.8 136.1L773.7 139.5L777.2 144.4L781.8 145.7L784.7 148.0L792.2 148.7L792.0 153.7L789.4 157.4L790.1 161.1L793.5 163.2L797.0 170.5L799.8 172.5L801.1 177.7L804.5 179.7L803.7 180.8L807.5 182.1L812.7 181.2L819.3 185.4L821.1 184.3L829.3 185.3L832.6 184.4L835.6 189.4L841.0 191.4L842.6 190.1L843.0 186.5L845.3 187.3L847.4 184.3L849.7 189.8L852.7 188.6L854.2 190.0L852.3 194.0L854.6 196.5L856.3 195.6L856.4 197.8L859.1 198.9L856.9 192.9L861.0 193.9L862.3 196.5L864.4 195.6L863.6 191.9L865.9 189.8L872.0 188.5L871.6 190.8L874.9 192.1L877.4 197.4L879.3 210.3L881.9 214.3L881.4 220.3L884.4 220.5L888.7 223.4L892.1 228.1L891.0 229.3L890.3 236.0L879.8 237.0L874.5 235.5L871.7 236.1L869.1 232.3L867.7 232.8L866.1 236.3L864.5 233.4L857.0 236.8L857.3 233.1L853.0 233.5L852.5 231.4L844.1 225.3L841.1 225.6L827.1 232.6L818.1 230.6L815.9 235.5L822.6 242.9L824.2 250.5L822.5 253.1L819.4 252.7L817.0 255.6L812.0 254.8L809.5 257.2L809.7 259.5L806.7 261.7L807.9 264.6L805.6 267.0L801.9 267.7L798.4 264.6L798.1 266.4L796.6 267.1L794.5 265.6L790.9 272.1L776.9 277.4L775.7 275.6L772.9 276.7L772.2 275.8L771.1 278.1L762.0 281.6L762.4 283.8L761.1 285.2L731.2 291.1L728.8 288.7L728.3 286.1L724.4 287.9L723.4 285.5L719.1 284.1L710.4 286.6L709.6 285.1L711.1 282.6L707.1 283.4ZM711.6 179.0L711.6 179.0L711.4 179.1L711.6 179.0Z","c":[725.3,194.2]},{"id":"SI033","na":"Koroška","nm":12,"d":"M541.0 221.4L539.6 220.8L540.0 218.3L532.2 215.2L530.8 216.4L531.2 220.0L524.1 215.4L513.3 212.9L506.7 213.4L498.7 208.2L492.2 205.9L491.4 206.3L493.7 211.0L488.7 212.5L488.2 215.5L478.7 215.9L473.7 221.4L465.7 221.0L459.3 222.3L456.4 219.8L445.8 220.0L441.7 217.3L439.4 218.2L437.6 216.1L435.5 216.8L434.8 220.2L432.5 221.8L425.6 210.5L423.2 210.5L422.5 208.4L409.7 208.7L408.7 208.0L410.1 205.0L409.0 203.3L411.2 200.7L416.0 202.5L416.9 200.9L415.5 197.9L416.8 195.3L418.9 195.2L420.6 187.0L422.7 187.7L424.6 191.1L428.5 184.8L430.5 188.0L434.0 185.1L438.9 185.1L441.5 187.3L451.3 183.0L451.0 177.7L453.3 174.3L452.6 171.8L455.2 170.2L452.6 167.4L455.4 166.3L457.5 156.4L461.2 152.6L462.6 147.7L465.0 147.2L465.8 142.3L471.5 138.8L474.3 140.0L475.7 139.2L476.7 142.2L479.4 142.5L479.4 141.6L481.0 143.5L481.9 143.1L482.1 135.4L484.6 137.8L491.8 130.3L496.3 133.9L498.8 143.7L503.4 138.4L503.3 135.2L509.6 126.9L517.0 122.2L524.1 122.1L529.2 125.0L530.8 122.1L534.0 121.5L536.6 118.8L539.9 121.3L540.7 120.4L542.8 122.9L544.5 120.0L546.2 120.2L547.7 118.7L550.8 120.5L553.4 119.8L554.1 121.1L558.6 120.2L563.0 124.7L571.0 125.7L574.4 127.4L582.3 125.1L586.6 125.5L593.6 121.4L599.0 123.7L601.5 121.4L606.3 122.4L609.0 120.6L609.7 122.1L614.6 122.8L623.3 121.1L626.1 124.2L626.5 126.6L628.1 126.3L631.8 128.9L632.9 136.0L636.9 136.4L636.6 138.5L635.1 139.0L635.8 141.1L632.2 144.9L632.7 147.5L631.6 148.7L633.1 150.7L635.7 148.9L636.6 150.3L634.4 152.8L634.6 157.9L630.9 159.7L621.9 151.4L615.2 150.4L612.2 152.6L613.8 155.4L614.8 154.8L613.4 157.6L614.1 159.9L611.7 161.1L610.6 160.0L609.5 165.2L607.1 163.6L606.4 164.5L607.0 167.7L605.0 170.1L605.7 171.3L604.5 173.9L605.7 174.6L604.0 177.7L600.2 179.1L601.3 181.3L597.1 188.4L596.8 191.1L598.2 194.2L597.7 195.7L596.6 195.4L596.6 198.2L598.7 203.0L601.8 205.7L600.8 207.8L599.2 209.1L591.8 208.8L583.6 211.6L580.5 218.2L580.0 224.5L578.3 225.2L574.9 231.2L573.4 231.0L574.2 233.9L560.5 235.6L558.3 234.8L555.9 233.9L555.5 232.3L558.2 228.5L557.7 225.3L555.2 226.3L554.0 225.3L551.3 226.6L551.3 229.0L548.6 228.8L548.1 226.2L546.9 227.0L543.7 225.6L541.5 224.0L541.0 221.4Z","c":[527.9,177.1]},{"id":"SI034","na":"Savinjska","nm":31,"d":"M541.3 326.4L536.8 320.8L534.2 319.4L527.4 322.6L520.3 320.5L518.5 319.4L517.9 316.5L515.9 318.8L511.7 318.6L509.8 320.1L507.7 319.3L508.8 317.3L507.7 317.7L507.8 316.9L501.7 317.9L499.6 316.6L488.6 321.3L484.4 321.6L477.8 314.9L477.7 310.0L480.3 309.1L480.9 309.9L483.5 308.2L478.7 307.1L477.3 302.3L475.2 303.2L473.8 301.2L471.0 301.1L469.2 298.2L465.6 297.3L461.6 293.9L446.9 291.7L438.4 294.0L435.0 292.4L432.6 293.7L424.8 290.7L417.2 290.6L414.6 286.7L417.5 281.9L417.3 279.0L410.7 280.4L408.1 279.4L409.3 273.6L408.3 268.1L407.0 266.4L403.5 266.4L397.4 259.2L398.3 257.6L397.6 245.0L390.7 247.8L384.2 246.9L382.8 248.8L376.1 243.4L376.2 240.4L380.0 239.3L381.0 237.4L380.2 236.3L382.7 231.6L383.1 223.4L381.3 222.0L382.5 216.9L385.2 215.4L385.4 213.9L404.2 210.7L407.6 207.9L413.1 209.2L422.5 208.4L423.2 210.5L425.6 210.5L427.8 212.6L431.8 221.7L434.8 220.2L435.5 216.8L437.6 216.1L439.4 218.2L441.7 217.3L445.8 220.0L456.4 219.8L459.3 222.3L465.7 221.0L473.7 221.4L478.7 215.9L488.2 215.5L488.7 212.5L493.7 211.0L491.4 206.1L492.8 205.9L499.6 208.6L506.7 213.4L513.3 212.9L524.1 215.4L531.1 220.0L531.8 215.1L539.8 218.2L539.6 220.8L540.8 220.7L541.5 224.0L545.5 226.5L548.1 226.2L548.6 228.8L551.3 229.0L551.3 226.6L554.0 225.3L555.2 226.3L557.7 225.3L558.2 228.5L555.5 231.5L555.6 233.2L560.5 235.6L574.2 233.9L573.4 231.0L574.9 231.2L578.3 225.2L580.0 224.5L580.5 218.2L584.5 210.9L600.5 208.1L601.8 205.7L598.7 203.0L596.6 198.2L596.6 195.4L598.2 195.7L599.9 197.8L603.6 197.4L603.7 201.6L606.4 204.6L606.0 208.7L609.3 209.9L613.7 209.4L615.3 213.4L619.9 215.9L622.9 213.3L624.3 216.3L628.9 219.2L626.8 221.4L626.4 227.5L624.1 227.0L622.9 227.9L624.6 230.2L627.0 230.9L628.8 234.1L627.4 233.9L626.7 236.8L622.4 237.2L625.9 239.9L630.0 240.5L629.7 242.6L632.4 244.4L637.5 245.2L636.9 247.5L639.1 247.9L639.2 248.9L641.4 248.0L644.2 248.9L646.7 247.3L649.2 249.3L652.0 246.6L653.5 247.4L653.7 251.4L655.3 253.2L662.8 250.3L664.4 251.5L664.0 255.7L666.0 258.7L667.0 264.9L666.5 268.7L668.6 271.3L666.9 276.4L669.1 278.2L666.5 282.2L669.4 281.6L670.8 283.6L673.6 277.5L677.6 279.1L682.3 276.4L684.8 278.9L690.7 277.2L694.8 280.7L694.0 283.0L698.1 281.9L699.5 283.1L704.7 282.0L707.1 283.4L711.1 282.6L709.6 285.1L710.4 286.6L719.1 284.1L723.4 285.5L724.4 287.9L728.3 286.1L728.8 288.7L731.2 291.1L739.8 288.9L742.9 296.0L742.2 298.2L740.6 298.7L740.8 302.4L738.3 307.3L732.0 310.9L727.9 310.5L728.5 305.9L725.0 305.2L721.7 307.6L720.5 306.3L721.2 304.7L713.3 305.0L707.2 302.9L705.0 303.1L702.0 306.2L697.0 307.6L695.3 311.5L697.4 312.7L697.7 318.5L696.5 320.4L693.9 320.8L694.5 322.4L693.1 324.7L685.7 328.7L684.3 331.5L687.6 334.8L682.2 337.6L687.5 343.4L684.8 352.3L686.5 354.8L687.7 354.5L688.1 357.9L691.0 357.6L689.1 361.1L691.8 364.4L687.9 369.8L685.0 368.1L682.9 370.5L683.7 379.8L685.7 383.6L690.4 384.3L690.4 385.5L694.5 385.2L697.5 382.6L700.4 384.6L697.6 386.4L699.7 386.9L694.5 389.6L685.0 398.5L677.2 402.1L675.0 401.2L677.5 397.9L678.4 398.7L678.1 397.5L679.3 397.3L682.3 389.1L676.7 390.1L675.1 389.2L672.8 391.3L671.0 390.6L667.6 391.9L666.0 380.0L662.9 379.7L660.7 374.1L658.3 372.9L653.3 375.9L653.6 374.7L651.6 372.7L645.7 370.0L639.5 372.1L636.5 370.7L631.9 372.7L630.2 371.8L624.0 372.5L618.7 369.2L615.3 371.2L611.7 369.1L603.3 369.9L598.7 368.8L595.6 369.7L593.7 371.8L588.5 371.4L589.1 377.4L586.1 375.5L587.3 369.5L583.9 368.8L584.6 365.1L583.2 362.8L581.6 367.1L580.5 366.5L578.9 367.9L573.5 367.4L569.7 363.7L566.7 366.1L564.1 365.8L563.5 364.2L560.1 365.1L559.3 367.5L556.5 367.6L555.0 364.1L552.2 363.2L549.9 359.7L544.7 356.2L546.5 355.0L546.0 353.2L547.4 352.9L550.7 356.4L555.5 358.2L556.4 355.2L561.1 353.9L558.8 351.5L558.4 347.1L556.6 346.7L557.1 344.6L555.2 342.1L551.7 340.6L551.8 336.5L549.5 335.8L548.2 332.8L545.3 334.2L542.4 333.3L543.5 329.8L541.6 329.7L541.3 326.4Z","c":[605.2,298.8]},{"id":"SI035","na":"Zasavska","nm":4,"d":"M419.0 367.4L420.4 364.9L429.7 363.1L431.6 361.0L431.0 359.1L433.6 358.2L434.5 357.0L433.3 356.2L434.8 355.0L435.5 356.3L435.9 354.9L436.7 356.3L437.1 354.7L438.5 355.3L438.4 354.1L442.1 354.2L443.3 355.4L442.7 352.8L443.9 351.5L446.6 352.5L444.6 348.4L448.0 346.3L451.0 346.7L454.0 343.2L456.7 342.9L457.0 341.2L454.1 340.5L457.2 340.8L458.1 338.3L455.8 337.3L454.9 334.1L453.1 332.9L453.2 330.4L450.4 330.0L448.9 328.0L458.7 328.5L462.9 327.5L466.6 325.0L472.3 326.4L471.7 324.1L474.1 323.2L476.0 320.6L474.5 312.3L477.8 312.2L478.0 316.2L481.3 317.4L484.4 321.6L488.6 321.3L499.6 316.6L501.7 317.9L507.8 316.9L507.7 317.7L508.8 317.3L507.7 319.3L509.8 320.1L511.7 318.6L515.9 318.8L517.9 316.5L519.5 320.2L527.4 322.6L534.4 319.5L541.3 326.4L541.6 329.7L543.5 329.8L542.6 333.5L545.3 334.2L548.2 332.8L549.5 335.8L551.8 336.5L551.3 339.9L556.6 343.9L556.6 346.7L558.4 347.1L558.8 351.5L561.1 353.9L556.4 355.2L555.3 358.2L550.7 356.4L547.4 352.9L546.0 353.2L546.5 355.0L544.7 356.2L551.0 361.0L546.7 364.1L541.6 364.2L540.6 362.4L534.8 361.4L535.4 363.2L534.0 365.0L535.4 365.9L534.9 367.0L532.0 368.1L529.8 367.4L529.8 372.0L527.0 370.8L524.6 374.9L526.7 381.9L531.3 383.6L531.1 387.0L534.5 392.9L529.5 391.6L529.4 395.7L526.2 395.1L525.9 394.0L523.4 394.5L522.0 395.3L521.2 399.2L512.6 399.1L511.4 401.6L512.6 401.9L515.1 406.9L514.3 410.1L512.3 409.9L509.2 412.6L510.4 414.9L508.8 416.4L506.2 415.7L505.7 416.8L500.8 413.9L495.8 414.1L494.4 411.6L489.6 410.3L489.7 408.0L488.4 407.2L482.7 407.4L482.2 403.6L483.8 402.5L483.7 399.7L481.5 398.0L483.2 392.2L480.7 386.4L482.7 382.6L479.4 381.2L475.9 376.8L473.9 377.4L473.2 374.1L471.1 374.4L464.7 370.6L467.0 374.9L465.9 377.0L460.8 378.6L457.6 378.1L454.9 380.5L448.0 377.6L446.6 378.8L447.9 380.4L444.7 380.6L444.2 382.2L442.3 381.6L441.6 379.4L435.4 377.8L434.6 376.7L435.8 376.4L431.0 372.2L422.6 372.8L421.2 371.7L422.4 370.0L419.0 367.4Z","c":[478.5,364.6]},{"id":"SI036","na":"Posavska","nm":6,"d":"M627.0 490.1L624.6 483.6L621.4 480.7L618.5 480.4L618.7 478.1L616.9 475.6L617.5 472.9L619.4 472.1L619.2 469.8L617.3 465.4L616.5 466.0L614.4 463.9L616.4 462.6L617.5 463.4L620.5 460.7L622.0 461.0L623.9 458.7L619.6 458.8L619.2 454.6L617.6 454.3L618.4 450.4L614.9 449.1L615.1 448.1L609.0 449.2L604.8 447.1L607.8 443.4L606.9 431.6L609.7 427.5L604.3 424.2L604.0 418.1L600.8 419.3L595.7 417.7L595.9 422.8L588.2 418.0L586.1 422.6L588.6 425.3L588.9 427.5L584.9 428.2L584.7 425.6L580.7 421.7L578.2 423.2L579.0 426.1L576.2 426.9L575.1 429.7L574.0 427.7L571.3 428.8L572.1 431.5L569.6 431.4L567.1 429.4L565.0 429.8L562.2 426.6L560.4 426.4L559.6 424.3L553.3 419.9L553.1 415.7L550.2 414.2L549.1 410.4L549.7 408.0L552.6 407.3L552.6 405.0L553.8 404.1L552.7 402.2L554.4 401.7L552.6 401.5L550.3 402.8L549.7 402.0L549.3 404.2L545.3 404.9L543.9 408.4L543.2 401.1L535.6 397.6L536.2 395.1L531.1 387.0L531.3 383.6L528.1 383.1L526.2 381.2L524.9 373.0L527.3 370.7L529.8 372.0L529.8 367.4L532.0 368.1L534.9 367.0L535.4 365.9L534.0 365.0L535.3 361.0L540.6 362.4L541.6 364.2L546.7 364.1L551.0 361.0L552.2 363.2L555.9 365.1L556.9 367.8L559.3 367.5L560.2 365.0L563.5 364.2L564.1 365.8L566.7 366.1L569.7 363.7L573.5 367.4L578.9 367.9L580.5 366.5L581.6 367.1L583.2 362.8L584.6 365.1L583.9 368.8L587.3 369.5L586.1 375.5L589.1 377.4L588.5 371.4L593.7 371.8L595.6 369.7L598.7 368.8L603.3 369.9L611.7 369.1L615.3 371.2L618.7 369.2L624.0 372.5L630.2 371.8L631.9 372.7L636.5 370.7L639.5 372.1L645.7 370.0L651.6 372.7L653.6 374.7L653.3 375.9L658.3 372.9L660.7 374.1L662.9 379.7L666.0 380.0L667.6 391.9L671.0 390.6L672.8 391.3L675.1 389.2L676.7 390.1L682.3 389.1L679.3 397.3L678.1 397.5L678.4 398.7L677.5 397.9L675.0 401.2L676.9 402.1L685.0 398.5L694.5 389.6L699.7 386.9L697.6 386.8L700.4 384.6L697.5 382.6L694.5 385.2L690.4 385.5L690.4 384.3L685.7 383.6L683.7 379.8L683.1 369.7L685.0 368.1L687.9 369.8L691.6 363.5L694.1 364.7L695.8 364.3L696.2 362.6L698.0 363.0L698.0 364.8L699.8 364.1L701.1 365.8L700.9 369.8L704.6 368.6L705.6 370.0L707.5 369.6L707.8 371.0L708.3 370.2L708.3 371.6L709.5 370.3L710.6 371.0L709.3 371.3L709.5 372.7L716.4 375.2L717.7 374.6L720.5 377.8L720.3 379.5L722.4 379.9L722.5 383.0L720.7 382.0L720.5 383.5L718.9 383.9L718.5 387.8L719.5 388.2L718.0 388.4L717.3 390.2L718.2 391.6L715.3 394.0L717.1 393.9L716.6 395.0L718.2 396.1L717.0 396.1L717.2 398.4L715.1 400.6L714.2 399.7L713.6 401.4L715.5 402.6L713.8 402.2L715.7 404.6L713.8 404.8L715.3 406.5L716.7 416.4L716.2 422.2L717.4 426.0L716.2 426.3L716.9 428.8L714.9 431.3L716.1 433.6L713.9 434.4L714.1 436.2L711.0 437.2L711.3 438.3L707.8 441.1L709.3 446.3L708.1 447.1L709.9 449.1L710.2 448.3L711.7 449.3L710.8 451.5L708.4 450.4L709.5 452.4L708.0 452.8L709.0 455.8L707.4 456.3L709.6 459.0L713.5 460.6L717.0 465.8L715.2 466.5L713.1 464.6L711.3 467.7L703.8 468.1L696.9 477.1L693.0 471.8L688.2 470.9L687.0 468.5L679.0 465.7L675.8 463.0L672.2 471.4L669.6 466.6L665.9 465.7L665.2 473.6L660.6 477.1L654.8 476.7L655.3 473.9L652.3 472.5L648.1 474.4L648.0 477.9L644.3 478.4L647.3 487.0L645.5 488.2L635.7 488.9L631.2 487.9L628.4 488.4L627.0 490.1Z","c":[662.1,425.5]},{"id":"SI037","na":"Jugovzhodna Slovenija","nm":21,"d":"M500.9 616.4L484.5 602.5L481.2 603.1L478.8 607.1L479.8 613.2L478.3 614.5L479.6 617.5L477.9 620.0L477.6 624.2L467.3 626.8L465.4 629.5L450.3 632.3L449.5 627.0L446.3 624.0L446.3 620.7L444.4 618.3L445.8 616.7L443.4 613.5L441.6 614.9L440.6 612.0L435.2 612.3L435.4 609.7L432.6 610.4L426.3 604.6L425.2 602.1L423.8 602.5L420.9 600.2L415.7 600.0L414.8 603.9L411.8 603.4L410.2 599.9L412.0 594.0L411.3 592.2L414.8 588.0L411.9 580.3L408.1 576.5L400.2 575.5L397.2 570.7L394.0 569.9L393.0 565.8L388.7 564.7L383.5 560.3L385.3 557.7L385.3 553.2L387.8 546.9L387.1 544.0L384.6 543.5L384.0 542.1L378.4 543.9L377.4 541.0L373.2 539.8L372.9 532.1L366.3 512.2L369.5 510.3L373.2 514.7L378.7 513.1L374.8 506.5L376.5 500.5L376.1 496.1L371.4 495.4L369.0 492.5L369.4 491.2L374.0 491.1L375.3 488.2L383.6 488.9L384.1 485.6L387.1 486.3L389.9 484.7L394.4 486.7L396.1 484.8L399.7 485.8L403.1 484.0L403.6 482.4L404.9 483.0L408.3 477.5L412.6 478.2L416.6 482.4L417.3 485.2L427.9 493.0L429.3 496.9L435.0 503.7L452.1 518.0L457.6 511.2L454.3 508.7L454.0 506.0L447.7 503.3L444.9 496.5L445.6 495.8L444.7 491.8L446.9 489.7L445.8 487.9L450.6 486.0L455.5 488.5L460.5 488.4L462.5 485.8L462.5 471.7L460.2 471.1L459.6 469.6L461.0 467.5L458.9 467.3L458.0 462.8L459.6 461.9L469.0 463.1L469.4 461.3L468.3 461.0L469.8 460.6L469.7 458.4L468.0 457.5L466.3 455.1L466.8 453.4L463.2 449.8L467.6 445.1L468.0 442.5L469.7 441.9L468.2 432.4L470.9 428.3L469.8 427.0L470.1 424.1L472.5 424.4L474.6 423.2L476.0 423.7L475.3 424.5L477.7 424.2L478.3 421.0L480.4 419.9L481.5 417.4L486.8 416.3L486.6 413.5L487.9 411.1L492.3 410.7L494.4 411.6L495.8 414.1L500.8 413.9L504.4 416.9L506.2 415.7L508.8 416.4L510.4 414.9L509.2 412.6L512.3 409.9L514.3 410.1L514.1 407.7L515.1 407.1L512.6 401.9L511.4 401.6L511.6 400.2L512.9 398.9L521.2 399.2L522.0 395.3L523.4 394.5L525.9 394.0L526.2 395.1L529.5 395.7L528.9 392.5L530.5 391.5L535.7 394.3L535.8 397.8L543.2 401.1L543.9 408.4L545.3 404.9L549.3 404.2L549.7 402.0L550.3 402.8L552.6 401.5L554.4 401.7L552.7 402.2L553.8 404.1L552.6 405.0L552.6 407.3L550.9 407.2L549.3 408.9L550.2 414.2L553.1 415.7L553.3 419.9L559.6 424.3L560.4 426.4L562.2 426.6L565.0 429.8L568.1 429.7L569.6 431.4L572.1 431.5L571.3 428.8L573.5 427.7L575.1 429.7L576.2 426.9L579.0 426.1L578.2 423.2L580.7 421.7L584.7 425.6L584.9 428.2L588.9 427.5L588.6 425.3L586.1 422.6L588.2 418.0L595.9 422.8L595.7 417.7L600.8 419.3L604.0 418.1L604.3 424.2L609.7 427.5L606.9 431.6L607.8 443.4L604.8 447.1L609.0 449.2L615.1 448.1L614.9 449.1L618.4 450.4L617.6 454.3L619.2 454.6L619.6 458.8L623.9 458.7L622.0 461.0L620.5 460.7L617.5 463.4L616.4 462.6L614.4 463.9L616.5 466.0L617.3 465.4L619.2 469.8L619.4 472.1L617.5 472.9L616.9 475.6L618.7 478.1L618.5 480.4L621.4 480.7L624.6 483.6L626.0 489.5L622.3 491.4L619.2 495.3L617.0 494.6L615.6 496.4L613.2 496.3L604.3 502.2L594.7 506.0L593.2 508.8L587.2 512.1L587.4 513.4L582.1 518.8L581.8 521.2L585.0 522.0L585.7 526.2L589.8 524.9L591.2 527.1L591.3 532.5L594.8 535.2L595.7 534.4L593.7 533.6L593.9 532.2L594.1 533.4L594.5 533.4L596.5 531.4L594.6 532.7L594.5 530.4L598.1 530.3L596.5 534.0L600.3 540.2L601.7 540.4L602.8 539.6L600.4 531.3L604.6 528.4L606.7 523.0L608.3 523.9L611.9 523.2L612.8 525.4L612.0 529.6L613.9 529.8L614.2 532.2L612.9 535.6L611.4 534.9L609.9 536.3L609.3 541.5L610.3 542.3L611.0 539.2L612.4 539.7L613.7 538.5L613.6 534.6L615.6 532.0L616.4 532.8L615.4 535.4L622.4 543.1L623.5 549.0L626.8 550.5L621.9 555.9L616.6 553.9L616.2 552.3L614.3 553.1L607.9 552.4L608.1 554.2L610.6 554.9L610.1 556.5L606.9 558.0L602.6 557.1L596.6 558.3L595.4 562.0L597.4 566.0L592.7 566.7L588.1 570.1L594.7 579.0L595.7 599.6L596.9 601.0L599.3 601.2L599.6 605.0L602.7 606.1L604.7 610.2L613.9 616.9L616.4 615.7L620.9 620.4L613.2 624.5L609.0 633.4L606.4 633.3L603.4 635.1L586.9 629.5L578.1 635.1L573.7 642.0L572.8 646.4L566.1 646.5L563.3 642.0L561.7 643.3L561.8 645.7L558.1 648.5L551.3 646.5L546.6 638.8L542.2 637.7L536.4 631.1L530.9 629.2L530.8 622.3L528.3 622.6L526.3 620.2L522.9 620.0L521.0 617.4L517.8 620.2L513.0 621.2L509.1 616.3L500.9 616.4Z","c":[475.4,520.0]},{"id":"SI038","na":"Primorsko-notranjska","nm":6,"d":"M356.9 574.8L353.8 588.7L354.7 593.5L351.5 598.6L347.2 600.0L341.8 605.4L337.0 607.3L335.0 610.3L332.6 611.4L329.1 610.1L323.9 613.1L322.7 616.8L312.5 621.0L309.4 620.4L301.0 626.8L299.2 621.4L296.0 622.5L291.5 620.5L290.2 618.1L287.0 618.6L284.6 621.6L283.6 621.3L277.8 611.6L275.4 611.4L271.2 613.3L270.2 616.7L267.3 618.5L266.0 621.5L266.9 622.5L266.4 626.9L256.0 622.4L250.3 621.7L247.0 624.3L245.0 624.3L239.6 621.6L242.1 620.4L241.7 617.1L243.6 617.9L241.1 610.7L241.6 607.6L238.8 610.6L235.6 606.3L231.4 606.4L231.7 603.4L235.0 599.6L234.9 593.4L238.0 590.8L238.4 585.7L239.9 583.6L236.4 582.4L234.2 584.8L232.5 583.2L232.1 579.2L233.5 575.9L232.2 575.6L239.3 567.9L234.2 565.2L233.9 559.9L229.7 557.2L232.6 554.9L230.9 553.4L230.9 550.2L226.8 546.5L229.4 542.1L228.1 541.6L228.4 535.4L224.9 534.4L225.9 531.0L225.1 530.9L227.1 528.1L227.1 524.3L227.8 525.4L229.7 522.5L233.7 524.0L235.1 521.3L233.8 516.9L234.8 516.3L231.3 516.1L234.1 515.9L234.4 513.8L231.0 514.0L231.1 512.2L230.0 513.6L230.7 511.7L229.6 511.4L231.5 510.4L228.2 506.9L220.9 505.9L218.2 502.1L219.7 496.3L221.7 497.5L222.4 485.3L224.8 483.3L225.7 485.7L226.7 479.5L220.6 469.0L236.6 464.1L235.8 463.2L239.1 458.6L242.5 457.7L245.7 453.9L247.5 454.2L251.1 452.2L253.2 454.5L263.1 451.6L263.6 453.1L265.9 453.6L268.5 456.4L270.5 455.8L271.7 456.7L273.3 458.6L271.9 459.7L272.4 460.6L278.8 459.8L279.3 461.0L277.6 461.5L279.3 463.5L280.5 462.9L280.9 464.6L284.0 461.4L283.4 463.4L287.3 463.0L289.2 465.5L296.3 450.5L295.9 448.6L299.2 445.9L303.2 446.0L308.1 451.9L310.9 449.7L312.2 451.6L312.1 455.3L313.9 456.1L317.7 452.9L321.3 457.7L323.1 458.3L323.1 460.6L325.4 461.5L328.3 454.8L331.2 455.4L334.9 460.6L336.4 460.6L339.3 459.6L342.6 455.1L345.6 456.6L352.7 450.9L355.8 453.8L355.0 455.8L356.3 456.3L356.0 460.2L354.1 461.5L354.7 464.3L357.8 467.0L357.0 469.2L362.6 474.5L364.3 480.0L369.2 480.3L370.6 486.2L374.3 488.6L374.3 490.9L369.4 491.2L369.0 492.5L371.4 495.4L376.1 496.1L376.5 500.5L374.8 506.5L378.7 513.1L373.2 514.7L369.5 510.3L366.3 512.2L372.9 532.1L373.2 539.8L376.0 540.5L375.2 547.5L365.3 565.8L359.1 568.7L355.2 568.4L356.9 574.8Z","c":[300.8,535.9]},{"id":"SI041","na":"Osrednjeslovenska","nm":25,"d":"M331.2 455.4L328.3 454.8L325.1 461.4L323.1 460.6L323.1 458.3L321.3 457.7L317.7 452.9L313.9 456.1L312.1 455.3L312.2 451.6L310.9 449.7L308.1 451.9L303.2 446.0L299.2 445.9L295.9 448.6L296.3 450.5L289.2 465.5L287.3 463.0L283.4 463.4L284.0 461.4L280.9 464.6L280.5 462.9L279.3 463.5L277.6 461.5L279.3 461.0L278.8 459.8L272.4 460.6L271.9 459.7L273.3 458.6L271.7 456.7L270.5 455.8L268.5 456.4L265.9 453.6L263.6 453.1L263.1 451.6L253.2 454.5L251.1 452.2L247.5 454.2L245.7 453.9L244.7 455.5L242.3 444.0L236.4 437.9L235.6 429.3L239.6 427.0L239.8 421.9L242.4 420.1L242.0 413.5L239.2 414.4L238.5 411.3L240.6 410.0L239.8 408.0L245.6 407.9L247.1 402.8L249.9 402.5L248.3 400.7L250.2 398.5L248.5 397.7L249.7 396.1L251.4 396.3L251.5 392.7L253.7 392.7L253.8 390.6L256.6 391.7L258.6 391.0L259.3 387.3L262.1 386.2L262.3 384.0L266.3 381.4L266.9 377.1L269.3 375.5L269.9 373.3L268.8 370.7L269.8 364.2L273.7 360.6L274.2 358.7L281.0 358.4L283.1 354.5L285.5 353.9L296.1 356.9L299.1 356.2L301.7 358.5L305.4 358.8L307.4 355.3L307.3 352.2L304.6 349.8L305.1 344.7L310.7 342.2L313.3 337.5L315.6 338.1L315.8 335.0L318.9 335.7L318.7 337.8L320.0 338.3L321.6 335.8L321.0 332.7L325.1 332.9L333.2 328.8L330.8 326.4L328.3 319.0L331.2 319.6L333.5 318.4L336.4 319.0L336.3 319.9L343.9 318.5L347.2 316.1L344.6 313.3L347.4 312.5L350.0 314.1L355.4 313.8L356.5 314.8L360.6 308.1L362.7 306.9L365.4 307.3L371.6 297.3L376.8 295.5L375.5 293.4L376.5 291.2L378.4 291.0L374.7 286.1L375.9 284.5L371.0 282.8L372.5 279.6L367.6 272.5L368.2 269.7L372.5 266.1L372.9 264.2L371.6 262.0L371.2 262.8L368.1 260.0L367.8 258.6L371.5 252.6L370.5 250.0L367.2 247.9L368.6 245.5L375.0 245.1L376.1 243.4L382.8 248.8L384.2 246.9L390.7 247.8L397.6 245.0L398.3 257.6L397.4 259.2L403.5 266.4L407.0 266.4L408.3 268.1L409.3 273.6L408.1 279.4L410.7 280.4L417.3 279.0L417.5 281.9L414.6 286.7L417.2 290.6L424.8 290.7L432.6 293.7L435.0 292.4L438.4 294.0L446.9 291.7L461.6 293.9L465.6 297.3L469.2 298.2L471.0 301.1L473.8 301.2L475.2 303.2L477.3 302.3L478.7 307.1L483.6 308.2L480.9 309.9L480.3 309.1L477.7 310.0L478.3 311.8L477.3 312.6L474.4 312.4L476.0 320.6L474.1 323.2L471.7 324.1L472.3 326.4L466.6 325.0L462.9 327.5L458.7 328.5L448.9 328.0L450.4 330.0L453.2 330.4L453.1 332.9L454.9 334.1L455.8 337.3L458.1 338.3L457.2 340.8L454.1 340.5L457.0 341.2L456.7 342.9L454.0 343.2L451.0 346.7L448.0 346.3L444.6 348.4L446.6 352.5L443.9 351.5L442.7 352.8L443.3 355.4L442.1 354.2L438.4 354.1L438.5 355.3L437.1 354.7L436.7 356.3L435.9 354.9L435.5 356.3L434.8 355.0L433.3 356.2L434.5 357.0L433.6 358.2L431.0 359.1L431.6 361.0L429.7 363.1L420.4 364.9L419.0 367.4L422.4 370.0L421.2 371.7L422.6 372.8L431.0 372.2L435.8 376.4L434.6 376.7L435.4 377.8L441.6 379.4L442.3 381.6L444.2 382.2L444.7 380.6L447.9 380.4L446.6 378.8L448.0 377.6L454.9 380.5L457.6 378.1L460.8 378.6L465.9 377.0L467.0 374.9L464.7 370.6L471.1 374.4L473.2 374.1L473.9 377.4L475.9 376.8L479.4 381.2L482.7 382.6L480.7 386.4L483.2 392.2L481.5 398.0L483.7 399.7L483.8 402.5L482.2 403.6L482.7 407.4L489.7 408.0L489.6 410.2L487.1 411.9L486.8 416.3L481.5 417.4L480.4 419.9L478.3 421.0L477.7 424.2L475.3 424.5L476.0 423.7L474.6 423.2L472.5 424.4L470.1 424.1L469.8 427.0L470.9 428.3L468.2 432.4L469.7 441.9L468.0 442.5L467.6 445.1L463.2 449.8L466.8 453.4L466.3 455.1L468.0 457.5L469.7 458.4L469.8 460.6L468.3 461.0L469.4 461.3L469.0 463.1L459.6 461.9L458.0 462.8L458.9 467.3L461.0 467.5L459.6 469.6L460.2 471.1L462.5 471.7L462.5 485.8L460.5 488.4L455.5 488.5L450.6 486.0L445.8 487.9L446.9 489.7L444.7 491.8L445.6 495.8L444.9 496.5L447.7 503.3L454.0 506.0L454.3 508.7L457.6 511.2L452.1 518.0L435.0 503.7L429.3 496.9L427.9 493.0L417.3 485.2L416.6 482.4L412.6 478.2L408.3 477.5L404.9 483.0L403.6 482.4L403.1 484.0L399.7 485.8L396.1 484.8L394.4 486.7L389.9 484.7L387.1 486.3L384.1 485.6L383.6 488.9L375.3 488.2L374.6 489.9L370.6 486.2L369.2 480.3L364.3 480.0L362.6 474.5L357.0 469.2L357.8 467.0L354.7 464.3L354.1 461.5L356.0 460.2L356.3 456.3L355.0 455.8L355.8 453.8L352.7 450.9L345.6 456.6L342.6 455.1L339.3 459.6L336.4 460.6L334.9 460.6L331.2 455.4Z","c":[354.1,380.7]},{"id":"SI042","na":"Gorenjska","nm":18,"d":"M251.4 396.3L243.0 397.9L242.9 396.0L241.0 396.6L240.2 394.4L238.1 394.4L239.3 392.2L237.5 390.4L238.0 388.0L236.4 386.2L237.4 385.2L236.5 384.1L233.3 386.3L232.4 385.4L231.4 387.8L229.7 388.0L232.6 383.4L230.3 383.2L231.1 382.0L229.9 377.9L215.2 368.1L212.8 363.3L213.9 357.1L216.2 353.5L220.1 351.2L220.5 347.7L224.8 342.7L224.3 339.6L229.4 332.7L229.6 328.9L219.4 325.6L215.2 327.0L212.3 325.3L208.4 326.9L203.8 323.7L204.9 312.8L206.8 309.9L209.5 309.5L210.4 306.1L209.9 301.0L205.8 297.6L201.6 297.0L198.1 299.2L195.3 297.6L192.2 299.9L179.2 300.3L176.5 302.2L173.7 300.7L170.9 302.0L166.3 301.0L164.4 298.9L162.1 298.9L158.9 296.4L150.9 295.7L139.6 286.5L135.2 286.1L133.4 281.5L129.9 279.3L128.1 275.5L128.9 273.0L126.6 271.2L133.0 264.8L131.7 255.8L132.9 253.8L142.6 249.6L147.0 245.8L150.2 246.2L151.6 244.4L154.1 244.8L157.4 242.6L160.3 236.6L160.2 235.4L156.7 235.3L154.0 232.6L153.1 223.1L150.0 222.9L149.5 221.4L147.4 221.2L143.3 217.4L136.1 215.9L131.9 210.2L128.3 211.5L125.1 214.4L114.8 218.3L113.6 216.6L115.9 209.8L118.5 208.0L120.1 202.5L118.7 197.7L123.6 191.8L121.6 190.5L122.3 187.4L121.5 184.5L125.7 181.2L125.1 174.2L128.6 174.2L131.9 176.8L136.9 176.5L140.5 178.1L143.9 176.9L144.5 179.2L148.8 182.1L154.0 181.8L159.7 176.6L166.7 178.7L173.7 176.6L174.7 175.0L180.3 176.8L183.5 175.9L186.8 177.0L188.2 179.1L192.6 180.1L200.4 186.5L202.2 185.9L206.0 188.2L206.3 190.2L211.2 193.3L215.5 193.2L221.4 188.4L236.4 191.7L239.4 194.6L245.2 195.7L249.1 203.4L249.1 206.8L253.9 210.2L254.8 213.3L257.4 214.2L261.3 214.1L265.7 209.9L270.5 211.9L274.0 210.3L276.2 213.4L279.2 215.0L284.9 212.2L287.3 212.5L292.9 210.3L298.3 212.6L300.2 215.9L305.5 215.8L310.8 213.1L322.1 212.5L330.3 209.4L336.2 209.2L338.8 210.9L336.3 213.9L339.7 217.1L340.2 219.6L347.1 220.0L350.0 220.9L350.6 223.6L352.3 222.8L354.6 223.9L358.6 219.1L363.4 217.8L366.4 223.3L368.7 224.6L373.7 235.9L373.7 239.6L376.1 241.3L376.1 243.4L375.0 245.1L368.6 245.5L367.3 247.6L370.5 250.0L371.5 252.6L367.8 258.6L368.1 260.0L371.2 262.8L371.6 262.0L372.9 264.2L372.5 266.1L368.2 269.7L367.6 272.5L372.5 279.6L371.0 282.8L375.9 284.5L374.7 286.1L378.4 291.0L376.5 291.2L375.5 293.4L376.8 295.5L371.6 297.3L365.4 307.3L362.7 306.9L360.6 308.1L356.5 314.8L355.4 313.8L350.0 314.1L347.4 312.5L344.6 313.3L347.2 316.1L343.9 318.5L336.3 319.9L336.4 319.0L333.5 318.4L331.2 319.6L328.3 319.0L330.8 326.4L333.2 328.8L325.1 332.9L321.0 332.7L321.6 335.8L320.0 338.3L318.7 337.8L318.9 335.7L315.8 335.0L315.6 338.1L313.3 337.5L310.7 342.2L305.1 344.7L304.6 349.8L307.3 352.2L307.4 355.3L305.4 358.8L301.7 358.5L299.1 356.2L296.1 356.9L285.5 353.9L283.1 354.5L281.0 358.4L274.2 358.7L273.7 360.6L269.8 364.2L268.8 370.7L269.9 373.3L269.3 375.5L266.9 377.1L266.3 381.4L262.3 384.0L262.1 386.2L259.3 387.3L258.6 391.0L256.6 391.7L253.8 390.6L253.7 392.7L251.6 392.6L251.0 393.8L251.4 396.3Z","c":[255.0,286.1]},{"id":"SI043","na":"Goriška","nm":13,"d":"M121.9 458.4L120.9 465.1L116.9 468.4L113.0 468.5L110.7 476.5L103.1 476.5L98.9 474.7L85.2 474.5L82.8 467.8L78.7 464.7L78.9 459.9L84.5 451.0L82.5 447.8L84.5 443.8L89.3 440.6L92.2 433.6L98.3 425.3L96.9 419.3L100.1 404.9L97.4 402.2L92.8 404.7L84.6 401.6L80.6 404.5L77.8 410.6L72.8 409.7L70.0 412.1L66.5 411.5L65.3 408.7L62.7 407.7L61.6 405.5L58.0 405.2L53.4 397.0L50.6 394.1L51.6 391.8L56.8 389.8L60.5 381.9L60.5 377.2L56.9 376.2L57.1 371.8L58.9 370.1L60.2 371.0L65.7 368.1L67.1 368.5L67.0 367.0L68.1 367.3L70.9 364.1L71.6 361.5L73.3 362.1L73.6 361.0L80.0 359.4L83.2 354.3L87.1 352.6L88.7 349.2L95.5 344.4L98.7 339.9L101.5 338.9L104.9 332.9L104.6 328.6L108.3 324.1L107.9 321.6L105.3 318.1L98.9 315.5L93.2 318.6L92.6 316.5L85.8 316.8L86.5 314.7L82.3 318.0L79.0 317.7L77.7 309.8L74.9 307.7L70.9 305.7L68.1 306.2L68.0 303.3L64.0 305.0L60.2 304.6L58.6 303.8L58.5 301.9L54.4 300.6L42.8 300.1L43.4 305.5L36.5 308.2L32.4 304.3L34.7 301.1L33.1 299.0L36.4 297.5L36.6 296.1L31.6 292.0L28.2 282.4L28.0 275.4L26.3 271.8L24.4 272.5L23.1 268.7L31.2 267.9L32.4 265.5L35.7 265.7L35.3 260.9L38.2 258.4L42.1 258.6L43.7 255.2L45.0 254.9L45.3 253.3L41.8 244.9L42.4 242.5L46.4 241.2L51.2 242.4L56.5 238.3L60.1 238.2L63.3 235.7L65.7 235.7L65.7 233.1L68.9 230.9L72.2 231.9L73.1 229.6L76.1 229.3L78.4 226.6L81.0 226.1L84.0 222.4L84.6 214.6L88.3 210.6L93.9 208.5L95.6 209.5L97.3 208.1L101.0 208.5L105.3 206.5L106.9 209.6L113.4 209.4L115.6 210.6L113.5 216.5L114.6 218.2L125.1 214.4L128.3 211.5L131.9 210.2L136.1 215.9L143.3 217.4L147.4 221.2L149.5 221.4L150.0 222.9L153.3 223.2L154.0 232.6L156.7 235.3L160.2 235.4L160.3 237.6L157.4 242.6L154.1 244.8L151.6 244.4L150.2 246.2L147.0 245.8L142.6 249.6L132.9 253.8L131.7 255.8L133.0 264.8L126.6 271.2L128.9 273.0L128.1 275.5L129.9 279.3L133.4 281.5L135.2 286.1L139.6 286.5L150.9 295.7L158.9 296.4L162.1 298.9L164.4 298.9L166.3 301.0L170.9 302.0L173.7 300.7L176.5 302.2L179.2 300.3L192.2 299.9L195.3 297.6L198.1 299.2L201.6 297.0L205.8 297.6L209.9 301.0L210.4 306.1L209.5 309.5L206.8 309.9L204.9 312.8L203.8 323.7L208.4 326.9L212.3 325.3L215.2 327.0L219.4 325.6L229.6 328.9L229.4 332.7L224.3 339.6L224.8 342.7L220.5 347.7L220.1 351.2L216.2 353.5L213.4 358.1L212.5 361.1L214.0 366.3L218.8 370.9L224.9 374.1L226.7 376.7L229.9 377.9L231.1 382.0L230.3 383.2L232.6 383.4L229.7 388.0L231.4 387.8L232.4 385.4L233.3 386.3L236.5 384.1L237.4 385.2L236.4 386.2L238.0 388.0L237.5 390.4L239.3 392.2L238.1 394.4L240.2 394.4L241.0 396.6L242.9 396.0L243.0 397.9L248.3 397.6L249.9 398.0L250.2 398.6L248.3 400.7L249.9 402.5L247.1 402.8L245.6 407.9L239.8 408.0L240.6 410.0L238.5 411.3L238.6 414.0L242.0 413.5L242.4 420.1L239.8 421.9L239.6 427.0L235.6 429.3L236.4 437.9L242.3 444.0L244.7 455.5L242.5 457.7L239.1 458.6L235.8 463.2L236.6 464.1L220.6 469.0L226.7 479.5L225.7 485.7L224.8 483.3L222.4 485.3L221.7 497.5L219.7 496.3L218.2 501.5L210.9 496.4L208.5 496.2L207.4 499.3L206.8 498.2L205.0 499.9L204.2 499.2L205.6 497.7L201.0 493.8L196.6 492.6L192.8 489.2L186.0 487.7L178.5 480.3L177.6 478.1L176.2 478.2L176.7 476.7L174.7 476.7L175.2 474.3L173.3 474.1L173.4 471.9L168.1 472.8L167.4 474.0L163.2 473.2L160.0 472.1L157.7 469.7L157.9 467.7L152.0 464.7L150.7 466.3L149.1 466.0L149.2 469.1L143.0 469.4L137.5 466.3L135.7 463.1L130.7 459.5L121.0 456.4L121.9 458.4Z","c":[150.5,354.0]},{"id":"SI044","na":"Obalno-kraška","nm":8,"d":"M105.9 636.3L98.4 629.9L85.2 626.0L79.2 620.5L78.6 617.1L76.9 615.5L80.5 616.0L80.4 610.6L82.6 603.5L77.4 601.2L74.6 594.3L80.8 595.9L130.1 589.4L130.1 586.8L127.0 582.2L118.0 572.0L118.9 570.6L122.0 571.4L128.6 570.1L140.5 576.8L156.1 577.3L159.8 576.3L160.5 573.1L164.1 571.3L165.3 565.8L171.6 562.8L180.3 555.7L166.2 545.8L158.6 535.2L155.2 532.4L155.4 523.8L148.5 516.8L143.8 507.8L135.2 504.8L134.2 502.5L129.3 502.8L126.2 500.9L126.1 499.3L118.7 494.6L109.6 485.8L108.2 487.3L106.7 483.4L97.2 483.9L97.2 482.6L93.1 484.8L93.0 483.0L84.8 479.5L85.2 474.5L98.9 474.7L103.1 476.5L110.7 476.5L113.0 468.5L116.9 468.4L120.9 465.1L122.1 459.2L121.0 456.4L130.7 459.5L135.7 463.1L137.5 466.3L143.0 469.4L149.2 469.1L149.1 466.0L150.7 466.3L152.0 464.7L157.9 467.7L157.7 469.7L160.0 472.1L163.2 473.2L167.4 474.0L168.1 472.8L173.4 471.9L173.3 474.1L175.2 474.3L174.7 476.7L176.7 476.7L176.2 478.2L177.6 478.1L178.5 480.3L186.0 487.7L192.8 489.2L196.6 492.6L201.0 493.8L205.6 497.7L204.2 499.2L205.0 499.9L206.8 498.2L207.4 499.3L208.5 496.2L213.4 497.6L217.8 501.0L220.9 505.9L228.2 506.9L231.5 510.4L229.6 511.4L230.7 511.7L230.0 513.6L231.1 512.2L231.0 514.0L234.4 513.8L234.1 515.9L232.8 515.2L231.3 516.1L234.8 516.3L233.8 516.9L234.6 522.4L233.7 524.0L229.7 522.5L227.8 525.4L227.1 524.3L227.1 528.1L225.1 530.9L225.9 531.0L224.9 534.4L228.4 535.4L228.1 541.6L229.4 542.1L226.8 546.5L230.9 550.2L230.9 553.4L232.6 554.9L229.7 557.2L233.9 559.9L234.2 565.2L239.3 567.9L232.2 575.6L233.5 575.9L232.1 579.2L232.5 583.2L234.2 584.8L236.4 582.4L239.9 583.6L238.4 585.7L238.0 590.8L234.9 593.4L235.0 599.6L231.7 603.4L231.4 606.4L235.6 606.3L238.8 610.6L241.6 607.6L241.1 610.7L243.6 617.9L241.7 617.1L242.1 620.4L239.6 621.6L226.0 620.0L218.9 613.9L216.7 613.7L207.5 604.6L204.7 604.5L203.4 606.4L204.7 609.6L200.4 608.9L196.8 606.6L192.7 610.4L193.7 614.6L198.5 616.7L201.6 620.6L199.8 620.6L202.9 624.9L199.3 626.5L199.3 631.9L194.9 635.4L190.9 632.0L178.1 632.6L172.8 637.6L172.9 639.1L171.4 639.2L169.6 644.4L162.0 643.4L159.8 644.3L158.8 641.3L148.0 640.4L147.8 637.6L144.4 636.0L145.8 630.7L139.5 626.6L136.5 627.6L133.4 626.2L131.3 628.3L121.5 629.1L121.1 630.9L115.9 632.2L115.6 630.1L108.0 635.6L106.4 635.3L105.9 636.3Z","c":[201.8,550.5]}],"munline":"M126.7 271.0L122.7 272.0L118.8 270.9L108.4 276.1L104.6 274.4L101.6 271.2L96.4 268.9L94.8 270.8L87.4 273.6L78.1 269.0L76.8 269.6L72.8 267.8L70.4 268.0L65.7 273.0L66.5 275.8L67.0 274.3L68.7 274.4L68.9 277.3L68.6 279.4L65.6 283.1L58.5 279.9L51.1 279.4L39.4 274.3L34.3 273.3L33.5 272.7L34.0 271.2L30.3 269.5L31.2 267.9M98.9 315.5L93.2 318.6L92.3 318.1L92.6 316.5L85.8 316.8L86.5 314.7L80.8 318.4L80.3 317.2L78.6 317.4L77.7 309.8L72.8 306.3L68.1 306.2L68.0 303.3L64.0 305.0L60.2 304.6L58.6 303.8L58.5 301.9L53.0 300.4L49.2 301.0L46.6 299.9L42.8 300.1L44.0 304.0L43.4 305.5L36.5 308.2L32.4 304.3L34.7 301.1L33.1 299.0L36.4 297.5L36.6 296.1L31.6 292.0L28.2 282.4L28.0 275.4L26.3 271.8L24.4 272.5L23.1 268.7L31.2 267.9M31.2 267.9L32.4 265.5L35.9 265.5L35.1 261.7L35.9 260.2L38.2 258.4L42.0 258.7L43.7 255.2L45.0 254.9L45.3 253.3L41.8 244.9L42.4 242.5L46.4 241.2L51.6 242.2L56.5 238.3L60.1 238.2L63.3 235.7L65.7 235.7L65.7 233.1L68.9 230.9L72.2 231.9L73.1 229.6L76.7 229.0L78.4 226.6L80.2 226.9L84.0 222.4L84.6 214.6L88.3 210.6L93.9 208.5L95.6 209.5L97.3 208.1L101.0 208.5L105.3 206.5L106.8 207.8L106.9 209.6L113.4 209.4L115.6 210.6M93.5 404.1L89.9 404.2L84.6 401.6L80.6 404.5L77.8 410.6L72.2 409.8L69.8 412.1L65.8 411.2L65.3 408.7L62.7 407.7L61.6 405.5L58.0 405.2L56.4 403.2L53.4 397.0L50.6 394.1L51.6 391.8L56.8 389.8L60.5 381.9L60.5 377.2L56.9 376.2L57.0 371.9L58.9 370.1L60.2 371.0L67.2 368.2M67.2 368.2L67.1 366.9L68.1 367.3L68.4 365.9L70.9 364.1L71.2 361.8L73.3 362.1L73.6 361.0L80.0 359.4L83.2 354.3L87.1 352.6L88.7 349.2L95.5 344.4L98.7 339.9L101.5 338.9L104.9 332.9L104.6 328.6L107.8 324.8M67.2 368.2L67.5 368.1L68.0 368.4L70.7 370.7L76.6 372.4L78.4 376.1L77.1 377.5L77.7 381.8L81.6 383.4L82.4 385.6L81.6 385.9L84.1 386.7L84.3 389.1L85.5 389.1L86.1 387.7L87.1 388.3L90.1 393.7M85.2 474.5L98.9 474.7L103.1 476.5L110.7 476.5L113.0 468.5L116.9 468.4L120.9 465.1L122.1 459.2L121.0 456.4M118.2 494.2L109.6 485.8L108.2 487.3L106.7 483.4L97.2 483.9L97.2 482.6L93.1 484.8L93.0 483.0L87.2 481.3L84.8 479.5L85.2 474.5M85.2 474.5L83.8 472.9L82.8 467.8L78.7 464.7L78.9 460.0L80.3 458.7L82.7 452.4L84.5 451.0L82.5 447.8L84.5 443.8L85.5 442.3L89.3 440.6L90.1 438.6M88.7 594.9L88.4 596.7L90.3 597.8L89.8 601.8L93.1 607.1L92.1 610.1L93.3 612.0L92.0 613.1L96.8 614.4L95.8 616.4L97.7 616.7L99.8 620.5L98.6 621.8L99.5 622.8L105.2 622.0L106.5 614.0M104.4 635.0L98.4 629.9L83.9 625.2L79.2 620.5L78.6 617.1L76.9 615.5L80.5 616.0L80.4 610.6L82.6 606.2L82.6 603.5L77.4 601.2L74.6 594.3L80.8 595.9L88.7 594.9M88.7 594.9L111.7 591.9M90.1 393.7L93.5 396.2L97.0 401.0L92.6 402.8L93.5 404.1M139.0 356.1L138.9 364.9L134.9 370.2L133.8 370.0L134.0 372.7L129.0 376.6L128.8 375.5L122.5 370.6L119.5 365.3L117.7 367.3L117.6 366.1L116.1 365.9L116.4 366.8L114.9 367.1L113.5 365.5L110.0 371.8L106.9 373.2L103.6 377.0L99.0 387.7L94.5 386.9L103.6 397.7L98.7 398.9L93.2 393.6L91.3 392.7L90.1 393.7M102.3 442.1L100.9 440.7L94.2 441.8L92.3 440.3L93.2 439.1L90.1 438.6M90.1 438.6L92.2 433.6L98.3 425.3L98.0 424.0M98.0 424.0L96.9 419.3L98.5 410.7L99.4 410.4L99.0 406.4L100.2 405.0L97.4 402.2L93.5 404.1M112.4 429.9L112.4 428.8L109.6 430.6L107.8 427.7L104.3 429.0L101.0 425.0L98.7 423.5L98.0 424.0M107.8 324.8L108.6 323.3L106.5 319.1L98.9 315.5M129.6 277.6L124.4 277.3L119.1 281.4L115.2 286.8L113.8 292.5L115.8 294.5L117.3 301.0L110.5 299.6L110.0 298.6L109.1 300.2L107.1 299.4L106.0 300.9L103.9 301.0L104.2 302.2L101.8 303.9L100.5 303.4L99.3 300.5L94.9 305.4L96.7 307.0L94.6 313.7L98.9 315.5M102.3 442.1L101.4 445.1L100.3 444.2L99.8 445.4L96.1 444.5L93.4 445.1L94.5 446.9L98.0 447.0L96.7 452.4L109.8 456.9L112.9 457.2L113.1 454.4L120.7 456.3M112.4 429.9L111.4 436.7L108.6 434.3L107.1 434.9L106.9 435.6L105.5 435.9L105.1 436.6L106.4 436.6L106.3 437.7L102.4 438.0L104.2 439.1L103.5 439.6L104.4 440.6L102.3 442.1M104.4 635.0L106.4 632.6L108.7 632.7L107.2 629.9L108.7 631.0L109.7 629.9L108.8 628.2L109.8 624.8L110.5 625.6L113.4 622.6L115.0 623.1L117.4 617.9L117.4 616.0L116.1 615.2L108.2 613.5L106.5 614.0M204.7 604.5L203.4 606.4L204.7 609.6L200.4 608.9L196.8 606.6L192.7 610.4L193.7 614.6L198.5 616.7L201.6 620.6L199.8 620.6L202.9 624.9L199.3 626.5L199.3 631.9L194.9 635.4L190.9 632.0L187.7 631.5L187.0 632.5L180.9 633.3L178.1 632.6L172.8 637.6L172.9 639.1L171.4 639.2L169.6 644.4L162.0 643.4L159.8 644.3L158.8 641.3L151.5 640.0L148.0 640.4L147.8 637.6L144.4 636.0L145.8 630.7L139.5 626.6L136.5 627.6L133.4 626.2L131.3 628.3L121.5 629.1L121.1 630.9L115.9 632.2L115.6 630.1L108.0 635.6L106.4 635.3L105.9 636.3L105.1 635.8L104.7 635.0L104.5 635.0L104.4 635.0M106.5 614.0L108.5 608.9L111.6 604.9L110.7 601.6L111.2 598.1L112.2 597.6L111.0 595.2L111.7 591.9M139.0 356.1L135.8 355.2L136.5 353.9L135.8 351.8L134.0 352.5L131.9 350.5L130.5 351.3L127.3 348.3L128.2 348.2L125.5 346.6L123.2 346.8L121.7 343.9L118.9 344.3L118.4 343.0L121.2 341.9L116.8 342.0L116.0 339.4L114.4 338.6L114.6 334.1L112.3 329.7L112.0 326.4L110.6 324.5L108.4 324.8L107.8 324.8M111.7 591.9L130.1 589.4L130.1 587.0M120.7 456.3L119.4 454.8L121.3 454.5L120.5 450.8L114.0 445.2L114.6 444.0L116.7 443.9L116.7 441.6L118.7 441.4L120.3 439.0L122.5 439.2L121.3 438.6L122.5 429.0L118.7 428.4L117.4 428.8L117.1 430.3L113.2 429.2L112.4 429.9M160.3 236.6L160.2 235.4L156.7 235.3L154.0 232.6L153.1 223.1L150.0 222.9L149.5 221.4L147.4 221.2L147.6 220.2L143.3 217.4L136.1 215.9L131.9 210.2L128.3 211.5L125.1 214.4L120.1 215.6L114.8 218.3L113.5 216.5L115.6 210.6M115.6 210.6L118.5 208.0L120.1 202.5L118.7 197.7L123.6 191.8L121.6 190.5L122.3 187.4L121.5 184.5L125.7 181.2L125.1 174.2L128.6 174.2L131.9 176.8L136.9 176.5L140.5 178.1L143.9 176.9L144.5 179.2L148.8 182.1L154.0 181.8L158.4 178.7L159.7 176.6L166.7 178.7L171.5 176.5L173.7 176.6L174.7 175.0L180.3 176.8L183.5 175.9L186.8 177.0L188.2 179.1L192.6 180.1L200.4 186.5L202.2 185.9L206.0 188.2L206.3 190.2L208.7 190.8L211.2 193.3M174.4 551.3L166.2 545.8L162.2 541.6L158.6 535.2L155.2 532.4L154.5 529.9L155.9 527.8L155.4 523.8L148.5 516.8L143.9 508.0L140.7 506.0L135.2 504.8L134.2 502.5L129.3 502.8L126.2 500.9L125.6 500.3L126.8 500.0L124.6 498.0L118.2 494.2M178.1 479.5L174.1 483.6L174.5 482.5L172.3 481.6L169.5 482.2L169.3 480.7L167.8 480.0L165.5 480.9L163.6 483.9L158.4 485.6L156.4 484.2L155.6 486.7L149.9 486.4L147.0 487.9L145.9 486.0L141.7 488.8L136.4 489.0L134.8 490.1L129.0 489.1L127.9 486.0L126.6 489.2L127.4 490.4L128.6 490.2L129.3 492.5L126.2 492.4L125.8 491.3L124.9 492.4L122.5 491.8L118.2 494.2M121.0 456.4L120.7 456.3M158.1 469.0L157.2 468.5L157.9 467.7L152.0 464.7L150.7 466.3L149.1 466.0L149.9 467.8L149.2 469.1L143.0 469.4L137.5 466.3L135.7 463.1L130.7 459.5L121.0 456.4M130.1 587.0L131.6 587.6L135.4 584.8L135.4 582.1L134.2 579.8L128.2 577.4L127.7 574.9L124.6 574.1L123.1 575.5L121.8 575.0L122.2 572.3L125.0 572.4L125.1 570.8M130.1 587.0L118.0 572.0L118.9 570.6L120.1 571.4L125.1 570.8M125.1 570.8L128.6 570.1L140.5 576.8L147.4 577.7L156.1 577.3L159.8 576.2L160.5 573.1L164.2 571.2L165.2 565.9L165.9 565.6L167.6 565.2M129.6 277.6L128.1 275.5L128.9 273.0L126.7 271.0M126.7 271.0L133.0 264.8L131.7 255.8L132.9 253.8L142.6 249.6L147.0 245.8L150.2 246.2L151.6 244.4L154.1 244.8L157.4 242.6L160.3 236.6M206.0 297.8L201.6 297.0L197.9 299.3L195.3 297.6L192.2 299.9L182.0 300.9L179.2 300.3L176.5 302.2L173.7 300.7L170.9 302.0L167.2 300.5L166.3 301.0L164.4 298.9L162.1 298.9L158.1 296.2L152.3 296.4L143.6 290.6L139.6 286.5L136.0 286.7L132.5 280.5L130.2 279.9L129.6 277.6M167.5 396.5L162.4 392.1L159.5 390.4L158.8 391.3L156.7 389.2L154.8 383.3L149.7 376.9L150.7 369.7L149.8 368.2L153.2 365.4L149.2 361.1L150.6 358.5L148.8 352.6L145.5 352.1L144.1 353.2L141.8 352.0L139.0 356.1M173.5 472.0L165.1 473.8L160.9 471.6L160.0 472.1L158.1 469.0M163.5 398.4L160.1 399.6L166.2 407.7L155.5 410.9L147.2 408.5L148.9 418.7L145.0 426.8L138.0 434.4L132.6 435.5L130.1 438.5L128.2 438.1L126.5 439.3L127.9 440.6L130.1 439.7L132.2 440.6L133.3 446.0L140.1 448.1L146.3 452.5L145.2 455.3L146.1 455.4L146.4 457.1L147.8 457.0L148.2 459.9L149.2 460.0L149.0 460.8L149.2 461.1L152.7 462.7L154.5 462.4L154.3 464.2L158.5 464.3L157.9 465.1L159.3 467.7L158.1 469.0M162.2 237.3L160.3 236.6M203.9 250.4L201.5 249.6L195.3 250.5L192.0 246.2L189.2 244.4L187.9 245.2L179.9 241.1L176.9 243.3L169.4 245.6L162.2 237.3M205.3 210.6L200.7 210.7L200.0 215.5L196.3 215.0L191.3 216.6L187.0 225.1L181.3 226.1L177.4 229.4L162.2 237.3M163.5 398.4L167.7 401.5L168.8 404.4L167.7 406.4L168.5 407.4L176.1 411.8L179.6 411.6L180.1 414.2L184.1 420.3L187.2 423.2L191.1 423.9L190.9 425.3L192.9 428.3L196.3 426.4L196.4 428.9L202.2 431.0L206.2 434.4L206.1 437.1L211.1 437.9L216.5 440.7L215.9 443.4L221.4 448.9L223.2 446.7L225.5 448.4L228.4 446.4L229.8 446.6L231.6 449.0L243.1 451.6M167.5 396.5L163.5 398.4M176.3 370.6L173.3 369.3L172.7 374.2L166.4 369.9L167.1 373.6L165.6 375.7L166.6 377.2L170.1 377.8L169.4 379.2L170.6 381.6L170.2 382.3L167.1 380.5L168.6 385.0L167.5 396.5M204.7 604.5L203.1 604.5L198.5 600.2L193.0 589.8L181.4 592.4L177.7 585.6L174.5 585.7L173.0 584.4L169.9 577.0L170.3 574.8L168.1 569.4L165.2 568.7L165.3 565.9L167.6 565.2M167.6 565.2L180.2 556.7L180.3 555.7L174.4 551.3M173.5 472.0L173.3 474.1L175.2 474.3L174.7 476.7L176.7 476.7L176.2 478.2L177.6 478.1L178.1 479.5M220.6 469.0L216.1 469.0L212.8 465.6L210.5 465.4L211.0 459.8L213.4 459.4L212.1 458.5L212.8 457.3L209.0 454.3L209.7 453.4L206.0 451.3L198.0 449.9L195.9 450.8L195.5 453.2L194.3 452.4L192.7 455.9L190.5 455.0L188.2 457.6L187.2 456.8L183.5 458.3L185.0 460.9L182.3 463.3L179.3 463.8L177.0 465.4L176.9 466.7L174.1 466.8L175.0 469.5L173.5 472.0M174.4 551.3L180.5 551.0L186.2 552.3L188.9 551.4M176.3 370.6L178.4 370.9L181.5 374.3L183.1 373.3L186.3 375.0L187.4 372.7L186.8 370.9L184.8 369.7L185.2 368.8L187.5 368.1L188.1 371.3L189.8 369.5L191.9 370.8L192.3 367.2L195.2 366.4L195.6 363.1L194.6 361.7L195.6 360.9L202.6 368.3L210.2 373.0L211.7 371.4L213.4 371.2L215.0 372.9L217.1 371.7L216.2 368.5M204.2 316.6L200.0 323.4L192.6 323.0L191.3 325.2L189.1 324.1L187.7 325.6L183.6 325.3L182.1 328.5L178.1 328.8L178.3 331.8L174.8 334.6L175.8 339.5L175.2 341.6L172.8 340.7L173.0 343.3L177.3 349.4L179.5 350.5L177.7 354.1L178.5 355.3L177.8 360.7L181.1 367.9L179.2 368.8L176.3 367.5L177.4 369.3L176.3 370.6M178.1 479.5L186.0 487.7L190.8 489.5L192.8 489.2L193.0 490.3L194.7 490.2L196.6 492.6L201.0 493.8L205.6 497.7L204.2 499.2M188.9 551.4L188.9 554.5L196.5 553.7L199.6 554.6L203.3 557.5L203.5 559.5L206.0 560.1L207.9 563.2L211.3 564.5L214.1 563.5L217.4 564.4L225.7 563.2L222.5 566.9L222.2 569.8L226.8 570.0L228.9 568.6L229.4 565.5L233.8 563.8M204.2 499.2L204.3 503.7L201.0 507.1L195.5 509.7L192.6 508.6L193.3 511.0L197.5 514.3L194.7 519.4L200.0 524.5L196.7 526.1L192.7 531.2L192.3 534.7L190.2 536.5L185.0 537.5L192.7 540.0L192.4 544.6L188.9 551.4M240.7 269.6L239.7 269.0L237.5 271.8L237.0 274.9L234.8 273.9L235.4 273.0L233.9 271.3L233.5 263.3L231.7 265.3L229.6 265.2L229.5 266.6L227.0 266.2L226.5 268.3L224.8 266.6L219.3 266.8L216.0 262.1L216.4 261.0L213.1 258.0L210.4 256.3L208.1 258.6L203.9 250.4M203.9 250.4L206.6 249.4L207.5 245.6L213.0 244.1L214.6 244.5L214.3 245.2L214.8 245.5L221.0 244.9L222.9 245.9L223.8 247.9L225.8 247.6L225.6 245.6L230.8 243.2L232.8 240.7L232.7 238.6L236.9 233.5L237.2 231.8L235.6 229.2L236.6 229.0M218.1 501.4L210.9 496.4L209.9 497.1L208.5 496.2L207.3 499.3L206.8 498.2L205.0 499.9L204.2 499.2M204.2 316.6L203.4 320.7L204.5 321.9L203.4 322.6L206.8 326.3L208.4 326.9L212.3 325.3L215.8 327.0L219.4 325.6L227.5 328.9L229.5 328.6L229.4 332.5M206.0 297.8L209.9 301.0L210.4 306.1L209.5 309.5L206.2 310.5L204.2 316.6M239.6 621.6L231.6 621.2L225.3 619.6L218.9 613.9L216.7 613.7L207.5 604.6L205.3 604.5L204.8 604.5L204.7 604.5M236.6 229.0L229.4 221.5L222.3 218.8L221.5 216.9L219.2 217.4L213.0 214.9L208.9 211.3L205.3 210.6M211.2 193.3L212.5 206.5L209.8 205.8L211.4 207.4L206.7 206.3L205.3 210.6M256.8 280.3L252.7 282.2L249.5 281.5L246.9 279.4L240.2 278.5L238.2 279.4L236.7 281.5L237.3 283.1L236.2 285.4L235.4 292.7L236.4 296.0L235.5 297.8L231.7 298.1L230.4 296.7L224.9 295.5L217.0 291.4L216.4 292.6L206.9 295.3L208.1 297.0L206.0 297.8M211.2 193.3L211.3 193.3L211.7 193.2L213.3 192.9L215.5 193.2L221.4 188.4L224.5 188.4L230.2 191.0L237.3 192.0L239.4 194.6L245.2 195.7L244.9 196.7L249.1 203.4L249.0 206.6L253.9 210.2L254.4 212.8M215.8 368.3L216.0 368.6L216.2 368.5M229.4 332.5L228.1 335.5L224.3 339.6L224.8 342.7L223.1 343.6L220.5 347.7L220.1 351.2L216.2 353.5L213.4 358.1L212.8 363.3L214.0 366.3L215.2 368.1L215.8 368.3M262.3 384.0L261.0 383.0L259.7 383.7L257.4 381.6L255.8 379.5L256.3 378.6L253.0 376.4L253.2 374.4L251.3 374.4L250.0 370.5L247.3 368.4L246.7 369.1L244.9 367.5L243.0 367.7L243.0 366.8L239.8 368.7L237.6 367.4L234.4 368.6L234.2 367.3L232.6 367.7L232.6 366.0L228.7 366.3L226.9 364.4L222.6 364.1L221.5 363.0L216.2 364.7L215.8 368.3M216.2 368.5L223.3 373.0M216.2 368.5L220.9 367.2L222.5 369.1L223.9 368.9L223.3 373.0M220.6 469.0L226.7 479.5L225.7 485.7L224.8 483.3L222.4 485.3L221.7 497.5L219.7 496.3L218.8 499.7L218.2 501.5L218.1 501.4M218.1 501.4L220.9 505.9L228.2 506.9L231.5 510.4L229.6 511.4L230.7 511.7L230.0 513.6L231.1 512.2L231.0 514.0L234.4 513.8L233.6 514.0L234.1 515.9L232.8 515.2L231.3 516.1L234.8 516.3L233.8 516.9L235.0 520.9M244.7 455.5L242.5 457.7L240.6 457.4L239.1 458.6L235.8 463.2L236.6 464.1L220.6 469.0M223.3 373.0L226.7 376.7L229.9 377.9L229.5 379.4L231.1 382.0L230.3 383.2L232.6 383.4L229.7 388.0L231.4 387.8L232.4 385.4L233.3 386.3L236.5 384.1L237.4 385.2L236.4 386.2L238.0 388.0L237.5 390.4L239.3 392.2L238.1 394.4L240.2 394.4L241.0 396.6L242.9 396.0L243.0 397.9L248.5 397.7M229.4 332.5L229.9 333.7L232.7 332.7L234.4 328.5L232.7 326.9L237.3 327.4L239.0 326.2L239.0 328.0L241.3 329.0L239.8 326.8L241.0 325.9L246.4 325.3L249.2 323.4L250.0 324.6L251.5 323.9L252.6 325.0L255.1 323.4L255.7 324.0M239.6 621.6L242.1 620.4L241.7 617.1L243.6 617.9L241.1 610.7L241.6 607.6L238.8 610.6L237.4 610.0L235.6 606.3L232.2 605.6L231.4 606.4L231.7 603.4L235.0 599.6L234.9 593.4L238.0 590.8L238.4 585.7L239.9 583.6L236.4 582.4L234.2 584.8L232.5 583.2L232.1 579.2L233.5 575.9L232.2 575.6L233.5 573.5L235.1 573.6L239.3 567.9L234.2 565.2L233.8 563.8M233.8 563.8L233.9 559.9M235.0 520.9L233.7 524.0L229.8 523.4L229.7 522.5L227.8 525.4L227.1 524.3L227.1 528.1L225.1 530.9L225.9 531.0L224.9 534.4L228.4 535.4L228.2 540.3L228.9 540.2L228.1 541.6L229.4 542.1L226.8 546.5L230.9 550.2L230.9 553.4L232.6 554.9L229.7 557.2L233.9 559.9M233.9 559.9L235.4 561.8L237.3 561.6L239.5 559.9L240.5 556.3L242.3 555.3L243.9 556.8L247.1 555.6L248.0 557.6L254.2 561.5L261.2 560.4L263.6 558.5L266.2 560.1L270.5 559.6L274.2 557.0L277.1 552.5L285.4 549.3L289.6 545.9L290.3 546.9L294.9 547.6L303.0 544.8L306.4 545.1L305.9 541.4L302.5 540.8L303.5 540.4L302.8 538.2L309.7 534.9L318.1 546.4L317.4 550.5L318.6 552.4L323.3 551.5L327.9 553.1L333.5 551.9M235.0 520.9L239.6 521.7L240.5 523.7L242.2 523.3L249.8 527.4L256.6 526.3L262.3 524.7L263.0 523.6L264.7 523.9L264.4 522.5L264.4 522.0L266.1 521.9L270.3 517.0L272.2 520.7L277.4 518.8L278.2 517.4L282.4 517.7L283.1 516.0L287.7 513.4L286.6 512.4L288.8 512.3L303.0 504.3M245.7 227.7L243.6 226.0L236.6 229.0M355.4 580.4L354.4 582.1L354.8 585.8L353.8 588.7L354.7 593.5L351.5 598.6L347.2 600.0L341.8 605.4L337.0 607.3L335.0 610.3L332.6 611.4L329.1 610.1L326.8 612.3L323.9 613.1L324.4 614.0L322.7 616.8L312.5 621.0L309.4 620.4L301.0 626.8L299.2 621.4L296.0 622.5L291.5 620.5L290.2 618.1L287.0 618.6L284.6 621.6L283.6 621.3L277.8 611.6L275.4 611.4L271.2 613.3L270.2 616.7L267.3 618.5L266.0 621.5L266.9 622.5L266.1 623.0L266.4 626.9L256.0 622.4L250.3 621.7L247.0 624.3L245.0 624.3L239.6 621.6M260.5 279.3L262.2 273.0L258.7 268.9L257.5 270.1L257.8 271.9L249.2 272.6L240.7 269.6M248.8 241.8L248.4 243.6L250.2 243.6L252.2 247.5L251.6 248.8L253.6 249.7L253.2 251.8L254.6 252.4L253.7 253.8L252.0 253.4L250.7 255.6L246.7 256.1L247.1 257.5L246.0 259.1L247.2 261.3L244.6 263.6L241.5 264.3L240.7 269.6M243.1 451.6L244.7 455.5M248.5 397.7L250.2 398.5L248.3 400.7L249.9 402.5L247.1 402.8L245.6 407.9L243.6 408.7L239.8 408.0L240.6 410.0L238.5 411.3L238.6 414.0L242.0 413.5L242.4 420.1L239.8 421.9L239.6 427.0L235.6 429.3L236.7 433.0L236.4 437.9L242.3 444.0L243.1 451.6M289.2 465.5L287.3 463.0L283.4 463.4L284.0 461.4L280.9 464.6L280.5 462.9L279.3 463.5L277.6 461.5L279.3 461.0L278.8 459.8L272.4 460.6L271.9 459.7L273.3 458.6L271.7 456.7L270.5 455.8L268.5 456.4L265.9 453.6L263.6 453.1L263.1 451.6L253.2 454.5L251.1 452.2L247.5 454.2L245.7 453.9L244.7 455.5M248.8 241.8L247.6 240.5L248.3 238.2L246.8 237.5L245.9 234.0L244.5 234.3L243.6 232.7L245.7 227.7M254.4 212.8L252.1 211.9L245.6 217.7L244.6 220.3L246.5 222.8L245.6 223.8L246.4 225.0L245.7 227.7M248.5 397.7L249.7 396.1L251.4 396.3L251.0 393.8L251.6 392.6L253.7 392.7L253.8 390.6L256.6 391.7L258.6 391.0L258.6 388.2L262.3 386.0L262.3 384.0M278.0 219.4L274.6 219.5L270.6 221.7L265.4 230.6L265.6 235.5L263.5 237.3L263.7 235.4L262.7 236.0L263.0 237.5L261.8 237.1L260.8 239.3L261.3 240.4L259.0 237.9L254.9 236.0L254.2 236.3L250.5 240.5L249.3 241.6L249.0 241.8L248.8 241.8M254.4 212.8L254.5 212.8L254.7 213.0L254.8 213.3L256.1 213.9L259.2 214.4L261.5 214.0L265.7 209.9L270.5 211.9L274.0 210.3L276.2 213.4L279.2 215.0M255.7 324.0L258.0 324.7L258.4 323.4L259.1 325.0L260.1 323.6L262.3 323.2L264.9 324.4L268.1 322.4L270.8 322.7L272.3 325.9L275.3 326.9L272.1 330.7L271.1 333.7L269.5 332.7L268.3 333.2L269.1 333.3L268.2 334.8L269.6 335.7L267.5 336.8L266.6 339.8L265.4 340.0L268.7 341.1L269.4 344.9L266.6 347.8L266.1 347.3L266.0 349.6L270.7 353.0L273.2 352.4L272.7 354.2L274.3 358.6M281.5 296.8L280.3 298.2L280.5 300.6L276.5 300.6L275.2 302.4L279.3 305.7L278.9 306.9L276.9 306.4L276.7 312.9L273.9 313.2L272.6 312.3L270.7 313.8L267.6 312.6L267.2 314.5L263.8 313.6L258.1 318.6L255.7 319.4L255.7 324.0M281.5 296.8L277.9 294.5L277.2 291.9L276.0 294.9L274.9 293.7L273.9 294.7L273.3 293.8L269.0 294.0L268.9 291.5L266.6 291.6L263.5 283.8L256.8 280.3M256.8 280.3L260.5 279.3M289.2 283.3L287.1 284.2L281.5 283.5L278.7 284.7L278.2 283.4L276.5 285.3L276.7 283.8L274.8 283.0L274.6 281.3L270.0 282.2L269.7 279.3L266.2 281.9L260.5 279.3M263.5 383.7L262.9 384.0L262.6 384.0L262.3 384.0M263.5 383.7L264.7 385.4L263.0 388.7L263.9 389.3M274.3 358.6L273.6 360.7L271.1 362.0L268.9 366.9L268.8 371.0L269.9 373.2L269.3 375.5L266.9 377.1L266.3 381.4L263.5 383.7M263.9 389.3L263.5 397.6L266.0 395.6L270.7 396.3L270.8 397.6L277.3 402.2L273.6 403.7L272.0 403.1L271.9 406.3L270.2 406.9L270.1 410.7L272.3 411.0L273.1 414.4L267.9 418.0L271.0 419.3L270.8 421.4L272.6 421.9L273.1 420.0L274.6 420.4L274.8 421.4L280.7 423.9L280.3 425.6L282.6 425.9L281.9 428.5L283.7 429.3L293.9 441.0L294.0 444.2L295.9 448.6M263.9 389.3L267.5 389.0L271.0 390.8L279.1 390.1M274.3 358.6L281.0 358.4L283.1 354.5L285.5 353.9L289.4 354.3L292.5 356.2L300.0 356.5L301.7 358.5L304.4 359.0M287.1 261.7L282.3 257.2L286.2 253.6L285.3 251.7L281.8 255.1L282.3 253.1L281.2 253.6L279.8 250.9L282.5 244.1L282.2 237.0L283.6 237.1L283.3 234.2L281.8 232.7L283.2 227.7L281.0 224.6L283.3 222.1L280.9 219.6L278.0 219.4M278.0 219.4L279.2 215.0M279.1 390.1L282.7 394.3L278.2 394.1L276.7 395.7L276.9 397.3L279.6 399.6L287.8 401.5L288.5 403.6L291.0 402.9L289.8 400.8L290.0 398.1L296.1 398.8L301.4 395.6L307.2 395.4M307.2 395.4L307.5 391.8L308.9 391.0L308.1 386.4L307.0 384.1L303.6 381.2L302.0 382.6L298.7 382.7L296.3 382.0L295.6 380.4L294.2 381.4L289.8 379.7L285.0 382.1L282.4 381.5L280.5 384.9L278.7 385.2L277.4 387.3L279.2 388.2L279.1 390.1M279.2 215.0L284.9 212.2L287.3 212.5L292.9 210.3L298.3 212.6L300.2 215.9L305.5 215.8L310.8 213.1L322.1 212.5L330.3 209.4L336.2 209.2L338.8 210.9L336.3 213.9L339.8 217.3L339.9 219.2M325.1 332.9L320.5 321.7L316.8 322.3L317.4 324.1L315.4 324.2L314.2 320.6L314.8 318.6L317.9 317.9L318.3 316.4L313.3 317.7L313.0 319.6L310.2 320.3L310.0 319.4L308.6 319.8L306.3 318.1L304.6 314.6L301.5 315.7L299.7 314.0L296.2 314.3L293.8 309.2L292.2 311.2L290.4 310.6L290.1 311.9L289.0 309.6L286.8 310.5L286.1 309.8L286.7 306.6L290.3 305.7L291.0 304.6L289.6 303.8L291.6 301.4L287.8 298.0L285.3 298.4L281.5 296.8M305.0 264.4L302.6 264.5L302.2 263.2L298.9 261.9L297.4 262.7L297.8 264.2L295.3 265.8L295.2 262.8L292.4 263.7L289.7 261.3L288.8 261.0L287.9 261.2L287.4 261.7L287.1 261.7M287.1 261.7L286.2 262.1L287.6 264.9L286.5 265.5L285.4 274.1L287.4 281.5L289.2 283.3M289.2 283.3L300.1 287.2L303.2 292.1L305.2 293.4L306.5 291.7L305.3 288.7L307.1 288.7L308.4 281.6L306.0 281.8L303.5 280.5L303.7 278.0L301.5 276.1L300.2 276.4L299.2 273.2L304.6 270.1L303.2 267.1L304.7 266.1L306.3 267.0L305.0 264.4M289.2 465.5L291.2 467.6L289.7 467.6L289.5 471.7L288.0 472.2L287.5 477.1L285.1 480.0L285.4 483.3L281.0 486.4L287.3 494.2L286.1 495.1L293.8 503.6L303.0 504.3M295.9 448.6L296.3 450.5L289.2 465.5M317.4 452.8L315.4 455.7L313.9 456.1L312.1 455.3L312.2 451.6L310.9 449.7L308.1 451.9L303.2 446.0L301.2 445.4L295.9 448.6M303.0 504.3L304.3 510.4L306.4 512.2L308.7 511.5L316.7 520.7L321.6 524.7M304.4 359.0L306.1 361.3L306.4 364.2L311.4 363.2L310.7 364.6L313.4 367.1L318.0 366.8L318.5 365.8L313.8 363.0L317.4 361.0L320.5 360.8L321.6 363.4L323.5 363.8L325.7 366.5L328.8 365.6M304.4 359.0L305.9 358.5L307.4 355.3L306.6 353.3L307.3 352.2L304.6 349.8L305.1 344.7L310.7 342.2L313.3 337.5L314.4 338.6L315.6 338.1L315.8 335.0L318.9 335.7L318.7 337.8L320.0 338.3L321.6 335.8L321.0 332.7L325.1 332.9M328.5 250.6L322.7 251.8L313.2 250.7L311.0 255.0L311.5 256.2L308.3 255.5L307.4 256.8L304.6 256.8L305.5 259.8L304.5 259.9L305.4 260.7L305.0 264.4M307.2 395.4L311.0 400.0L313.0 401.4L316.3 399.9L317.0 402.2M322.1 387.1L316.5 387.4L313.3 390.1L313.9 393.7L307.2 395.4M331.2 455.4L330.2 453.2L328.5 452.4L328.8 447.4L327.0 446.0L331.1 443.3L329.9 440.3L331.4 439.4L331.9 430.6L331.0 431.7L328.1 430.4L327.3 431.7L323.2 429.6L317.7 423.6L317.2 421.3L316.5 421.8L315.0 418.3L316.6 416.9L316.3 415.1M316.3 415.1L312.4 415.1L309.0 416.5L307.7 419.8L308.6 420.6L306.0 423.8L307.6 427.7L306.6 429.3L308.9 433.5L309.8 438.4L311.9 442.2L314.8 442.3L314.1 445.3L312.9 445.6L315.5 451.3L317.4 452.8M317.0 402.2L320.9 411.6L316.3 415.1M317.0 402.2L316.7 400.6L320.0 397.5L328.4 397.4L326.1 393.7L326.3 390.2L322.0 388.1L322.1 387.1M331.2 455.4L328.3 454.8L325.4 461.5L323.1 460.6L323.0 458.2L321.3 457.7L317.4 452.8M321.6 524.7L323.0 524.6L325.3 527.7L334.1 518.8L332.7 516.4L334.5 516.2L335.3 517.7L338.5 514.5L338.3 513.1L340.6 512.8L341.3 511.4L348.8 507.9M333.5 551.9L334.5 548.4L335.8 547.9L335.6 545.2L334.2 543.8L328.0 542.4L324.8 538.6L318.8 528.6L322.7 526.8L321.6 524.7M322.1 387.1L329.2 384.7L331.6 386.7L333.2 386.1L333.6 387.9L335.3 388.6M328.2 319.1L330.8 326.4L333.2 328.8L325.1 332.9M331.4 277.9L330.2 280.8L331.7 282.7L329.5 282.7L327.3 286.4L325.4 286.4L326.2 287.5L325.4 287.9L327.3 288.6L328.6 291.6L328.7 292.7L326.2 293.2L326.5 295.5L325.7 296.3L325.9 301.2L328.7 303.5L327.7 305.4L328.4 305.6L327.2 307.6L323.8 306.6L322.5 308.4L324.3 309.9L325.8 313.9L328.6 316.3L328.2 319.1M328.2 319.1L328.6 318.8L331.2 319.6L333.5 318.4L336.4 319.0L336.3 319.9L343.9 318.5M367.3 247.7L364.3 246.4L362.3 248.2L358.4 245.7L354.7 247.1L349.8 245.0L346.8 245.7L340.0 243.6L337.9 243.8L337.0 248.9L335.1 249.9L335.6 251.9L332.5 252.6L328.5 250.6M331.4 277.9L328.7 275.8L325.6 277.4L323.9 275.9L319.5 279.8L318.9 276.5L317.3 275.7L318.1 271.9L316.2 270.1L316.5 269.4L319.1 271.6L320.0 270.9L321.2 272.0L320.8 273.4L323.2 271.7L324.2 262.3L328.5 250.6M339.9 219.2L336.3 224.4L336.3 227.6L338.0 228.5L333.5 230.6L332.4 232.4L332.9 236.8L331.7 238.6L328.0 239.9L327.6 242.2L329.5 247.4L328.5 250.6M328.8 365.6L333.5 366.1L332.9 370.0L334.9 371.0L333.8 372.1L335.5 372.9L334.1 373.2L334.9 374.5L336.3 373.3L336.1 374.7L337.0 374.7L338.4 377.8L338.7 379.6L336.3 380.4L336.0 382.2L337.0 384.1L338.2 384.0L338.8 385.9L335.3 388.6M347.1 340.0L345.7 341.2L346.8 342.9L341.2 345.5L339.4 348.7L337.5 345.5L334.1 345.4L332.3 351.6L334.4 351.2L335.3 356.7L339.0 359.6L337.1 360.6L335.5 359.9L334.9 360.8L331.5 360.8L329.6 362.6L328.8 365.6M352.7 450.9L345.6 456.6L344.3 455.1L342.6 455.1L339.3 459.6L336.4 460.6L334.9 460.6L331.2 455.4M346.4 276.9L342.1 276.2L338.7 277.9L338.5 276.1L336.4 278.6L333.7 278.3L333.2 277.3L332.5 278.2L331.4 277.9M355.4 580.4L351.7 578.2L349.2 579.3L346.9 578.6L346.5 580.2L344.3 578.6L335.0 579.2L336.0 578.7L335.4 575.9L338.9 576.5L340.8 571.6L339.0 571.2L337.5 567.3L332.3 566.3L330.3 564.0L330.8 562.3L332.9 560.9L331.8 559.0L333.7 555.5L333.1 554.7L334.3 554.3L333.5 551.9M335.3 388.6L337.3 394.8L343.5 396.0L345.4 397.9L344.4 400.2L338.6 402.7L339.8 403.3L335.2 406.0L334.5 408.0L336.3 410.8L338.3 411.6L339.2 410.7L339.7 411.5M339.7 411.5L345.1 423.3L343.5 427.2L345.8 436.4L345.5 442.6L347.5 447.1L352.7 450.9M365.7 404.7L363.2 404.0L361.7 401.8L359.5 402.1L358.6 399.3L347.4 402.7L349.3 409.8L348.7 410.3L346.0 410.7L345.9 409.7L343.5 409.3L343.1 410.6L339.7 411.5M339.9 219.2L341.2 220.1L347.1 220.0L350.0 220.9L350.6 223.6L352.3 222.8L354.6 223.9L358.6 219.1L363.4 217.8L366.4 223.3L368.7 224.6L369.4 228.0L373.7 235.9L373.7 239.6L376.1 241.3M343.9 318.5L343.1 320.0L344.1 321.7L343.5 322.8L344.5 322.7L343.1 324.2L344.4 327.7L346.6 327.8L345.5 332.8L347.1 340.0M343.9 318.5L347.2 316.5L344.3 314.1L346.0 313.0M356.5 314.8L355.8 313.8L350.0 314.1L347.4 312.5L346.0 313.0M346.0 313.0L343.4 312.7L342.4 307.0L341.2 305.5L339.5 306.0L338.4 304.4L340.0 303.1L339.3 301.0L340.3 299.3L338.6 291.8L339.4 285.8L341.1 282.8L342.1 283.0L343.6 281.3L341.8 281.1L344.3 279.3L346.2 279.3L346.4 276.9M346.4 276.9L347.2 274.8L349.5 274.1L357.3 275.9L361.9 274.0L360.5 272.0L362.8 272.8L362.8 271.0L364.5 271.6L364.7 269.7L366.7 269.6L367.3 268.1L369.3 268.3M360.3 338.9L357.9 338.1L356.5 339.7L352.3 340.1L351.2 341.8L349.0 342.5L347.8 339.7L347.1 340.0M348.8 507.9L353.9 511.0L356.8 516.0L358.5 515.9L360.4 514.0L363.1 515.2L366.3 512.2M348.8 507.9L354.7 504.6L351.2 500.0L349.1 500.9L348.4 499.3L346.5 499.1L345.6 500.2L341.2 495.3L339.7 496.4L339.2 496.3L340.7 493.2L340.4 490.7L337.5 489.1L337.9 488.2L336.5 486.9L338.4 486.8L340.5 484.8L340.6 482.4L339.6 482.0L342.3 477.9L346.6 478.3L344.8 475.9L347.7 473.9L350.3 473.7L350.8 472.2L349.8 470.6L354.6 470.2L355.9 467.9L357.1 468.1M352.7 450.9L352.7 450.9M357.1 468.1L357.8 467.0L354.7 464.3L354.1 461.5L356.0 460.2L356.3 456.3L355.0 455.8L355.8 453.8L352.7 450.9M381.1 444.7L382.9 449.9L381.2 455.4L376.0 458.9L372.1 457.2L371.2 455.6L367.7 454.8L366.2 452.1L359.7 448.9L356.5 448.3L352.7 450.9M375.9 540.6L373.9 551.7L365.3 565.8L359.1 568.7L355.2 568.4L356.9 574.8L355.4 580.4M367.5 326.9L365.3 326.8L364.9 325.5L363.3 325.8L362.6 323.9L363.3 322.0L358.8 319.2L358.5 316.4L356.5 314.8M372.5 296.9L365.4 307.3L362.7 306.9L358.8 309.9L358.2 313.0L356.5 314.8M374.6 489.9L373.4 487.7L370.6 486.2L369.2 480.3L364.3 480.0L362.6 474.5L357.0 469.2L357.1 468.1M362.2 344.6L362.2 343.2L360.1 341.1L360.3 338.9M367.5 326.9L366.9 329.4L368.6 331.9L363.7 333.8L362.4 336.5L362.8 338.2L360.3 338.9M376.8 353.8L372.3 350.8L370.5 352.1L367.9 351.1L366.8 348.9L363.2 346.9L362.2 344.6M380.9 338.5L374.4 338.9L373.8 341.0L371.2 343.0L364.8 343.2L362.2 344.6M390.0 402.3L391.0 401.5L389.7 400.0L388.3 400.3L385.0 397.0L382.8 397.0L380.8 392.5L377.8 392.4L377.6 393.6L376.2 393.4L373.5 395.4L364.8 393.9L364.5 394.7L368.2 398.1L366.5 400.7L365.8 404.7L365.7 404.7M365.7 404.7L366.2 406.1L370.4 407.6L372.1 412.6L373.3 412.8L373.1 415.2L370.8 415.2L373.7 419.0L374.6 426.9L373.6 427.2L373.5 429.8L370.5 431.8L371.1 436.4L372.2 437.3L373.4 435.6L375.4 435.6L375.6 438.6L374.5 440.2L375.2 441.9L377.9 443.5L379.3 442.6L380.6 445.9L381.1 444.7M375.9 540.6L373.2 539.8L372.9 532.1L366.3 512.2M366.3 512.2L369.5 510.3L373.2 514.7L378.7 513.0M369.3 268.3L372.5 266.1L372.9 264.2L371.6 262.0L371.2 262.8L368.1 260.0L367.8 258.6L371.5 252.6L370.5 250.0L367.3 247.7M376.1 243.4L375.0 245.1L368.6 245.5L367.3 247.7M380.9 317.0L367.5 326.9M369.3 268.3L367.6 272.5L372.5 279.6L371.0 282.8L375.9 284.5L374.7 286.1L378.4 291.0L376.5 291.2L375.5 293.4L376.8 295.6L372.5 296.9M380.9 317.0L378.2 315.1L376.3 311.5L376.5 305.8L374.4 305.0L374.6 299.5L372.4 299.4L372.5 296.9M378.7 513.0L374.8 506.5L375.0 503.3L376.5 500.5L376.1 496.1L371.4 495.4L369.0 492.5L369.4 491.2L374.0 491.1L374.6 489.9M374.6 489.9L375.3 488.2L380.8 488.9M411.4 580.0L408.1 576.5L400.2 575.5L397.2 570.7L394.0 569.9L393.0 565.8L388.7 564.7L383.5 560.3L385.4 557.3L385.3 553.2L387.8 546.8L386.9 546.4L387.3 544.4L384.6 543.5L384.0 542.1L379.9 544.2L378.4 543.9L378.5 542.0L378.0 542.7L377.4 541.0L375.9 540.6M397.6 245.0L390.7 247.8L384.2 246.9L382.8 248.8L376.1 243.4M376.1 241.3L376.1 243.4M376.1 241.3L376.4 240.2L380.0 239.4L381.0 237.4L380.1 236.4L382.4 232.9L383.4 225.5L383.1 223.4L381.4 221.8L382.5 216.9L385.2 215.4L385.4 213.9L390.4 212.6L395.9 212.8L398.7 211.3L404.2 210.7L406.3 208.3L408.7 208.0M383.8 359.8L383.4 356.2L380.8 354.4L379.8 356.6L378.9 355.6L377.6 356.7L376.8 353.8M376.8 353.8L378.3 352.8L376.0 348.0L377.0 341.9L378.8 341.5L379.3 339.5L380.9 338.5M378.7 513.0L380.6 512.5L382.2 513.3L384.5 516.1L385.7 515.4L387.5 516.3L388.4 515.0L391.1 514.4L392.8 517.1L394.7 517.0L398.0 522.9M380.8 488.9L383.6 488.9L384.1 485.6L387.1 486.3L389.9 484.7L394.7 486.0L394.4 486.7L396.1 484.8L399.7 485.8L403.1 484.0L403.6 482.4L404.9 483.0L408.3 477.5L411.6 478.3M398.0 522.9L401.8 522.0L404.3 513.5L406.1 513.1L405.4 511.4L406.9 506.9L408.8 506.3L408.5 504.0L410.1 503.6L407.6 500.8L405.0 501.0L407.1 497.5L400.5 496.8L400.3 495.9L396.3 496.4L391.5 493.6L391.7 492.9L388.7 493.5L380.4 490.6L380.8 488.9M380.9 338.5L382.4 338.4L382.5 335.8L383.7 334.8L383.7 333.1L382.7 333.0L383.8 332.1L381.8 331.5L382.7 326.4L380.9 326.0L382.9 320.5M382.9 320.5L379.6 319.5L380.9 317.0M386.2 439.9L383.4 442.3L384.0 445.9L382.1 443.7L381.1 444.7M410.6 316.4L406.3 313.3L402.5 314.3L402.2 312.1L399.8 314.5L397.1 314.6L395.6 317.7L388.7 322.2L387.2 322.8L386.2 320.5L382.9 320.5M411.7 350.9L407.0 349.4L402.9 350.7L401.5 356.1L397.3 357.1L395.5 359.1L393.5 358.5L392.0 360.8L383.8 359.8M419.1 367.6L414.6 368.0L413.0 369.6L411.6 367.7L408.8 366.9L408.4 363.9L404.9 367.1L400.7 367.0L393.7 368.8L383.5 364.1L383.8 359.8M386.2 439.9L384.4 437.9L382.2 430.4L384.0 427.7L384.5 421.4L383.5 420.7L384.5 418.7L383.5 416.6L384.9 415.6L382.4 415.2L382.9 411.9L381.0 407.6L386.0 406.1L386.9 404.1L387.3 405.1L389.8 404.9L390.0 402.3M397.4 454.2L397.1 453.2L395.7 454.0L393.8 451.2L394.5 449.9L393.5 449.9L392.8 448.4L393.7 446.6L392.9 445.1L390.9 444.1L386.6 439.7L386.2 439.9M427.6 402.0L424.9 401.8L422.4 399.3L421.4 400.6L419.8 395.8L416.8 394.3L415.1 396.5L414.3 395.6L413.7 397.4L410.6 396.3L407.8 398.9L410.4 401.3L406.1 403.6L406.2 405.8L405.2 406.2L397.9 405.1L397.7 406.1L395.6 402.7L394.6 403.4L396.5 406.2L392.8 406.2L390.0 402.3M411.6 478.3L411.6 476.3L406.3 469.6L399.1 464.8L398.1 468.2L396.0 465.9L395.7 462.3L398.0 459.4L397.4 454.2M397.4 454.2L401.3 454.1L404.0 450.8L402.1 449.0L404.1 448.5L403.8 447.3L404.9 446.4L405.9 447.4L407.2 446.6L409.9 450.1L413.8 451.9L414.3 450.8L416.5 451.0L418.0 452.3L417.2 453.0L420.9 453.7L422.3 455.1L430.6 450.4M431.8 221.5L425.3 227.5L428.2 233.7L425.9 236.7L422.1 236.0L416.4 240.4L414.0 238.4L406.1 246.5L400.9 246.4L397.6 245.0M397.6 245.0L398.3 257.6L397.4 259.2L403.5 266.4L407.0 266.4L408.3 268.1L409.3 273.6L408.1 279.4L410.7 280.4L417.3 279.0M398.0 522.9L401.1 529.7L404.4 532.9L402.9 535.7L421.4 538.8L421.8 542.6L424.6 541.7L425.3 549.0L424.0 550.9M408.7 208.0L413.1 209.2L422.5 208.4L423.2 210.5L425.6 210.5L427.8 212.6L431.8 221.5M408.7 208.0L410.1 205.0L409.0 203.3L411.2 200.7L414.1 202.4L416.0 202.5L416.9 201.1L415.5 197.9L416.8 195.3L418.9 195.2L420.6 187.0L422.7 187.7L424.6 191.1L428.5 184.8L430.5 188.0L434.0 185.1L438.9 185.1L439.8 186.9L441.5 187.3L447.6 183.8L451.3 183.0M410.6 316.4L411.7 317.4L410.9 318.1L408.6 317.4L407.4 318.8L405.4 319.1L406.8 320.4L405.7 320.9L405.1 324.7L404.0 326.9L399.8 330.3L398.6 333.1L401.1 332.0L403.5 332.8L405.0 336.6L406.2 336.8L406.6 335.4L407.7 335.3L407.3 336.7L409.1 336.8L408.5 337.8L411.6 339.7M474.7 313.2L473.0 311.9L468.9 312.9L468.4 313.9L462.5 314.0L459.6 316.5L454.5 316.2L447.9 314.0L446.9 316.7L446.3 315.5L441.8 316.9L439.8 316.1L438.4 317.3L434.8 316.2L435.0 319.6L432.7 319.4L432.9 320.1L432.7 320.2L430.8 318.8L430.7 317.3L428.8 317.8L428.7 316.2L426.8 314.2L418.3 313.3L417.4 316.7L414.9 316.9L413.2 315.6L410.6 316.4M440.9 614.5L440.6 612.0L435.2 612.3L435.4 609.7L432.6 610.4L426.3 604.6L425.2 602.1L423.8 602.5L420.9 600.2L415.7 600.0L414.8 603.9L411.8 603.4L410.2 599.9L412.0 594.0L411.3 592.2L413.3 590.9L414.8 588.0L411.4 580.0M421.5 571.7L412.5 576.6L413.3 577.3L411.4 580.0M450.7 516.7L435.0 503.7L429.3 496.9L427.9 493.0L419.6 487.4L417.3 485.2L416.3 482.0L414.2 481.0L413.3 478.8L412.6 478.2L411.6 478.3M453.4 333.0L450.0 333.5L447.4 332.0L447.2 330.6L446.6 332.1L444.4 331.6L442.2 332.6L439.0 328.8L436.5 331.1L431.5 332.7L425.6 329.3L421.4 330.6L420.4 334.1L418.8 333.6L418.8 335.9L417.1 339.0L415.8 339.3L415.3 338.3L413.8 339.9L411.6 339.7M411.6 339.7L409.3 341.7L413.0 344.0L411.9 346.0L412.6 347.3L413.3 345.8L413.3 348.0L411.7 350.9M411.7 350.9L414.9 354.0L419.5 352.7L422.8 353.7L419.9 359.3L420.6 360.3L424.0 357.6L426.0 359.7L431.0 359.1M417.3 279.0L417.5 281.9L414.6 286.7L417.2 290.6L424.8 290.7L432.6 293.7L435.0 292.4L438.4 294.0L446.9 291.7L461.6 293.9M417.3 279.0L419.1 276.2L419.2 273.2L421.2 273.5L422.9 272.1L423.9 268.4L427.7 267.7L428.3 266.1L432.1 266.0L433.1 265.3L432.3 264.4L432.8 261.9L434.7 262.4L436.9 259.0L439.6 257.5M419.1 367.6L422.4 370.0L421.2 371.7L422.6 372.8L429.3 371.9M431.0 359.1L431.6 361.0L429.7 363.1L420.4 364.9L419.1 367.6M443.4 605.7L431.5 594.1L422.3 589.2L423.6 585.2L425.5 583.8L423.0 582.5L421.5 571.7M424.0 550.9L423.8 555.3L422.9 556.0L413.8 556.9L418.8 562.0L421.5 571.7M450.7 516.7L447.1 521.6L448.6 522.7L436.6 535.7L438.7 542.4L440.9 545.1L437.6 551.0L438.3 555.1L436.1 556.5L429.2 555.5L425.5 551.1L424.0 550.9M427.6 402.0L427.4 403.7L428.4 404.1L427.7 404.9L426.2 404.2L423.5 406.9L422.6 408.8L423.2 411.0L420.6 412.7L421.0 414.2L419.0 414.5L416.8 419.0L419.1 422.3L419.7 421.7L418.7 420.9L420.9 420.8L422.2 422.8L424.1 422.0L424.0 423.0L426.1 423.8L424.0 425.1L425.5 427.9L426.2 433.0L428.0 436.9L431.4 440.6L430.6 441.7L428.7 441.0L428.3 445.2L430.6 450.4M429.8 400.0L427.6 402.0M489.5 410.2L489.7 408.0L488.4 407.2L482.7 407.4L482.2 403.6L483.8 402.5L483.7 399.7L481.5 398.0L483.2 392.2L481.8 387.0L480.7 386.4L482.7 382.6L479.4 381.2L475.9 376.8L473.9 377.4L473.2 374.1L471.1 374.4L464.7 370.6L467.0 374.9L465.9 377.0L460.8 378.6L457.6 378.1L454.9 380.5L448.0 377.6L446.6 378.8L447.9 380.4L444.7 380.6L444.2 382.2L442.3 381.6L441.6 379.4L437.8 379.1L435.4 377.8L434.6 376.7L435.8 376.4L434.5 374.9L429.3 371.9M429.3 371.9L429.5 375.5L424.9 378.8L423.0 378.6L426.4 383.5L428.4 384.2L432.0 388.2L431.0 389.7L431.7 390.8L428.4 391.0L427.4 392.1L427.6 393.6L429.1 394.4L427.9 394.6L429.8 395.5L428.9 397.7L430.9 397.7L429.8 400.0M482.5 416.8L478.5 416.3L476.2 413.7L472.5 407.2L473.4 404.7L470.4 404.2L469.1 399.1L466.5 397.2L465.8 398.9L463.7 398.3L464.3 401.7L462.6 403.5L456.4 401.3L454.5 402.1L452.8 400.8L451.1 401.1L450.3 399.0L448.9 399.0L448.3 400.3L447.0 397.8L446.5 398.8L445.0 398.1L444.2 395.4L441.3 397.9L438.3 397.1L438.1 399.7L436.2 401.2L432.9 401.8L429.8 400.0M430.6 450.4L433.3 451.9L436.7 459.1L434.1 459.5L433.0 462.3L430.9 463.2L431.4 473.3L433.8 471.6L435.6 473.0L435.9 475.8L440.1 478.4L439.3 483.5L445.4 485.4L446.5 487.2M455.5 342.9L454.0 343.2L451.0 346.7L448.0 346.3L444.6 348.4L446.6 352.5L443.9 351.5L442.7 352.8L443.3 355.4L442.1 354.2L438.4 354.1L438.5 355.3L437.1 354.7L437.6 355.6L436.7 356.3L435.9 354.9L435.5 356.3L434.8 355.0L433.3 356.2L434.5 357.0L433.1 357.5L433.6 358.2L431.0 359.1M445.8 220.0L441.7 217.3L439.4 218.2L437.6 216.1L435.0 217.5L434.8 220.2L432.5 221.8L431.8 221.5M439.6 257.5L445.3 254.7L444.4 256.4L446.4 257.1L445.9 260.2L447.5 260.3L448.7 262.0L450.7 261.2L453.6 261.9L457.2 268.0L460.0 268.7L462.1 267.4L465.1 267.5M439.6 257.5L438.6 256.5L440.0 255.7L439.7 251.5L443.7 246.6L442.8 243.3L444.5 242.4L445.1 239.1L447.9 236.8L449.5 232.4L446.2 226.5L447.7 221.0L445.8 220.0M493.5 610.1L484.5 602.5L481.2 603.1L478.8 607.1L479.8 613.2L478.3 614.5L479.6 617.5L477.9 620.0L477.6 624.2L467.3 626.8L465.4 629.5L463.0 629.2L458.9 630.9L450.3 632.3L449.5 627.0L446.3 624.0L446.3 620.7L444.4 618.3L445.8 616.7L443.4 613.5L441.9 614.9L440.9 614.5M440.9 614.5L442.4 612.4L442.4 606.3L443.4 605.7M443.4 605.7L446.8 608.8L448.1 613.7L451.9 613.5L454.5 612.4L456.7 607.6L457.5 604.3L455.5 601.5L462.1 597.8L466.7 600.4L468.4 602.7L476.0 605.5L476.3 603.9L478.8 603.7L479.7 601.6L485.7 600.5L493.4 607.6L493.5 610.1M469.9 221.3L465.7 221.0L460.2 222.4L456.4 219.8L449.0 220.6L445.8 220.0M452.9 505.3L447.7 503.3L444.9 496.5L445.6 495.8L444.7 492.1L446.9 489.7L445.9 488.2L446.5 487.2M446.5 487.2L448.7 486.6L449.0 487.4L450.6 486.0L455.5 488.5L458.7 488.5L460.5 488.4L462.2 486.3L462.5 471.7L460.2 471.1L459.6 469.6L461.0 467.5L458.9 467.3L458.0 462.8L459.6 461.9L469.0 463.1L469.4 461.3L468.3 461.0L469.8 460.6L469.7 458.5L467.9 456.6M452.9 505.3L454.6 506.7L454.3 508.7L457.6 511.2L452.1 518.0L450.7 516.7M475.0 187.0L474.3 189.2L468.7 191.3L466.9 190.1L466.3 188.0L464.1 188.3L464.2 187.4L461.4 187.4L460.7 189.2L458.0 188.8L455.0 186.1L456.1 183.7L455.5 182.5L454.2 181.9L451.3 183.0M451.3 183.0L451.0 177.7L453.3 174.3L452.6 171.8L455.2 170.2L452.6 168.6L454.0 166.6M498.6 500.9L490.6 500.1L482.6 496.8L481.8 499.0L479.0 499.0L478.0 501.4L476.0 502.7L477.1 506.6L473.2 510.9L470.5 509.2L467.2 510.3L466.9 507.0L463.0 504.1L456.9 505.2L456.1 504.4L456.9 502.5L455.7 501.4L452.9 505.3M453.4 333.0L454.9 334.1L455.8 337.3L458.2 338.5L457.2 340.8L454.1 340.5L457.0 341.2L456.7 342.9L455.5 342.9M474.7 313.2L474.7 313.1L475.0 313.3L475.1 313.5L475.5 314.8L475.5 317.1L476.0 317.1L476.0 320.6L474.1 323.2L471.7 324.1L472.4 326.3L466.6 325.0L462.9 327.5L458.7 328.5L448.9 328.0L450.4 330.0L453.2 330.4L453.4 333.0M454.0 166.6L454.9 167.5L458.3 166.7L458.9 167.8L460.0 166.6L461.7 167.3L464.7 165.5L466.0 166.9L464.6 170.0L465.8 169.2L466.4 171.1L467.2 170.0L468.8 171.4L469.3 170.0L467.5 175.8L469.5 175.9L471.3 179.9L476.2 181.0L476.1 183.3L474.8 183.2L474.6 184.8L475.6 185.4L475.0 187.0M454.0 166.6L455.4 166.3L457.1 162.2L456.0 160.0L457.7 158.9L457.1 157.5L458.8 154.1L461.2 152.6L462.6 147.7L465.0 147.2L465.8 142.3L470.8 139.3M504.4 353.6L501.8 351.0L493.8 356.1L491.7 359.9L489.9 361.1L486.5 362.0L478.4 361.1L475.7 362.3L473.2 360.1L473.1 356.4L471.5 355.0L473.2 352.3L473.0 346.3L463.9 345.9L463.3 345.0L461.5 346.5L460.8 345.8L455.8 346.9L455.5 342.9M461.6 293.9L463.5 296.0L470.4 299.4M468.3 273.8L468.9 275.2L467.1 275.5L468.0 277.7L465.6 279.9L464.7 279.4L464.4 281.5L462.5 282.9L463.1 283.6L461.3 289.0L461.6 293.9M465.1 267.5L465.6 270.6L467.8 272.0L468.3 273.8M471.8 243.1L471.2 248.5L468.6 250.7L467.5 256.5L469.7 261.8L467.7 262.7L467.8 266.5L465.1 267.5M513.8 468.0L510.7 470.1L508.2 470.4L507.8 469.0L507.0 469.3L507.9 465.6L504.1 465.5L500.9 467.3L498.9 470.1L495.7 468.5L495.1 469.3L492.9 469.0L490.8 466.3L491.0 462.0L488.9 460.0L487.5 456.1L485.1 456.3L480.5 460.1L478.7 458.1L472.0 456.5L471.1 458.2L467.9 456.6M467.9 456.6L466.3 455.1L466.8 453.4L463.2 449.8L467.6 445.1L468.0 442.5L469.7 441.9L468.3 436.5L469.1 433.7L468.2 432.4L470.9 428.3L469.8 427.0L470.1 424.1L472.5 424.4L474.6 423.2L476.0 423.7L475.3 424.5L476.7 423.6L477.6 424.2L478.3 421.0L480.4 419.9L480.5 418.4L482.5 416.8M488.1 258.0L486.0 258.3L486.9 259.5L486.5 261.1L484.3 260.9L484.9 263.9L487.0 264.3L486.4 265.8L487.3 266.9L485.2 269.4L480.9 272.7L479.0 272.6L476.8 274.8L471.2 274.0L471.4 273.2L469.7 272.6L468.3 273.8M469.9 221.3L471.0 221.6L472.7 221.5L475.3 223.9L474.0 229.5L475.6 233.7M491.4 206.1L493.8 210.9L488.7 212.5L488.2 215.5L478.7 215.9L473.9 221.3L469.9 221.3M470.4 299.4L471.0 301.1L473.8 301.2L475.0 303.1L477.3 302.3L478.7 307.1L483.5 308.2L481.1 308.9L480.9 309.9L480.3 309.1L477.7 310.0L477.8 312.2M494.7 281.7L491.2 282.0L490.9 280.5L489.0 280.8L490.3 283.7L489.8 285.4L488.5 285.9L486.3 284.6L484.0 285.7L481.0 287.8L481.1 290.6L473.4 289.0L472.9 289.9L474.9 293.2L473.6 296.3L471.6 296.7L470.4 299.4M470.8 139.3L470.7 140.8L473.0 142.3L472.0 146.0L473.3 145.8L475.0 150.1L476.2 150.6L477.1 149.0L477.9 151.3L479.6 150.8L482.1 155.4L484.0 159.5L482.4 161.7L484.9 162.1L487.5 160.9L489.3 163.7L488.6 165.9L486.4 165.9L486.4 168.1L485.3 168.7L486.8 169.2L487.7 173.5L489.2 174.2L488.2 175.6L490.9 176.6L489.3 179.4L491.1 180.1L488.2 180.6L486.1 184.1L484.9 184.2L485.2 186.1L483.9 185.6L481.6 187.1M470.8 139.3L472.4 138.9L474.3 140.0L475.7 139.2L476.7 142.2L479.4 142.5L479.5 141.6L481.0 143.5L482.2 142.9L481.9 140.9M475.6 233.7L474.3 239.0L471.8 243.1M471.8 243.1L472.9 242.9L473.5 243.3L478.2 247.8L481.3 248.2L482.9 254.0L486.7 255.8L488.1 258.0M477.8 312.2L476.1 313.0L474.5 312.3L474.7 313.2M475.0 187.0L476.2 187.9L477.1 187.1L481.6 187.1M475.6 233.7L476.0 233.6L477.5 234.4L482.3 229.0L485.8 228.4L487.3 228.6L490.3 232.7L493.6 235.0L494.7 234.8L494.8 233.3L496.2 234.2L501.1 233.9L500.2 233.2L501.6 231.9L503.7 233.7L503.6 235.9L505.9 236.7L504.5 237.8L504.1 240.7M495.6 318.1L488.6 321.3L484.4 321.6L481.3 317.4L478.0 316.2L477.8 312.2M481.6 187.1L486.6 187.3L488.0 191.5L487.4 194.0L494.7 193.6M507.7 168.1L509.3 164.8L508.1 158.7L506.0 160.3L504.0 158.9L503.9 156.5L497.9 155.2L498.3 153.7L495.6 153.2L494.1 150.1L494.1 148.3L495.7 147.5L494.9 146.7L493.8 146.1L493.2 147.6L490.8 147.8L489.6 146.7L488.4 148.1L486.5 146.5L486.9 145.3L485.2 144.9L483.5 143.2L483.3 141.3L481.9 140.9M481.9 140.9L482.1 135.4L484.6 137.8L491.8 130.3L496.3 133.9L498.8 143.7L503.4 138.4L503.3 135.2L509.6 126.9L513.6 125.1L514.9 123.4L517.7 122.0L524.1 122.1L529.2 125.0M489.5 410.2L487.1 411.9L486.6 416.6L482.5 416.8M495.8 273.1L494.6 272.3L495.5 270.7L495.4 266.1L492.4 261.9L489.4 260.1L489.2 258.2L488.6 257.9L488.1 258.0M504.4 416.9L500.8 413.9L495.8 414.1L494.4 411.6L489.5 410.2M494.7 193.6L493.9 197.0L494.9 198.2L492.6 200.9L491.4 206.1M491.4 206.1L492.2 205.9L493.5 206.1L495.7 207.8L497.8 207.7L507.1 213.5L513.3 212.9L516.6 214.4L524.7 215.7L531.2 220.0M522.1 618.3L519.6 617.6L517.8 620.2L513.0 621.2L509.1 616.3L500.9 616.4L493.5 610.1M494.7 281.7L497.5 282.5L501.0 287.6L503.3 287.4L504.4 289.6L508.0 290.0M495.8 273.1L496.8 276.4L495.3 279.0L496.1 280.4L494.7 281.7M494.7 193.6L494.8 193.6L495.0 193.6L495.3 193.5L495.8 192.6L501.6 191.1L502.8 189.8L502.7 187.4L505.7 187.5L506.1 181.8L506.5 180.9L507.3 181.6L507.6 178.6L507.4 175.2L505.7 172.7L507.7 168.1M506.3 317.3L506.1 316.6L501.7 317.9L499.6 316.6L497.2 318.1L496.0 318.2L495.6 318.1M508.0 290.0L506.2 290.6L506.0 295.0L504.1 294.8L504.0 296.7L501.7 296.5L501.3 298.2L499.7 298.9L498.3 303.7L494.3 308.4L494.3 314.7L495.6 318.1M507.4 258.2L502.5 260.9L501.1 264.4L501.8 267.3L500.4 269.1L498.7 269.0L495.8 273.1M498.6 500.9L498.7 501.0L500.4 497.8L501.2 496.6L503.3 492.9L502.4 492.4L503.5 492.5L505.5 489.2L513.0 490.0L515.8 494.4L520.6 493.2M513.0 557.0L510.2 554.6L508.2 547.3L508.6 538.6L503.4 535.9L497.8 528.7L493.1 526.1L494.5 525.9L493.9 519.3L494.7 519.9L495.0 514.9L495.3 514.2L497.7 514.5L497.0 511.4L499.7 508.3L497.9 507.0L499.0 504.8L498.6 500.9M524.0 251.9L520.1 249.9L516.9 251.2L515.2 248.9L511.2 248.3L510.0 246.3L507.0 246.6L507.1 244.6L504.1 240.7M504.1 240.7L503.3 243.3L505.3 243.6L503.9 245.1L503.5 249.4L505.6 251.9L504.5 254.4L507.4 258.2M529.6 368.0L527.6 366.3L528.2 364.5L527.0 363.8L525.2 364.5L524.4 363.7L525.2 362.8L523.2 362.2L521.9 359.3L519.3 360.8L519.9 362.0L518.5 362.7L504.2 354.2M524.9 373.0L517.8 375.6L516.4 375.2L509.7 379.8L501.3 377.6L500.8 376.3L505.3 375.1L502.7 372.7L503.0 368.6L500.8 364.5L505.1 362.7L506.1 359.2L504.2 354.2M504.2 354.2L504.4 353.6M504.4 353.6L505.0 352.6L507.3 353.3L509.3 352.3L508.8 351.1L511.0 350.4L510.9 349.6L512.1 350.3L514.4 347.6L513.6 346.6L514.6 345.5L513.8 343.9L511.9 343.7L513.0 342.4L510.8 338.1L512.1 336.6L509.6 336.3L510.2 334.0L509.3 330.8L506.3 331.4L506.3 332.7L503.8 329.1L502.2 329.1L502.3 330.3L501.1 330.2L500.8 331.1L499.1 330.5L502.4 327.0L507.0 325.9L507.7 324.4L510.0 324.8L509.6 322.8L505.6 319.4L504.6 319.7L506.3 317.3M535.9 436.4L534.7 436.1L531.4 438.2L528.6 435.9L529.2 435.0L527.8 434.6L527.2 432.4L522.8 433.1L521.3 434.8L517.3 431.0L513.4 430.6L513.2 426.9L509.9 425.9L509.3 424.3L510.1 421.5L507.7 421.5L503.8 419.5L505.3 419.1L504.4 416.9M514.2 410.1L512.3 409.9L509.2 412.6L510.4 414.9L508.8 416.4L506.2 415.7L505.9 416.8L504.4 416.9M517.9 316.5L515.9 318.8L511.7 318.6L509.8 320.1L507.7 319.3L508.8 317.3L506.3 317.3M507.4 258.2L509.6 260.7L511.2 260.5L513.9 263.4L515.8 263.6L516.0 265.3L519.2 268.5L519.2 270.6M507.7 168.1L513.4 174.1L514.7 173.6L514.1 170.6L516.3 172.3L515.8 171.1L517.5 170.5L519.0 167.0L522.6 169.9L521.5 170.7L522.2 172.3L524.1 171.6L525.0 172.7L523.3 168.3L519.6 165.3L525.0 161.8L526.9 162.3L531.7 161.0L532.9 159.4L535.6 159.4M518.4 304.0L517.9 300.6L516.5 301.3L516.7 298.4L518.3 297.5L514.6 297.0L515.3 295.2L513.0 294.2L513.7 292.2L512.8 291.0L511.3 291.5L508.0 290.0M523.8 569.4L518.7 567.0L513.0 557.0M535.1 534.3L533.9 536.6L532.2 533.9L528.3 532.2L522.7 534.0L521.8 535.1L522.7 537.7L520.7 538.6L520.2 542.6L516.1 544.5L514.0 547.2L513.6 548.6L516.5 551.8L513.0 557.0M513.8 468.0L513.1 458.6L515.2 458.3L515.3 456.0L517.7 455.5L518.9 456.7L520.5 455.8L521.6 451.0L523.2 452.2L528.5 451.9L529.7 449.7L529.1 446.9L530.8 444.3L533.6 444.8M529.9 482.4L523.6 475.8L518.4 475.3L516.5 473.0L516.3 467.2L513.8 468.0M514.2 410.1L514.1 407.7L515.1 406.9L512.6 401.9L511.4 401.6L512.6 399.1L521.2 399.2L522.0 395.3L523.4 394.5L525.9 394.0L526.2 395.1L529.4 395.7L529.5 391.6L534.5 392.9M534.7 423.6L532.1 421.8L527.1 421.1L521.0 413.2L519.4 414.0L518.4 413.2L517.7 414.6L516.3 414.5L516.9 412.5L515.4 410.1L515.1 410.2L514.6 410.1L514.2 410.1M536.8 320.8L534.2 319.4L527.2 322.5L519.5 320.2L517.9 316.5M517.9 316.5L519.4 311.0L520.6 311.1L517.9 306.3L518.4 304.0M531.8 290.4L528.3 291.9L527.7 295.2L525.2 295.8L526.6 298.2L524.6 298.6L522.7 302.8L519.3 302.8L518.4 304.0M519.2 270.6L521.2 275.4L523.1 276.8L522.6 278.1L523.9 280.3L528.3 287.1L531.8 290.4M519.2 270.6L521.1 269.6L522.2 270.1L520.7 268.6L520.5 266.6L522.1 264.7L521.7 255.7L523.8 255.5L524.0 251.9M520.6 493.2L521.8 495.8L521.1 497.7L528.2 505.9L526.7 508.3L531.1 512.3L537.6 516.1M520.6 493.2L526.3 489.0L529.9 482.4M594.2 578.1L595.7 599.6L596.9 601.0L599.3 601.2L599.6 605.0L602.7 606.1L604.7 610.2L613.9 616.9L616.4 615.7L617.2 617.4L620.9 619.6L620.7 620.6L613.2 624.5L609.0 633.4L606.4 633.3L603.4 635.1L587.3 629.4L578.1 635.1L573.7 642.0L572.8 646.4L566.1 646.5L563.3 642.0L561.7 643.3L561.8 645.7L559.5 647.8L555.1 648.2L549.4 644.7L546.6 638.8L542.2 637.7L536.4 631.1L530.7 629.0L530.8 622.3L528.3 622.6L526.3 620.2L522.9 620.0L522.1 618.3M523.8 569.4L523.2 570.7L525.9 571.7L525.9 574.4L524.3 576.1L527.5 579.5L525.5 582.5L525.6 588.0L531.4 589.1L533.1 590.8L531.8 594.6L529.8 594.7L529.5 592.5L528.2 592.1L527.8 594.3L525.7 594.7L524.7 596.4L523.3 595.4L522.2 596.2L523.2 597.2L521.2 600.9L520.9 604.9L524.4 607.4L531.7 603.0L535.5 602.1L538.7 605.2L537.1 609.2L533.2 608.9L528.3 611.0L526.8 613.0L523.9 614.3L523.7 617.4L522.1 618.3M568.1 566.1L566.9 564.9L565.8 566.1L564.9 564.3L556.4 561.9L554.3 559.8L549.1 561.2L546.6 563.5L544.8 567.1L545.5 569.0L543.2 571.5L533.5 573.5L523.8 569.4M524.9 251.4L524.0 251.9M524.9 251.4L528.5 252.8L528.5 256.6L532.3 257.8L533.7 259.7L536.0 258.4L537.9 265.7L540.6 266.4M531.2 220.0L531.7 226.0L530.0 228.7L531.5 229.9L529.8 233.5L530.3 234.9L528.7 236.6L529.2 240.7L526.5 240.6L523.7 242.7L525.5 243.6L524.9 251.4M524.9 373.0L524.8 377.0L526.4 379.0L526.2 381.2L528.1 383.1L531.3 383.6M529.6 368.0L530.4 368.9L529.8 372.0L527.3 370.7L524.9 373.0M529.2 125.0L531.9 126.7L532.3 129.6L531.1 130.4L535.6 141.9L538.8 142.3L542.6 146.6M529.2 125.0L530.8 122.1L533.6 121.7L536.8 118.7L539.9 121.3L540.7 120.4L542.8 122.9L544.4 120.1L546.2 120.2L547.1 118.9L550.8 120.5L552.1 119.8M535.3 361.0L535.4 363.2L534.0 365.0L535.4 365.9L534.9 367.0L529.6 368.0M532.7 478.7L532.6 481.5L530.8 482.6L529.9 482.4M541.2 221.8L540.8 220.7L539.6 220.8L540.0 218.3L536.4 217.7L531.8 215.1L530.8 216.4L531.2 220.0M534.5 392.9L531.1 387.0L531.3 383.6M531.3 383.6L534.9 384.5L542.3 382.4L542.9 381.3L545.4 381.4L551.3 383.7L564.0 386.3L564.3 388.5L566.1 390.1L574.2 387.0L575.3 385.2L571.9 381.3L566.0 381.1L565.9 375.7L563.9 374.5L564.4 371.4L559.3 367.5M531.8 290.4L534.2 291.2M532.7 478.7L539.5 482.0L539.4 485.5L540.4 485.1L540.4 486.2L541.4 486.3L540.9 487.7L542.2 489.4L539.8 491.0L540.9 492.6L537.9 494.5L538.6 497.1L537.8 499.7L539.4 502.0L537.3 502.6L537.9 504.4L535.6 506.3L535.9 508.5L540.1 512.3L537.6 516.1M545.9 454.6L544.1 457.9L545.1 458.8L543.9 459.3L544.8 463.2L544.2 466.7L538.3 466.0L539.2 471.5L537.0 473.2L537.1 477.4L535.1 477.6L533.4 476.1L532.7 478.7M533.6 444.8L535.9 443.8L535.5 440.3L537.1 438.7L535.9 436.4M545.9 454.6L540.3 452.3L536.4 448.0L533.4 446.4L533.6 444.8M534.2 291.2L538.0 296.0L537.5 296.9L545.1 298.3L547.1 300.0L546.1 302.7L544.7 301.5L543.1 302.6L543.0 316.5L536.8 320.8M540.6 266.4L539.5 276.8L540.4 277.2L537.5 282.1L536.1 281.6L533.7 284.5L537.3 287.2L534.2 291.2M549.1 410.4L549.7 408.0L552.6 407.3L552.6 405.0L553.8 404.1L552.7 402.2L554.4 401.7L552.6 401.5L550.3 402.8L549.7 402.0L549.3 404.2L545.3 404.9L543.9 408.4L543.2 401.1L535.7 397.7L536.2 395.1L534.5 392.9M534.7 423.6L534.8 423.6L535.0 423.6L535.0 423.4L535.4 423.4L535.4 423.3L535.6 423.4L536.1 422.7L538.2 423.3L540.5 422.2L539.3 419.1L541.0 419.1L540.6 419.0L540.3 418.8L541.8 418.4L543.9 415.8L544.4 417.9L545.9 418.1L546.2 415.0L548.0 412.8L548.0 409.7L549.1 410.4M535.9 436.4L539.2 436.7L538.6 433.8L540.1 433.1L539.4 431.2L536.0 431.2L536.0 429.2L534.6 427.7L534.7 423.6M535.1 534.3L536.6 534.4L538.1 533.6L539.0 534.4L542.6 532.3L544.8 533.0L548.6 531.0L549.9 532.1L551.0 531.6L552.5 533.9L556.4 536.0L558.4 533.5L565.7 530.4L567.2 526.9L569.5 526.2M537.6 516.1L537.2 519.0L540.6 521.4L539.8 526.0L541.1 526.6L540.1 527.7L538.6 526.7L538.8 528.8L535.8 529.4L536.0 528.7L535.0 529.9L534.1 531.7L535.1 534.3M551.0 361.0L550.2 362.3L548.2 362.1L548.8 363.2L546.7 364.1L541.6 364.2L540.6 362.4L538.9 362.7L535.3 361.0M535.3 361.0L532.7 356.9L532.9 354.4L530.5 353.7L530.4 352.4L527.4 352.5L525.3 347.6L523.3 346.8L525.0 342.8L522.9 342.2L522.1 340.5L523.1 338.3L525.0 337.6L525.7 335.2L529.4 334.4L527.5 328.6L529.6 328.3L529.3 326.7L530.2 327.5L531.5 325.9L537.4 325.1L536.6 322.4M542.6 146.6L541.3 147.7L538.1 146.0L536.9 149.1L537.9 150.9L534.4 151.6L537.1 156.6L536.4 157.0L536.8 158.7L535.6 159.4M535.6 159.4L536.2 161.3L545.3 166.5L545.9 171.1L544.5 174.3L546.1 176.5L549.2 176.6L551.0 179.0L554.8 177.7L557.1 180.2L560.6 181.3M538.1 323.3L536.6 322.4M536.6 322.4L536.8 320.8M551.0 361.0L544.7 356.2L546.5 355.0L546.0 353.2L547.4 352.9L550.7 356.4L552.4 356.2L555.5 358.2L556.4 355.2L560.9 353.4L558.8 351.5L558.4 347.1L556.6 346.7L556.6 343.9L551.3 339.9L551.8 336.5L549.5 335.8L549.7 334.2L548.2 332.8L545.3 334.2L542.6 333.5L543.5 329.8L541.6 329.7L541.3 326.4L538.1 323.3M567.5 316.4L565.1 318.6L564.0 321.6L560.0 320.7L559.9 321.7L558.6 321.2L554.7 322.5L553.2 321.2L555.0 319.8L553.1 318.3L550.9 320.2L549.7 319.7L548.4 321.5L538.1 323.3M562.2 261.7L561.1 263.9L558.6 264.7L555.3 261.4L553.5 257.6L550.4 255.3L550.9 257.1L548.4 258.4L546.0 258.2L545.5 261.9L542.2 262.2L540.6 266.4M562.6 183.8L562.0 189.1L554.4 201.3L552.6 202.7L547.7 203.1L550.9 207.5L549.5 211.9L547.1 213.3L546.8 210.1L544.3 210.0L544.1 214.8L545.1 216.5L543.1 220.3L542.3 220.1L541.5 221.0L541.3 221.8L541.2 221.8M541.2 221.8L541.5 224.0L543.7 225.6L546.9 227.0L548.1 226.2L548.6 228.8L551.3 229.0L551.3 226.6L554.0 225.3L555.2 226.3L557.7 225.3L558.2 228.5L555.5 231.5L555.6 233.2L560.5 235.6M558.7 137.4L555.2 140.2L554.6 142.5L549.4 147.4L547.2 147.9L542.6 146.6M564.4 453.7L557.8 457.8L555.0 455.8L549.7 455.5L548.2 453.9L547.2 455.1L546.4 454.6L545.9 454.6M549.1 410.4L550.2 414.2L553.1 415.7L553.3 419.9L557.7 422.6L560.4 426.4L562.2 426.6L565.0 429.8L567.1 429.4L569.6 431.4L572.1 431.5M559.3 367.5L556.2 367.4L555.9 365.1L552.2 363.2L551.0 361.0M552.1 119.8L552.4 122.0L554.0 122.6L553.5 124.4L555.8 124.4L556.5 125.7L555.1 129.8L560.8 136.3L558.6 136.3L558.7 137.4M552.1 119.8L553.4 119.8L554.8 121.2L558.6 120.2L563.0 124.7L569.2 126.2L571.0 125.7L574.4 127.4L582.3 125.1L586.6 125.5L591.7 121.6L596.4 121.7L599.0 123.7L601.4 121.4L603.7 121.4M563.7 175.9L559.2 177.2L557.6 175.9L557.4 172.0L555.6 170.7L555.3 168.7L557.3 168.5L557.2 166.0L560.0 164.4L559.5 162.7L561.4 161.2L560.2 158.5L562.2 157.4L559.8 157.3L557.7 154.8L561.8 155.3L563.9 157.0L569.2 147.7L566.5 142.9L563.0 142.3L558.7 137.4M611.7 369.1L611.0 369.9L603.3 369.9L598.3 368.8L593.7 371.8L588.5 371.4L589.1 377.4L586.1 375.5L587.3 369.5L583.9 368.8L584.6 365.1L583.2 362.8L583.0 364.8L581.3 365.9L581.6 367.1L580.5 366.5L578.9 367.9L573.5 367.4L569.7 363.7L566.7 366.1L564.1 365.8L563.5 364.2L560.2 365.0L559.3 367.5M560.5 235.6L560.2 238.4L561.9 241.8L562.0 246.1L565.0 250.2L565.9 254.1L564.2 255.5L564.5 257.6L562.8 259.1L562.2 261.7M560.5 235.6L572.3 234.1M560.6 181.3L561.3 183.5L562.6 183.8M563.7 175.9L560.6 181.3M570.8 265.9L566.6 264.0L566.0 262.3L562.2 261.7M596.8 191.0L593.1 191.2L591.5 189.2L586.4 191.1L585.0 189.7L580.6 188.6L574.0 192.6L570.6 190.7L566.5 185.1L562.6 183.8M584.9 157.7L582.9 157.5L579.7 161.2L577.1 162.5L576.4 161.5L574.8 163.5L575.0 162.5L573.5 163.5L571.4 167.8L570.3 166.8L568.6 168.3L566.8 167.4L566.9 169.2L565.6 170.0L566.7 171.4L565.5 174.3L566.8 174.4L565.3 177.0L563.7 175.9M580.8 465.7L577.5 461.3L575.0 461.6L572.5 464.4L571.5 462.8L569.6 463.2L569.2 459.8L567.3 458.7L564.4 453.7M573.2 432.5L568.4 436.3L569.2 438.8L568.5 441.4L570.5 441.9L571.4 444.2L569.0 446.0L567.7 448.1L568.4 449.0L566.1 449.5L568.2 450.8L564.4 453.7M592.4 319.9L580.5 318.7L579.7 315.5L578.4 315.0L573.3 317.8L573.3 319.6L570.8 320.1L570.6 318.2L567.1 319.2L568.6 316.6L567.5 316.4M567.5 316.4L568.0 305.9L570.2 301.4L569.6 299.1L571.0 298.3L568.8 295.2L568.8 291.2L567.3 289.5L569.6 289.1L567.7 288.1L567.8 283.8L570.2 281.6L571.7 281.8L568.7 278.3L569.4 273.1L570.7 272.8L570.0 270.8L571.5 269.1L570.8 265.9M569.5 526.2L570.4 527.2L572.3 526.0L574.5 536.6L575.9 535.3L580.6 538.0L582.5 541.4L580.8 543.8L585.0 547.9L586.1 547.8L587.7 550.4L584.6 553.6L580.7 553.5L578.9 555.2L577.6 559.1L578.5 561.1L575.9 561.5L575.0 564.2L573.3 564.5L573.3 566.3L571.8 565.5L571.0 567.2L568.1 566.1M594.2 578.1L592.5 579.0L592.9 580.6L588.0 584.1L585.7 578.9L581.9 580.4L577.7 577.9L576.3 574.8L576.9 573.4L574.3 573.0L577.1 570.6L576.9 569.5L574.9 569.4L572.5 572.5L566.6 570.2L568.1 566.1M569.5 526.2L572.2 522.6L576.8 519.2L578.9 519.5L580.7 517.8L582.7 518.1M570.8 265.9L573.3 263.6L574.8 264.3M572.1 431.5L573.2 432.5M609.7 427.5L604.3 424.2L603.5 422.2L604.0 418.1L600.8 419.3L595.7 417.7L595.9 422.8L588.2 418.0L586.1 422.6L588.6 425.3L588.9 427.5L584.9 428.2L584.7 425.6L580.7 421.7L578.2 423.2L579.0 426.1L576.2 426.9L575.1 429.7L574.0 427.7L571.3 428.8L572.1 431.5M572.3 234.1L577.4 237.5L580.1 244.0L583.5 245.2M599.7 208.6L591.8 208.8L583.6 211.6L583.8 213.0L580.5 218.2L580.0 224.5L578.3 225.2L574.9 231.2L573.4 231.0L574.2 233.9L572.3 234.1M573.2 432.5L577.3 437.9L579.4 437.8L581.4 440.9L582.8 440.9L582.5 443.9L584.9 440.5L585.9 441.3L587.5 440.7L587.5 443.8L585.9 444.4L585.5 445.8L587.8 452.1L594.3 448.4L594.4 450.5L590.6 453.7L592.0 455.0L591.6 456.9M574.8 264.3L576.3 266.2L584.2 269.3L586.3 272.5L585.5 275.4L589.3 277.8L587.2 280.3L588.6 282.5L589.8 281.9L593.6 283.0L593.9 284.9L596.5 284.5L597.2 282.8L598.5 284.2L599.3 281.9L602.4 285.0L608.6 287.7L609.4 289.2M583.5 245.2L582.7 245.7L584.0 246.7L582.5 248.2L580.9 247.9L580.1 250.1L580.2 254.2L581.5 255.6L578.6 256.1L574.8 264.3M580.8 465.7L582.6 468.2L582.6 472.7L584.5 478.0L588.1 478.5L591.1 486.9L597.7 491.8L599.6 503.7M591.6 456.9L584.1 461.0L583.8 463.6L580.8 465.7M582.7 518.1L581.8 521.2L585.0 522.0L585.7 526.2L587.1 526.6L589.1 524.6L591.2 526.8L591.4 532.6L594.8 535.2L595.7 534.4L593.7 533.6L593.9 532.2L594.1 533.4L594.5 533.4L596.5 531.4L596.0 530.7L594.6 532.7L594.5 530.4L595.5 529.7L598.1 530.3L596.5 534.0L600.7 540.2L602.8 539.6L600.9 534.9L600.7 530.8L604.6 528.4L606.7 523.0L608.3 523.9L611.9 523.2L612.8 525.4L612.0 529.6L613.9 529.8L614.2 532.2L612.9 535.6L611.4 534.9L609.9 536.3L609.3 541.5L610.3 542.3L611.5 540.5L611.0 539.2L612.4 539.7L612.1 539.0L612.8 539.6L613.7 538.5L613.6 534.6L615.5 533.4L615.6 532.0L616.4 532.8L615.4 535.4L622.4 543.1L623.5 549.0L626.8 550.5L624.4 554.2L621.9 555.9L616.6 553.9L616.2 552.3L614.3 553.1L610.1 552.0L607.5 552.9L610.7 555.5L608.0 557.7L602.6 557.1L596.2 558.6L595.4 562.0L597.4 566.0L592.7 566.7L588.1 570.1L594.2 578.1M599.6 503.7L596.9 505.8L594.7 506.0L592.0 509.7L588.6 510.9L588.3 512.4L587.2 512.1L587.4 513.4L582.7 518.1M601.4 245.0L593.9 243.7L592.0 246.1L588.2 244.3L587.3 246.2L586.5 244.9L583.5 245.2M600.9 182.0L597.6 182.1L596.4 180.5L597.5 178.2L596.8 172.1L598.8 170.1L596.5 166.7L596.8 164.9L591.1 167.3L591.3 163.1L584.9 157.7M603.7 121.4L602.2 126.4L603.3 130.8L601.6 134.6L603.8 139.0L601.0 140.6L596.2 140.5L594.8 142.2L593.0 141.5L591.6 144.4L588.9 143.7L587.6 146.7L588.8 147.1L589.0 149.3L586.8 149.5L586.1 151.9L586.9 153.6L584.9 157.7M591.6 456.9L595.4 456.0L598.8 457.7L603.3 456.2L605.8 452.6L608.1 454.8L609.7 450.8L609.1 449.2M592.4 319.9L593.7 322.6L592.3 322.9L592.9 324.0L591.9 323.7L592.8 325.8L588.9 326.3L587.8 327.9L588.5 329.6L593.1 330.2L593.2 331.1L600.0 329.6L600.6 327.4L602.5 327.0L602.7 324.0L603.2 325.4L604.6 325.5L610.5 322.7M603.7 302.9L602.6 301.1L599.9 302.1L600.2 304.1L595.7 305.7L593.2 305.2L592.1 306.6L592.9 309.6L591.8 312.8L593.3 313.6L594.2 312.9L594.4 316.7L595.9 318.7L592.4 319.9M597.7 195.7L598.2 193.9L596.8 191.0M596.8 191.0L597.5 187.1L600.9 182.0M603.6 197.4L599.9 197.8L597.7 195.7M597.7 195.7L596.6 195.6L597.2 200.2L602.0 206.0L599.7 208.6M626.0 489.5L622.3 491.4L619.2 495.3L617.0 494.6L615.4 496.5L613.2 496.3L612.6 497.6L610.2 498.0L604.3 502.2L599.6 503.7M599.7 208.6L601.4 209.6L600.6 210.9L601.9 211.9L604.4 211.9L604.8 209.1L606.7 210.8L603.9 212.9L601.2 211.7L599.7 213.9L599.5 217.5L602.2 220.6L601.0 227.4L605.2 227.1L607.7 228.4L609.8 227.6L610.3 230.0L609.7 237.3L607.5 236.7L607.3 238.1L605.8 237.8L605.9 239.6L604.7 239.0L604.2 239.8L605.6 241.2L602.8 241.7L603.3 242.8L601.4 245.0M600.9 182.0L601.2 180.4L600.2 179.1L604.0 177.7L605.7 174.5L604.5 173.9L605.7 171.3L605.0 170.1L607.0 167.7L606.4 164.5L607.1 163.6L609.5 165.2L610.6 160.0L611.7 161.1L614.1 159.9L613.4 157.6L614.8 154.8L613.8 155.4L612.2 152.6L615.2 150.4L621.9 151.4L630.9 159.7L634.6 157.9L634.4 152.8L635.7 151.6M601.4 245.0L603.6 245.6L603.6 250.0L604.7 251.5L603.3 254.1L604.8 253.6L611.0 257.8L613.0 257.9M628.9 219.2L624.3 216.3L622.9 213.3L619.9 215.9L615.9 212.9L615.3 213.4L615.2 211.1L613.7 209.4L611.9 208.9L609.3 209.9L606.0 208.7L606.4 204.6L603.7 201.6L603.6 197.4M625.2 196.9L620.5 197.2L616.6 202.5L614.7 200.1L612.9 200.2L611.5 195.3L609.7 196.7L603.6 197.4M603.7 121.4L603.8 121.4L604.1 121.5L604.4 121.4L605.2 122.3L606.3 122.4L609.1 120.6L609.7 122.1L614.6 122.8L615.6 121.9L623.3 121.1M609.4 289.2L609.1 294.0L603.0 297.5L603.7 302.9M610.5 322.7L609.6 322.6L608.6 318.1L610.3 315.4L610.2 310.6L611.9 309.4L611.6 305.0L608.3 305.5L607.9 303.0L605.0 303.6L604.6 303.0L604.3 302.9L603.7 302.9M609.1 449.2L605.8 448.5L604.7 446.9L606.4 446.2L607.8 443.4L606.9 431.6L609.7 427.5M618.2 450.3L613.9 447.8L609.0 448.4L609.1 449.2M614.9 267.4L612.1 271.5L613.1 273.3L617.2 274.0L615.2 278.0L613.0 279.5L610.0 279.3L609.0 284.2L610.6 288.0L609.4 289.2M626.5 372.5L624.8 373.9L625.6 377.4L627.5 380.2L624.9 379.8L626.0 386.8L624.9 387.6L626.2 387.9L626.9 392.0L629.5 394.0L628.6 395.6L631.4 400.3L629.2 400.6L628.4 404.8L622.3 408.3L618.5 408.8L616.8 410.4L616.3 416.6L614.7 419.3L612.4 418.9L612.5 422.1L613.7 422.7L612.2 424.0L609.5 423.9L610.4 425.9L609.9 427.5L609.7 427.5M612.9 342.4L609.2 336.7L610.5 334.2L614.6 332.9L614.2 328.4L615.4 327.2L612.6 322.5L610.5 322.7M626.5 372.5L621.0 371.6L618.7 369.2L615.3 371.2L611.7 369.1M611.7 369.1L613.8 366.6L613.7 364.6L616.4 363.5L616.6 357.7L614.1 356.7L614.5 353.9L616.5 352.6M616.5 352.6L613.7 347.1L612.9 342.4M616.5 352.6L617.7 354.0L622.5 353.9L622.9 350.8L627.5 348.4L627.2 345.6L628.3 344.8L630.6 349.2L632.1 350.2L633.3 349.5L634.2 348.6L632.6 346.2L634.9 345.9L634.9 341.2L631.9 341.6L631.7 340.2L628.2 339.6L628.3 337.4L626.1 337.9L625.1 334.3L626.8 333.3L625.7 332.2L621.6 334.2L621.3 336.4L618.7 337.3L617.7 339.2L614.9 338.8L614.6 341.6L612.9 342.4M613.0 257.9L610.5 263.0L614.9 267.4M613.0 257.9L614.4 257.6L616.6 250.2L619.1 246.7L621.1 245.7L624.7 251.1L626.2 248.3L628.6 246.7L627.8 244.6L629.1 244.1L628.2 242.5L629.7 242.4M660.0 281.5L654.2 278.0L653.6 279.2L651.7 279.0L651.9 280.8L650.3 281.5L650.0 279.6L645.6 279.7L644.3 277.1L639.5 276.6L637.7 274.3L632.5 274.4L631.7 272.9L628.6 272.9L627.7 271.7L623.5 270.8L617.5 271.4L617.5 269.6L614.9 267.4M626.0 489.5L624.6 483.6L621.4 480.7L618.5 480.4L618.7 478.1L616.9 475.6L617.5 472.9L619.4 472.1L619.2 469.8L617.3 465.4L616.5 466.0L614.4 464.0L616.4 462.6L617.5 463.4L619.1 461.4L622.0 461.0L624.0 458.9L619.6 458.8L619.2 454.6L617.6 454.3L618.2 450.3M618.2 450.3L618.1 448.7L624.5 448.8L624.5 447.2L633.4 447.1L632.9 458.1L636.6 459.6L636.5 462.3L640.8 464.1L642.7 470.2L645.0 473.0L648.1 474.4M623.3 121.1L626.1 124.2L626.5 126.6L628.1 126.3L631.8 128.9L632.9 136.0L636.9 136.4L636.0 137.4L636.6 138.5L635.1 139.0L635.8 141.1L633.3 143.3L633.7 144.5L632.2 144.9L632.7 147.5L631.6 148.7L633.1 150.7L635.7 148.9L636.6 150.3L635.7 151.6M623.3 121.1L628.7 120.5L629.6 121.5L629.2 123.8L631.7 124.0L634.4 126.9L637.4 125.8L639.5 127.3L639.0 131.1L641.6 134.1L641.1 137.4L643.2 138.4L645.9 138.3L648.8 135.0L652.2 136.1L653.0 137.9L655.8 136.7L656.0 134.4L658.2 134.6M639.7 160.3L638.9 160.7L638.7 164.8L636.9 165.2L636.2 168.1L634.2 169.7L637.6 169.8L637.9 171.2L636.0 172.8L635.7 175.0L633.2 175.6L633.5 180.3L629.4 183.7L626.1 184.2L624.9 186.1L625.8 189.1L622.4 193.9L625.2 196.9M663.6 187.8L662.1 188.7L654.5 189.0L651.7 187.7L644.8 190.0L636.0 195.4L632.6 194.9L630.1 196.7L627.7 195.4L625.2 196.9M648.1 474.4L648.0 477.9L644.3 478.4L647.0 487.3L643.3 489.0L631.2 487.9L628.4 488.4L627.0 490.1L626.0 489.5M647.6 370.6L645.7 370.0L639.5 372.1L637.9 370.8L634.7 370.8L631.9 372.7L630.2 371.8L626.5 372.5M629.7 242.4L630.0 240.5L625.9 239.9L622.4 237.2L626.7 236.8L627.4 233.9L628.8 234.1L627.0 230.9L624.6 230.2L622.9 227.9L624.1 227.0L626.4 227.5L626.8 221.4L628.9 219.2M628.9 219.2L629.6 218.9L633.5 220.4L635.4 225.1L637.3 225.0L638.0 229.7L640.6 231.7L641.9 228.7L644.5 228.9L645.2 227.5L650.5 230.9L649.0 233.3L650.1 235.3L648.9 237.8L651.9 246.7M651.9 246.7L649.2 249.3L646.7 247.3L644.2 248.9L641.4 248.0L639.5 249.0L639.1 247.9L636.9 247.5L637.5 245.2L636.0 244.1L632.4 244.4L629.7 242.4M635.7 151.6L639.2 155.3L639.7 160.3M639.7 160.3L639.2 164.9L637.9 168.5L640.2 172.1L643.8 172.7L647.5 172.2L649.4 169.0L655.9 166.4L659.2 162.6L668.1 160.3M667.6 391.9L666.0 380.0L662.9 379.7L660.7 374.1L657.0 372.8L655.6 375.0L653.3 375.9L653.6 374.7L651.6 372.7L647.6 370.6M661.2 343.4L656.5 344.4L655.8 345.7L657.0 347.9L654.7 348.5L653.6 350.9L654.2 353.0L653.2 353.6L650.1 354.7L647.3 352.2L647.6 351.2L645.7 350.4L643.7 353.5L640.3 351.8L641.2 354.3L642.8 355.0L641.7 358.8L643.1 362.2L645.0 364.2L648.0 364.3L648.8 366.0L647.6 370.6M665.7 468.0L665.2 473.6L660.6 477.1L654.8 476.7L655.3 473.9L652.3 472.5L648.1 474.4M664.9 257.8L664.0 255.7L664.7 252.4L663.5 250.4L655.3 253.2L653.7 251.4L653.5 247.4L652.3 247.3L652.1 246.7L652.0 246.6L651.9 246.7M658.2 134.6L658.5 137.8L660.0 138.0L658.8 140.0L659.4 141.2L657.3 141.2L659.1 142.3L658.4 143.5L660.2 144.0L659.5 144.6L661.9 146.8L664.3 146.4L667.0 147.8L664.4 152.1L666.4 154.3L665.2 157.2L667.5 158.2L668.1 160.3M658.2 134.6L663.2 129.3L664.3 129.3L664.8 131.0M660.0 281.5L657.9 284.8L655.1 285.7L655.8 287.5L653.7 289.6L652.5 289.4L652.2 291.6L649.1 292.7L648.6 294.1L643.4 295.5L643.2 297.5L641.2 297.7L641.3 298.7L638.9 300.1L638.3 299.2L636.2 303.4L634.1 304.1L636.2 307.5L635.8 309.6L638.1 313.8L637.8 315.0L639.5 315.4L639.9 317.5L642.8 317.9L641.8 320.2L644.6 322.2L644.6 328.4L646.7 328.9L646.8 331.7L649.5 332.2L652.9 334.7L653.5 333.0L655.2 333.0L656.1 330.8L659.4 330.6L660.2 329.6L662.2 332.4L664.2 332.8M666.5 281.2L660.0 281.5M661.2 343.4L662.4 347.0L665.3 347.3L665.5 345.3L669.5 347.2L670.0 350.4L672.1 352.4L676.2 352.1L680.3 353.6L683.1 359.5L680.3 360.7L678.7 363.3L676.8 363.1L676.5 364.8L679.7 372.3L682.9 371.0M664.2 332.8L664.2 336.0L661.8 338.5L661.2 343.4M663.6 187.8L664.2 188.6L663.3 189.8L665.0 193.6M670.8 182.6L665.6 184.3L663.6 187.8M683.9 312.1L683.8 313.3L679.7 315.0L679.2 317.3L678.3 316.6L676.4 317.3L676.5 319.0L675.2 319.4L674.6 321.3L672.6 321.4L673.1 322.5L671.3 323.6L672.2 325.1L671.9 329.9L666.5 331.4L665.9 333.0L664.2 332.8M695.5 146.8L689.9 144.5L691.2 139.8L686.0 136.9L684.9 134.8L682.5 136.0L682.7 133.8L680.7 131.0L679.5 131.7L677.7 130.5L676.2 132.5L671.9 132.9L669.2 130.7L668.0 131.9L664.8 131.0M664.8 131.0L667.3 126.5L665.2 124.1L666.0 122.9L667.4 123.4L668.0 121.8L665.0 114.1L667.2 112.7L669.6 113.3L670.7 111.6L672.0 111.5L672.2 109.4L675.1 109.1L675.0 108.1L678.6 108.0L680.5 105.0L684.1 106.1L683.0 106.6L683.2 108.9L685.5 107.9L688.4 109.6M664.9 257.8L666.0 258.7L667.0 264.9L666.5 268.7L668.6 271.3L667.7 271.9L668.3 273.6L666.9 274.7L666.9 276.4L669.1 278.2L666.5 281.2M694.1 262.1L691.3 262.9L690.8 264.3L688.7 263.8L687.5 264.6L688.1 263.2L685.4 264.0L685.7 262.1L684.1 260.8L679.7 262.8L678.5 262.0L678.3 259.8L675.9 258.6L669.1 259.0L666.6 257.0L664.9 257.8M665.0 193.6L668.4 195.1L667.6 196.9L665.7 197.4L667.1 201.1L674.9 204.0L681.3 211.0L683.1 210.1L692.7 213.5L690.7 216.1L699.8 217.9L701.9 220.8L701.6 221.9L706.3 225.4M715.0 203.5L712.9 201.2L708.4 202.0L707.9 200.7L703.7 203.6L701.9 202.3L696.2 204.0L692.3 199.8L685.5 198.1L685.9 195.4L680.7 195.5L679.6 198.6L671.4 193.2L667.4 192.4L665.0 193.6M665.7 468.0L663.3 465.1L656.3 462.3L654.4 456.3L651.7 453.2L651.5 450.3L652.8 441.0L654.3 441.1L655.7 439.1L658.1 441.7L661.6 439.3L663.1 440.3L664.1 438.7L667.1 440.0L666.4 436.4L667.3 434.2L665.1 431.9L670.0 432.8L671.4 429.8L672.6 423.1L671.5 422.9L670.6 416.8L672.3 411.8L670.0 408.0L672.0 403.2L675.0 401.2L673.4 399.9L668.0 400.3L667.8 398.2L669.7 396.7L668.4 396.7L668.2 393.9L666.6 393.1L667.6 391.9M719.3 376.6L720.8 378.6L720.3 379.5L721.5 379.4L723.1 381.1L722.5 383.0L720.7 382.0L720.5 383.5L718.3 385.0L718.5 387.9L719.5 388.2L718.0 388.4L717.3 390.2L718.2 391.6L715.3 394.0L717.1 393.9L716.6 395.0L718.2 396.1L717.0 396.1L717.2 398.4L716.0 398.6L715.1 400.6L714.2 399.7L713.6 401.4L715.5 402.6L713.8 402.2L715.7 404.6L713.8 404.8L715.3 406.5L714.9 409.1L716.7 416.4L716.3 424.3L717.4 426.0L716.2 426.3L716.9 428.8L715.4 429.9L715.9 431.4L714.9 431.3L716.1 432.0L715.7 434.4L713.9 434.4L714.1 436.2L711.0 437.2L711.3 438.3L707.8 441.1L709.3 446.3L709.2 447.2L708.1 447.1L709.9 449.1L710.2 448.3L710.5 449.4L711.7 449.3L710.6 449.9L710.8 451.5L708.4 450.4L709.5 452.4L708.0 452.8L709.0 455.8L707.4 456.3L709.6 459.0L713.5 460.6L717.0 465.8L715.2 466.5L713.1 464.6L712.7 466.8L711.3 467.7L703.8 468.1L699.5 472.6L697.0 477.1L693.0 471.8L692.1 472.4L688.2 470.9L688.5 469.9L687.0 468.5L679.0 465.7L676.1 463.1L673.2 467.3L672.2 471.4L669.2 466.3L665.9 465.7L665.7 468.0M670.8 283.6L669.7 281.7L667.0 282.3L666.5 281.2M699.1 387.2L694.5 389.6L691.1 393.8L687.9 394.8L685.0 398.5L677.2 402.1L675.0 401.2L677.5 397.9L678.4 398.7L678.1 397.5L679.3 397.3L682.3 389.1L680.8 388.6L676.7 390.1L675.1 389.2L672.8 391.3L671.0 390.6L668.9 392.1L667.6 391.9M668.1 160.3L669.7 160.1L670.4 163.0L668.8 170.4L667.5 172.2L668.2 176.0L667.0 176.6L666.8 179.6L670.8 182.6M670.8 182.6L685.4 177.2L686.1 178.8L685.3 180.5L694.3 182.7L697.6 181.8L697.8 179.5L701.2 179.4L700.8 181.3L706.8 178.7L708.0 180.1M670.8 283.6L671.0 288.3L673.5 289.4L674.8 292.7L675.0 295.4L673.9 296.3L675.4 295.9L675.5 298.8L676.6 298.3L676.2 300.9L677.8 303.2L682.3 303.6L682.1 305.5L680.3 307.0L682.7 309.0L682.7 311.1L683.9 312.1M693.8 280.0L690.7 277.2L684.8 278.9L682.3 276.4L677.6 279.1L676.7 278.0L673.6 277.5L670.8 283.6M682.9 371.0L683.7 379.8L685.3 383.3L690.4 384.3L690.4 385.5L694.5 385.2L697.5 382.6L700.4 384.6L697.6 386.4L699.1 387.2M682.9 371.0L685.0 368.1L687.9 369.8L687.3 369.3L691.6 363.5M683.9 312.1L685.2 311.9L686.7 312.2L688.1 316.0L692.3 315.5L693.9 320.8M688.4 109.6L689.1 111.4L687.8 113.2L688.0 116.2L690.8 116.6L691.2 120.0L694.9 125.8M688.4 109.6L691.6 108.8L691.0 107.4L693.1 104.4L697.3 104.1L696.2 98.3L704.0 97.8L709.7 101.1L717.8 102.4L722.5 100.6L731.4 100.8L736.4 97.2M691.6 363.5L694.1 364.7L695.8 364.3L696.2 362.6L698.0 363.0L698.0 364.8L699.8 364.1L701.1 365.8L700.9 369.8L702.1 370.1L704.6 368.6L705.6 370.0L707.5 369.6L707.8 371.0L708.3 370.2L708.3 371.6L709.5 370.3L710.6 370.9L709.2 371.6L710.5 373.4L716.4 375.2L717.7 374.6L719.3 376.6M693.9 320.8L694.5 322.4L693.1 324.7L687.5 327.0L684.2 331.2L687.6 334.8L682.2 337.6L687.5 343.4L684.8 352.3L686.5 354.8L687.7 354.5L688.1 357.9L691.0 357.6L689.1 361.1L691.6 363.5M693.8 280.0L695.2 280.2L697.0 279.2L699.9 274.7L700.1 272.5L697.7 271.5L698.6 270.5L697.6 264.7L695.1 261.9L694.1 262.1M704.7 282.6L699.5 283.1L698.1 281.9L694.0 283.0L693.6 281.9L694.8 280.7L693.8 280.0M705.3 303.0L702.0 306.2L697.0 307.6L695.3 311.5L697.4 312.7L697.8 318.4L696.5 320.4L693.9 320.8M703.3 251.6L694.2 250.4L693.4 257.6L694.2 258.4L692.9 258.5L694.1 262.1M694.9 125.8L696.6 134.0L700.3 142.6L695.1 143.5L695.5 146.8M694.9 125.8L697.8 124.4L698.8 125.9L700.9 126.4L704.3 124.7L704.3 123.1L703.1 122.3L703.0 118.5L703.9 117.8L703.1 116.8L707.8 115.8L707.1 111.6L710.6 111.1L710.7 112.8L714.0 115.4L716.6 112.9L717.0 110.9L722.4 114.3L721.7 117.6L723.6 117.7L723.5 120.0L724.1 119.3L726.1 120.3L727.0 121.8L726.4 123.4L728.9 125.0L732.2 128.8L732.1 129.2M695.5 146.8L696.1 146.9L697.3 146.4L698.5 146.8L701.1 145.5L702.0 146.5L704.0 145.3L707.0 146.3L707.6 148.6L706.1 152.3L709.6 153.3L712.2 156.2L714.5 156.0L719.0 160.6L722.9 156.8L725.3 157.1L727.0 155.7M719.3 376.6L719.8 378.0L719.0 377.7L718.1 379.1L714.3 378.1L710.4 381.4L706.8 379.8L702.9 380.9L700.5 385.8L700.8 387.0L699.5 387.3L699.1 387.2M703.3 251.6L707.2 253.1L710.1 251.3L714.7 250.6L717.2 254.1L717.2 255.8L714.7 256.9L715.8 257.6L715.7 266.0L714.6 266.5L714.3 271.8L709.1 280.4L704.7 282.6M704.2 242.2L702.8 243.0L702.4 246.0L703.3 251.6M745.5 246.8L739.9 247.1L739.5 244.6L733.4 244.1L733.4 242.8L725.3 243.9L718.5 242.6L715.1 243.6L706.2 243.1L704.2 242.2M706.3 225.4L701.7 227.8L702.4 228.7L708.0 228.5L707.7 230.9L705.5 229.4L703.4 230.6L707.6 233.3L705.0 238.3L703.5 236.3L702.7 237.0L703.3 237.8L701.9 240.1L704.2 242.2M722.1 285.4L719.1 284.1L716.5 285.6L712.7 285.2L710.4 286.6L709.6 285.1L711.1 282.6L707.1 283.4L704.7 282.6M739.8 288.9L742.9 296.0L742.3 298.1L740.6 298.7L740.8 302.4L738.3 307.3L733.0 310.6L728.4 311.0L727.8 309.2L729.0 306.2L726.3 305.3L723.5 305.7L721.7 307.6L720.5 306.3L721.2 304.7L713.3 305.0L705.3 303.0M705.3 303.0L705.5 298.0L708.4 298.1L709.5 296.2L710.9 297.5L710.4 292.4L712.2 289.4L713.7 288.3L715.0 289.0L718.0 288.1L722.1 285.4M706.3 225.4L716.9 219.5L720.2 216.5M708.0 180.1L711.4 179.1M708.0 180.1L706.3 180.8L710.2 185.2L710.9 188.2L707.8 188.3L706.0 189.9L710.5 195.0L715.0 203.3M711.6 179.0L711.4 179.1M711.4 179.1L711.6 179.0L711.6 179.0M711.6 179.0L711.9 178.9L712.9 181.7L713.0 182.8L717.8 184.1L718.5 186.0L720.1 186.4M715.0 203.5L717.9 207.9L714.9 209.1L716.3 210.0L718.3 215.0L719.8 214.1L720.2 216.5M715.0 203.3L715.0 203.5M720.1 186.4L718.8 190.1L715.9 189.1L721.6 197.0L719.7 198.4L719.7 198.9L717.3 200.7L716.5 202.0L715.6 202.9L715.1 203.3L715.0 203.3M720.1 186.4L719.7 184.9L720.4 184.9M720.2 216.5L722.8 214.1L726.6 215.2L727.4 217.2L727.9 215.6L732.0 216.9L735.5 212.2L739.7 214.9M720.4 184.9L722.2 186.2L722.6 190.6L726.3 190.9L727.5 193.2L731.2 194.8L734.1 199.3M726.4 166.0L722.6 170.6L721.5 173.7L719.1 173.2L718.2 174.6L715.4 174.4L717.1 182.4L720.4 184.9M728.3 286.1L724.4 287.9L723.4 285.5L722.2 285.4L722.1 285.4M726.4 166.0L727.3 167.9L730.6 167.1L733.3 164.6L736.9 167.9L736.7 171.8L742.4 174.5L745.2 177.4L746.5 180.9L744.1 180.8L742.3 182.4L742.0 185.1L744.4 185.4L744.7 187.3M727.0 155.7L729.2 159.5L732.8 159.8L732.0 162.5L729.5 163.2L728.6 164.9L726.8 164.9L726.4 166.0M729.2 151.4L726.8 153.1L727.0 155.7M728.3 286.1L728.8 288.7L731.2 291.1L739.8 288.9M739.3 262.1L737.4 263.6L736.7 269.9L735.1 272.3L733.1 272.1L728.4 274.7L727.2 278.7L728.5 281.0L727.2 283.6L728.3 286.1M751.8 137.1L745.7 140.7L747.4 142.6L747.2 144.5L739.8 148.1L739.6 149.6L737.1 149.6L734.7 152.0L733.3 151.8L733.7 152.6L729.2 151.4M732.1 129.2L730.4 129.0L729.6 130.0L729.7 133.4L726.5 141.8L726.5 146.6L729.2 151.4M740.6 123.3L737.8 122.8L735.8 124.6L732.1 122.3L733.4 124.5L732.0 125.0L734.0 126.9L734.1 128.8L732.7 129.6L732.1 129.2M734.1 199.3L738.0 199.2L741.4 197.3L742.5 199.4L741.8 201.9L746.1 204.4M744.7 187.3L742.3 187.7L744.4 189.1L744.4 191.0L741.5 191.3L740.2 193.5L736.0 195.4L734.1 199.3M736.4 97.2L740.4 101.9L742.2 101.3M736.4 97.2L740.5 93.9L749.0 91.1L759.6 90.8L773.6 95.9L782.6 103.9L787.6 105.4M747.4 267.4L743.8 264.6L742.2 265.6L742.3 264.3L739.3 262.1M745.5 246.8L745.4 251.4L744.3 253.5L742.1 254.3L741.0 257.1L741.7 259.0L739.3 262.1M746.1 204.4L739.4 208.0L740.7 209.3L739.4 211.4L742.3 213.9L739.7 214.9M739.7 214.9L739.2 217.2L741.4 217.3L741.4 220.1L743.6 220.6L743.8 225.1L745.4 224.6L747.1 225.9L746.8 228.7L748.6 230.2M762.0 281.8L762.4 283.8L761.1 285.2L754.1 286.0L751.1 287.6L745.6 287.7L742.6 288.8L741.2 288.6L740.2 288.9L739.8 288.9M751.8 137.1L745.2 134.6L747.4 132.8L746.0 130.8L744.6 123.0L741.2 124.0L740.6 123.3M742.2 101.3L740.5 104.4L742.1 108.5L739.5 112.3L741.6 113.6L737.0 116.2L740.6 123.3M767.4 115.3L762.8 114.2L760.5 116.3L759.6 113.2L758.3 114.4L757.3 113.3L755.9 113.8L755.3 112.6L753.3 113.1L751.1 109.3L748.0 109.2L746.0 107.0L748.1 105.1L745.0 100.2L742.2 101.3M744.7 187.3L746.3 188.1M748.6 230.2L745.8 234.1L745.5 246.8M760.4 234.7L760.0 233.5L761.9 232.4L760.3 229.6L757.8 231.3L755.6 228.3L757.7 227.4L755.2 226.0L755.3 225.0L757.6 223.9L757.0 221.9L754.9 222.2L755.1 220.2L753.6 219.4L755.3 218.4L754.2 215.1L747.5 205.3L746.3 204.2L746.1 204.4M782.1 193.9L781.5 192.7L778.9 194.4L778.1 196.5L774.3 197.5L774.4 199.0L770.6 201.6L770.9 203.9L766.5 205.8L766.6 207.4L759.3 203.9L757.5 202.2L758.1 201.1L754.9 198.9L756.0 196.6L753.6 193.0L751.2 193.0L747.8 191.1L746.5 189.6L747.3 188.1L746.3 188.1M746.3 188.1L751.1 184.2L752.2 184.8L753.6 182.8L755.0 183.5L755.1 182.7M762.0 281.8L759.7 278.1L757.1 278.8L753.6 277.3L754.5 275.7L753.3 275.5L750.4 270.0L748.9 270.5L747.6 269.5L747.4 267.4M747.4 267.4L749.0 258.9L748.8 257.0L746.8 256.3L746.7 254.8L749.9 254.5L751.0 250.0L754.0 251.8L756.2 248.8L757.2 249.6L759.4 247.9L760.2 249.1L763.8 247.7L765.1 250.8L769.4 251.0L773.4 254.5L772.8 256.9L774.4 259.2L772.0 260.8L772.1 264.4L774.9 269.1L774.4 273.1L775.7 275.6M760.4 234.7L757.9 234.7L758.7 235.8L757.1 235.7L757.7 234.4L756.5 234.2L754.1 236.0L748.6 230.2M756.3 137.9L755.6 139.6L752.4 139.8L753.0 138.1L751.8 137.1M755.1 182.7L757.0 183.2L759.6 185.9L761.3 185.0L763.7 185.5L764.0 182.7L765.3 182.0L766.7 182.6L765.4 183.5L767.5 182.8L767.6 184.3L768.5 183.4L772.1 184.6L776.9 182.7M755.1 182.7L755.5 179.6L757.5 177.1L757.4 174.5L758.8 173.4L758.3 171.1L759.6 170.1M761.3 142.6L760.0 138.2L756.4 138.7L756.3 137.9M765.9 123.6L760.8 122.9L761.4 124.4L759.9 126.3L760.7 129.8L756.3 134.1L757.0 135.0L756.0 135.4L756.3 137.9M759.6 170.1L755.9 166.7L753.6 166.4L753.5 165.1L759.8 160.9L758.5 157.6L759.6 154.6L757.0 155.2L757.6 153.4L756.0 151.5L756.3 149.2L758.3 147.9L757.0 145.1L761.3 142.6M776.7 170.6L775.3 171.4L775.5 170.0L773.8 169.7L774.2 168.3L772.1 168.0L772.3 166.9L771.2 166.4L770.3 166.8L770.1 164.0L765.6 163.1L765.3 165.5L761.1 170.9L760.5 170.9L760.4 170.6L759.9 170.1L759.8 170.1L759.6 170.1L759.6 170.1M769.8 230.1L767.4 228.1L767.9 229.6L764.0 231.0L765.0 232.5L763.4 232.4L760.4 234.7M777.2 144.4L774.6 147.2L772.8 146.8L771.7 149.2L771.3 147.9L769.1 148.4L768.1 147.6L768.9 150.7L767.1 151.0L763.5 143.3L761.3 142.6M775.7 275.6L772.9 276.7L772.2 275.8L771.1 278.1L764.1 280.0L762.0 281.8M765.9 123.6L767.7 119.3L767.4 115.3M777.2 144.4L773.7 139.5L773.8 136.1L771.9 133.5L772.8 132.2L776.5 131.6L776.4 130.1L778.6 129.6L780.4 126.0L778.0 126.3L775.8 125.2L773.3 126.9L770.6 124.9L768.2 125.1L767.5 123.8L766.5 123.5L765.9 123.6M787.6 105.4L787.5 106.8L784.6 107.8L784.8 108.8L781.6 109.1L780.5 114.2L777.5 114.6L776.4 116.1L770.3 115.8L769.0 117.3L767.4 115.3M788.6 244.8L785.8 243.6L784.3 241.6L779.3 242.1L779.4 234.9L773.5 234.2L769.8 230.1M783.2 219.3L781.4 219.9L781.2 223.5L778.0 224.2L775.7 226.2L773.2 224.9L774.1 226.1L772.0 226.5L769.8 230.1M793.1 267.9L790.9 272.1L786.1 273.6L784.4 275.3L776.9 277.4L775.7 275.6M776.9 182.7L777.2 179.4L779.3 179.3L776.7 170.6M776.9 168.8L776.7 170.6M782.6 189.7L780.0 188.6L779.9 187.3L778.7 187.6L776.9 182.7M783.5 147.4L782.2 150.0L778.5 150.0L773.8 154.7L771.4 155.1L772.2 160.7L771.3 161.5L773.0 162.4L774.9 168.8L776.9 168.8M776.9 168.8L777.0 167.1L780.3 167.0L783.0 169.2L782.7 171.7L786.2 172.3L786.2 170.9L788.2 170.7L788.3 169.0L791.5 169.1L792.1 167.0L794.6 165.5M783.5 147.4L781.8 145.7L777.2 144.4M782.6 189.7L783.3 192.7L782.8 193.9L782.5 193.8L782.3 193.9L782.1 193.9M782.1 193.9L781.2 198.1L782.2 201.8L781.3 202.5L782.7 205.5L784.1 206.0M800.8 175.1L799.4 174.4L793.6 176.0L791.0 179.5L783.7 182.2L782.6 184.5L782.6 189.7M793.0 220.6L783.2 219.3M784.1 206.0L784.3 208.1L781.9 211.7L783.0 212.2L781.6 218.7L783.2 219.3M792.2 148.8L789.9 147.7L786.0 148.3L783.5 147.4M784.1 206.0L785.3 205.5L786.9 206.3L789.0 210.4L791.3 210.5L792.4 206.9L799.7 199.8L800.3 195.9L799.0 192.8L802.3 193.1L804.4 189.0M787.6 105.4L787.6 105.4L789.2 105.5L794.5 106.3L798.7 107.8L802.5 114.6L809.4 117.6M793.1 267.9L791.8 266.3L792.8 265.2L791.3 262.8L792.0 261.0L788.7 257.0L790.3 256.1L789.7 254.4L790.7 252.1L786.9 249.8L788.9 246.4L788.6 244.8M798.9 241.0L795.7 243.2L788.6 244.8M792.2 148.8L792.0 153.7L789.3 157.6L790.1 161.1L792.9 162.6L794.6 165.5M802.7 145.2L800.4 145.9L799.5 147.7L794.7 147.4L792.2 148.8M793.0 220.6L792.4 222.9L793.6 222.9L794.0 225.4L792.6 229.7L795.8 229.8L798.9 241.0M805.7 213.9L801.8 211.2L797.7 215.7L795.7 215.3L793.9 220.6L793.3 220.6L793.0 220.6M811.7 255.2L809.5 257.2L809.7 259.5L806.7 261.7L807.9 264.6L805.7 267.0L801.9 267.7L798.4 264.6L798.0 266.5L796.6 267.1L794.6 265.6L793.1 267.9M794.6 165.5L800.8 175.1M811.0 103.4L807.8 99.2L808.0 94.5L805.5 94.9L803.4 92.4L800.3 92.4L800.2 89.8L797.1 86.4L794.5 77.4L796.0 75.0L795.7 67.7M795.7 67.7L797.0 59.7L796.5 55.5L798.1 52.8L794.9 48.0L794.3 45.3L795.9 42.9L797.4 41.8L800.8 43.7L802.5 41.5L806.5 39.2L808.5 41.6L808.1 42.8L811.1 39.3L813.6 40.7L814.6 39.3L815.7 40.1M795.7 67.7L798.4 67.6L801.3 68.1L801.1 70.3L805.1 75.8L809.5 74.4L814.6 75.1L815.8 76.3M798.9 241.0L802.4 237.4L807.3 235.3L807.6 236.1M800.8 175.1L801.1 177.7L804.5 179.7M821.7 145.3L819.4 149.4L817.3 149.4L818.1 147.9L817.3 141.4L815.1 138.8L813.4 140.1L812.6 137.7L811.5 142.4L809.3 142.4L807.0 148.3L805.1 148.0L805.4 146.0L802.7 145.2M809.4 117.6L804.6 120.8L802.8 125.8L799.3 126.9L798.7 128.5L798.5 135.3L804.6 137.5L804.5 140.4L801.5 144.1L802.9 144.4L802.7 145.2M803.7 180.8L802.3 181.9L804.4 183.4L805.0 186.3L803.7 188.4L804.4 189.0M804.5 179.7L803.7 180.8M803.7 180.8L804.1 180.8L805.1 181.1L806.3 181.1L807.5 182.1L812.7 181.2L819.3 185.4L821.1 184.3L829.3 185.3L832.6 184.4L835.2 188.9M804.4 189.0L810.5 195.9L811.2 198.3L809.4 200.4L810.6 200.3L810.4 202.9M820.9 167.6L816.7 167.5L810.0 164.2L809.5 168.5L808.6 168.3L805.6 171.8L807.3 172.4L804.5 179.7M805.7 213.9L807.2 215.7L813.3 215.2L813.6 221.9L812.0 223.2L816.2 227.3L818.3 227.8L817.3 228.5L818.1 230.6M810.4 202.9L809.6 208.3L806.3 210.5L805.7 213.9M807.6 236.1L807.8 239.6L806.6 239.9L807.4 241.7L805.8 242.8L806.5 244.7L805.7 245.7L808.0 247.6L809.4 247.0L810.1 249.8L809.4 253.4L810.0 255.1L811.7 255.2M817.5 232.1L813.3 231.1L807.6 236.1M809.4 117.6L810.7 118.3M835.2 188.9L834.6 191.3L831.8 192.5L834.3 193.8L833.3 196.2L834.6 194.7L834.8 195.9L835.8 195.9L836.0 196.8L833.8 198.9L835.2 201.0L832.3 202.3L829.0 206.0L825.0 205.7L823.5 203.4L824.6 201.9L823.4 201.4L821.1 209.5L817.7 208.1L813.9 203.0L812.6 203.6L811.0 202.7L810.4 202.9M810.7 118.3L810.2 120.8L822.4 129.0L829.4 135.6M810.7 118.3L811.9 105.6L811.0 103.4M816.9 99.0L814.1 103.2L812.3 102.5L812.1 103.3L811.2 103.3L811.0 103.4L811.0 103.4M817.5 232.1L815.9 235.5L822.6 242.7L824.2 250.9L821.7 253.5L819.4 252.7L817.0 255.6L813.9 254.6L811.7 255.2M815.7 40.1L815.9 44.6L814.6 48.9L815.8 51.1M815.7 40.1L817.8 36.9L817.8 35.3L819.4 33.9L821.7 34.0L825.4 28.9L827.7 30.5L831.0 26.8L832.7 27.7L832.7 29.2L835.0 29.4L835.6 32.0L838.0 32.3M815.8 51.1L819.9 52.0L826.3 43.3L827.5 45.1L830.9 44.7L832.3 45.8L836.8 44.2M818.0 73.3L813.8 71.7L815.4 64.7L814.5 60.1L815.6 59.4L815.0 57.6L815.9 55.9L815.3 54.4L813.8 54.3L815.8 51.1M816.9 99.0L812.3 90.4L816.4 87.9L817.0 86.1L816.0 85.0L817.0 83.1L816.5 81.8L817.6 81.0L815.8 76.3M815.8 76.3L818.0 73.3M831.0 104.0L826.8 103.3L823.2 99.0L820.8 99.9L816.9 99.0M818.1 230.6L817.9 231.6L817.6 232.2L817.5 232.1M839.6 45.2L837.7 53.1L839.1 56.5L836.7 62.7L837.0 64.9L835.3 65.9L832.3 64.9L833.0 71.2L832.0 73.8L827.4 74.3L827.2 72.7L819.2 70.3L818.0 73.3M862.9 234.0L857.0 236.8L857.3 233.1L853.0 233.5L852.5 231.4L847.0 226.5L844.1 225.3L841.1 225.6L827.1 232.6L818.1 230.6M821.7 145.3L821.8 145.2L821.9 145.3L823.2 147.7L823.9 148.4L823.9 148.9L824.2 149.1L824.0 153.2L826.4 155.3L825.5 158.0L821.1 157.7L820.2 161.2L820.9 167.6M849.9 157.5L850.4 158.4L849.5 159.6L848.5 159.1L848.3 160.6L851.6 161.8L849.7 163.0L849.1 168.7L847.6 171.4L845.2 170.7L844.3 172.0L842.6 171.8L841.8 173.6L837.0 171.0L832.5 172.4L828.7 170.5L828.7 168.4L826.3 166.1L826.5 166.8L820.9 167.6M831.9 138.7L826.6 139.2L821.7 145.3M829.4 135.6L831.9 138.7M829.4 135.6L837.3 121.5L835.1 119.7L833.2 120.9L832.4 118.6L830.6 117.6L830.8 114.3L828.3 109.3L830.4 108.2L831.0 104.0M831.0 104.0L837.1 105.3L837.9 103.2L841.7 103.4L844.2 105.8L847.1 99.4L851.3 102.0L851.4 100.7M831.9 138.7L831.0 139.9L833.1 141.4L837.6 140.6M872.0 188.5L865.9 189.8L863.6 191.9L864.4 195.6L862.3 196.5L861.0 193.9L859.1 192.7L856.9 192.9L858.1 195.2L857.3 196.2L859.1 198.9L856.4 197.8L856.3 195.6L854.6 196.5L852.3 194.0L854.2 190.0L852.7 188.6L849.7 189.8L847.4 184.3L845.3 187.3L843.0 186.5L843.0 189.2L841.4 191.4L835.2 188.9M836.8 44.2L835.2 42.8L836.7 40.8L835.2 39.3L836.1 38.2L838.4 38.7L838.0 32.3M836.8 44.2L837.1 44.2L837.4 44.2L838.9 45.2L839.6 45.2M837.6 140.6L837.5 143.4L840.2 144.7L837.9 145.5L841.8 148.8L843.6 147.6L843.6 149.2L845.4 148.8L844.3 150.5L845.8 150.5L845.0 152.1L846.1 152.6L842.9 157.1L846.8 155.8L849.9 157.5M837.6 140.6L838.5 140.5L842.6 141.2M838.0 32.3L842.6 32.3L844.3 33.3L846.9 30.5L849.9 31.7M839.6 45.2L841.0 45.2L843.2 45.4L847.3 49.3L848.1 50.7L846.0 53.2L847.1 54.6L849.7 55.2L853.0 59.8L854.0 60.6L855.4 59.4L858.6 60.1L861.6 66.9L857.2 69.6L853.5 75.5L856.6 76.6L857.9 75.7L857.1 77.6L860.0 77.9L860.9 80.3M842.6 141.2L843.5 142.6L846.4 143.0L856.8 148.5L859.1 151.0M842.6 141.2L842.9 141.1L845.3 142.0L850.6 136.3L852.7 136.3L853.9 129.3L858.0 131.4L859.4 128.7L858.2 126.5L859.4 127.3L860.4 125.7L862.0 126.6L862.7 122.9L864.6 125.0L865.7 122.4L869.6 119.2M849.9 31.7L854.8 34.7L856.4 34.4L859.0 37.8L864.8 41.2L867.2 44.2L874.0 46.0L874.0 50.2L875.7 49.6L878.5 55.9L876.3 62.1L874.9 63.1L875.7 64.7L874.6 65.9M849.9 31.7L852.8 28.0L858.1 26.4L861.7 26.7L864.9 25.5L866.8 23.1L876.2 25.0L883.8 24.5L885.7 27.2M859.1 151.0L857.6 154.0L856.7 153.6L857.2 156.7L856.3 155.7L854.8 156.1L854.8 153.9L853.6 153.1L852.5 156.7L851.0 156.4L849.9 157.5M860.9 80.3L859.1 81.4L857.3 87.4L858.5 88.0L856.4 90.9L855.2 90.0L854.8 90.8L852.5 87.9L851.0 90.4L849.8 90.2L849.7 97.6L851.4 100.7M851.4 100.7L853.2 102.3L853.7 105.8L855.9 107.8L854.1 113.3L856.9 114.1L859.1 112.9L858.6 115.1L859.7 116.5L865.6 119.2L869.6 119.2M870.4 161.2L859.1 151.0M874.6 65.9L870.7 69.3L869.9 73.4L866.5 74.4L867.3 76.9L864.4 82.3L860.9 80.3M880.8 213.0L879.2 214.1L878.1 217.0L876.5 216.9L876.4 218.7L874.6 217.7L873.0 218.1L871.6 213.1L869.3 212.6L869.0 209.3L865.7 212.6L866.1 215.6L865.7 214.5L862.3 215.7L862.6 218.6L866.7 222.4L863.2 226.2L865.6 226.8L865.5 228.9L866.4 229.2L865.5 231.4L862.9 231.6L862.9 234.0M880.8 213.0L882.3 217.4L881.4 220.3L884.4 220.5L887.0 223.3L888.7 223.4L892.0 227.8L890.3 236.0L881.6 236.1L879.8 237.0L874.5 235.5L871.7 236.1L870.5 233.0L869.1 232.3L867.7 232.8L866.1 236.3L864.8 233.5L862.9 234.0M869.6 119.2L871.8 119.2L878.1 122.4L880.4 114.9L884.6 120.9L886.3 121.0M870.4 161.2L879.2 167.5M876.3 154.6L875.4 155.6L875.9 156.8L872.1 159.7L872.6 160.5L870.4 161.2M872.0 188.5L871.6 190.8L874.9 192.1L876.9 195.9L877.2 200.9L879.2 204.8L878.9 208.5L880.8 213.0M874.9 184.0L871.8 184.9L872.0 188.5M890.6 64.9L885.5 67.5L881.4 68.1L874.6 65.9M892.9 173.4L893.2 175.3L892.0 175.2L891.2 178.0L889.4 178.8L887.4 178.4L887.6 177.7L887.1 178.5L886.2 177.1L881.5 178.0L880.6 176.5L880.3 177.5L878.9 177.6L879.2 182.0L875.7 183.8L875.9 184.8L874.9 184.0M879.2 167.5L877.7 170.6L872.1 174.3L872.9 175.7L872.3 176.5L873.5 177.2L870.4 179.0L871.6 180.2L872.0 178.5L875.6 178.2L874.9 184.0M886.1 143.3L887.8 144.9L886.0 145.3L882.8 152.1L879.7 151.0L878.1 154.6L876.3 154.6M886.1 143.3L883.4 142.2L882.5 143.4L878.6 140.6L874.8 145.8L873.9 149.7L875.5 150.9L876.3 154.6M879.2 167.5L880.6 170.4L882.2 169.3L889.1 173.7L892.9 173.4M885.7 27.2L886.9 30.1L889.0 30.1L889.0 31.4L891.9 31.4L895.2 36.3L898.4 35.3L898.1 37.0L900.5 37.8L901.5 41.5L901.5 42.6L899.8 42.7L899.6 46.0L898.6 46.1L898.6 53.7L892.1 55.2L890.7 56.5M890.7 56.5L885.9 55.6L885.8 52.8L888.5 50.4L888.5 48.9L889.4 49.0L890.0 44.9L889.2 41.5L887.3 41.3L885.6 38.2L887.8 36.9L883.8 30.6L885.7 27.2M886.9 141.5L886.1 143.3M886.3 121.0L890.6 122.6M886.3 121.0L885.4 123.4L882.8 124.0L882.5 126.0L877.2 128.4L880.3 130.9L878.0 130.6L879.5 133.0L889.0 135.0L886.9 141.5M895.5 147.2L894.6 148.5L893.5 147.8L890.0 144.1L888.0 143.6L888.2 142.1L886.9 141.5M890.6 122.6L897.6 129.6L898.4 133.3L903.8 135.7M890.6 122.6L889.0 118.8L890.9 119.4L891.7 117.6L894.0 106.7L895.1 107.1L895.2 105.6L897.0 105.3L899.0 102.5L900.1 104.8L903.3 105.6M890.6 64.9L892.1 65.2L895.9 64.9L892.7 75.1L896.8 77.4L897.5 79.6L901.1 82.7L902.2 86.0L901.3 87.7L903.2 87.5L904.3 92.0L908.4 88.5L911.0 91.4L910.9 93.3L907.7 96.2M890.7 56.5L890.6 64.9M899.7 165.5L902.1 166.8L900.8 169.0L901.0 171.1L899.5 172.2L898.6 171.0L895.9 171.4L892.9 173.4M899.7 165.5L899.0 164.1L896.0 165.7L894.4 163.1L892.3 163.1L893.5 160.2L895.0 159.5M895.0 159.5L897.9 156.8L895.1 153.9L896.3 152.6L895.6 152.3L896.4 148.6L895.5 147.2M909.0 140.6L911.3 144.1L918.1 150.1L918.1 152.0L913.7 151.3L913.2 152.8L910.0 153.5L909.9 155.0L906.0 158.1L901.0 159.5L900.9 160.9L898.7 160.0L898.1 160.6L896.6 159.6L895.9 159.9L895.2 159.5L895.0 159.5M909.0 140.6L907.4 144.0L904.5 141.8L898.6 139.7L897.9 142.0L896.3 142.3L897.2 143.6L895.5 147.2M914.7 124.4L915.1 126.3L917.4 126.1L921.3 128.8L925.0 134.9L931.1 135.7L933.2 140.1L936.0 141.7L938.2 146.4L939.6 145.6L942.6 149.4L942.5 154.8L944.7 154.9L945.5 156.2L950.1 154.9L953.2 160.2L953.0 167.3L956.1 167.8L957.5 169.3L957.0 172.0L955.1 174.4L955.6 176.1L957.8 176.5L956.9 179.5L955.3 179.0L955.0 180.5L963.8 185.9L968.7 187.7L972.2 191.8L976.9 192.7L970.5 194.7L967.4 193.9L966.4 192.1L959.6 193.0L958.4 190.7L955.5 191.8L952.9 191.0L953.3 186.4L950.4 186.2L950.7 184.9L946.0 184.0L943.8 181.8L944.6 179.4L942.3 179.2L941.6 177.6L939.2 178.3L939.2 175.5L937.8 176.1L938.1 177.7L936.9 177.1L937.3 174.0L936.0 176.2L933.5 175.5L930.4 176.8L929.5 174.9L930.4 172.3L929.2 171.0L927.7 171.6L926.8 169.3L925.6 169.5L925.2 171.4L920.9 168.9L922.0 170.5L920.6 172.0L918.8 169.7L919.1 166.6L915.3 168.2L914.4 168.1L913.7 165.5L910.3 165.5L909.2 163.7L912.3 162.9L912.4 161.1L908.6 160.2L908.4 163.4L905.9 164.5L904.2 162.7L903.9 164.1L906.0 165.4L906.1 167.2L905.0 167.2L904.5 165.0L902.0 165.7L899.7 165.5M903.3 105.6L903.4 109.0L905.9 109.4L909.0 113.3L912.2 114.5L915.4 114.3M903.3 105.6L904.8 100.4L906.7 99.2L907.7 96.2M903.8 135.7L909.0 140.6M914.7 124.4L910.3 127.1L908.7 125.6L907.6 126.3L905.6 129.2L906.8 130.7L903.8 135.7M907.7 96.2L911.7 98.8L925.5 100.3L923.5 106.1L924.7 106.7L923.2 108.8L924.7 110.4L922.7 113.0L923.2 115.5L918.3 115.5L918.3 114.5L916.1 113.0L914.8 113.4L915.4 114.3M915.4 114.3L914.8 117.1L913.0 117.7L913.3 121.8L915.2 123.2L914.7 124.4","muns":[{"r":"SI031","c":[879.9,93.7],"a":144},{"r":"SI031","c":[927.2,159.5],"a":121},{"r":"SI031","c":[834.9,75.5],"a":108},{"r":"SI031","c":[839.0,175.0],"a":107},{"r":"SI031","c":[789.7,127.1],"a":75},{"r":"SI031","c":[864.1,56.4],"a":67},{"r":"SI031","c":[852.3,120.7],"a":64},{"r":"SI031","c":[868.3,137.8],"a":62},{"r":"SI031","c":[881.5,45.7],"a":58},{"r":"SI031","c":[765.0,104.0],"a":53},{"r":"SI031","c":[805.4,158.8],"a":51},{"r":"SI031","c":[834.7,156.1],"a":46},{"r":"SI031","c":[805.8,57.7],"a":40},{"r":"SI031","c":[820.8,117.3],"a":39},{"r":"SI031","c":[826.7,58.7],"a":37},{"r":"SI031","c":[813.0,133.6],"a":34},{"r":"SI031","c":[886.0,157.6],"a":34},{"r":"SI031","c":[806.5,85.5],"a":31},{"r":"SI031","c":[902.0,119.1],"a":31},{"r":"SI031","c":[894.1,134.7],"a":24},{"r":"SI031","c":[825.7,39.5],"a":23},{"r":"SI031","c":[913.4,106.0],"a":20},{"r":"SI031","c":[907.2,150.3],"a":19},{"r":"SI031","c":[895.4,42.0],"a":18},{"r":"SI031","c":[851.4,149.1],"a":12},{"r":"SI031","c":[882.0,176.1],"a":10},{"r":"SI031","c":[879.9,147.7],"a":7},{"r":"SI032","c":[671.3,226.2],"a":260},{"r":"SI032","c":[691.2,157.8],"a":147},{"r":"SI032","c":[837.1,210.5],"a":142},{"r":"SI032","c":[618.6,176.7],"a":84},{"r":"SI032","c":[781.1,252.8],"a":80},{"r":"SI032","c":[712.9,135.8],"a":76},{"r":"SI032","c":[726.6,265.0],"a":73},{"r":"SI032","c":[728.1,229.7],"a":71},{"r":"SI032","c":[766.9,210.8],"a":67},{"r":"SI032","c":[731.3,113.4],"a":65},{"r":"SI032","c":[646.9,146.5],"a":64},{"r":"SI032","c":[744.3,162.8],"a":62},{"r":"SI032","c":[650.2,178.5],"a":61},{"r":"SI032","c":[685.1,190.5],"a":54},{"r":"SI032","c":[697.9,208.9],"a":51},{"r":"SI032","c":[680.6,125.9],"a":49},{"r":"SI032","c":[760.3,264.8],"a":46},{"r":"SI032","c":[730.1,182.0],"a":40},{"r":"SI032","c":[821.8,195.1],"a":38},{"r":"SI032","c":[741.0,276.6],"a":38},{"r":"SI032","c":[706.1,266.5],"a":37},{"r":"SI032","c":[683.1,270.3],"a":37},{"r":"SI032","c":[752.8,120.0],"a":37},{"r":"SI032","c":[791.4,192.6],"a":36},{"r":"SI032","c":[729.5,200.9],"a":34},{"r":"SI032","c":[766.6,194.7],"a":34},{"r":"SI032","c":[639.1,234.1],"a":33},{"r":"SI032","c":[876.7,223.2],"a":33},{"r":"SI032","c":[800.0,251.6],"a":32},{"r":"SI032","c":[739.9,137.5],"a":31},{"r":"SI032","c":[783.6,231.9],"a":30},{"r":"SI032","c":[804.3,226.0],"a":29},{"r":"SI032","c":[802.3,204.9],"a":28},{"r":"SI032","c":[765.2,157.0],"a":26},{"r":"SI032","c":[780.9,159.9],"a":25},{"r":"SI032","c":[764.9,136.9],"a":24},{"r":"SI032","c":[767.9,174.7],"a":23},{"r":"SI032","c":[748.2,220.1],"a":22},{"r":"SI032","c":[814.2,243.3],"a":19},{"r":"SI032","c":[785.7,177.5],"a":18},{"r":"SI032","c":[712.3,191.1],"a":13},{"r":"SI033","c":[531.8,190.3],"a":174},{"r":"SI033","c":[454.2,202.2],"a":156},{"r":"SI033","c":[570.3,209.7],"a":112},{"r":"SI033","c":[516.2,148.0],"a":105},{"r":"SI033","c":[600.0,151.3],"a":104},{"r":"SI033","c":[578.7,148.4],"a":94},{"r":"SI033","c":[497.5,166.4],"a":63},{"r":"SI033","c":[581.3,175.2],"a":59},{"r":"SI033","c":[472.8,163.6],"a":58},{"r":"SI033","c":[548.4,159.3],"a":50},{"r":"SI033","c":[545.0,133.3],"a":39},{"r":"SI033","c":[460.6,178.4],"a":26},{"r":"SI034","c":[625.5,319.8],"a":222},{"r":"SI034","c":[585.1,346.2],"a":197},{"r":"SI034","c":[551.5,289.3],"a":117},{"r":"SI034","c":[420.2,248.2],"a":109},{"r":"SI034","c":[658.8,307.7],"a":108},{"r":"SI034","c":[404.0,228.2],"a":103},{"r":"SI034","c":[638.2,261.7],"a":98},{"r":"SI034","c":[508.8,228.9],"a":96},{"r":"SI034","c":[589.3,292.0],"a":95},{"r":"SI034","c":[443.9,274.2],"a":90},{"r":"SI034","c":[670.5,372.7],"a":90},{"r":"SI034","c":[543.6,240.8],"a":83},{"r":"SI034","c":[457.4,244.2],"a":79},{"r":"SI034","c":[595.6,266.5],"a":75},{"r":"SI034","c":[691.0,298.6],"a":71},{"r":"SI034","c":[613.7,226.8],"a":67},{"r":"SI034","c":[674.0,342.1],"a":61},{"r":"SI034","c":[589.6,227.4],"a":59},{"r":"SI034","c":[510.1,281.1],"a":55},{"r":"SI034","c":[493.1,250.7],"a":54},{"r":"SI034","c":[485.7,301.0],"a":53},{"r":"SI034","c":[481.3,278.7],"a":43},{"r":"SI034","c":[530.6,306.4],"a":41},{"r":"SI034","c":[723.2,298.4],"a":39},{"r":"SI034","c":[507.2,305.0],"a":35},{"r":"SI034","c":[529.6,271.4],"a":34},{"r":"SI034","c":[572.4,250.1],"a":32},{"r":"SI034","c":[477.0,258.9],"a":30},{"r":"SI034","c":[602.2,316.1],"a":28},{"r":"SI034","c":[513.7,255.7],"a":18},{"r":"SI034","c":[623.9,343.2],"a":17},{"r":"SI035","c":[493.9,379.8],"a":221},{"r":"SI035","c":[483.7,337.2],"a":147},{"r":"SI035","c":[539.9,343.3],"a":59},{"r":"SI035","c":[518.1,342.3],"a":58},{"r":"SI036","c":[642.5,423.5],"a":287},{"r":"SI036","c":[583.2,397.3],"a":272},{"r":"SI036","c":[693.9,426.9],"a":268},{"r":"SI036","c":[630.2,468.6],"a":58},{"r":"SI036","c":[545.4,375.6],"a":52},{"r":"SI036","c":[699.6,374.9],"a":31},{"r":"SI037","c":[465.3,558.9],"a":555},{"r":"SI037","c":[568.3,604.3],"a":340},{"r":"SI037","c":[567.8,494.8],"a":236},{"r":"SI037","c":[495.5,483.5],"a":164},{"r":"SI037","c":[502.6,440.3],"a":163},{"r":"SI037","c":[426.7,517.3],"a":154},{"r":"SI037","c":[551.0,549.9],"a":147},{"r":"SI037","c":[405.9,545.2],"a":134},{"r":"SI037","c":[517.6,523.1],"a":110},{"r":"SI037","c":[606.8,551.0],"a":109},{"r":"SI037","c":[600.2,475.8],"a":96},{"r":"SI037","c":[555.0,433.6],"a":73},{"r":"SI037","c":[593.2,437.7],"a":60},{"r":"SI037","c":[461.5,615.0],"a":56},{"r":"SI037","c":[529.2,407.6],"a":49},{"r":"SI037","c":[391.7,505.7],"a":49},{"r":"SI037","c":[529.1,463.3],"a":48},{"r":"SI037","c":[420.7,593.1],"a":36},{"r":"SI037","c":[577.3,449.1],"a":34},{"r":"SI037","c":[522.0,424.1],"a":31},{"r":"SI037","c":[529.8,497.5],"a":29},{"r":"SI038","c":[293.9,580.9],"a":480},{"r":"SI038","c":[253.1,490.7],"a":270},{"r":"SI038","c":[309.1,486.5],"a":241},{"r":"SI038","c":[273.4,532.9],"a":223},{"r":"SI038","c":[354.9,544.2],"a":167},{"r":"SI038","c":[354.8,491.8],"a":75},{"r":"SI041","c":[383.2,374.8],"a":275},{"r":"SI041","c":[394.3,283.1],"a":266},{"r":"SI041","c":[448.8,442.0],"a":227},{"r":"SI041","c":[260.1,424.3],"a":173},{"r":"SI041","c":[404.7,424.8],"a":134},{"r":"SI041","c":[302.7,374.6],"a":117},{"r":"SI041","c":[292.3,422.5],"a":116},{"r":"SI041","c":[427.9,482.3],"a":103},{"r":"SI041","c":[375.9,464.9],"a":103},{"r":"SI041","c":[359.0,429.2],"a":99},{"r":"SI041","c":[455.3,393.7],"a":95},{"r":"SI041","c":[331.2,422.6],"a":91},{"r":"SI041","c":[326.6,342.8],"a":78},{"r":"SI041","c":[434.5,326.0],"a":75},{"r":"SI041","c":[393.8,336.4],"a":72},{"r":"SI041","c":[433.0,344.6],"a":61},{"r":"SI041","c":[379.1,419.2],"a":43},{"r":"SI041","c":[320.6,438.3],"a":42},{"r":"SI041","c":[293.9,391.7],"a":33},{"r":"SI041","c":[406.6,359.5],"a":33},{"r":"SI041","c":[355.9,327.4],"a":31},{"r":"SI041","c":[367.5,312.0],"a":24},{"r":"SI041","c":[375.1,330.9],"a":22},{"r":"SI041","c":[318.2,394.7],"a":11},{"r":"SI041","c":[369.4,346.1],"a":9},{"r":"SI042","c":[180.9,269.4],"a":334},{"r":"SI042","c":[165.4,205.7],"a":256},{"r":"SI042","c":[244.8,306.1],"a":164},{"r":"SI042","c":[307.4,237.4],"a":155},{"r":"SI042","c":[244.8,353.3],"a":153},{"r":"SI042","c":[285.9,291.6],"a":151},{"r":"SI042","c":[298.6,327.9],"a":146},{"r":"SI042","c":[267.5,252.3],"a":119},{"r":"SI042","c":[206.1,229.9],"a":116},{"r":"SI042","c":[347.0,261.7],"a":87},{"r":"SI042","c":[357.5,291.5],"a":78},{"r":"SI042","c":[228.5,208.7],"a":76},{"r":"SI042","c":[228.9,250.5],"a":72},{"r":"SI042","c":[353.0,235.2],"a":69},{"r":"SI042","c":[243.7,380.6],"a":49},{"r":"SI042","c":[257.5,225.9],"a":43},{"r":"SI042","c":[332.6,297.8],"a":40},{"r":"SI042","c":[294.4,277.3],"a":28},{"r":"SI043","c":[144.9,336.9],"a":382},{"r":"SI043","c":[96.6,244.8],"a":367},{"r":"SI043","c":[206.7,406.3],"a":294},{"r":"SI043","c":[123.2,410.7],"a":279},{"r":"SI043","c":[169.0,436.2],"a":245},{"r":"SI043","c":[73.5,293.2],"a":193},{"r":"SI043","c":[106.4,361.7],"a":146},{"r":"SI043","c":[198.0,345.8],"a":132},{"r":"SI043","c":[199.8,475.7],"a":107},{"r":"SI043","c":[72.1,390.1],"a":72},{"r":"SI043","c":[101.1,457.6],"a":63},{"r":"SI043","c":[109.7,442.9],"a":29},{"r":"SI043","c":[102.3,432.8],"a":15},{"r":"SI044","c":[158.0,604.8],"a":303},{"r":"SI044","c":[172.4,515.8],"a":217},{"r":"SI044","c":[208.3,586.4],"a":195},{"r":"SI044","c":[208.9,533.2],"a":145},{"r":"SI044","c":[143.0,475.3],"a":103},{"r":"SI044","c":[88.2,614.7],"a":45},{"r":"SI044","c":[101.3,607.6],"a":31},{"r":"SI044","c":[128.4,579.1],"a":7}],"mot":"M72.1 471.7L82.1 474.5L95.2 480.4L114.8 497.3L130.7 513.3M98.5 634.5L94.7 640.1M191.2 567.8L181.3 584.3L176.6 588.6L170.6 590.2L145.0 591.9L131.2 596.8M145.1 527.8L158.3 546.2L192.4 565.4M159.5 524.1L169.2 515.5L180.1 509.7L187.4 509.3L209.9 514.1M214.5 181.0L211.8 199.7L212.6 204.2L216.7 210.5L225.3 214.4L242.5 217.1L247.6 221.2L258.2 241.9L263.8 248.8L270.4 254.2L291.3 266.9L309.2 282.1L333.4 298.5L347.5 312.2L350.9 323.1L350.1 341.1L346.8 354.2L343.6 359.4L339.3 361.0M217.7 510.3L220.1 499.8L226.6 494.9L234.8 493.6L268.5 497.5L277.9 496.1L287.1 491.3L293.8 481.3L295.5 473.7L294.7 458.5L289.5 437.0L289.3 429.8L290.7 422.6L293.7 416.4L305.9 401.7L320.8 389.3L335.4 383.0L340.1 383.0L344.7 384.9M281.7 621.0L285.8 631.1M344.8 385.5L353.9 392.5L360.7 395.5L364.4 396.1L371.4 393.6M719.6 475.3L709.9 469.3L692.0 453.2L682.8 447.6L660.4 440.3L646.7 438.3L632.9 438.0L619.2 439.5L607.2 442.7L595.8 448.9L571.3 469.7L561.4 473.0L556.3 472.1L550.5 468.8L535.3 452.8L525.7 446.2L503.5 441.5L480.7 429.8L474.3 430.1L458.6 434.4L452.2 433.9L445.9 431.3L429.1 415.3L423.5 411.7L408.2 411.2L394.4 407.3L379.1 394.0L373.1 391.5L370.4 392.8M704.9 200.1L700.0 208.9L690.3 220.5L679.4 229.7L652.8 246.8L648.5 251.7L631.4 278.1L621.5 285.1L610.9 287.5L562.1 282.3L547.6 288.0L529.9 287.3L515.6 288.3L502.1 291.6L489.7 298.3L484.2 303.6L473.2 318.1L465.2 323.7L420.6 327.7L406.3 330.7L392.7 337.1L384.5 346.1L382.2 352.4L382.0 360.0M611.8 640.3L617.5 638.0M691.5 89.9L705.6 161.6L708.1 189.3L707.9 194.6L704.9 200.1M704.9 200.1L704.2 199.8M747.3 219.7L737.0 213.4L704.9 200.1M938.9 162.2L936.4 160.1L933.1 151.7L927.9 147.2L923.2 145.7L899.3 144.0L871.7 125.1L860.1 121.4L854.7 121.3L849.6 123.0L845.1 127.3L836.0 141.8L831.8 146.2L825.5 149.9L811.8 151.1L788.6 148.5L773.8 150.1L745.2 143.2L735.8 145.1L706.7 159.7","mot2":"M82.7 431.5L100.7 432.3L115.7 435.7L137.7 445.6L149.5 449.3L164.2 447.6L175.1 449.1L181.3 453.1L186.4 459.0L203.2 488.4L209.2 494.5L216.0 498.7M159.5 544.9L162.4 541.7L165.1 535.8L163.2 528.3L154.2 522.4L138.9 517.9M192.7 565.6L191.2 567.8M192.4 565.4L192.7 565.6M192.7 565.6L279.0 618.3L281.7 621.0M209.9 514.1L215.4 516.8L216.2 520.2L203.7 537.0L198.7 556.0L192.7 565.6M207.5 513.1L216.8 498.8M286.9 201.8L286.2 209.2L287.6 217.1L297.2 236.3L297.6 244.6L289.8 268.4M371.4 393.6L381.3 384.3L385.2 373.6L385.1 367.6L383.4 362.2L380.0 357.9L373.4 354.5L366.5 353.1L358.3 353.8L346.7 357.2L338.2 363.0L336.6 366.8L337.2 373.1L340.4 379.9L344.8 385.5M607.0 644.2L613.1 638.5M855.2 225.0L886.1 235.6L900.4 235.9M929.4 186.4L931.1 171.8L937.5 159.5M967.1 168.6L959.5 165.2L938.9 162.2","rail":"M89.5 428.3L84.5 435.6L74.7 441.9M75.2 480.7L81.6 482.6L88.5 491.3L99.4 492.5L102.1 494.8M87.1 424.1L89.5 428.3M89.5 428.3L93.8 429.2L102.4 427.6M102.4 427.6L107.7 432.7L110.1 437.8L119.6 444.5L128.4 447.1L142.8 460.3L151.2 464.3L156.9 470.2L161.0 476.9L157.1 484.0L155.9 494.8L153.5 500.1L155.8 501.6L154.3 507.6M228.1 210.3L227.1 213.0L228.2 215.3L235.3 220.2L236.8 226.0L233.4 239.3L226.0 252.1L225.6 269.7L223.4 271.5L200.7 274.4L196.0 277.6L194.9 284.0L198.3 306.2L196.8 309.0L189.1 312.4L184.5 320.3L180.2 323.4L177.2 328.3L170.8 328.7L166.4 331.8L148.9 329.4L145.5 329.7L138.8 334.6L133.0 333.2L117.2 349.0L97.9 356.0L94.6 369.5L92.9 371.7L85.0 375.2L84.0 377.8L90.0 390.8L103.1 401.5L103.8 404.4L100.1 420.8L102.4 427.6M110.7 500.5L116.0 502.8L117.6 505.6M133.4 587.2L168.4 599.7L171.7 602.7L179.3 615.4L181.0 614.5L180.7 611.8L172.7 592.2L176.0 591.0L184.2 592.7L186.8 589.6M144.9 526.2L148.0 526.8M148.0 526.8L145.0 528.2M148.0 526.8L156.2 529.6L168.4 523.1M154.3 507.6L149.7 514.9L148.0 526.8M154.3 507.6L163.8 512.2L168.4 523.1M168.4 523.1L171.7 522.5L176.5 525.7L183.3 526.9L194.1 532.6M199.5 643.9L191.5 632.3L190.0 613.0L184.0 603.7L189.9 597.7L190.1 595.4L186.8 589.6M194.1 532.6L191.3 546.6L197.7 555.6L197.0 558.7L184.9 570.1L186.8 589.6M194.1 532.6L199.2 534.0L203.6 530.6L206.9 531.5L210.3 539.5L212.7 541.2L218.9 539.9L224.6 542.0L230.0 541.6L232.0 543.5L247.5 536.2L262.0 539.4M228.1 210.3L214.3 204.2L216.5 180.0M347.7 359.3L339.5 352.8L335.0 345.7L323.8 333.5L320.5 332.5L315.0 326.1L306.9 322.0L306.0 319.2L314.2 311.7L316.5 305.8L310.4 296.6L301.6 293.1L298.5 288.4L287.6 283.1L285.6 281.1L283.1 272.4L272.2 263.6L267.9 256.3L258.1 250.0L251.1 237.8L247.8 219.8L235.3 212.1L228.1 210.3M262.0 539.4L262.0 546.2L264.5 551.5L258.8 557.3L260.0 563.0L268.8 570.1L270.9 579.1L276.7 585.3L277.5 588.1L276.3 590.8L277.4 601.1L274.9 608.4L277.4 616.3L275.0 626.2L275.7 629.2M262.0 539.4L263.1 533.5L260.4 514.3L268.9 499.6L271.6 489.0L277.0 484.2L283.1 481.6L295.9 483.7L298.7 481.2L288.2 456.1L274.9 439.0L274.9 433.9L277.4 427.9L282.3 422.4L292.7 425.0L302.5 420.2L306.9 424.2L313.1 437.2L314.6 439.1L317.8 439.1L318.7 435.9L314.9 428.3L315.6 424.1L324.0 414.2L330.8 392.0L343.3 382.3M343.3 382.3L341.6 369.1L344.0 363.2L347.7 359.3M357.6 374.5L343.3 382.3M357.6 374.5L347.7 359.3M390.0 301.4L384.9 318.0L386.0 325.9L384.4 336.3L385.6 342.4L378.6 347.7L374.1 356.8L364.8 362.6L357.6 374.5M368.0 373.7L357.6 374.5M559.9 363.0L552.1 356.6L549.4 351.6L543.1 349.7L533.1 343.6L516.4 340.8L509.8 345.9L502.9 345.4L497.2 347.3L490.1 356.0L477.1 357.8L466.4 362.3L459.0 370.6L456.1 371.5L452.3 364.3L439.2 358.5L434.8 361.9L428.4 362.8L420.9 366.8L412.2 365.0L405.2 369.6L391.2 374.4L368.0 373.7M402.8 420.2L390.1 410.4L383.6 410.7L384.1 404.7L377.1 406.9L367.8 396.5L362.2 380.3L368.0 373.7M511.4 439.3L503.0 438.0L493.5 427.9L487.1 425.9L481.5 427.7L473.4 424.0L457.9 427.0L440.6 426.6L437.5 425.9L436.4 423.3L425.1 418.9L420.0 425.6L410.9 424.2L407.2 420.1L404.2 420.5L402.8 420.2M402.8 420.2L402.1 427.2L407.0 432.5L410.3 442.1L416.4 444.8L418.5 447.4L416.2 452.5L418.7 458.9L415.7 461.1L407.5 461.8L399.8 467.1L399.7 470.1L404.3 477.1L403.8 485.6L408.1 489.7L415.8 505.5L434.5 517.0L443.7 524.5L456.9 546.7L464.0 555.1M515.0 147.7L505.8 157.4L503.5 163.4L494.7 165.8L470.7 163.8L459.8 158.4L447.7 155.0M636.3 553.0L629.7 552.0L618.0 554.9L608.8 548.2L602.5 548.3L596.9 554.7L586.9 554.3L585.0 556.4L578.9 557.7L577.2 559.8L577.9 562.9L575.5 568.4L561.6 582.0L559.5 581.3L553.4 572.0L551.5 566.3L551.7 556.5L555.1 547.7L543.1 521.9L546.3 517.1L546.6 510.1L548.7 503.9L553.5 501.1L554.6 498.1L549.6 474.6L532.5 463.6L531.5 457.1L526.7 453.9L524.0 449.1L518.7 446.1L516.1 441.2L511.4 439.3M594.9 394.1L586.1 400.2L579.8 401.2L575.5 404.8L572.3 405.2L570.2 407.0L568.4 413.1L563.1 415.4L553.0 415.0L540.0 418.2L531.6 417.3L525.9 419.1L514.4 431.4L513.3 437.4L511.4 439.3M515.0 147.7L514.5 152.5L516.4 157.9L529.6 172.0L530.9 177.6L530.0 182.3M699.0 161.5L681.7 158.6L668.6 160.2L655.4 166.1L648.8 171.1L642.4 172.1L637.2 169.3L635.9 166.8L637.8 157.3L636.6 156.4L634.5 158.2L631.4 157.9L624.3 153.3L607.6 151.4L603.2 147.8L587.1 149.2L582.1 146.2L567.7 144.5L559.2 140.5L546.6 146.8L537.4 144.0L526.8 143.7L515.0 147.7M594.9 394.1L589.3 389.4L587.5 380.1L585.5 378.2L582.2 377.6L576.5 379.6L569.5 374.6L559.9 363.0M633.8 308.4L629.8 309.7L622.5 309.3L583.2 300.0L582.4 309.4L575.6 314.2L573.1 319.9L574.2 322.5L572.8 329.1L574.7 334.8L573.8 337.3L567.6 338.5L563.9 342.6L569.8 348.1L569.3 354.3L559.9 363.0M716.4 450.0L671.0 425.3L657.3 422.3L653.8 418.1L650.2 406.7L647.8 405.0L637.1 403.1L619.4 403.4L610.4 400.0L606.5 396.1L594.9 394.1M701.2 229.2L697.5 234.9L689.6 238.3L683.3 244.1L677.3 245.4L673.2 249.2L675.3 257.8L673.1 267.2L657.5 274.6L650.1 282.9L638.0 285.8L633.4 288.9L632.4 295.4L635.2 307.5L633.8 308.4M674.0 307.0L671.6 307.5L665.2 302.0L646.7 301.2L638.0 308.0L633.8 308.4M674.0 307.0L681.9 315.9L681.7 324.7L683.1 327.4L681.6 335.2L683.5 345.3L689.7 350.6L694.2 357.1L698.4 358.9L701.9 364.4L710.8 366.4L722.3 375.2L722.2 379.1L719.2 386.1L717.6 402.6L719.3 426.4L712.7 437.2L716.4 450.0M747.2 311.4L741.9 309.8L731.5 309.9L726.5 306.5L719.6 306.5L709.8 303.7L697.5 305.9L693.3 298.6L690.7 297.2L685.0 299.0L675.4 296.6L673.0 298.1L672.2 301.3L674.0 307.0M687.5 94.1L689.9 96.2M689.9 96.2L698.1 109.4L700.7 124.4L706.2 141.3L700.2 150.6L699.0 161.5M770.4 84.5L747.5 85.5L741.7 87.1L737.7 91.1L732.0 92.9L714.5 93.1L696.7 91.2L689.9 96.2M699.0 161.5L698.0 167.1L700.7 182.9L701.2 229.2M852.4 225.7L847.2 220.4L837.9 222.2L809.6 217.2L772.7 216.1L766.1 217.8L760.5 224.1L755.1 226.1L701.2 229.2M721.0 451.9L716.4 450.0M848.8 164.6L815.3 125.9L807.2 120.5L799.6 108.7L797.1 98.9L788.5 90.5M852.4 225.7L853.8 214.7L846.1 199.6L845.9 178.2L847.7 176.0L854.8 177.2L858.2 177.0L860.1 175.0L859.3 172.2L848.8 164.6M893.5 46.2L868.6 48.6L862.3 51.0L858.2 55.9L847.7 76.7L844.9 89.8L846.9 101.4L851.8 116.2L859.7 122.2L861.2 126.4L860.3 131.9L852.6 148.0L848.8 164.6M901.6 229.7L856.3 227.0L852.4 225.7M906.5 46.0L911.2 42.9M932.1 151.5L930.6 162.3L930.9 183.4L932.2 186.3M936.6 131.9L939.6 131.2","rivers":[{"n":"Drava","d":"M486.9 122.1L492.7 127.6L500.0 139.4L504.5 143.7L510.4 144.9L524.3 139.6L531.1 138.0L537.3 138.7L543.1 141.0L548.6 141.8L559.6 136.6L565.1 137.9L577.7 143.8L585.8 144.8L605.6 144.6L614.6 145.7L621.3 148.2L629.4 152.8L635.4 151.2L638.9 162.9L642.4 166.6L647.6 166.4L662.5 158.8L673.1 155.6L683.0 154.7L704.1 159.4L711.6 162.6L715.3 169.1L717.0 176.8L719.5 182.9L724.6 187.4L741.2 196.4L756.6 212.1L777.3 228.9L783.9 235.7L791.3 237.5L815.3 228.7L822.4 228.9L826.4 231.2L830.5 231.7L834.6 229.8L838.7 226.2L843.6 224.4L857.9 230.7L875.3 231.1L889.4 239.5L895.3 240.0L897.9 241.9","km":126},{"n":"Ljubljanica","d":"M354.6 581.9L353.3 561.6L346.6 546.4L345.7 537.3L343.6 528.5L337.3 521.6L330.0 516.4L321.1 506.1L307.0 492.2L304.0 485.3L303.0 480.4L297.3 474.6L287.6 461.9L279.3 457.5L272.0 451.2L269.2 440.3L275.2 427.0L286.4 416.4L296.1 412.2L318.1 409.9L331.5 405.4L344.9 398.3L354.2 389.9L357.8 382.3L358.9 376.9L362.1 373.9L384.9 375.7L392.1 371.6L396.6 367.7","km":87},{"n":"Mura","d":"M689.3 91.6L696.7 96.0L719.2 99.2L727.0 98.6L746.9 90.4L755.1 89.6L763.3 91.1L783.3 101.0L795.3 103.0L798.6 105.2L804.2 112.1L807.7 114.5L811.9 115.5L819.3 123.2L835.2 133.8L859.9 145.1L863.8 148.4L875.1 163.9L879.3 167.1L883.3 163.8L886.4 169.1L891.8 170.5L897.5 168.5L901.6 163.5L903.8 166.7L905.6 163.5L909.1 166.1L920.0 166.4L930.2 175.0L939.1 174.3L945.2 176.4L954.2 183.3L952.6 183.3L967.1 191.0L971.1 194.9L973.0 194.9L974.2 191.1L976.0 189.6L986.5 192.5","km":92},{"n":"Sava","d":"M396.2 367.8L392.0 367.6L385.8 364.6L370.9 365.1L363.1 363.1L360.6 355.7L354.1 351.0L345.6 350.8L340.3 349.1L330.3 340.7L330.8 334.1L334.4 332.4L334.0 329.1L329.6 323.9L327.9 316.0L323.2 309.2L315.6 303.5L311.8 297.1L299.8 287.2L287.4 281.6L285.3 274.8L282.0 268.6L268.1 262.0L264.0 258.3L259.0 256.5L243.7 232.3L245.7 227.7L245.8 223.5L214.5 209.0L206.3 206.3L199.3 202.3L182.7 198.0L175.1 194.3L166.2 194.3L157.2 189.9L141.9 188.9L132.7 187.3M396.6 367.7L406.2 361.5L412.9 359.7L424.2 359.7L432.7 356.8L441.5 356.6L454.0 368.4L461.4 367.1L469.8 362.2L486.5 356.6L501.9 347.2L509.4 344.4L524.9 344.0L533.9 347.0L544.3 353.0L554.1 361.2L573.3 381.3L578.5 383.7L587.7 382.1L593.3 382.3L613.5 390.2L634.6 393.1L640.9 396.4L646.1 402.6L649.0 412.9L650.8 416.2L654.1 419.0L667.8 425.6L678.7 426.2L683.1 427.4L690.3 433.0L710.4 455.8L725.8 462.0","km":194}],"aff":{"minx":368848.359,"maxy":199757.134,"k":0.003849634143817927},"entries":[{"id":"tomacevo","n":"Tomačevo Bridge","sl":"Most čez Savo v Tomačevem","cls":"doc","cat":"bridge","lat":46.0856,"lon":14.53642,"prec":"derived","loc":"Ljubljana","crosses":"Sava","carries":"H3 northern ring road","built":1982,"len_m":null,"spans":7,"typ":"Seven-span continuous post-tensioned double-T deck, cast in place with sliding formwork, on circular piers with deep foundations","role":"Bridge weigh-in-motion and structural health monitoring","detail":"Elastomeric bearings at the piers and guided unidirectional pot bearings at the abutments. ZAG, Cestel and Dewesoft Monitoring instrumented the bridge for combined bridge weigh-in-motion and structural health monitoring. A controlled load test in May 2024 ran two pre-weighed calibration trucks over 72 passages across two nights, recording strain, acceleration, temperature and displacement at 500 Hz. During normal operation in March 2023 the system captured a 13-axle vehicle weighing over 200 tonnes.","people":["Doron Hekič (ZAG / UL FGG)","Jan Kalin (ZAG)","Aleš Žnidarič (ZAG / UL FGG)","Andrej Anžlin (ZAG)","Peter Češarek (UL FGG)"],"partners":["Cestel d.o.o.","Dewesoft Monitoring d.o.o.","UL FGG"],"years":"2023-2025","src":["appsci2025","dewesoft"],"p":[366.87,364.03],"tm":[464148.6,105194.5],"reg":"SI041","dom":"ai","doms":["ai","bridge"]},{"id":"ravbarkomanda","n":"Ravbarkomanda Viaduct","sl":"Viadukt Ravbarkomanda","cls":"doc","cat":"bridge","lat":45.821,"lon":14.24,"prec":"approximate","loc":"A1 between Planina and Postojna","crosses":"A double-track railway and a state road, crossed twice","carries":"A1 motorway (Ljubljana-Koper)","built":1972,"len_m":588,"spans":15,"typ":"Twin precast prestressed I-girder viaducts on elastomeric bearings, each divided into four units by expansion joints","role":"Long-term structural health monitoring and bridge weigh-in-motion","detail":"Two parallel structures carrying one direction each, built in 1972 on what is now the Venice to Lviv corridor. ZAG instrumented span P14D of the right-hand viaduct with strain gauges on the bottom flange of four main girders at mid-span, and triaxial accelerometers across several spans for ambient and traffic-induced modal testing. A bridge weigh-in-motion system supplies the traffic loading, and the measured response is used to update a finite element model of the structure. Both viaducts were fully rehabilitated between May 2017 and July 2019, including carbon fibre strengthening of the cantilevers, bearing replacement and a one metre deck widening.","people":["Doron Hekič (ZAG)","Andrej Anžlin (ZAG)","Aleš Žnidarič (ZAG)","Peter Češarek (UL FGG)","Diogo Ribeiro (Polytechnic of Porto)"],"partners":["DARS","UL FGG","Polytechnic of Porto"],"years":"2023-2024","src":["sensors2023","sensors2024","kolektor","stareslike"],"note":"Dimensions differ between the two papers. Sensors 23(4) gives 588 m with 15 spans for the left structure and 544 m with 17 spans for the right; Sensors 24(9) gives 560 m and 16 spans. The figures shown are from the earlier and more detailed description. The coordinate is taken from the A1 alignment between Planina and Postojna, not from a survey point.","tm":[440944.3,75963.4],"p":[277.54,476.56],"reg":"SI038","dom":"ai","doms":["ai","bridge"]},{"id":"vransko","n":"Vransko Bridge","sl":"Most pri Vranskem","cls":"doc","cat":"road","lat":46.25111,"lon":14.94472,"prec":"locality","loc":"Vransko","crosses":"Motorway crossing in the Savinja valley","carries":"A1 motorway","built":null,"len_m":26,"span_m":24.8,"spans":1,"typ":"Simply supported beam and slab deck, 12 m wide, no skew","role":"Bridge weigh-in-motion measurement and direct measurement of dynamic amplification","detail":"One of the earliest long SiWIM deployments. Strain was recorded continuously for 58 days, from 25 September to 21 November 2006, capturing 147,524 vehicles including roughly 74,000 five-axle articulated trucks. Total and static bending moments at mid-span were separated to measure the dynamic amplification directly from traffic rather than inferring it from a code factor. The work was done with University College Dublin.","people":["Aleš Žnidarič (ZAG)","Eugene J. OBrien (UCD)","Arturo González (UCD)","Jason Dowling (UCD)"],"partners":["University College Dublin","Cestel d.o.o."],"years":"2006-2009","src":["ucd2009"],"note":"The coordinate is the settlement of Vransko, not the bridge deck.","tm":[495737.7,123486.8],"p":[488.48,293.61],"reg":"SI034","dom":"ai","doms":["ai","bridge"]},{"id":"nm_brv","n":"Novo Mesto Stress Ribbon Footbridge","sl":"Brv čez Krko, Novo mesto","cls":"doc","cat":"foot","lat":45.8,"lon":15.167,"prec":"locality","loc":"Novo mesto","crosses":"Krka","carries":"Footway and cycleway","built":2023,"len_m":null,"span_m":120.5,"spans":1,"typ":"Stress ribbon deck of 46 precast concrete panels carried on six tendons in grouted HDPE ducts, 4 m wide","role":"Static and dynamic load testing, and validation of the finite element model","detail":"The first bridge in Slovenia built with stress ribbon technology. ZAG carried out the load test in March 2023: static loading in three stages, dynamic testing with a light truck driven over artificial obstacles, and ambient vibration measurement. Vertical displacements, natural frequencies and mode shapes were compared against a finite element model and agreed well. The reported deflection was 130 mm under a 70 tonne load. Client was the City Municipality of Novo mesto, built by CGP Novo mesto with Freyssinet Adria, designed by Ponting Bridges and Pipenbaher Consulting Engineers.","people":["Đorđe Đukić (ZAG)","Doron Hekič (ZAG)","Mirko Kosič (ZAG)","Andrej Anžlin (ZAG)","Rok Vezočnik (UM FGPA)","Andrej Štrukelj (UM FGPA)","Marjan Pipenbaher","Tomaž Weingerl"],"partners":["Mestna občina Novo mesto","CGP Novo mesto","Freyssinet Adria","Ponting Bridges","Pipenbaher Consulting Engineers","UM FGPA"],"years":"2023","src":["iabmas2024","freyssinet"],"note":"The sources place the footbridge in Novo mesto over the Krka but do not give the exact crossing, so the coordinate is the town centre. Novo mesto opened more than one footbridge over the Krka in 2023.","tm":[512981.6,73362.2],"p":[554.86,486.57],"reg":"SI037","dom":"bridge","doms":["bridge"]},{"id":"crna","n":"Črna na Koroškem Bridge","sl":"Most v Črni na Koroškem","cls":"doc","cat":"bridge","lat":46.4697417,"lon":14.8489639,"prec":"locality","loc":"Črna na Koroškem","crosses":"Meža","carries":"Local road","built":2024,"len_m":null,"spans":1,"typ":"Reused precast prestressed girders on new abutments","role":"Structural reuse of salvaged girders","detail":"Built under the CIRCUIT project, which demonstrates circular practice in construction. The girders were recovered from a bridge that was being demolished, assessed for residual capacity, and reused in the new structure rather than being crushed for aggregate. ZAG carried out the assessment work.","people":[],"partners":["Direkcija RS za infrastrukturo"],"years":"2023-2024","src":["bilten2024"],"note":"Coordinate is the settlement centre, not the bridge itself.","tm":[488400.8,147796.7],"p":[460.23,200.03],"reg":"SI033","dom":"mat","doms":["mat","bridge"]},{"id":"verd","n":"Verd Viaduct","sl":"Viadukt Verd","cls":"doc","cat":"bridge","lat":45.9531444,"lon":14.3000444,"prec":"locality","loc":"Verd, Vrhnika","crosses":"Ljubljanica headwaters plain","carries":"A1 motorway","built":null,"len_m":null,"spans":null,"typ":"Prestressed concrete viaduct","role":"First Slovenian application of an expansive grout additive","detail":"The first structure on which the Ikaton expansive additive was used for grouting prestressing cable ducts. The additive compensates for the shrinkage of cement grout so that the duct fills completely and the tendon is protected from corrosion. Built by Beograjska Mostogradnja. The additive line was developed at ZAG.","people":[],"partners":["DARS"],"years":null,"src":["bilten2024"],"note":"Coordinate is the settlement of Verd; the viaduct runs above it.","tm":[445738.9,90607.0],"p":[296.0,420.19],"reg":"SI041","dom":"mat","doms":["mat","bridge"]},{"id":"he_solkan","n":"HE Solkan","sl":"Hidroelektrarna Solkan","cls":"doc","cat":"dam","lat":45.9694972,"lon":13.6454917,"prec":"locality","loc":"Solkan, Nova Gorica","crosses":"Soča","carries":null,"built":1984,"len_m":null,"spans":null,"typ":"Run-of-river hydroelectric plant","role":"Expansive and non-shrink cement grouts","detail":"One of the hydroelectric plants where ZAG grout formulations were used for cable duct grouting and non-shrink structural grouting. The work sits in a long ZAG line of research on expansive cements and additives.","people":[],"partners":["Soške elektrarne Nova Gorica"],"years":null,"src":["bilten2024"],"note":"Coordinate is the settlement of Solkan.","tm":[395028.5,93078.4],"p":[100.78,410.67],"reg":"SI043","dom":"energy","doms":["energy","mat"]},{"id":"he_zlatolicje","n":"HE Zlatoličje","sl":"Hidroelektrarna Zlatoličje","cls":"doc","cat":"dam","lat":46.4562111,"lon":15.790083,"prec":"locality","loc":"Zlatoličje, Starše","crosses":"Drava","carries":null,"built":1969,"len_m":null,"spans":null,"typ":"Run-of-river hydroelectric plant on a diversion canal, 136 MW","role":"Expansive and non-shrink cement grouts","detail":"Named in ZAG material as one of the hydroelectric plants where ZAG expansive and non-shrink grouts were applied. The plant works from a diversion canal rather than directly on the Drava channel.","people":[],"partners":["Dravske elektrarne Maribor"],"years":null,"src":["bilten2024","wp_zlat"],"note":"Coordinate is the settlement of Zlatoličje; the plant is south of it.","tm":[560691.3,146585.1],"p":[738.53,204.69],"reg":"SI032","dom":"energy","doms":["energy","mat"]},{"id":"he_vuhred","n":"HE Vuhred","sl":"Hidroelektrarna Vuhred","cls":"doc","cat":"dam","lat":46.5924944,"lon":15.2328417,"prec":"locality","loc":"Vuhred, Radlje ob Dravi","crosses":"Drava","carries":null,"built":1956,"len_m":null,"spans":null,"typ":"Run-of-river hydroelectric plant","role":"Expansive and non-shrink cement grouts","detail":"Named in ZAG material alongside Zlatoličje and Solkan as a site where ZAG grout formulations were used.","people":[],"partners":["Dravske elektrarne Maribor"],"years":null,"src":["bilten2024","wp_vuh"],"note":"Coordinate is the settlement of Vuhred.","tm":[517841.4,161456.0],"p":[573.57,147.45],"reg":"SI033","dom":"energy","doms":["energy","mat"]},{"id":"strunjan","n":"Sveti Križ Bay Cliff","sl":"Zaliv Sv. Križa v Strunjanu","cls":"doc","cat":"geo","lat":45.5340583,"lon":13.606806,"prec":"locality","loc":"Strunjan, Piran","crosses":null,"carries":null,"built":null,"len_m":null,"spans":null,"typ":"Flysch sea cliff","role":"Rockfall investigation and slope characterisation","detail":"ZAG investigated a coastal rockfall of roughly 2,000 cubic metres between 2019 and 2021, combining geological mapping, geodetic remote sensing and geomechanical laboratory testing of samples taken from the cliff. The work sits within ZAG's wider study of erosion on the unstable flysch cliffs of the Slovenian coast.","people":[],"partners":[],"years":"2019-2021","src":["lp2021"],"note":"The coordinate is the settlement of Strunjan; the cliff is on the coast to its north.","tm":[391187.4,44737.8],"p":[86.0,596.77],"reg":"SI044","dom":"geo","doms":["geo"]},{"id":"sitarjevec","n":"Sitarjevec Mine","sl":"Rudnik Sitarjevec v Litiji","cls":"doc","cat":"geo","lat":46.067,"lon":14.817,"prec":"locality","loc":"Litija","crosses":null,"carries":null,"built":null,"len_m":null,"spans":null,"typ":"Former lead, zinc and barite mine","role":"Characterisation of mine ochre as a pigment","detail":"ZAG characterised the yellow limonite mud that forms in the mine and assessed it as a source of natural pigment for artistic and textile use. The work is an example of the institute's materials side rather than its structures side.","people":[],"partners":[],"years":"2021","src":["lp2021"],"note":"The coordinate is the town of Litija; the mine is on the Sitarjevec hill immediately to its south.","tm":[485842.8,103039.0],"p":[450.39,372.33],"reg":"SI035","dom":"geo","doms":["geo","mat"]},{"id":"zag","n":"ZAG","sl":"Zavod za gradbeništvo Slovenije","cls":"inst","cat":"inst","lat":46.0657,"lon":14.5128,"prec":"address","loc":"Dimičeva ulica 12, Ljubljana","role":"Slovenian National Building and Civil Engineering Institute","detail":"Founded 1994. 255 staff, six research and testing departments, a metrology department and three notified-body services under the Construction Products Regulation. Home of SiWIM bridge weigh-in-motion and of the BrAId project applying machine learning to B-WIM data quality.","src":["zagbridges","zag_bridges_svc"],"p":[359.79,372.5],"tm":[462308.4,102993.7],"reg":"SI041","dom":"inst","doms":["inst","build","mat","bridge"],"groups":["g_struct","g_stone","g_phys","g_metal","g_geo","g_org","g_conc","g_metro"]},{"id":"zag_logatec","n":"ZAG Fire Laboratory Logatec","sl":"Požarni laboratorij ZAG Logatec","cls":"inst","cat":"inst","lat":45.9167028,"lon":14.2297278,"prec":"locality","loc":"Logatec","crosses":null,"carries":null,"built":2022,"len_m":null,"spans":null,"typ":"Fire testing laboratory","role":"Fire resistance and reaction to fire testing","detail":"Opened in 2022 and staffed by around twenty five people. It carries out fire resistance and reaction to fire testing on construction products and assemblies, including large scale furnace tests that the older Gameljne facility could not accommodate.","people":[],"partners":[],"years":"2022-","src":["bilten2024"],"note":"Coordinate is the town of Logatec.","tm":[440248.7,86607.2],"p":[274.87,435.59],"reg":"SI041","dom":"fire","doms":["fire","inst"]},{"id":"zag_gameljne","n":"ZAG Fire Laboratory Gameljne","sl":"Požarni laboratorij ZAG Gameljne","cls":"inst","cat":"inst","lat":46.1216,"lon":14.4907,"prec":"locality","loc":"Zgornje Gameljne, Ljubljana","crosses":null,"carries":null,"built":1986,"len_m":null,"spans":null,"typ":"Fire testing laboratory","role":"Fire testing, original ZAG fire facility","detail":"ZAG built its first dedicated fire laboratory here in 1986. It remained the institute's fire testing base until the Logatec laboratory opened.","people":[],"partners":[],"years":"1986-","src":["bilten2024"],"note":"Coordinate is the settlement of Zgornje Gameljne.","tm":[460638.4,109217.2],"p":[353.36,348.55],"reg":"SI041","dom":"fire","doms":["fire","inst"]},{"id":"zag_maribor","n":"ZAG Maribor Unit","sl":"ZAG enota Maribor, Dobrovce","cls":"inst","cat":"inst","lat":46.480806,"lon":15.7026583,"prec":"locality","loc":"Dobrovce, Miklavž na Dravskem polju","crosses":null,"carries":null,"built":2021,"len_m":null,"spans":null,"typ":"Regional laboratory and office","role":"ZAG regional unit for north-east Slovenia","detail":"Opened in 2021, replacing the 1972 Maribor premises. It serves construction testing and site work across Podravska and Pomurska.","people":[],"partners":[],"years":"2021-","src":["bilten2024"],"note":"Coordinate is the settlement of Dobrovce.","tm":[553951.4,149255.4],"p":[712.58,194.41],"reg":"SI032","dom":"inst","doms":["inst"]},{"id":"cestel","n":"Cestel d.o.o.","sl":"Cestel cestni inženiring d.o.o.","cls":"inst","cat":"inst","dom":"ai","doms":["ai","inst"],"lat":46.13528,"lon":14.56,"prec":"locality","loc":"Trzin","crosses":null,"carries":null,"built":null,"len_m":null,"spans":null,"typ":"Engineering company, maker of the SiWIM bridge weigh-in-motion system","role":"Industrial partner on bridge weigh-in-motion work","detail":"SiWIM grew out of the weigh-in-motion research ZAG has run since the 1990s. Cestel supplies and operates the systems, and is a partner alongside ZAG in the BRIDGITISE doctoral network and on the Tomačevo bridge installation.","people":[],"partners":["ZAG","UL FGG"],"years":null,"src":["cestel","cordis_bridgitise"],"note":"Coordinate is the Trzin business zone, not the exact street address.","tm":[466002.7,110705.7],"p":[374.01,342.82],"reg":"SI041"},{"id":"innorenew","n":"InnoRenew CoE","sl":"InnoRenew CoE, Izola","cls":"inst","cat":"inst","dom":"inst","doms":["inst","mat"],"lat":45.53444,"lon":13.6675,"prec":"locality","loc":"Izola","crosses":null,"carries":null,"built":2017,"len_m":null,"spans":null,"typ":"Research and innovation centre of excellence for renewable materials","role":"Partner institute, ZAG is a founding partner","detail":"Set up under the Horizon 2020 teaming action with ZAG among the partners. It works on renewable building materials and healthy indoor environments. Friderik Knez led ZAG's side of the project from 2017 to 2022.","people":["Friderik Knez (ZAG)"],"partners":["University of Primorska","Fraunhofer WKI"],"years":"2017 to 2022","src":["innorenew","zag_intl"],"note":"Coordinate is the town of Izola.","tm":[395928.5,44699.7],"p":[104.25,596.91],"reg":"SI044"},{"id":"ulfgg","n":"UL FGG","sl":"Fakulteta za gradbeništvo in geodezijo","cls":"inst","cat":"inst","lat":46.0455,"lon":14.4945,"prec":"address","loc":"Jamova cesta 2, Ljubljana","role":"Faculty of Civil and Geodetic Engineering, University of Ljubljana","detail":"ZAG's nearest academic partner, five kilometres away. Co-supervises BRIDGITISE doctoral candidates and co-authors the Tomačevo influence-line work.","src":["ulfgg_s0"],"p":[354.28,381.11],"tm":[460878.3,100757.5],"reg":"SI041","dom":"inst","doms":["inst"]},{"id":"ijs","n":"Jožef Stefan Institute","sl":"Institut Jožef Stefan","cls":"inst","cat":"inst","lat":46.0424,"lon":14.4879,"prec":"address","loc":"Jamova cesta 39, Ljubljana","role":"Technical coordinator of the SLAIF AI Factory","detail":"Slovenia's largest research institute and the methodological partner for machine-learning work. Technical coordinator of the AI Factory component of SLAIF.","src":["ijs_s0"],"p":[352.31,382.43],"tm":[460365.3,100416.2],"reg":"SI041","dom":"inst","doms":["inst"]},{"id":"izum","n":"IZUM / Vega","sl":"Institut informacijskih znanosti","cls":"inst","cat":"inst","lat":46.5588,"lon":15.6458,"prec":"address","loc":"Prešernova ulica 17, Maribor","role":"Host of the Vega supercomputer and coordinator of SLAIF","detail":"Slovenia's EuroHPC petascale system Vega runs here, 120 km from ZAG. SLAIF, the Slovenian AI Factory, is coordinated from IZUM with a new data centre at Mariborski otok.","src":["izum_s0"],"p":[695.5,161.18],"tm":[549514.8,157887.1],"reg":"SI032","dom":"inst","doms":["inst"]},{"id":"solkan","n":"Solkan Bridge","sl":"Solkanski most","cat":"rail","lat":45.978981,"lon":13.651822,"prec":"surveyed","loc":"Nova Gorica","crosses":"Soča","carries":"Bohinj railway","built":1906,"len_m":220,"span_m":85,"typ":"Masonry semi-circular arch","note":"The longest stone arch span ever built for a railway. Rebuilt 1927 after wartime destruction.","cls":"ctx","role":"Notable Slovenian structure","src":["solkan_s0"],"p":[102.74,406.65],"tm":[395536.9,94124.1],"reg":"SI043","dom":"bridge","doms":["bridge"]},{"id":"crnikal","n":"Črni Kal Viaduct","sl":"Viadukt Črni Kal","cat":"road","lat":45.5500028,"lon":13.8784389,"prec":"locality","loc":"Črni Kal","crosses":"Osp valley","carries":"A1 motorway","built":2004,"len_m":1054,"span_m":141,"typ":"Twin prestressed concrete haunched box girders on Y-shaped piers","note":"Northern structure 1,053.50 m, southern 1,056.35 m, main span 141.14 m, pier heights from 9.0 m to 87.5 m. Opened 23 September 2004. Designed by Marjan Pipenbaher with Janez Koželj. The longest and highest viaduct in Slovenia. No public source ties ZAG to it, so it is carried as context.","cls":"ctx","role":"Notable Slovenian structure","src":["structurae_ck","wp_bridges"],"p":[167.76,591.23],"tm":[412427.4,46177.4],"reg":"SI044","spans":null,"dom":"bridge","doms":["bridge"]},{"id":"puch","n":"Puch Bridge","sl":"Puhov most","cat":"road","lat":46.412831,"lon":15.878141,"prec":"surveyed","loc":"Ptuj","crosses":"Drava","carries":"Ptuj eastern bypass","built":2007,"len_m":430,"span_m":100,"typ":"Extradosed bridge, span arrangement 65 + 100 + 100 + 100 + 65 m, 2.7 m deep box girder on low outward leaning pylons","note":"Client DARS. Designed by Ponting d.o.o. Maribor with Viktor Markelj as responsible designer, supervision by DDC d.o.o., built by the SCT and Porr joint venture. A widely circulated AI generated web summary states that ZAG was involved. The primary record for the bridge names designer, supervisor and contractor and does not name ZAG, so the entry stays as context.","cls":"ctx","role":"Notable Slovenian structure","src":["izs_puh","wp_bridges"],"p":[764.77,222.98],"tm":[567509.1,141834.8],"reg":"SI032","dom":"bridge","doms":["bridge"],"spans":5},{"id":"maribor_old","n":"Old Bridge","sl":"Stari most","cat":"road","lat":46.5557611,"lon":15.6459056,"prec":"surveyed","loc":"Maribor","crosses":"Drava","carries":"City road","built":1913,"len_m":null,"span_m":null,"typ":"Steel deck arch","note":"Maribor's principal historic Drava crossing.","cls":"ctx","role":"Notable Slovenian structure","src":["maribor_old_s0"],"p":[695.54,162.48],"tm":[549525.7,157549.4],"reg":"SI032","dom":"bridge","doms":["bridge"]},{"id":"crnuce","n":"Črnuče Bridge","sl":"Črnuški most","cat":"road","lat":46.1006139,"lon":14.519075,"prec":"surveyed","loc":"Ljubljana","crosses":"Sava","carries":"City road","built":1906,"len_m":143,"span_m":null,"typ":"Road bridge","note":"Upstream of Tomačevo on the same reach of the Sava.","cls":"ctx","role":"Notable Slovenian structure","src":["crnuce_s0"],"p":[361.75,357.58],"tm":[462817.3,106871.1],"reg":"SI041","dom":"bridge","doms":["bridge"]},{"id":"borovnica","n":"Borovnica Viaduct","sl":"Borovniški viadukt","cat":"rail","lat":45.919297,"lon":14.364654,"prec":"surveyed","loc":"Borovnica","crosses":"Borovnica valley","carries":"Southern Railway","built":1856,"len_m":561,"span_m":null,"typ":"Two-storey masonry arcade, 47 arches","note":"Dismantled by 1950 after wartime damage. A single pier still stands.","cls":"ctx","role":"Notable Slovenian structure","src":["borovnica_s0"],"p":[315.17,434.83],"tm":[450717.5,86803.3],"reg":"SI041","dom":"bridge","doms":["bridge"]},{"id":"dragon","n":"Dragon Bridge","sl":"Zmajski most","cat":"road","lat":46.052,"lon":14.51,"prec":"surveyed","loc":"Ljubljana","crosses":"Ljubljanica","carries":"City road","built":1901,"len_m":33,"span_m":33,"typ":"Reinforced concrete deck arch","note":"One of the earliest reinforced concrete bridges in Europe.","cls":"ctx","role":"Notable Slovenian structure","src":["dragon_s0"],"p":[358.92,378.36],"tm":[462082.4,101472.4],"reg":"SI041","dom":"bridge","doms":["bridge"]},{"id":"triple","n":"Triple Bridge","sl":"Tromostovje","cat":"foot","lat":46.051,"lon":14.506,"prec":"surveyed","loc":"Ljubljana","crosses":"Ljubljanica","carries":"Pedestrian and city road","built":1842,"len_m":null,"span_m":null,"typ":"Masonry and concrete deck arch","note":"Plečnik added the two flanking footbridges in 1932.","cls":"ctx","role":"Notable Slovenian structure","src":["triple_s0"],"p":[357.72,378.78],"tm":[461772.1,101363.1],"reg":"SI041","dom":"bridge","doms":["bridge"]},{"id":"hradecky","n":"Hradecky Bridge","sl":"Hradeckega most","cat":"foot","lat":46.044356,"lon":14.50575,"prec":"surveyed","loc":"Ljubljana","crosses":"Ljubljanica","carries":"Footbridge","built":1867,"len_m":33,"span_m":33,"typ":"Cast iron deck arch","note":"Slovenia's oldest surviving iron bridge. Relocated twice, most recently in 2011.","cls":"ctx","role":"Notable Slovenian structure","src":["hradecky_s0"],"p":[357.63,381.62],"tm":[461748.2,100624.8],"reg":"SI041","dom":"bridge","doms":["bridge"]}],"meta":{"built":"September 2026","area_km2":20273.6,"muns":212,"n":29,"np":67,"ng":8,"aris_total":145,"researchers":200},"src":{"sensors2023":{"k":"journal","a":"Hekič, D., Anžlin, A., Kreslin, M., Žnidarič, A. and Češarek, P.","y":2023,"t":"Model updating concept using bridge weigh-in-motion data","c":"Sensors","d":"23(4), 2067","doi":"10.3390/s23042067","u":"https://doi.org/10.3390/s23042067"},"sensors2024":{"k":"journal","a":"Hekič, D., Ribeiro, D., Anžlin, A., Žnidarič, A. and Češarek, P.","y":2024,"t":"Improved finite element model updating of a highway viaduct using acceleration and strain data","c":"Sensors","d":"24(9), 2788","doi":"10.3390/s24092788","u":"https://doi.org/10.3390/s24092788"},"appsci2025":{"k":"journal","a":"Hekič, D., Kalin, J., Žnidarič, A., Češarek, P. and Anžlin, A.","y":2025,"t":"Model updating of bridges using measured influence lines","c":"Applied Sciences","d":"15(8), 4514","doi":"10.3390/app15084514","u":"https://doi.org/10.3390/app15084514"},"iabmas2024":{"k":"conference","a":"Đukić, Đ., Hekič, D., Kosič, M., Vezočnik, R., Anžlin, A., Štrukelj, A., Pipenbaher, M. and Weingerl, T.","y":2024,"t":"Load testing of the first stress ribbon bridge in Slovenia","c":"Bridge Maintenance, Safety, Management, Life-Cycle Sustainability and Innovations, Proceedings of IABMAS 2024, Copenhagen","d":"pp. 418-425, CRC Press","doi":null,"u":"https://dirros.openscience.si/IzpisGradiva.php?lang=eng&id=20205"},"ucd2009":{"k":"conference","a":"OBrien, E. J., González, A., Dowling, J. and Žnidarič, A.","y":2009,"t":"Direct measurement of dynamics in road bridges using a bridge weigh-in-motion system","c":"University College Dublin research repository, with ZAG Ljubljana","d":null,"doi":null,"u":"https://researchrepository.ucd.ie/rest/bitstreams/17030/retrieve"},"bilten2024":{"k":"report","a":"Zavod za gradbeništvo Slovenije","y":2024,"t":"ZAG bilten 2024","c":"ZAG institutional bulletin","d":null,"doi":null,"u":"https://www.zag.si/dl/ZAG-bilten-2024.pdf"},"lp2021":{"k":"report","a":"Zavod za gradbeništvo Slovenije","y":2022,"t":"Letno poročilo za leto 2021","c":"ZAG annual report","d":null,"doi":null,"u":"https://www.zag.si/wp-content/uploads/2022/09/Letno-porocilo-2021.pdf"},"zagbridges":{"k":"inst","a":"Zavod za gradbeništvo Slovenije","y":null,"t":"The Section for Bridges and Other Civil Engineering Structures","c":"zag.si","d":null,"doi":null,"u":"https://www.zag.si/en/organizational-units/the-department-of-structures/the-section-for-bridges-and-other-civil-engineering-structures-2/"},"dewesoft":{"k":"web","a":"Dewesoft","y":2024,"t":"Bridge weigh-in-motion and structural health monitoring on Tomačevo bridge","c":"dewesoft.com","d":null,"doi":null,"u":"https://dewesoft.com/blog/bridge-weigh-in-motion-structural-health-monitoring-tomacevo-bridge"},"kolektor":{"k":"web","a":"Kolektor Gradbeništvo","y":null,"t":"Rekonstrukcija avtoceste Unec-Postojna z rehabilitacijo viadukta Ravbarkomanda","c":"kolektorgradbenistvo.si","d":null,"doi":null,"u":"https://www.kolektorgradbenistvo.si/reference/rekonstrukcija-avtoceste-unec-postojna-z-rehabilitacijo-viadukta-ravbarkomanda"},"freyssinet":{"k":"web","a":"Freyssinet","y":2023,"t":"Krka river stress-ribbon footbridge, Novo mesto","c":"freyssinet.com","d":null,"doi":null,"u":"https://www.freyssinet.com/case-study/krka-river-stress-ribbon-footbridge/"},"structurae_ck":{"k":"web","a":"Structurae","y":null,"t":"Črni Kal Viaduct","c":"structurae.net","d":null,"doi":null,"u":"https://structurae.net/en/structures/crni-kal-viaduct"},"wp_bridges":{"k":"web","a":"Wikipedia contributors","y":null,"t":"List of bridges in Slovenia","c":"en.wikipedia.org","d":null,"doi":null,"u":"https://en.wikipedia.org/wiki/List_of_bridges_in_Slovenia"},"stareslike":{"k":"web","a":"Stare slike, Cerknica","y":2023,"t":"1971 Ravbarkomanda, avtocestni viadukt","c":"stareslike.cerknica.org","d":null,"doi":null,"u":"https://stareslike.cerknica.org/2023/03/21/1971-ravbarkomanda-avtocestni-viadukt/"},"wp_zlat":{"k":"web","a":"Wikipedia contributors","y":null,"t":"Zlatoličje","c":"en.wikipedia.org","d":null,"doi":null,"u":"https://en.wikipedia.org/wiki/Zlatoli%C4%8Dje"},"wp_vuh":{"k":"web","a":"Wikipedia contributors","y":null,"t":"Vuhred","c":"en.wikipedia.org","d":null,"doi":null,"u":"https://en.wikipedia.org/wiki/Vuhred"},"ulfgg_s0":{"k":"web","a":null,"y":null,"t":"UL FGG","c":null,"d":null,"doi":null,"u":"https://www.fgg.uni-lj.si/en/"},"ijs_s0":{"k":"web","a":null,"y":null,"t":"IJS","c":null,"d":null,"doi":null,"u":"https://www.ijs.si"},"izum_s0":{"k":"web","a":null,"y":null,"t":"IZUM","c":null,"d":null,"doi":null,"u":"https://www.izum.si/en/hpc-en/"},"solkan_s0":{"k":"web","a":null,"y":null,"t":"List of bridges in Slovenia, Wikipedia","c":null,"d":null,"doi":null,"u":"https://en.wikipedia.org/wiki/List_of_bridges_in_Slovenia"},"puch_s0":{"k":"web","a":null,"y":null,"t":"List of bridges in Slovenia, Wikipedia","c":null,"d":null,"doi":null,"u":"https://en.wikipedia.org/wiki/List_of_bridges_in_Slovenia"},"maribor_old_s0":{"k":"web","a":null,"y":null,"t":"List of bridges in Slovenia, Wikipedia","c":null,"d":null,"doi":null,"u":"https://en.wikipedia.org/wiki/List_of_bridges_in_Slovenia"},"crnuce_s0":{"k":"web","a":null,"y":null,"t":"List of bridges in Slovenia, Wikipedia","c":null,"d":null,"doi":null,"u":"https://en.wikipedia.org/wiki/List_of_bridges_in_Slovenia"},"borovnica_s0":{"k":"web","a":null,"y":null,"t":"List of bridges in Slovenia, Wikipedia","c":null,"d":null,"doi":null,"u":"https://en.wikipedia.org/wiki/List_of_bridges_in_Slovenia"},"dragon_s0":{"k":"web","a":null,"y":null,"t":"List of bridges in Slovenia, Wikipedia","c":null,"d":null,"doi":null,"u":"https://en.wikipedia.org/wiki/List_of_bridges_in_Slovenia"},"triple_s0":{"k":"web","a":null,"y":null,"t":"List of bridges in Slovenia, Wikipedia","c":null,"d":null,"doi":null,"u":"https://en.wikipedia.org/wiki/List_of_bridges_in_Slovenia"},"hradecky_s0":{"k":"web","a":null,"y":null,"t":"List of bridges in Slovenia, Wikipedia","c":null,"d":null,"doi":null,"u":"https://en.wikipedia.org/wiki/List_of_bridges_in_Slovenia"},"zag_intl":{"k":"inst","a":"Zavod za gradbeništvo Slovenije","y":null,"t":"International research projects","c":"zag.si","d":null,"doi":null,"u":"https://www.zag.si/en/research-and-development/research-projects/international-projects/"},"zag_nat":{"k":"inst","a":"Zavod za gradbeništvo Slovenije","y":null,"t":"National research projects","c":"zag.si","d":null,"doi":null,"u":"https://www.zag.si/en/research-and-development/research-projects/national-projects/"},"zag_12":{"k":"inst","a":"Zavod za gradbeništvo Slovenije","y":2023,"t":"ZAG in 12 research projects","c":"zag.si","d":null,"doi":null,"u":"https://www.zag.si/en/zag-in-12-research-projects/"},"cordis_frissbe":{"k":"report","a":"European Commission","y":2021,"t":"Fire-safe Sustainable Built Environment, FRISSBE","c":"CORDIS","d":"H2020 ERA Chairs, grant agreement 952395","doi":null,"u":"https://cordis.europa.eu/project/id/952395"},"cordis_bridgitise":{"k":"report","a":"European Commission","y":2024,"t":"Industrial Doctoral Network on Bridge Digitalised Integrity Management, BRIDGITISE","c":"CORDIS","d":"HORIZON MSCA, grant agreement 101119554","doi":null,"u":"https://cordis.europa.eu/project/id/101119554"},"frissbe_web":{"k":"web","a":"FRISSBE","y":null,"t":"FRISSBE project site","c":"frissbe.eu","d":null,"doi":null,"u":"https://www.frissbe.eu/"},"bridgitise_web":{"k":"web","a":"Politecnico di Milano","y":null,"t":"BRIDGITISE project site","c":"bridgitise.polimi.it","d":null,"doi":null,"u":"https://www.bridgitise.polimi.it/"},"innorenew":{"k":"web","a":"InnoRenew CoE","y":null,"t":"InnoRenew CoE, institute","c":"innorenew.eu","d":null,"doi":null,"u":"https://innorenew.eu/about/institute/"},"izs_puh":{"k":"web","a":"Inženirska zbornica Slovenije","y":null,"t":"Puhov most na Ptuju, primeri dobre prakse","c":"arhiv.izs.si","d":null,"doi":null,"u":"https://arhiv.izs.si/dobra-praksa/primeri-dobre-prakse/inzenirski-objekti/puhov-most-na-ptuju/"},"zag_bridges_svc":{"k":"inst","a":"Zavod za gradbeništvo Slovenije","y":null,"t":"Bridges, areas of expertise","c":"zag.si","d":null,"doi":null,"u":"https://www.zag.si/en/areas-of-expertise/bridges/"},"cestel":{"k":"web","a":"Cestel d.o.o.","y":null,"t":"SiWIM bridge weigh-in-motion system","c":"cestel.si","d":null,"doi":null,"u":"https://cestel.si/en/siwim/"},"zag_nat2":{"k":"inst","a":"Zavod za gradbenistvo Slovenije","y":null,"t":"National research projects register","c":"zag.si","d":null,"doi":null,"u":"https://www.zag.si/en/research-and-development/research-projects/national-projects/"},"sicris_org":{"k":"report","a":"SICRIS, Slovenian Current Research Information System","y":null,"t":"Zavod za gradbenistvo Slovenije, organisation record 743","c":"cris.cobiss.net","d":"200 researchers in 8 research groups, 145 ARIS projects recorded","doi":null,"u":"https://cris.cobiss.net/ecris/si/sl/organization/743"},"sicris_p2":{"k":"report","a":"SICRIS","y":null,"t":"Gradbeni objekti in materiali, research programme P2-0273","c":"cris.cobiss.net","d":"ARIS research programme, 2019 to 2027, leader Andraz Legat","doi":null,"u":"https://cris.cobiss.net/ecris/si/sl/project/17642"}},"domains":{"bridge":{"n":"Bridges and viaducts","d":"Structural assessment, load testing, inspection and rehabilitation of bridges"},"ai":{"n":"AI, data and monitoring","d":"Bridge weigh-in-motion, structural health monitoring, digital twins and machine learning"},"build":{"n":"Buildings and structures","d":"Building physics, seismic safety, glazing, acoustics and indoor air"},"mat":{"n":"Materials and circularity","d":"Cements, concrete, metals, timber, ashes and recycled construction materials"},"fire":{"n":"Fire safety","d":"Fire resistance and reaction to fire of products, assemblies and timber"},"geo":{"n":"Geotechnics and ground","d":"Slopes, rockfall, soils, rail substructure, mine sites and coastal cliffs"},"energy":{"n":"Hydropower and energy","d":"Dams, run of river plants and the grouts and concretes they are built with"},"herit":{"n":"Cultural heritage","d":"Conservation of monuments, murals, stone masonry and historic materials"},"inst":{"n":"Institutions and laboratories","d":"ZAG premises and the partner organisations the register refers to"}},"projects":[{"id":"bridgitise","ac":"BRIDGITISE","t":"Industrial doctoral network on bridge digitalised integrity management","fund":"Horizon Europe MSCA, grant 101119554, EU contribution 4.02 million euro","y":"2024 to 2027","dom":"ai","role":"Beneficiary","lead":"Andrej Anžlin","d":"Fifteen doctoral projects across fourteen partners, grouped into low cost data collection, AI and IoT for bridges, and digital decision support. Coordinated by Politecnico di Milano. Cestel is an industrial partner and ZAG hosts doctoral candidates.","sites":["zag","cestel","ulfgg"],"src":["cordis_bridgitise","bridgitise_web"],"kind":"project"},{"id":"bridgemon","ac":"BRIDGEMON","t":"Bridge safety monitoring","fund":"EU Seventh Framework Programme","y":"2012 to 2014","dom":"ai","role":"Partner","lead":"Aleš Žnidarič","d":"Improved bridge monitoring and weigh-in-motion methods for network level assessment.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"trimm","ac":"TRIMM","t":"Tomorrow's road infrastructure monitoring and management","fund":"EU Seventh Framework Programme","y":"2011 to 2014","dom":"ai","role":"Partner","lead":"Aleš Žnidarič","d":"Network level monitoring of road infrastructure.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"shmvalue","ac":"SHM value","t":"Quantifying the value of structural health monitoring","fund":"COST Action","y":"2014 to 2018","dom":"ai","role":"Partner","lead":"Aleš Žnidarič","d":"European action on when monitoring is worth its cost.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"bim4ce","ac":"BIM4CE","t":"Bridge monitoring using real time data and digital twins","fund":"Interreg Central Europe","y":"2022 to 2025","dom":"ai","role":"Partner","lead":"Mirko Kosič","d":"Digital twins of bridges fed by live monitoring data.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"augccam","ac":"AUGMENTED CCAM","t":"Augmenting and evaluating the physical and digital infrastructure for connected automated mobility","fund":"Horizon Europe","y":"2022 to 2025","dom":"ai","role":"Partner","lead":"Darko Kokot","d":"Prepares road infrastructure, physical and digital, for automated vehicles.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"infracoms","ac":"INFRACOMS","t":"Innovative and future proof road asset condition monitoring systems","fund":"CEDR","y":"2022 to 2024","dom":"ai","role":"Partner","lead":"Darko Kokot","d":"Condition monitoring systems for road assets.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"circuit","ac":"CIRCUIT","t":"Holistic approach to foster circular and resilient transport infrastructures","fund":"Horizon Europe, cluster 5","y":"2023 to 2027","dom":"mat","role":"Partner","lead":"Lucija Hanžič","d":"Circular practice in transport infrastructure. The demonstration in Slovenia reused girders salvaged from a demolished bridge in a new bridge at Črna na Koroškem.","sites":["zag","crna"],"src":["zag_intl","bilten2024"],"kind":"project"},{"id":"overflow","ac":"oVERFLOw","t":"Vulnerability assessment of embankments and bridges exposed to flooding hazards","fund":"Horizon 2020","y":"2019 to 2021","dom":"bridge","role":"Partner","lead":"Andrej Anžlin","d":"How flooding damages embankments and bridge foundations, and how to assess the risk.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"bridgespec","ac":"BridgeSpec","t":"Quality specifications for roadway bridges, standardisation at a European level","fund":"COST Action","y":"2015 to 2019","dom":"bridge","role":"Partner","lead":"Andrej Anžlin","d":"European work towards common quality specifications for road bridges.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"arches","ac":"ARCHES","t":"Assessment and rehabilitation of Central European highway structures","fund":"EU Sixth Framework Programme","y":"2006 to 2009","dom":"bridge","role":"Partner","lead":"Aljoša Šajna","d":"Assessment and repair methods for motorway structures in central Europe.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"regen","ac":"RE-GEN","t":"Risk assessment of ageing infrastructure","fund":"CEDR transnational research","y":"2014 to 2016","dom":"bridge","role":"Partner","lead":"Aleš Žnidarič","d":"Risk based management of ageing road structures.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"adriseismic","ac":"ADRISEISMIC","t":"New approaches for seismic improvement and renovation of Adriatic urban centres","fund":"Interreg ADRION","y":"2020 to 2022","dom":"build","role":"Partner","lead":"Andrej Anžlin","d":"Seismic strengthening of buildings and structures around the Adriatic.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"crosscade","ac":"CROSScade","t":"Cross border cascading risk management for critical infrastructure","fund":"Union Civil Protection Mechanism","y":"2022 to 2024","dom":"bridge","role":"Partner","lead":"Mirko Kosič","d":"How failures in one piece of infrastructure cascade across borders.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"frissbe","ac":"FRISSBE","t":"Fire safe sustainable built environment","fund":"Horizon 2020 ERA Chairs, grant 952395, 2.50 million euro","y":"2021 to 2026","dom":"fire","role":"Coordinator","lead":"Andraž Legat, ERA Chair Grunde Jomaas","d":"The ERA Chair that built ZAG's fire research department. It funds three doctoral candidates and six post doctoral posts, and works out of the new fire laboratory in Logatec.","sites":["zag","zag_logatec"],"src":["cordis_frissbe","frissbe_web"],"kind":"project"},{"id":"exfires","ac":"EXFires","t":"Exploration fire safety","fund":"European Space Agency","y":"2022 to 2024","dom":"fire","role":"Partner","lead":"Grunde Jomaas","d":"Fire safety for space exploration environments.","sites":["zag","zag_logatec"],"src":["zag_intl"],"kind":"project"},{"id":"livinglab","ac":"LivingLab fire","t":"New cross border LivingLab for fire response research","fund":"Interreg Slovenia Austria","y":"2018 to 2020","dom":"fire","role":"Partner","lead":"Friderik Knez","d":"Shared fire response research facility across the Slovenian and Austrian border.","sites":["zag","zag_gameljne"],"src":["zag_intl"],"kind":"project"},{"id":"geolab","ac":"GEOLAB","t":"Enhancing Europe's critical infrastructure, geotechnical research facilities","fund":"Horizon 2020","y":"2021 to 2025","dom":"geo","role":"Partner","lead":"Stanislav Lenart","d":"Opens geotechnical laboratories across Europe to shared use.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"assets4rail","ac":"Assets4Rail","t":"Measuring, monitoring and data handling for railway assets","fund":"Horizon 2020 Shift2Rail","y":"2018 to 2021","dom":"geo","role":"Partner","lead":"Stanislav Lenart","d":"Monitoring of bridges, tunnels and track for railway asset managers.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"potrog","ac":"POTROG","t":"Seismic risk in Slovenia for civil protection","fund":"Ministry of Defence","y":"2011 to 2018","dom":"build","role":"Coordinator","lead":"Marjanca Lutman","d":"National seismic risk assessment used by the civil protection service, run in several phases.","sites":["zag"],"src":["zag_nat"],"kind":"project"},{"id":"vodpreg","ac":"VODPREG","t":"Earth and concrete water dams of strategic importance in Slovenia","fund":"National","y":"2011 to 2012","dom":"energy","role":"Coordinator","lead":"Mojca Ravnikar Turk","d":"Survey of the condition of Slovenia's strategically important dams.","sites":["zag","he_solkan","he_zlatolicje","he_vuhred"],"src":["zag_nat"],"kind":"project"},{"id":"endurcrete","ac":"EnDurCrete","t":"New environmentally friendly and durable concrete integrating industrial by products","fund":"Horizon 2020","y":"2018 to 2021","dom":"mat","role":"Partner","lead":"Andraž Legat","d":"Durable low carbon concrete using industrial by products.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"ashcycle","ac":"AshCycle","t":"Integration of underutilised ashes into material cycles","fund":"Horizon Europe","y":"2022 to 2026","dom":"mat","role":"Partner","lead":"Vilma Ducman","d":"Turns ash streams into construction materials.","sites":["zag"],"src":["zag_intl"],"kind":"project"},{"id":"innorenew_p","ac":"InnoRenew CoE","t":"Renewable materials and healthy environments research and innovation centre of excellence","fund":"Horizon 2020 teaming","y":"2017 to 2022","dom":"mat","role":"Partner","lead":"Friderik Knez","d":"Founding of the InnoRenew centre in Izola, with ZAG among the partners.","sites":["zag","innorenew"],"src":["zag_intl","innorenew"],"kind":"project"},{"id":"print3d","ac":"2F-3D Print, L2-50045","t":"Two filament 3D printing with concrete and earth","fund":"Slovenian Research and Innovation Agency, L2-50045","y":"2023 to 2026","dom":"mat","role":"Coordinator","lead":"Lucija Hanžič","d":"Dual nozzle printing that combines concrete and earth based materials.","sites":["zag"],"src":["zag_12"],"kind":"project"},{"id":"tigr","ac":"TIGR","t":"Sustainable and innovative construction","fund":"Ministry of Higher Education, Science and Technology","y":"2011 to 2013","dom":"mat","role":"Coordinator","lead":"Friderik Knez","d":"National programme on sustainable construction practice.","sites":["zag"],"src":["zag_nat"],"kind":"project"},{"id":"p2_0273","ac":"P2-0273","t":"Gradbeni objekti in materiali, building structures and materials","fund":"ARIS research programme","y":"2019 to 2027","dom":"build","role":"Host","lead":"Andraz Legat","d":"The umbrella research programme that funds ZAG as a public research institute. It covers sustainable construction, smart buildings and cities, transport and energy infrastructure, fire and earthquake engineering, flood and landslide protection, heritage conservation and new materials.","sites":["zag"],"src":["sicris_p2","sicris_org"],"kind":"programme"},{"id":"j7_50096","ac":"BrAId, J7-50096","t":"Improving B-WIM performance with big data and artificial intelligence","fund":"ARIS","y":"2023 to 2026","dom":"ai","role":"Coordinator","lead":"Ales Znidaric","d":"Applies machine learning to bridge weigh-in-motion data so the weights are reliable enough for legal enforcement, not only for statistics.","sites":["zag","tomacevo","ravbarkomanda","cestel"],"src":["zag_12","zag_nat2"],"kind":"project"},{"id":"j2_2490","ac":"DataBridge, J2-2490","t":"Data driven modelling of the behaviour of building structures","fund":"ARIS","y":"2020 to 2023","dom":"ai","role":"Coordinator","lead":"Uros Bohinc","d":"Data driven models of structural behaviour, run with UL FGG.","sites":["zag","ulfgg"],"src":["zag_nat2"],"kind":"project"},{"id":"j2_9224","ac":"J2-9224","t":"Multiparametric dynamic modelling of stratified strongly inhomogeneous elastic structures","fund":"ARIS","y":"2018 to 2021","dom":"build","role":"Coordinator","lead":"Uros Bohinc","d":"Dynamic models for layered structures with strongly varying stiffness.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j2_8170","ac":"J2-8170","t":"Nonlinear dynamics of spatial frames with complete kinematic compatibility","fund":"ARIS","y":"2017 to 2020","dom":"build","role":"Coordinator","lead":"Matija Gams","d":"Nonlinear frame dynamics for demanding industrial applications.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"v2_2257","ac":"V2-2257","t":"Strategic bases for reducing the seismic hazard of justice buildings in Slovenia","fund":"ARIS","y":"2022 to 2025","dom":"build","role":"Coordinator","lead":"Meta Krzan","d":"Seismic assessment and strengthening priorities for Slovenian court buildings.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"l2_3172","ac":"L2-3172","t":"Development of technical guidelines for quadruple glazing","fund":"ARIS","y":"2021 to 2024","dom":"build","role":"Coordinator","lead":"Sabina Jordan","d":"Thermal, optical and structural guidance for four pane glazing units.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"n2_0258","ac":"N2-0258","t":"Thermal properties and lifetime impact of alternative hybrid eco-nanomaterials","fund":"ARIS","y":"2022 to 2025","dom":"build","role":"Coordinator","lead":"Sabina Jordan","d":"Thermal behaviour and life cycle impact of hybrid nanomaterials in buildings.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"v3_2234","ac":"V3-2234","t":"Risk to human health from the properties of the domestic water supply system","fund":"ARIS","y":"2022 to 2025","dom":"build","role":"Coordinator","lead":"Mirjam Bajt Leban","d":"Health risk from materials in drinking water installations.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"v3_2323","ac":"V3-2323","t":"Methodology for assessing health risk from volatile and semi volatile organic compounds","fund":"ARIS","y":"2023 to 2024","dom":"build","role":"Coordinator","lead":"Peter Nadrah","d":"Release of VOCs and SVOCs from construction and finishing materials into indoor air.","sites":["zag"],"src":["zag_12","zag_nat2"],"kind":"project"},{"id":"v2_2350","ac":"V2-2350","t":"Ensuring the quality of sustainable timber construction","fund":"ARIS and the ministry","y":"2023 to 2024","dom":"build","role":"Coordinator","lead":"Tomaz Pazlar","d":"Reviews timber construction standards and proposes quality assurance guidance.","sites":["zag"],"src":["zag_12","zag_nat2"],"kind":"project"},{"id":"j4_50132","ac":"WoDeFi, J4-50132","t":"Thermo hydro mechanically densified wood with improved fire performance","fund":"ARIS","y":"2023 to 2026","dom":"fire","role":"Partner","lead":"Ulises Rojas Alva","d":"Densified wood products with better mechanical and fire behaviour.","sites":["zag","zag_logatec"],"src":["zag_12","zag_nat2"],"kind":"project"},{"id":"j2_50063","ac":"J2-50063","t":"Sustainable long term use of timber structures, fire and post fire solutions","fund":"ARIS","y":"2023 to 2026","dom":"fire","role":"Partner","lead":"Urska Blumauer","d":"Experiments and numerical models for timber structures during and after fire.","sites":["zag","zag_logatec"],"src":["zag_12","zag_nat2"],"kind":"project"},{"id":"l2_50046","ac":"L2-50046","t":"Fire performance of building envelope systems, ETICS with expanded polystyrene","fund":"ARIS with Rockwool","y":"2023 to 2026","dom":"fire","role":"Coordinator","lead":"Grunde Jomaas","d":"Large scale fire tests of external thermal insulation composite systems used across Europe.","sites":["zag","zag_logatec"],"src":["zag_12","zag_nat2"],"kind":"project"},{"id":"j1_2477","ac":"J1-2477","t":"Erosion processes on coastal flysch cliffs with risk assessment","fund":"ARIS","y":"2020 to 2023","dom":"geo","role":"Coordinator","lead":"Karmen Fifer Bizjak","d":"Erosion and rockfall on the flysch cliffs of the Slovenian coast, with a risk assessment method. The Sveti Kriz bay rockfall at Strunjan sits in this line of work.","sites":["zag","strunjan"],"src":["zag_nat2"],"kind":"project"},{"id":"v2_1740","ac":"V2-1740","t":"Development of an innovative railway sleeper","fund":"ARIS","y":"2018 to 2021","dom":"geo","role":"Coordinator","lead":"Stanislav Lenart","d":"A new sleeper design for Slovenian railway track.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j1_50032","ac":"J1-50032","t":"Geological and lithogeochemical characterisation of Slovenian dolomites","fund":"ARIS","y":"2023 to 2026","dom":"geo","role":"Coordinator","lead":"Lea Zibret","d":"Assesses whether magnesium can be produced from domestic dolomite deposits.","sites":["zag"],"src":["zag_12","zag_nat2"],"kind":"project"},{"id":"l7_3185","ac":"L7-3185","t":"Interconnected processes for sustainable management of sewage sludge","fund":"ARIS","y":"2021 to 2024","dom":"geo","role":"Coordinator","lead":"Primoz Oprckal","d":"Turning sewage sludge into usable material rather than waste.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j7_50228","ac":"J7-50228","t":"Mining the technosphere for efficient use of resources","fund":"ARIS","y":"2023 to 2026","dom":"mat","role":"Coordinator","lead":"Ana Mladenovic","d":"Enhanced landfill mining to recover secondary raw materials while rehabilitating landfills.","sites":["zag","sitarjevec"],"src":["zag_12","zag_nat2"],"kind":"project"},{"id":"j2_9196","ac":"J2-9196","t":"Massive concrete, optimising technology with advanced testing methods","fund":"ARIS","y":"2018 to 2021","dom":"mat","role":"Coordinator","lead":"Ana Mladenovic","d":"Heat of hydration and cracking control in massive concrete pours.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"z2_2641","ac":"Z2-2641","t":"Crevice corrosion mechanisms at the steel to concrete interface","fund":"ARIS","y":"2020 to 2022","dom":"mat","role":"Coordinator","lead":"Miha Hren","d":"How corrosion starts in the gap between reinforcement and concrete.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j2_9211","ac":"J2-9211","t":"Improving the properties of metallic materials by subcooling","fund":"ARIS","y":"2018 to 2021","dom":"mat","role":"Coordinator","lead":"Tadeja Kosec","d":"Subcooling treatments for better metal performance.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j1_3026","ac":"J1-3026","t":"Applicability of the cold sintering process to clay minerals","fund":"ARIS","y":"2021 to 2024","dom":"mat","role":"Coordinator","lead":"Vilma Ducman","d":"Low temperature sintering of clays for construction ceramics.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j2_3035","ac":"J2-3035","t":"Synthesis of alkali activated materials with microwave heating","fund":"ARIS","y":"2021 to 2024","dom":"mat","role":"Coordinator","lead":"Barbara Horvat","d":"Microwave curing of alkali activated binders made from industrial residues.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"z2_3199","ac":"Z2-3199","t":"Immobilisation and leaching of toxic trace elements in alkali activated materials","fund":"ARIS","y":"2021 to 2023","dom":"mat","role":"Coordinator","lead":"Majda Pavlin","d":"Whether heavy metals stay bound in alkali activated binders.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j1_4413","ac":"J1-4413","t":"Hydraulic properties of ashes from thermal processes and their reactivity","fund":"ARIS","y":"2022 to 2025","dom":"mat","role":"Coordinator","lead":"Vesna Zalar Serjun","d":"Making ash streams react as binders instead of going to landfill.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j1_3029","ac":"J1-3029","t":"Holistic sustainability evaluation of critical raw materials","fund":"ARIS","y":"2021 to 2024","dom":"mat","role":"Coordinator","lead":"Alenka Mauko Pranjic","d":"New methods for judging the sustainability of critical raw materials.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j1_9179","ac":"J1-9179","t":"Non traditional isotopes as identifiers of authigenic carbonates","fund":"ARIS","y":"2018 to 2021","dom":"mat","role":"Coordinator","lead":"Vilma Ducman","d":"Isotope fingerprinting of carbonate formation.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"l4_7547","ac":"L4-7547","t":"Behaviour of wood and lignocellulosic composites in outdoor conditions","fund":"ARIS","y":"2016 to 2019","dom":"mat","role":"Coordinator","lead":"Andrijana Sever Skapin","d":"Weathering of timber and wood composites outdoors.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j4_4546","ac":"J4-4546","t":"Protein adhesives for high performance interior wooden structures","fund":"ARIS","y":"2022 to 2025","dom":"mat","role":"Coordinator","lead":"Andreja Pondelak","d":"Bio based adhesives to replace formaldehyde resins indoors.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"v4_2270","ac":"V4-2270","t":"Wood in green public procurement for a climate neutral society","fund":"ARIS","y":"2022 to 2025","dom":"mat","role":"Coordinator","lead":"Katja Malovrh Rebec","d":"How public buyers can specify timber to cut embodied carbon.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j7_50231","ac":"GROWTH, J7-50231","t":"Growth potential and wood properties of tree species of various provenances","fund":"ARIS","y":"2024 to 2027","dom":"mat","role":"Partner","lead":"Andrijana Sever Skapin","d":"Tree resilience to climate change and wood modification for decay and fire resistance.","sites":["zag"],"src":["zag_12"],"kind":"project"},{"id":"j1_50014","ac":"microBIOplast, J1-50014","t":"Effects of biodegradable microplastics on freshwater and terrestrial organisms","fund":"ARIS","y":"2023 to 2026","dom":"mat","role":"Partner","lead":"Andrijana Sever Skapin","d":"Ecological effects of biodegradable microplastics.","sites":["zag"],"src":["zag_12"],"kind":"project"},{"id":"j1_2482","ac":"J1-2482","t":"Effect of nano and micro plastics on terrestrial invertebrates","fund":"ARIS","y":"2020 to 2023","dom":"mat","role":"Coordinator","lead":"Andrijana Sever Skapin","d":"Environmentally relevant plastic particles and soil fauna.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"n2_0188","ac":"N2-0188","t":"CO2 transformation to valuable chemicals by catalytic and photocatalytic routes","fund":"ARIS","y":"2021 to 2024","dom":"mat","role":"Coordinator","lead":"Andrijana Sever Skapin","d":"Turning carbon dioxide into useful chemicals.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"nc_0017","ac":"NC-0017","t":"Photocatalytic heterostructured nanomaterials for solar energy harvesting","fund":"ARIS","y":"2021 to 2023","dom":"mat","role":"Coordinator","lead":"Andrijana Sever Skapin","d":"Nanomaterials that harvest sunlight for photocatalysis.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"z1_8149","ac":"Z1-8149","t":"Colorimetric determination of relative humidity with mesoporous silica","fund":"ARIS","y":"2017 to 2019","dom":"mat","role":"Coordinator","lead":"Erika Svara Fabjan","d":"A colour changing humidity indicator based on mesoporous silica.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j7_9404","ac":"J7-9404","t":"Bronze monuments protection in a changing environment","fund":"ARIS","y":"2018 to 2021","dom":"herit","role":"Coordinator","lead":"Tadeja Kosec","d":"Protective coatings and corrosion control for outdoor bronze monuments.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j2_4424","ac":"J2-4424","t":"An integrated approach to the conservation of cultural heritage murals","fund":"ARIS","y":"2022 to 2025","dom":"herit","role":"Coordinator","lead":"Andreja Pondelak","d":"Consolidation and conservation of wall paintings.","sites":["zag"],"src":["zag_nat2"],"kind":"project"},{"id":"j7_50226","ac":"J7-50226","t":"Next generation analytical tools for heritage science","fund":"ARIS","y":"2023 to 2026","dom":"herit","role":"Partner","lead":"Lidija Korat","d":"Four new analytical methods for understanding historic materials.","sites":["zag"],"src":["zag_12"],"kind":"project"},{"id":"hesci","ac":"HeSci","t":"Heritage science","fund":"European Union","y":"2023 to 2026","dom":"herit","role":"Partner","lead":"Lucia Mancini","d":"European heritage science infrastructure and methods.","sites":["zag"],"src":["zag_intl"],"kind":"project"}],"groups":[{"id":"g_struct","n":"Konstrukcije","en":"Structures","lead":"Ales Znidaric","pub":2494,"dom":"bridge","d":"Bridges and other engineering structures, load testing, weigh-in-motion and monitoring."},{"id":"g_stone","n":"Kamnine, veziva in keramika","en":"Stone, binders and ceramics","lead":"Vilma Ducman","pub":2541,"dom":"mat","d":"Aggregates, cements, alkali activated binders, ceramics and secondary raw materials."},{"id":"g_phys","n":"Gradbena fizika","en":"Building physics","lead":"Sabina Jordan","pub":2027,"dom":"build","d":"Thermal performance, acoustics, glazing, daylighting and indoor air quality."},{"id":"g_metal","n":"Kovine in kovinske konstrukcije","en":"Metals and metal structures","lead":"Andraz Legat","pub":1444,"dom":"mat","d":"Corrosion, steel in concrete, metal structures and protective coatings."},{"id":"g_geo","n":"Geotehnika in prometnice","en":"Geotechnics and transport infrastructure","lead":"Stanislav Lenart","pub":1312,"dom":"geo","d":"Soils, slopes, embankments, pavements and railway substructure."},{"id":"g_org","n":"Organski gradbeni materiali","en":"Organic building materials","lead":"Andrijana Sever Skapin","pub":1243,"dom":"mat","d":"Timber, polymers, coatings, adhesives and photocatalytic surfaces."},{"id":"g_conc","n":"Betoni in betonski polizdelki","en":"Concrete and precast concrete","lead":"Aljosa Sajna","pub":760,"dom":"mat","d":"Concrete technology, durability, massive concrete and precast products."},{"id":"g_metro","n":"Laboratorij za metrologijo","en":"Metrology laboratory","lead":"Miha Hiti","pub":77,"dom":"inst","d":"Force, pressure and dimensional metrology, traceable calibration."}],"peaks":[{"n":"Triglav","m":2864,"lon":13.83,"lat":46.38006,"p":[158.42,235.88]}]};
const VB = D.vb, AFF = D.aff, MPU = D.mpu;

/* ---------- projection: WGS84 <-> D96/TM (EPSG:3794) <-> canvas ---------- */
const A=6378137.0, F=1/298.257222101, E2=F*(2-F), K0=0.9999,
      LON0=15*Math.PI/180, FE=500000, FN=-5000000, EP2=E2/(1-E2);
function toTM(lon,lat){
  const p=lat*Math.PI/180, l=lon*Math.PI/180-LON0, s=Math.sin(p), c=Math.cos(p), t=Math.tan(p);
  const N=A/Math.sqrt(1-E2*s*s), T=t*t, C=EP2*c*c, a1=c*l;
  const M=A*((1-E2/4-3*E2*E2/64-5*E2*E2*E2/256)*p
      -(3*E2/8+3*E2*E2/32+45*E2*E2*E2/1024)*Math.sin(2*p)
      +(15*E2*E2/256+45*E2*E2*E2/1024)*Math.sin(4*p)
      -(35*E2*E2*E2/3072)*Math.sin(6*p));
  return [FE+K0*N*(a1+(1-T+C)*a1**3/6+(5-18*T+T*T+72*C-58*EP2)*a1**5/120),
          FN+K0*(M+N*t*(a1*a1/2+(5-T+9*C+4*C*C)*a1**4/24
                +(61-58*T+T*T+600*C-330*EP2)*a1**6/720))];
}
function fromTM(E,N){
  const M=(N-FN)/K0, e1=(1-Math.sqrt(1-E2))/(1+Math.sqrt(1-E2));
  const mu=M/(A*(1-E2/4-3*E2*E2/64-5*E2*E2*E2/256));
  const p1=mu+(3*e1/2-27*e1**3/32)*Math.sin(2*mu)
            +(21*e1*e1/16-55*e1**4/32)*Math.sin(4*mu)
            +(151*e1**3/96)*Math.sin(6*mu)+(1097*e1**4/512)*Math.sin(8*mu);
  const s=Math.sin(p1), c=Math.cos(p1), t=Math.tan(p1);
  const C1=EP2*c*c, T1=t*t, Nn=A/Math.sqrt(1-E2*s*s), R1=A*(1-E2)/Math.pow(1-E2*s*s,1.5);
  const Dd=(E-FE)/(Nn*K0);
  const lat=p1-(Nn*t/R1)*(Dd*Dd/2-(5+3*T1+10*C1-4*C1*C1-9*EP2)*Dd**4/24
        +(61+90*T1+298*C1+45*T1*T1-252*EP2-3*C1*C1)*Dd**6/720);
  const lon=LON0+(Dd-(1+2*T1+C1)*Dd**3/6
        +(5-2*C1+28*T1-3*C1*C1+8*EP2+24*T1*T1)*Dd**5/120)/c;
  return [lon*180/Math.PI, lat*180/Math.PI];
}
const toPx = (lon,lat)=>{const [e,n]=toTM(lon,lat); return [(e-AFF.minx)*AFF.k,(AFF.maxy-n)*AFF.k];};

/* ------------------------------- helpers -------------------------------- */
const $=id=>document.getElementById(id);
const NS='http://www.w3.org/2000/svg';
const el=(t,a)=>{const n=document.createElementNS(NS,t);for(const k in a)n.setAttribute(k,a[k]);return n;};
const esc=s=>{const d=document.createElement('div');d.textContent=s==null?'':String(s);return d.innerHTML;};
const CHEV='<svg class="cv" viewBox="0 0 8 13" aria-hidden="true"><path d="M1.4 1L6.6 6.5 1.4 12" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg>';

const DOMS=D.domains, PROJ=D.projects||[], SRC=D.src||{};
const GROUPS=D.groups||[];
const projCount=k=>PROJ.filter(p=>p.dom===k).length;
const mapCount=k=>entries.filter(e=>(e.doms||[e.dom]).includes(k)).length;
/* Relevance order puts the sectors closest to the bridge and monitoring work first.
   The other order is straight by project count. */
const REL=['ai','bridge','fire','mat','build','geo','herit','energy','inst'];
const byProjects=()=>Object.keys(DOMS).sort((a,b)=>
  projCount(b)-projCount(a) || mapCount(b)-mapCount(a) || DOMS[a].n.localeCompare(DOMS[b].n));
const byRelevance=()=>REL.filter(k=>DOMS[k]).concat(Object.keys(DOMS).filter(k=>!REL.includes(k)));
/* entries is declared above DOMKEYS, so mapCount is safe to call from here on */
let domOrder='relevance';
let DOMKEYS=byRelevance();
function setOrder(mode){
  domOrder=mode;
  DOMKEYS=(mode==='projects')?byProjects():byRelevance();
  buildChips(); paintMapLegend(); paint();
}
const CLS={doc:'ZAG work documented',inst:'ZAG or partner site',ctx:'Context only'};
const CLSS={doc:'Documented',inst:'Sites',ctx:'Context'};
const CLSDESC={
 doc:'A published source names ZAG and says what the institute did.',
 inst:'ZAG premises and the partner organisations the register refers to.',
 ctx:'Real Slovenian structures, correctly placed, that no public source ties to ZAG. They are here for orientation.'};
const CATN={bridge:'Bridge',road:'Road bridge',rail:'Railway structure',foot:'Footbridge',
            tunnel:'Tunnel',dam:'Hydropower plant',geo:'Geotechnical site',inst:'Institution',
            other:'Structure'};
const KIND={journal:'Journal article',conference:'Conference paper',report:'Official record',
            web:'Web page',inst:'Institutional page'};
const PREC={surveyed:'Published coordinate',derived:'Derived from river alignment',
            locality:'Locality centre, approximate',address:'Street address, approximate',
            approximate:'Approximate, from the road alignment'};

/* domain glyphs, drawn in screen pixels inside the marker disc */
const GLYPH={
  bridge:['p','M-5 2.4a5 5 0 0 1 10 0M-5 2.4h10'],
  ai:    ['p','M-5 2.6 -1.6-1.2 1.2 1.4 5-3.2'],
  energy:['p','M-5-1.6q2.5-2.4 5 0t5 0M-5 2.2q2.5-2.4 5 0t5 0'],
  geo:   ['p','M-5 3.2 0-3.4l5 6.6z'],
  fire:  ['p','M0-4.4c2.6 2.4 3.8 3.8 3.8 5.6A3.8 3.8 0 0 1 0 4.6 3.8 3.8 0 0 1-3.8 1.2c0-1.3.7-2.3 1.9-3.4 0 1.3.6 2 1.4 2.2-.3-1.9 0-3.4.5-4.4z'],
  mat:   ['p','M0-4.2 4 -2v4.4L0 4.4-4 2.4V-2z'],
  build: ['p','M-4.8 4V-1.4L0-4.4l4.8 3V4zM-1.8 4V0.4h3.6V4'],
  herit: ['p','M-4.8 4V-1h9.6v5M-3.2-1v-1.6h6.4V-1M0-4.6l3.6 2H-3.6z'],
  inst:  ['r',null]
};
function glyphEl(dom){
  const g=GLYPH[dom]||GLYPH.inst;
  if(g[0]==='r') return el('rect',{class:'glyph f',x:-3.4,y:-3.4,width:6.8,height:6.8,rx:1.5});
  return el('path',{class:'glyph',d:g[1]});
}
function glyphSVG(dom,cls,size,approx){
  const s=size||24, c=`var(--d-${dom})`;
  const hollow=cls==='ctx';
  const stroke=hollow?c:'#fff';
  const g=GLYPH[dom]||GLYPH.inst;
  const inner = g[0]==='r'
    ? `<rect x="${s/2-3.4}" y="${s/2-3.4}" width="6.8" height="6.8" rx="1.5" fill="${stroke}"/>`
    : `<path transform="translate(${s/2},${s/2})" d="${g[1]}" fill="none" stroke="${stroke}" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round"/>`;
  const core = hollow
    ? `<circle cx="${s/2}" cy="${s/2}" r="${s/2-2.6}" fill="#fff" stroke="${c}" stroke-width="2.6"/>`
    : `<circle cx="${s/2}" cy="${s/2}" r="${s/2-1.4}" fill="${c}"/>`;
  const band = cls==='inst'
    ? `<circle cx="${s/2}" cy="${s/2}" r="${s/2-4.2}" fill="none" stroke="#fff" stroke-width="1.6"/>` : '';
  const dash = approx
    ? `<circle cx="${s/2}" cy="${s/2}" r="${s/2-.9}" fill="none" stroke="${c}" stroke-width="1.3" stroke-dasharray="2.4 2.4"/>` : '';
  const r0 = approx ? s/2-3.4 : s/2-.4;
  const core2 = approx
    ? `<circle cx="${s/2}" cy="${s/2}" r="${s/2-4.4}" fill="${c}"/>` : core;
  const inner2 = approx
    ? `<path transform="translate(${s/2},${s/2}) scale(.72)" d="${(GLYPH[dom]||GLYPH.inst)[1]||''}" fill="none" stroke="#fff" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>` : inner;
  return `<svg width="${s}" height="${s}" viewBox="0 0 ${s} ${s}" aria-hidden="true" style="display:block;flex:0 0 auto"><circle cx="${s/2}" cy="${s/2}" r="${r0}" fill="#fff" stroke="rgba(0,0,0,.22)" stroke-width=".7"/>${core2}${approx?'':band}${inner2}${dash}</svg>`;
}
const domName=k=>(DOMS[k]||{}).n||k;
const phone=()=>matchMedia('(max-width:820px)').matches;
const reduced=()=>matchMedia('(prefers-reduced-motion: reduce)').matches;
function toast(msg){const t=$('toast');t.textContent=msg;t.classList.add('on');
  clearTimeout(toast._t);toast._t=setTimeout(()=>t.classList.remove('on'),2200);}
function announce(msg){$('live').textContent=msg;}

/* -------------------------------- state --------------------------------- */
const entries=D.entries.map(e=>({...e}));
let z=1,tx=0,ty=0,sel=null,selReg=null,query='',dom='all',ev='all',sortBy='name';
let stack=[{t:'home'}];
const TABS=[['detail','Detail'],['browse','Browse'],['projects','Projects'],
            ['sources','Sources'],['about','About']];
const TABOF={home:'detail',entry:'detail',river:'detail',list:'browse',region:'browse',
             regions:'browse',projects:'projects',project:'projects',sources:'sources',
             method:'about',layers:'about'};
const TABROOT={detail:{t:'home'},browse:{t:'list'},projects:{t:'projects'},
               sources:{t:'sources'},about:{t:'method'}};
const LAYERS={peaks:true,mun:true,reg:true,shade:false,riv:true,mot:true,rail:true,names:true,grat:false};

/* ---------------------------- static geometry ---------------------------- */
$('l-land').setAttribute('d',D.country);
$('l-coast').setAttribute('d',D.country);
$('l-mun').setAttribute('d',D.munline);
$('l-mot').setAttribute('d',D.mot);
$('l-mot2').setAttribute('d',D.mot2);
$('l-rail').appendChild(el('path',{class:'rail',d:D.rail}));
(D.peaks||[]).forEach(pk=>{
  const g=el('g',{class:'peak',transform:`translate(${pk.p[0]},${pk.p[1]})`});
  const inner=el('g',{class:'pin'});
  inner.appendChild(el('path',{class:'tri',d:'M-5 3.4 0-4 5 3.4z'}));
  const t=el('text',{x:8,y:3}); t.textContent=`${pk.n} ${pk.m} m`;
  inner.appendChild(t); g.appendChild(inner); pk._el=g; pk._in=inner;
  $('l-peaks').appendChild(g);
});
{
  const g=$('l-grat');
  for(let lon=13.0;lon<=17.0;lon+=0.5){let d='';
    for(let lat=45.2;lat<=47.1;lat+=0.1){const p=toPx(lon,lat);d+=(d?'L':'M')+p[0].toFixed(1)+' '+p[1].toFixed(1);}
    g.appendChild(el('path',{d}));}
  for(let lat=45.25;lat<=47.0;lat+=0.25){let d='';
    for(let lon=13.0;lon<=17.0;lon+=0.2){const p=toPx(lon,lat);d+=(d?'L':'M')+p[0].toFixed(1)+' '+p[1].toFixed(1);}
    g.appendChild(el('path',{d}));}
}
D.regions.forEach(r=>{
  const p=el('path',{class:'regfill',d:r.d,tabindex:'0',role:'button','data-reg':r.id,
    'aria-label':r.na+' statistical region'});
  p.__act=()=>go({t:'region',id:r.id});
  p.addEventListener('keydown',ev2=>{if(ev2.key==='Enter'||ev2.key===' '){ev2.preventDefault();p.__act();}});
  $('l-reg').appendChild(p);
});
D.rivers.forEach(r=>{
  $('l-riv').appendChild(el('path',{class:'riv',d:r.d}));
  const h=el('path',{class:'rivhit',d:r.d,tabindex:'0',role:'button','aria-label':'River '+r.n});
  h.__act=()=>go({t:'river',n:r.n});
  h.addEventListener('keydown',ev2=>{if(ev2.key==='Enter'||ev2.key===' '){ev2.preventDefault();h.__act();}});
  $('l-riv').appendChild(h);
});

/* ------------------------------- markers -------------------------------- */
const svg=$('map'), cam=$('cam'), mkLayer=$('l-mk'), clLayer=$('l-cl');
svg.setAttribute('viewBox',`0 0 ${VB[0]} ${VB[1]}`);
svg.setAttribute('preserveAspectRatio','xMidYMid meet');

function drawMarkers(){
  mkLayer.textContent='';
  entries.forEach(e=>{
    const exact = e.prec==='surveyed' || e.prec==='address';
    const g=el('g',{class:'mk','data-c':e.cls,'data-d':e.dom,'data-id':e.id,
      'data-p':exact?'exact':'approx',
      transform:`translate(${e.p[0]},${e.p[1]})`,tabindex:'0',role:'button',
      'aria-label':`${e.n}. ${domName(e.dom)}. ${CLS[e.cls]||''}. ${e.loc||''}. `+
        (exact?'Exact position.':'Approximate position.')});
    const inner=el('g',{class:'in'});
    inner.appendChild(el('circle',{class:'pulse',r:12}));
    inner.appendChild(el('circle',{class:'ring',r:11.5}));
    inner.appendChild(el('circle',{class:'core',r:e.cls==='ctx'?8.4:10}));
    inner.appendChild(el('circle',{class:'inner',r:7.3}));
    inner.appendChild(el('circle',{class:'approx',r:14.6}));
    inner.appendChild(glyphEl(e.dom));
    inner.appendChild(el('circle',{class:'hit',r:23}));
    const t=el('text',{class:'lab',x:16,y:4.5}); t.textContent=e.n; inner.appendChild(t);
    g.appendChild(inner); e._el=g; e._in=inner;
    g.__act=()=>go({t:'entry',id:e.id});
    g.addEventListener('keydown',ev2=>{if(ev2.key==='Enter'||ev2.key===' '){ev2.preventDefault();g.__act();}});
    mkLayer.appendChild(g);
  });
}

/* -------------------------- filter and clustering ------------------------ */
function matches(e){
  if(dom!=='all' && !(e.doms||[e.dom]).includes(dom)) return false;
  if(ev!=='all' && e.cls!==ev) return false;
  const q=query.trim().toLowerCase();
  if(!q) return true;
  const reg=(D.regions.find(r=>r.id===e.reg)||{}).na;
  const projs=PROJ.filter(p=>p.sites.includes(e.id)).map(p=>p.ac+' '+p.t).join(' ');
  return [e.n,e.sl,e.loc,e.crosses,e.carries,e.typ,e.role,e.detail,e.note,e.built,reg,
          CATN[e.cat],domName(e.dom),(e.people||[]).join(' '),(e.partners||[]).join(' '),projs]
    .filter(Boolean).join(' ').toLowerCase().includes(q);
}
const visible=()=>entries.filter(matches);
const projectsFor=id=>PROJ.filter(p=>p.sites.includes(id));

function paint(){
  const s=fitS(), k=1/(z*s), CLZ=2.4, kk=k.toFixed(4), vis=[];
  entries.forEach(e=>{
    const ok=matches(e);
    if(!e._el) return;
    e._el.classList.toggle('hide',!ok);
    e._el.classList.toggle('sel',e.id===sel);
    e._el.classList.toggle('named',false);
    e._el.classList.toggle('dim',!!selReg && e.reg!==selReg);
    e._in.setAttribute('transform',`scale(${kk})`);
    if(ok) vis.push(e);
  });
  (D.peaks||[]).forEach(pk=>{ if(pk._in) pk._in.setAttribute('transform',`scale(${kk})`); });
  $('l-peaks').classList.toggle('off',!LAYERS.peaks);
  clLayer.textContent='';
  if(z<CLZ){
    const cell=34*k, grid=new Map();
    vis.forEach(e=>{
      const key=Math.floor(e.p[0]/cell)+':'+Math.floor(e.p[1]/cell);
      if(!grid.has(key)) grid.set(key,[]);
      grid.get(key).push(e);
    });
    grid.forEach(list=>{
      if(list.length<2) return;
      list.forEach(e=>e._el.classList.add('hide'));
      const cx=list.reduce((s2,e)=>s2+e.p[0],0)/list.length;
      const cy=list.reduce((s2,e)=>s2+e.p[1],0)/list.length;
      const g=el('g',{class:'cl',transform:`translate(${cx},${cy})`,tabindex:'0',role:'button',
        'aria-label':list.length+' entries grouped here, activate to zoom in'});
      const inner=el('g',{transform:`scale(${kk})`});
      const R=13+Math.min(6,list.length);
      inner.appendChild(el('circle',{class:'cbg',r:R}));
      const t=el('text',{y:4.5}); t.textContent=list.length; inner.appendChild(t);
      inner.appendChild(el('circle',{class:'chit',r:R+5}));
      g.appendChild(inner);
      g.__act=()=>zoomTo(cx,cy,Math.max(3.2,z*2.4));
      g.__r=R+5; g.__names=list.map(e=>e.n);
      g.addEventListener('keydown',ev2=>{if(ev2.key==='Enter'||ev2.key===' '){ev2.preventDefault();g.__act();}});
      clLayer.appendChild(g);
    });
  }
  if(LAYERS.names){
    const s2=fitS(), kept=[];
    vis.filter(e=>!e._el.classList.contains('hide'))
       .sort((a,b)=>(a.cls==='doc'?0:1)-(b.cls==='doc'?0:1))
       .forEach(e=>{
      const p=screenOf(e.p[0],e.p[1]);
      const w=Math.min(150,e.n.length*6.2)+24;
      const clash=kept.some(q=>Math.abs(q[1]-p[1])<15 && p[0]<q[0]+q[2] && p[0]+w>q[0]);
      if(!clash){ kept.push([p[0],p[1],w]); e._el.classList.add('named'); }
    });
  }
  D.regions.forEach(r=>{
    const p=$('l-reg').querySelector(`[data-reg="${r.id}"]`);
    if(!p) return;
    p.classList.toggle('on',r.id===selReg);
    const c=vis.filter(e=>e.reg===r.id).length;
    const sh=LAYERS.shade&&c>0&&z<3.2;
    p.classList.toggle('shade',sh);
    p.style.fillOpacity = sh ? (0.045+0.032*Math.min(c,6)).toFixed(3) : '';
  });
  $('l-mun').classList.toggle('off',!LAYERS.mun);
  $('l-reg').classList.toggle('off',!LAYERS.reg);
  $('l-riv').classList.toggle('off',!LAYERS.riv);
  $('l-mot').classList.toggle('off',!LAYERS.mot);
  $('l-mot2').classList.toggle('off',!LAYERS.mot);
  $('l-rail').classList.toggle('off',!LAYERS.rail);
  $('l-grat').classList.toggle('off',!LAYERS.grat);
  const bs=$('brandsub');
  if(bs) bs.textContent = (vis.length===entries.length)
    ? `${entries.length} sites and structures, ${PROJ.length} projects`
    : `${vis.length} of ${entries.length} shown`;
  const f=$('filters');
  if(f) [...f.children].forEach(b=>{
    const c=b.dataset.dom, u=b.querySelector('u');
    if(u) u.textContent = c==='all'?entries.length:entries.filter(e=>(e.doms||[e.dom]).includes(c)).length;
  });
  updateScale();
}

/* -------------------------------- camera -------------------------------- */
const apply=()=>cam.setAttribute('transform',`translate(${tx.toFixed(2)},${ty.toFixed(2)}) scale(${z.toFixed(4)})`);
function fitS(){const r=svg.getBoundingClientRect();
  return Math.min(r.width/VB[0],r.height/VB[1])||1;}
function localFromScreen(sx,sy){
  const r=svg.getBoundingClientRect(), s=fitS();
  return [(sx-r.left-(r.width-VB[0]*s)/2)/s,(sy-r.top-(r.height-VB[1]*s)/2)/s];
}
function freeBox(){
  const r=svg.getBoundingClientRect();
  if(phone()){
    const top=r.top+118, bot=Math.max(top+120, r.bottom-(sheetVisible()||130));
    return {x:r.left+10, y:top, w:Math.max(60,r.width-20), h:Math.max(60,bot-top)};
  }
  return {x:r.left+20, y:r.top+120, w:Math.max(80,r.width-96), h:Math.max(80,r.height-186)};
}
function anchor(){const b=freeBox(); return [b.x+b.w/2, b.y+b.h/2];}
const MINZ=0.45; let homeZ=1;
function fitZoom(){
  const b=freeBox(), s=fitS();
  return Math.max(MINZ, Math.min(2.2, Math.min(b.w/s/VB[0], b.h/s/VB[1])));
}
let raf=0;
function glide(nz,nx,ny,dur){
  cancelAnimationFrame(raf);
  if(reduced()){z=nz;tx=nx;ty=ny;apply();paint();return;}
  const z0=z,x0=tx,y0=ty,t0=performance.now(),DUR=dur||480;
  (function step(t){
    const u=Math.min(1,(t-t0)/DUR), e=1-Math.pow(1-u,4);
    z=z0+(nz-z0)*e; tx=x0+(nx-x0)*e; ty=y0+(ny-y0)*e;
    apply();
    if(u<1) raf=requestAnimationFrame(step); else {raf=0;paint();}
  })(performance.now());
}
function zoomTo(px,py,nz,dur){
  nz=Math.max(MINZ,Math.min(40,nz));
  const [ax,ay]=anchor(), [lx,ly]=localFromScreen(ax,ay);
  glide(nz,lx-px*nz,ly-py*nz,dur);
}
function zoomBox(b,pad){
  pad=pad||1.2;
  const fb=freeBox(), s=fitS();
  const bw=Math.max(b[2]-b[0],14), bh=Math.max(b[3]-b[1],14);
  zoomTo((b[0]+b[2])/2,(b[1]+b[3])/2,Math.min(fb.w/s/(bw*pad),fb.h/s/(bh*pad)));
}
let userMoved=false;
function zoomAt(f,lx,ly){
  userMoved=true;
  const nz=Math.max(MINZ,Math.min(40,z*f));
  tx=lx-(lx-tx)*(nz/z); ty=ly-(ly-ty)*(nz/z); z=nz;
  apply(); paint();
}
function zoomAtSmooth(f,lx,ly){
  const nz=Math.max(MINZ,Math.min(40,z*f));
  glide(nz, lx-(lx-tx)*(nz/z), ly-(ly-ty)*(nz/z),320);
}
function zoomCentre(f){const [ax,ay]=anchor(); const p=localFromScreen(ax,ay); zoomAtSmooth(f,p[0],p[1]);}
function home(){
  selReg=null; homeZ=fitZoom();
  const [ax,ay]=anchor(), [lx,ly]=localFromScreen(ax,ay);
  glide(homeZ, lx-VB[0]/2*homeZ, ly-VB[1]/2*homeZ);
}
function snapHome(){
  homeZ=fitZoom();
  const [ax,ay]=anchor(), [lx,ly]=localFromScreen(ax,ay);
  z=homeZ; tx=lx-VB[0]/2*z; ty=ly-VB[1]/2*z; apply();
}
function updateScale(){
  const s=fitS()*z, mPerPx=MPU/s, target=86*mPerPx;
  const nice=[50,100,200,500,1000,2000,5000,10000,20000,50000,100000];
  let pick=nice[0]; for(const n of nice) if(n<=target) pick=n;
  const bar=document.querySelector('.scalebar .bar');
  if(bar) bar.style.width=Math.round(pick/mPerPx)+'px';
  $('scaletxt').textContent = pick>=1000 ? (pick/1000)+' km' : pick+' m';
}

/* -------------------------- deterministic hit test ----------------------- */
function screenOf(px,py){
  const r=svg.getBoundingClientRect(), s=fitS();
  const offX=r.left+(r.width-VB[0]*s)/2, offY=r.top+(r.height-VB[1]*s)/2;
  return [offX+(px*z+tx)*s, offY+(py*z+ty)*s];
}
function hitAt(cx,cy){
  let best=null, bd=1e9;
  clLayer.querySelectorAll('.cl').forEach(g=>{
    const m=(g.getAttribute('transform')||'').match(/translate\(([-\d.]+),([-\d.]+)\)/);
    if(!m) return;
    const p=screenOf(+m[1],+m[2]), d=Math.hypot(p[0]-cx,p[1]-cy);
    if(d<(g.__r||24)&&d<bd){bd=d;best=g;}
  });
  if(best) return best;
  entries.forEach(e=>{
    if(!e._el||e._el.classList.contains('hide')) return;
    const p=screenOf(e.p[0],e.p[1]), d=Math.hypot(p[0]-cx,p[1]-cy);
    if(d<24&&d<bd){bd=d;best=e._el;}
  });
  if(best) return best;
  const t=document.elementFromPoint(cx,cy);
  return (t&&t.closest) ? (t.closest('.rivhit')||t.closest('.regfill')) : null;
}

/* ---------------------- pointer: pan, pinch, inertia --------------------- */
let drag=null, ptrs=new Map(), pinch=null, downT=null, moved=false, vx=0, vy=0, lastT=0, inertia=0;
let lastTap=0, lastTapXY=[0,0];
const gap=(a,b)=>Math.hypot(a.clientX-b.clientX,a.clientY-b.clientY);
const mid=(a,b)=>({clientX:(a.clientX+b.clientX)/2,clientY:(a.clientY+b.clientY)/2});

svg.addEventListener('wheel',e2=>{
  e2.preventDefault(); cancelAnimationFrame(inertia);
  const p=localFromScreen(e2.clientX,e2.clientY);
  const f=Math.exp(-e2.deltaY*(e2.deltaMode===1?0.06:0.0022));
  zoomAt(Math.max(0.6,Math.min(1.6,f)),p[0],p[1]);
},{passive:false});

svg.addEventListener('pointerdown',e2=>{
  cancelAnimationFrame(inertia); cancelAnimationFrame(raf); raf=0;
  ptrs.set(e2.pointerId,e2);
  try{svg.setPointerCapture(e2.pointerId);}catch(_){}
  if(ptrs.size===2){
    const a=[...ptrs.values()]; drag=null; svg.classList.remove('drag');
    pinch={d:gap(a[0],a[1])||1}; moved=true; return;
  }
  drag={x:e2.clientX,y:e2.clientY,tx,ty};
  svg.classList.add('drag');
  downT=e2.target; moved=false; vx=vy=0; lastT=performance.now();
});
svg.addEventListener('pointermove',e2=>{
  if(ptrs.has(e2.pointerId)) ptrs.set(e2.pointerId,e2);
  if(pinch&&ptrs.size>=2){
    const a=[...ptrs.values()], nd=gap(a[0],a[1])||1, m=mid(a[0],a[1]);
    const c=localFromScreen(m.clientX,m.clientY);
    zoomAt(nd/pinch.d,c[0],c[1]); pinch.d=nd; return;
  }
  if(!drag) return;
  const dx=e2.clientX-drag.x, dy=e2.clientY-drag.y;
  if(Math.abs(dx)+Math.abs(dy)>6){moved=true;userMoved=true;}
  const s=fitS(), now=performance.now(), dt=Math.max(1,now-lastT);
  const ntx=drag.tx+dx/s, nty=drag.ty+dy/s;
  vx=(ntx-tx)/dt; vy=(nty-ty)/dt; lastT=now;
  tx=ntx; ty=nty;
  if(!raf) raf=requestAnimationFrame(()=>{raf=0;apply();});
});
function endPtr(type,e2){
  ptrs.delete(e2.pointerId);
  if(ptrs.size<2) pinch=null;
  if(ptrs.size) return;
  const wasDrag=!!drag;
  drag=null; svg.classList.remove('drag');
  if(type==='pointerup'&&!moved){
    const hit=hitAt(e2.clientX,e2.clientY);
    const now=performance.now();
    const near=Math.hypot(e2.clientX-lastTapXY[0],e2.clientY-lastTapXY[1])<26;
    if(hit&&hit.__act){ hit.__act(); if(hit.blur) hit.blur(); }
    else if(now-lastTap<330 && near){
      const p=localFromScreen(e2.clientX,e2.clientY); zoomAtSmooth(2,p[0],p[1]); lastTap=0;
    }else{
      lastTap=now; lastTapXY=[e2.clientX,e2.clientY];
      if(sel||selReg) clearSel();
      else if(phone()&&sheetDetent!=='peek') setDetent('peek');
    }
  }else if(wasDrag&&moved&&!reduced()){
    const s0=Math.hypot(vx,vy);
    if(s0>0.02){
      let ax=vx*16, ay=vy*16, t0=performance.now();
      (function step(){
        ax*=0.93; ay*=0.93; tx+=ax; ty+=ay; apply();
        if(Math.hypot(ax,ay)>0.06 && performance.now()-t0<1400) inertia=requestAnimationFrame(step);
        else {inertia=0;paint();}
      })();
    }
  }
  downT=null; moved=false;
  if(!inertia) paint();
}
['pointerup','pointercancel'].forEach(t=>svg.addEventListener(t,e2=>endPtr(t,e2)));

$('zin').onclick=()=>zoomCentre(1.7);
$('zout').onclick=()=>zoomCentre(1/1.7);
$('zres').onclick=()=>{userMoved=false;clearSel();home();toast('Whole of Slovenia');};
addEventListener('keydown',e2=>{
  if(e2.key==='Escape'){clearSel();return;}
  if(document.activeElement&&/INPUT|TEXTAREA|SELECT/.test(document.activeElement.tagName))return;
  const step=60/fitS();
  if(e2.key==='ArrowLeft'){tx+=step;userMoved=true;apply();paint();}
  else if(e2.key==='ArrowRight'){tx-=step;userMoved=true;apply();paint();}
  else if(e2.key==='ArrowUp'){ty+=step;userMoved=true;apply();paint();}
  else if(e2.key==='ArrowDown'){ty-=step;userMoved=true;apply();paint();}
  else if(e2.key==='+'||e2.key==='='){zoomCentre(1.7);}
  else if(e2.key==='-'||e2.key==='_'){zoomCentre(1/1.7);}
});
let rz;
addEventListener('resize',()=>{clearTimeout(rz);
  rz=setTimeout(()=>{measureSheet();if(!userMoved)snapHome();paint();},120);});

/* ============================== bottom sheet ============================== */
const sheet=$('sheet');
let DET={full:0,mid:0,peek:0}, sheetDetent='mid', sheetY=0;
function measureSheet(){
  if(!phone()){sheet.style.transform='';return;}
  const H=sheet.offsetHeight, vh=innerHeight;
  DET.full=0;
  DET.mid=Math.max(0,Math.round(H-vh*0.52));
  DET.peek=Math.max(0,Math.round(H-132));
  setDetent(sheetDetent,false);
}
function sheetVisible(){ return phone()? sheet.offsetHeight-sheetY : 0; }
function setSheetY(y,anim){
  sheetY=y;
  sheet.classList.toggle('anim',anim!==false&&!reduced());
  sheet.style.transform=`translateY(${y}px)`;
}
function setDetent(name,anim){
  const changed=sheetDetent!==name;
  sheetDetent=name;
  if(!phone()){sheet.style.transform='';return;}
  setSheetY(DET[name],anim);
  $('pane').style.overflowY = name==='peek'?'hidden':'auto';
  if(changed && z<=homeZ*1.06 && !userMoved){
    clearTimeout(setDetent._t);
    setDetent._t=setTimeout(()=>{ if(z<=homeZ*1.06&&!userMoved) home(); }, anim===false?0:360);
  }
}
function nearestDetent(y,v){
  const cands=[['full',DET.full],['mid',DET.mid],['peek',DET.peek]];
  const biased=y+v*160;
  let best=cands[0], bd=1e9;
  cands.forEach(c=>{const d=Math.abs(biased-c[1]); if(d<bd){bd=d;best=c;}});
  return best[0];
}
(function sheetDrag(){
  let st=null;
  const start=(e2,fromBody)=>{
    if(!phone()) return;
    st={y:e2.clientY,y0:sheetY,lt:performance.now(),v:0,fromBody};
    sheet.classList.remove('anim');
  };
  const move=e2=>{
    if(!st) return;
    const dy=e2.clientY-st.y;
    if(st.fromBody){
      const pane=$('pane');
      if(pane.scrollTop>0||dy<0){ if(sheetY<=DET.full+1){st=null;return;} }
    }
    const now=performance.now(), dt=Math.max(1,now-st.lt);
    const ny=Math.max(DET.full-24,Math.min(DET.peek+70,st.y0+dy));
    st.v=(ny-sheetY)/dt; st.lt=now;
    setSheetY(ny,false);
    e2.preventDefault();
  };
  const end=()=>{ if(!st) return; const d=nearestDetent(sheetY,st.v); st=null; setDetent(d,true); };
  const grab=$('grab'), head2=$('shead'), tabs=$('tabs');
  [grab,head2].forEach(n=>{
    n.addEventListener('pointerdown',e2=>{
      if(e2.target.closest('button')&&e2.target.closest('button')!==n) return;
      try{n.setPointerCapture(e2.pointerId);}catch(_){}
      start(e2,false);
    });
    n.addEventListener('pointermove',move);
    ['pointerup','pointercancel'].forEach(t=>n.addEventListener(t,end));
  });
  $('pane').addEventListener('pointerdown',e2=>{
    if(!phone()||sheetDetent==='peek') return;
    if($('pane').scrollTop>0) return;
    if(e2.target.closest('input,textarea,select,button,a')) return;
    start(e2,true);
  });
  $('pane').addEventListener('pointermove',e2=>{ if(st&&st.fromBody) move(e2); });
  ['pointerup','pointercancel'].forEach(t=>$('pane').addEventListener(t,end));
  grab.addEventListener('keydown',e2=>{
    if(e2.key==='ArrowUp'){e2.preventDefault();setDetent(sheetDetent==='peek'?'mid':'full');}
    if(e2.key==='ArrowDown'){e2.preventDefault();setDetent(sheetDetent==='full'?'mid':'peek');}
  });
})();
$('backbtn').onclick=()=>back();

/* ============================== navigation =============================== */
function go(v,replace){ if(replace) stack=[v]; else stack.push(v); enter(v); }
function back(){ if(stack.length>1) stack.pop(); enter(stack[stack.length-1],true); }
function enter(v,isBack){
  const tab=TABOF[v.t]||'detail';
  document.querySelectorAll('#tabs button').forEach(b=>
    b.setAttribute('aria-selected', b.dataset.tab===tab));
  if(v.t==='entry'){
    const e=entries.find(x=>x.id===v.id);
    if(!e){renderHome();return;}
    sel=e.id; selReg=null;
    renderEntry(e);
    if(phone()&&sheetDetent==='peek') setDetent('mid');
    if(!isBack) zoomTo(e.p[0],e.p[1], z<4?6.5:z);
    paint();
    announce(e.n+' selected');
  }else if(v.t==='region'){
    const r=D.regions.find(x=>x.id===v.id); if(!r){renderHome();return;}
    sel=null; selReg=r.id; renderRegion(r); paint();
    if(phone()&&sheetDetent==='peek') setDetent('mid');
    const b=regionBox(r); if(b&&!isBack) zoomBox(b,1.25);
  }else if(v.t==='river'){
    sel=null; selReg=null; paint(); renderRiver(v.n);
    if(phone()&&sheetDetent==='peek') setDetent('mid');
  }else if(v.t==='list'){ sel=null; paint(); renderList();
    if(phone()&&sheetDetent==='peek') setDetent('mid');
  }else if(v.t==='regions'){ renderRegions(); }
  else if(v.t==='groups'){ renderGroups(); if(phone()&&sheetDetent==='peek') setDetent('mid'); }
  else if(v.t==='projects'){ renderProjects(); if(phone()&&sheetDetent==='peek') setDetent('mid'); }
  else if(v.t==='project'){ renderProject(v.id); if(phone()&&sheetDetent==='peek') setDetent('mid'); }
  else if(v.t==='sources'){ renderSources(); }
  else if(v.t==='method'){ renderMethod(); }
  else if(v.t==='layers'){ renderLayers(); if(phone()&&sheetDetent==='peek') setDetent('mid'); }
  else { sel=null; selReg=null; paint(); renderHome(); }
  $('pane').scrollTop=0;
  try{ history.replaceState(null,'',location.pathname+location.search+(v.t==='entry'?'#'+v.id:'')); }catch(_){}
}
function clearSel(){
  if(!sel&&!selReg) return;
  sel=null; selReg=null; paint(); go({t:'home'},true);
}
function render(){ enter(stack[stack.length-1],true); }

/* ============================ shared fragments =========================== */
function head(t,s){
  const n=$('sheadt'); if(n) n.innerHTML='<b>'+esc(t)+'</b>'+(s?' · '+esc(s):'');
  const h=$('shead'); if(h) h.classList.toggle('on',stack.length>1);
}
function rowHTML(e){
  const sub=[domName(e.dom),e.loc].filter(Boolean).join(' · ');
  return `<button class="row" data-go="${esc(e.id)}">
    <span class="mkic">${glyphSVG(e.dom,e.cls,26)}</span>
    <span class="two"><b>${esc(e.n)}</b><s>${esc(sub)}</s></span>${CHEV}</button>`;
}
function projRow(p){
  return `<button class="row" data-proj="${esc(p.id)}">
    <span class="mkic">${glyphSVG(p.dom,'doc',26)}</span>
    <span class="two"><b>${esc(p.ac)}${p.kind==='programme'?' <em class="tagp">programme</em>':''}</b>
      <s>${esc(p.t)}</s>
      <s>${esc(p.fund.split(',')[0])} · ${esc(p.y)} · ${esc(p.role)}</s></span>${CHEV}</button>`;
}
function fmtCite(k){
  const s=SRC[k]; if(!s) return '';
  const bits=[];
  if(s.a) bits.push(esc(s.a));
  if(s.y) bits.push('('+s.y+')');
  let line=bits.join(' ');
  line+=(line?'. ':'')+`<span class="ti">${esc(s.t)}</span>`;
  const tail=[]; if(s.c) tail.push(esc(s.c)); if(s.d) tail.push(esc(s.d));
  if(tail.length) line+=`. <span class="me">${tail.join(', ')}</span>`;
  if(s.doi) line+=`. <span class="me mono">doi:${esc(s.doi)}</span>`;
  return line+'.';
}
function citeText(k){
  const s=SRC[k]; if(!s) return '';
  let t=''; if(s.a) t+=s.a+' '; if(s.y) t+='('+s.y+'). ';
  t+=s.t+'.'; if(s.c) t+=' '+s.c; if(s.d) t+=', '+s.d;
  if(s.doi) t+='. doi:'+s.doi; else if(s.u) t+='. '+s.u;
  return t;
}
function citeBlock(keys){
  if(!keys||!keys.length) return '';
  return `<div class="grp">${keys.map(k=>{
    const s=SRC[k]; if(!s) return '';
    return `<div class="cite"><span class="kind">${esc(KIND[s.k]||'Source')}</span>${fmtCite(k)}
      <span class="acts">${s.u?`<a href="${esc(s.u)}" target="_blank" rel="noopener">Open source</a>`:''}
      <button data-cite="${esc(k)}">Copy reference</button></span></div>`;
  }).join('')}</div>`;
}
async function copyText(t,msg){
  try{ await navigator.clipboard.writeText(t); toast(msg); return; }catch(_){}
  try{
    const ta=document.createElement('textarea'); ta.value=t; ta.setAttribute('readonly','');
    ta.style.cssText='position:fixed;top:-200px;opacity:0'; document.body.appendChild(ta);
    ta.select(); document.execCommand('copy'); ta.remove(); toast(msg);
  }catch(_){ toast('Copying is blocked here'); }
}
function nearest(e,n){
  return entries.filter(x=>x.id!==e.id)
    .map(x=>({e:x,d:Math.hypot(x.tm[0]-e.tm[0],x.tm[1]-e.tm[1])}))
    .sort((a,b)=>a.d-b.d).slice(0,n||4);
}
function wire(){
  const p=$('pane');
  p.querySelectorAll('[data-go]').forEach(b=>b.onclick=()=>go({t:'entry',id:b.dataset.go}));
  p.querySelectorAll('[data-proj]').forEach(b=>b.onclick=()=>go({t:'project',id:b.dataset.proj}));
  p.querySelectorAll('[data-reg-go]').forEach(b=>b.onclick=()=>go({t:'region',id:b.dataset.regGo}));
  p.querySelectorAll('[data-view]').forEach(b=>b.onclick=()=>go({t:b.dataset.view}));
  p.querySelectorAll('[data-cite]').forEach(b=>b.onclick=()=>copyText(citeText(b.dataset.cite),'Reference copied'));
  p.querySelectorAll('[data-order]').forEach(b=>b.onclick=()=>{setOrder(b.dataset.order);renderHome();});
  p.querySelectorAll('[data-domgo]').forEach(b=>b.onclick=()=>{
    setDom(b.dataset.domgo); go({t:'list'},true);
  });
}
function legendHTML(){
  const evs=[['doc','ZAG work documented','Filled disc'],
             ['inst','ZAG or partner site','Filled disc with a white inner ring'],
             ['ctx','Context only','Hollow disc']];
  return `<div class="sec">How exact the position is</div>
    <div class="grp lg">
      <div class="lgr">${glyphSVG('bridge','doc',26)}<span>Solid marker</span>
        <s>Position from a published coordinate or a street address</s></div>
      <div class="lgr">${glyphSVG('bridge','doc',26,true)}<span>Dashed outer ring</span>
        <s>Position is a settlement centre or read off a road alignment</s></div>
    </div>
    <div class="sec">What the fill means</div>
    <div class="grp lg">${evs.map(([c,t,s])=>
      `<div class="lgr">${glyphSVG('bridge',c,26)}<span>${t}</span><s>${s}</s></div>`).join('')}</div>
    <div class="sec">What the colour and shape mean</div>
    <div class="grp lg">${DOMKEYS.map((k,i)=>
      `<div class="lgr"><span class="rn">${i+1}</span>${glyphSVG(k,'doc',26)}
        <span><b style="font-weight:600">${esc(domName(k))}</b><br>
        <span style="font-size:12.5px;color:var(--label2)">${esc(DOMS[k].d)}</span></span>
        <s>${projCount(k)} project${projCount(k)===1?'':'s'}<br>${mapCount(k)} on the map</s></div>`
    ).join('')}</div>`;
}
function paintMapLegend(){
  const n=$('maplegend'); if(!n) return;
  n.innerHTML=`<strong>Sector, by projects</strong>`+
    DOMKEYS.map(k=>`<i>${glyphSVG(k,'doc',16)}<span style="flex:1">${esc(domName(k))}</span><b2>${projCount(k)}</b2></i>`).join('')+
    `<strong style="margin-top:4px">Evidence</strong>
     <i>${glyphSVG('bridge','doc',16)}Documented by a source</i>
     <i>${glyphSVG('bridge','inst',16)}ZAG or partner site</i>
     <i>${glyphSVG('bridge','ctx',16)}Context only</i>`;
}

/* ================================= views ================================= */
function renderHome(){
  head('ZAG structures and sites','Slovenia');
  const nDoc=entries.filter(e=>e.cls==='doc').length;
  const nSrc=Object.keys(SRC).length;
  const regWith=D.regions.filter(r=>entries.some(e=>e.reg===r.id)).length;
  $('pane').innerHTML=`
    <p class="eyebrow">Register, ${esc(D.meta.built)}</p>
    <h1 class="lt">Structures and sites ZAG has worked on</h1>
    <p class="sub">Slovenia, ${D.meta.area_km2.toLocaleString('en-GB')} km², ${D.meta.muns} municipalities</p>
    <div class="stats">
      <div><b>${entries.length}</b><s>sites and structures</s></div>
      <div><b>${PROJ.length}</b><s>research projects</s></div>
      <div><b>${nDoc}</b><s>documented entries</s></div>
      <div><b>${nSrc}</b><s>sources cited</s></div>
    </div>
    <p class="note" style="margin-top:10px">SICRIS records ${D.meta.aris_total} ARIS projects and
      ${D.meta.researchers} researchers at ZAG in ${GROUPS.length} research groups. The ${PROJ.length}
      projects listed here are the ones with a public record naming title, funder, years and leader.</p>
    <p class="lede">Click any marker, region or river. Drag to move the map, scroll or pinch to zoom.
      Colour and shape say which sector the work belongs to. The fill says how strong the evidence is.</p>

    <div class="sec">Sectors</div>
    <div class="seg" role="tablist" aria-label="Sector order">
      ${[['relevance','Relevance'],['projects','By project count']].map(([k,l])=>
        `<button role="tab" data-order="${k}" aria-selected="${domOrder===k}">${l}</button>`).join('')}
    </div>
    <p class="note" style="margin:9px 0 6px">${domOrder==='relevance'
      ? 'AI and data first, then bridges, fire and materials, then the rest by project count.'
      : 'Straight by how many projects each sector holds.'}</p>
    <div class="grp">${DOMKEYS.map((k,i)=>{
      const n=mapCount(k), np=projCount(k);
      const mx=Math.max(...DOMKEYS.map(projCount))||1;
      return `<button class="row rank" data-domgo="${k}">
        <span class="rn">${i+1}</span>
        <span class="mkic">${glyphSVG(k,'doc',28)}</span>
        <span class="two"><b>${esc(domName(k))}</b>
          <s>${esc(DOMS[k].d)}</s>
          <span class="bar"><span style="width:${Math.round(100*np/mx)}%;background:var(--d-${k})"></span></span></span>
        <s><b style="font-weight:700;font-size:16px;color:var(--d-${k})">${np}</b><br>project${np===1?'':'s'}<br>${n} on map</s>${CHEV}</button>`;
    }).join('')}</div>

    <div class="sec">Open a list</div>
    <div class="grp">
      <button class="row" data-view="list"><b>All sites and structures</b><s>${entries.length}</s>${CHEV}</button>
      <button class="row" data-view="projects"><b>All research projects</b><s>${PROJ.length}</s>${CHEV}</button>
      <button class="row" data-view="groups"><b>ZAG research groups</b><s>${GROUPS.length}</s>${CHEV}</button>
      <button class="row" data-view="regions"><b>Statistical regions</b><s>12 regions, ${regWith} with entries</s>${CHEV}</button>
      <button class="row" data-view="sources"><b>Every source</b><s>${nSrc}</s>${CHEV}</button>
      <button class="row" data-view="layers"><b>Legend, layers and appearance</b>${CHEV}</button>
      <button class="row" data-view="method"><b>Method, accuracy and gaps</b>${CHEV}</button>
    </div>

    <div class="callout warn">
      <p><strong>How to read the evidence.</strong> A filled marker means a published source names ZAG
      and says what it did. A hollow marker is a real Slovenian structure, correctly placed, that no
      public source ties to ZAG. Nothing here is asserted without a citation you can open.</p>
    </div>
    <p class="note">ZAG publishes no named project list, so the documented count is a limit of what is
      public rather than of what the institute has done. Where a coordinate is a settlement centre
      rather than the structure itself, the entry says so.</p>`;
  wire();
}

function renderEntry(e){
  const reg=D.regions.find(r=>r.id===e.reg);
  head(e.n,[domName(e.dom),reg&&reg.na].filter(Boolean).join(' · '));
  const f=[];
  if(e.loc)     f.push(['Location',esc(e.loc)]);
  if(e.crosses) f.push(['Crosses',esc(e.crosses)]);
  if(e.carries) f.push(['Carries',esc(e.carries)]);
  if(e.typ)     f.push(['Structure',esc(e.typ)]);
  if(e.built)   f.push(['Built',esc(e.built)]);
  if(e.spans)   f.push(['Spans',esc(e.spans)]);
  if(e.len_m)   f.push(['Length',`<span class="mono">${e.len_m} m</span>`]);
  if(e.span_m)  f.push(['Main span',`<span class="mono">${e.span_m} m</span>`]);
  if(e.years)   f.push(['ZAG activity',esc(e.years)]);
  const near=nearest(e,4), ps=projectsFor(e.id);
  $('pane').innerHTML=`
    <p class="eyebrow">${esc(CATN[e.cat]||'Structure')}${reg?' · '+esc(reg.na):''}</p>
    <h1 class="lt sm">${esc(e.n)}</h1>
    ${e.sl?`<p class="sub">${esc(e.sl)}</p>`:''}
    <p class="tagrow">
      <span class="badge dom" style="color:var(--d-${e.dom})">${glyphSVG(e.dom,'doc',18)}
        <span style="color:var(--label)">${esc(domName(e.dom))}</span></span>
      <span class="badge">${glyphSVG(e.dom,e.cls,18)}<span>${esc(CLS[e.cls])}</span></span>
      <span class="pill${e.prec==='surveyed'?' ok':''}">${esc(PREC[e.prec]||e.prec)}</span></p>
    ${e.role?`<p class="lede">${esc(e.role)}</p>`:''}
    ${e.detail?`<div class="sec">What was done</div><div class="callout"><p class="body">${esc(e.detail)}</p></div>`:''}
    ${f.length?`<div class="sec">Particulars</div><div class="grp">${
      f.map(([k,v])=>`<div class="fr"><span class="k">${k}</span><span class="v">${v}</span></div>`).join('')}</div>`:''}
    ${e.groups&&e.groups.length?`<div class="sec">Research groups based here</div>
      <div class="grp">${GROUPS.filter(g=>e.groups.includes(g.id)).map(g=>
        `<button class="row" data-domgo="${g.dom}"><span class="mkic">${glyphSVG(g.dom,'doc',26)}</span>
          <span class="two"><b>${esc(g.en)}</b><s>${esc(g.n)} · ${esc(g.lead)}</s></span>
          <s>${g.pub.toLocaleString('en-GB')}</s>${CHEV}</button>`).join('')}</div>`:''}
    ${ps.length?`<div class="sec">Research projects at this site, ${ps.length}</div>
      <div class="grp">${ps.slice(0,12).map(projRow).join('')}</div>
      ${ps.length>12?`<div class="btnrow"><button class="btn ghost" data-view="projects">See all ${PROJ.length} projects</button></div>`:''}`:''}
    ${e.people&&e.people.length?`<div class="sec">Named in the sources</div>
      <ul class="plain">${e.people.map(p=>`<li>${esc(p)}</li>`).join('')}</ul>`:''}
    ${e.partners&&e.partners.length?`<div class="sec">Partners and clients</div>
      <ul class="plain">${e.partners.map(p=>`<li>${esc(p)}</li>`).join('')}</ul>`:''}
    <div class="sec">Position</div>
    <div class="grp">
      <div class="fr"><span class="k">WGS84</span><span class="v mono">${e.lat.toFixed(5)}°N ${e.lon.toFixed(5)}°E</span></div>
      <div class="fr"><span class="k">D96/TM</span><span class="v mono">${e.tm[0].toLocaleString('en-GB')} E<br>${e.tm[1].toLocaleString('en-GB')} N</span></div>
      <div class="fr"><span class="k">Region</span><span class="v">${reg?esc(reg.na):'not set'}</span></div>
    </div>
    ${e.note?`<p class="note">${esc(e.note)}</p>`:''}
    <div class="btnrow">
      <button class="btn ghost" id="copyc">Copy coordinates</button>
      <button class="btn ghost" id="zoomhere">Centre the map here</button>
    </div>
    ${e.src&&e.src.length?`<div class="sec">Sources for this entry</div>${citeBlock(e.src)}`:''}
    ${near.length?`<div class="sec">Nearest other entries</div><div class="grp">${near.map(o=>
      `<button class="row" data-go="${esc(o.e.id)}">
        <span class="mkic">${glyphSVG(o.e.dom,o.e.cls,26)}</span>
        <span class="two"><b>${esc(o.e.n)}</b><s>${esc(domName(o.e.dom))}</s></span>
        <s>${(o.d/1000).toFixed(o.d<10000?1:0)} km</s>${CHEV}</button>`).join('')}</div>`:''}`;
  wire();
  $('zoomhere').onclick=()=>{zoomTo(e.p[0],e.p[1],11);if(phone())setDetent('peek');};
  $('copyc').onclick=()=>copyText(`${e.lat.toFixed(6)}, ${e.lon.toFixed(6)}`,'Coordinates copied');
}

function renderList(){
  const vis=visible();
  head('Browse', vis.length+(vis.length===1?' entry':' entries'));
  const cmp={
    name:(a,b)=>a.n.localeCompare(b.n),
    year:(a,b)=>((+b.built||0)-(+a.built||0))||a.n.localeCompare(b.n),
    region:(a,b)=>{const ra=(D.regions.find(r=>r.id===a.reg)||{}).na||'',
                         rb=(D.regions.find(r=>r.id===b.reg)||{}).na||'';
                   return ra.localeCompare(rb)||a.n.localeCompare(b.n);}
  }[sortBy]||((a,b)=>a.n.localeCompare(b.n));
  let out=`<p class="eyebrow">Register</p>
    <h1 class="lt sm">${vis.length} ${vis.length===1?'entry':'entries'}</h1>
    ${query?`<p class="sub">Matching "${esc(query)}"</p>`:''}
    ${dom!=='all'?`<p class="sub">Sector: ${esc(domName(dom))}</p>`:''}
    <div class="seg" role="tablist" aria-label="Evidence">
      ${[['all','All'],['doc','Documented'],['inst','Sites'],['ctx','Context']].map(([k,l])=>
        `<button role="tab" data-ev="${k}" aria-selected="${ev===k}">${l}</button>`).join('')}
    </div>
    <div class="seg" role="tablist" aria-label="Sort">
      ${[['name','A to Z'],['year','Newest'],['region','By region']].map(([k,l])=>
        `<button role="tab" data-sort="${k}" aria-selected="${sortBy===k}">${l}</button>`).join('')}
    </div>`;
  if(ev!=='all') out+=`<p class="note" style="margin-top:10px">${esc(CLSDESC[ev])}</p>`;
  if(sortBy==='region'){
    D.regions.forEach(r=>{
      const g=vis.filter(e=>e.reg===r.id).sort(cmp); if(!g.length) return;
      out+=`<div class="sec">${esc(r.na)}, ${g.length}</div><div class="grp">${g.map(rowHTML).join('')}</div>`;
    });
  }else{
    const byMap=DOMKEYS.slice().sort((a,b)=>mapCount(b)-mapCount(a));
    byMap.forEach(k=>{
      const g=vis.filter(e=>e.dom===k).sort(cmp); if(!g.length) return;
      out+=`<div class="sec">${esc(domName(k))}, ${g.length}</div><div class="grp">${g.map(rowHTML).join('')}</div>`;
    });
  }
  if(!vis.length) out+=`<div class="callout"><p>Nothing matches. Clear the search field, or set the sector chip above the map back to All.</p></div>`;
  $('pane').innerHTML=out; wire();
  $('pane').querySelectorAll('[data-sort]').forEach(b=>b.onclick=()=>{sortBy=b.dataset.sort;renderList();});
  $('pane').querySelectorAll('[data-ev]').forEach(b=>b.onclick=()=>{ev=b.dataset.ev;paint();renderList();});
}

function renderGroups(){
  head('Research groups','Eight groups at ZAG');
  const tot=GROUPS.reduce((s,g)=>s+g.pub,0);
  $('pane').innerHTML=`
    <p class="eyebrow">Who does the work</p><h1 class="lt sm">${GROUPS.length} research groups</h1>
    <p class="sub">${D.meta.researchers} researchers, ${tot.toLocaleString('en-GB')} recorded publications</p>
    <p class="lede">ZAG is organised into eight research groups. The bar shows each group's share of the
      institute's recorded publications, which is the only public measure of relative size.</p>
    <div class="sec">Ranked by recorded publications</div>
    <div class="grp">${GROUPS.map((g,i)=>`
      <button class="row rank" data-domgo="${g.dom}">
        <span class="rn">${i+1}</span>
        <span class="mkic">${glyphSVG(g.dom,'doc',28)}</span>
        <span class="two"><b>${esc(g.en)}</b>
          <s>${esc(g.n)}. Led by ${esc(g.lead)}. ${esc(g.d)}</s>
          <span class="bar"><span style="width:${Math.round(100*g.pub/GROUPS[0].pub)}%;background:var(--d-${g.dom})"></span></span></span>
        <s><b style="font-weight:700;font-size:16px">${g.pub.toLocaleString('en-GB')}</b><br>records</s>${CHEV}</button>`).join('')}</div>
    <p class="note">Group names, leaders and publication counts come from the SICRIS organisation record
      for ZAG. Clicking a group filters the map to the sector that group works in.</p>
    <div class="sec">Source</div>${citeBlock(['sicris_org'])}`;
  wire();
}
function renderProjects(){
  const q=query.trim().toLowerCase();
  const list=PROJ.filter(p=>{
    if(dom!=='all'&&p.dom!==dom) return false;
    if(!q) return true;
    return [p.ac,p.t,p.fund,p.y,p.lead,p.d,p.role].join(' ').toLowerCase().includes(q);
  });
  head('Projects', list.length+' of '+PROJ.length);
  let out=`<p class="eyebrow">Research and development</p>
    <h1 class="lt sm">${list.length} project${list.length===1?'':'s'}</h1>
    <p class="lede">Projects ZAG runs or takes part in, from the institute's own national and
      international project registers, the SICRIS record and CORDIS. Sectors are ordered by how many
      projects they hold. Each project lists the sites on this map that it touches.</p>
    ${dom!=='all'?`<p class="sub">Sector: ${esc(domName(dom))}</p>`:''}`;
  DOMKEYS.forEach(k=>{
    const g=list.filter(p=>p.dom===k); if(!g.length) return;
    g.sort((a,b)=>(b.kind==='programme'?1:0)-(a.kind==='programme'?1:0)
      || String(b.y).localeCompare(String(a.y)) || a.ac.localeCompare(b.ac));
    out+=`<div class="sec">${esc(domName(k))}, ${g.length}</div><div class="grp">${g.map(projRow).join('')}</div>`;
  });
  if(!list.length) out+=`<div class="callout"><p>No project matches. Clear the search field or reset the sector chip.</p></div>`;
  $('pane').innerHTML=out; wire();
}
function renderProject(id){
  const p=PROJ.find(x=>x.id===id); if(!p){renderProjects();return;}
  head(p.ac, domName(p.dom));
  const sites=p.sites.map(s=>entries.find(e=>e.id===s)).filter(Boolean);
  $('pane').innerHTML=`
    <p class="eyebrow">${esc(domName(p.dom))}</p>
    <h1 class="lt sm">${esc(p.ac)}</h1>
    <p class="sub">${esc(p.t)}</p>
    <p class="tagrow"><span class="badge dom" style="color:var(--d-${p.dom})">${glyphSVG(p.dom,'doc',18)}
      <span style="color:var(--label)">${esc(domName(p.dom))}</span></span>
      <span class="badge"><span>ZAG is ${esc(p.role.toLowerCase())}</span></span>
      ${p.kind==='programme'?'<span class="badge"><span>Research programme</span></span>':''}</p>
    <p class="lede">${esc(p.d)}</p>
    <div class="sec">Particulars</div>
    <div class="grp">
      <div class="fr"><span class="k">Funder</span><span class="v">${esc(p.fund)}</span></div>
      <div class="fr"><span class="k">Years</span><span class="v mono">${esc(p.y)}</span></div>
      <div class="fr"><span class="k">ZAG role</span><span class="v">${esc(p.role)}</span></div>
      <div class="fr"><span class="k">ZAG lead</span><span class="v">${esc(p.lead)}</span></div>
    </div>
    ${sites.length?`<div class="sec">Sites on the map</div><div class="grp">${sites.map(rowHTML).join('')}</div>`:''}
    <div class="sec">Sources</div>${citeBlock(p.src)}
    <div class="btnrow"><button class="btn ghost" data-view="projects">All projects</button></div>`;
  wire();
}

function renderRegion(r){
  head(r.na,'Statistical region '+r.id);
  const inR=entries.filter(e=>e.reg===r.id);
  const munN=D.muns.filter(m=>m.r===r.id).length;
  const area=D.muns.filter(m=>m.r===r.id).reduce((s,m)=>s+m.a,0);
  $('pane').innerHTML=`
    <p class="eyebrow">Statistical region, ${esc(r.id)}</p>
    <h1 class="lt sm">${esc(r.na)}</h1>
    <p class="sub">NUTS 3 region</p>
    <div class="sec">Particulars</div>
    <div class="grp">
      <div class="fr"><span class="k">Municipalities</span><span class="v mono">${munN}</span></div>
      <div class="fr"><span class="k">Area</span><span class="v mono">${Math.round(area).toLocaleString('en-GB')} km²</span></div>
      <div class="fr"><span class="k">Entries here</span><span class="v mono">${inR.length}</span></div>
    </div>
    ${inR.length?`<div class="sec">Sites and structures</div><div class="grp">${inR.map(rowHTML).join('')}</div>`
      :`<div class="callout"><p>Nothing in the register sits in ${esc(r.na)} yet. That is a gap in what is published, not a claim that ZAG has done no work here.</p></div>`}
    <div class="btnrow"><button class="btn ghost" data-view="regions">All regions</button></div>`;
  wire();
}
function renderRegions(){
  head('Regions','Twelve NUTS 3 regions');
  $('pane').innerHTML=`
    <p class="eyebrow">Slovenia</p><h1 class="lt sm">Statistical regions</h1>
    <p class="sub">Eurostat NUTS 3</p>
    <div class="sec">All regions</div>
    <div class="grp">${D.regions.map(r=>{
      const c=entries.filter(e=>e.reg===r.id).length;
      return `<button class="row" data-reg-go="${r.id}"><b>${esc(r.na)}</b><s>${c||'none'}</s>${CHEV}</button>`;
    }).join('')}</div>`;
  wire();
}
function regionBox(r){
  const nums=r.d.match(/-?\d+(\.\d+)?/g); if(!nums) return null;
  let x0=1e9,y0=1e9,x1=-1e9,y1=-1e9;
  for(let i=0;i+1<nums.length;i+=2){
    const x=+nums[i],y=+nums[i+1];
    if(x<x0)x0=x; if(x>x1)x1=x; if(y<y0)y0=y; if(y>y1)y1=y;
  }
  return [x0,y0,x1,y1];
}
function renderRiver(name){
  const r=D.rivers.find(x=>x.n===name); if(!r){renderHome();return;}
  head(r.n, r.km+' km in Slovenia');
  const on=entries.filter(e=>e.crosses===name);
  $('pane').innerHTML=`
    <p class="eyebrow">Watercourse</p><h1 class="lt sm">${esc(r.n)}</h1>
    <p class="sub">${r.km} km within Slovenia</p>
    <p class="lede">Rivers come from Natural Earth centrelines at 1:10 million, so the alignment is
      indicative rather than survey grade. They are drawn to show which structure crosses which water.</p>
    <div class="sec">Entries on this river</div>
    ${on.length?`<div class="grp">${on.map(rowHTML).join('')}</div>`
      :`<div class="callout"><p>No entry in the register crosses the ${esc(r.n)} yet.</p></div>`}
    <p class="note">Only the Sava, Drava, Mura and Ljubljanica are carried. The Soča, Savinja, Krka and
      Kolpa are absent from the open river data at usable resolution.</p>`;
  wire();
}

function renderSources(){
  head('Sources','Every reference used');
  const used={};
  entries.forEach(e=>(e.src||[]).forEach(k=>{(used[k]=used[k]||[]).push(e.n);}));
  PROJ.forEach(p=>(p.src||[]).forEach(k=>{(used[k]=used[k]||[]).push(p.ac);}));
  const keys=Object.keys(SRC).sort((a,b)=>{
    const ord={journal:0,conference:1,report:2,inst:3,web:4};
    return (ord[SRC[a].k]-ord[SRC[b].k])||((SRC[b].y||0)-(SRC[a].y||0))
        || String(SRC[a].t).localeCompare(String(SRC[b].t));
  });
  let out=`<p class="eyebrow">Bibliography</p><h1 class="lt sm">${keys.length} sources</h1>
    <p class="lede">Every factual claim on an entry or project page traces to one of these.
      Peer reviewed work comes first, then official records, then web pages.</p>`;
  ['journal','conference','report','inst','web'].forEach(kind=>{
    const g=keys.filter(k=>SRC[k].k===kind); if(!g.length) return;
    out+=`<div class="sec">${esc(KIND[kind])}, ${g.length}</div>
      <div class="grp">${g.map(k=>{
        const on=used[k]||[];
        return `<div class="cite">${fmtCite(k)}
          ${on.length?`<div class="citedby">Cited by ${on.map(esc).join(', ')}</div>`:''}
          <span class="acts">${SRC[k].u?`<a href="${esc(SRC[k].u)}" target="_blank" rel="noopener">Open source</a>`:''}
          <button data-cite="${esc(k)}">Copy reference</button></span></div>`;
      }).join('')}</div>`;
  });
  out+=`<p class="note">Links open in a new tab. Copy reference puts a plain text citation on the clipboard.</p>`;
  $('pane').innerHTML=out; wire();
}

function renderLayers(){
  head('Legend and layers','Map display');
  const items=[['peaks','Named peaks','Triglav, the only Slovenian peak in the open dataset'],
               ['mun','Municipal boundaries','212 municipalities'],
               ['reg','Statistical region outlines','NUTS 3'],
               ['shade','Shade regions by entry count','Darker means more entries'],
               ['riv','Rivers','Sava, Drava, Mura, Ljubljanica'],
               ['mot','Motorways',''],['rail','Railways',''],
               ['grat','Latitude and longitude grid','0.5 by 0.25 degrees'],
               ['names','Marker labels when zoomed in','']];
  const th=document.documentElement.getAttribute('data-theme')||'auto';
  $('pane').innerHTML=`
    <p class="eyebrow">Map</p><h1 class="lt sm">Legend and layers</h1>
    ${legendHTML()}
    <div class="sec">Show on the map</div>
    <div class="grp">${items.map(([k,l,s])=>
      `<div class="row" style="cursor:default">
        <span class="two"><b>${esc(l)}</b>${s?`<s>${esc(s)}</s>`:''}</span>
        <span class="switch"><input type="checkbox" data-layer="${k}" ${LAYERS[k]?'checked':''}
          aria-label="${esc(l)}"><i></i></span></div>`).join('')}</div>
    <div class="sec">Appearance</div>
    <div class="seg" role="tablist" aria-label="Appearance">
      ${[['auto','Automatic'],['light','Light'],['dark','Dark']].map(([k,l])=>
        `<button role="tab" data-theme="${k}" aria-selected="${th===k}">${l}</button>`).join('')}
    </div>
    <p class="note">Automatic follows the light or dark setting of your computer or phone.
      The choice is remembered in this browser.</p>`;
  $('pane').querySelectorAll('[data-layer]').forEach(c=>c.onchange=()=>{
    LAYERS[c.dataset.layer]=c.checked; paint();});
  $('pane').querySelectorAll('[data-theme]').forEach(b=>b.onclick=()=>{
    const v=b.dataset.theme;
    if(v==='auto') document.documentElement.removeAttribute('data-theme');
    else document.documentElement.setAttribute('data-theme',v);
    try{localStorage.setItem('zag-theme',v);}catch(_){}
    $('pane').querySelectorAll('[data-theme]').forEach(x=>x.setAttribute('aria-selected',x.dataset.theme===v));
    paintMapLegend();
  });
}

function renderMethod(){
  head('Method','Data, accuracy and gaps');
  $('pane').innerHTML=`
    <p class="eyebrow">Method</p><h1 class="lt sm">How this map was built</h1>
    <p class="lede">Every boundary, line and marker traces to a named open dataset. Nothing is drawn by
      hand, and nothing about ZAG is asserted without a citation you can open.</p>

    <div class="sec">Borders</div>
    <div class="callout"><p class="body">The outline is dissolved upward from Slovenia's ${D.meta.muns}
      municipalities at OpenStreetMap detail. It measures <span class="mono">${D.meta.area_km2.toLocaleString('en-GB')} km²</span>
      against the official <span class="mono">20,271 km²</span>, a difference of 0.05 per cent.</p></div>
    <div class="grp" style="margin-top:12px">
      <div class="fr"><span class="k">Croatia</span><span class="v mono">652 km measured, 670 published</span></div>
      <div class="fr"><span class="k">Austria</span><span class="v mono">321 km, 330</span></div>
      <div class="fr"><span class="k">Italy</span><span class="v mono">228 km, 232</span></div>
      <div class="fr"><span class="k">Hungary</span><span class="v mono">109 km, 102</span></div>
    </div>
    <p class="note">A 185 km² wedge reaching into the Gulf of Trieste was present in the source. That is
      Slovenia's claimed Piran Bay maritime area, not land, and it has been cut. The coastline elsewhere
      keeps its original detail. The Hungarian figure exceeds the published one because the reference
      outline for that stretch is heavily simplified.</p>

    <div class="sec">Projection</div>
    <div class="callout"><p class="body">Everything is projected to <span class="mono">EPSG:3794</span>,
      D96/TM, Slovenia's national grid. One map unit is <span class="mono">${MPU} m</span>. Coordinates
      are converted with the same transverse Mercator maths, checked against a reference implementation
      to below a millimetre.</p></div>

    <div class="sec">Coordinate precision</div>
    <div class="grp">${['surveyed','derived','locality','approximate','address'].map(k=>{
      const n=entries.filter(e=>e.prec===k).length;
      return n?`<div class="fr"><span class="k">${esc(PREC[k])}</span><span class="v mono">${n}</span></div>`:'';
    }).join('')}</div>
    <p class="note">Only entries marked as a published coordinate are survey grade. Everything else is a
      settlement centre, a street address or a point read off a road alignment, and each entry page says which.</p>

    <div class="sec">Where the data comes from</div>
    <div class="grp">
      <div class="fr"><span class="k">Municipalities</span><span class="v">geoBoundaries, OSM detail</span></div>
      <div class="fr"><span class="k">Regions</span><span class="v">Eurostat NUTS 3</span></div>
      <div class="fr"><span class="k">Roads, rail, rivers</span><span class="v">Natural Earth 1:10M</span></div>
      <div class="fr"><span class="k">Named peaks</span><span class="v">Natural Earth elevation points</span></div>
      <div class="fr"><span class="k">Structures</span><span class="v">Peer reviewed papers, ZAG bulletins and annual reports</span></div>
      <div class="fr"><span class="k">Projects</span><span class="v">ZAG national and international project registers, SICRIS and CORDIS</span></div>
      <div class="fr"><span class="k">Research groups</span><span class="v">SICRIS organisation record 743</span></div>
    </div>

    <div class="sec">Keyboard</div>
    <div class="grp">
      <div class="fr"><span class="k">Pan</span><span class="v"><kbd>&larr;</kbd> <kbd>&rarr;</kbd> <kbd>&uarr;</kbd> <kbd>&darr;</kbd></span></div>
      <div class="fr"><span class="k">Zoom</span><span class="v"><kbd>+</kbd> <kbd>&minus;</kbd></span></div>
      <div class="fr"><span class="k">Clear selection</span><span class="v"><kbd>Esc</kbd></span></div>
      <div class="fr"><span class="k">Move through markers</span><span class="v"><kbd>Tab</kbd></span></div>
    </div>

    <div class="sec">How complete the project list is</div>
    <div class="callout"><p class="body">SICRIS records <span class="mono">${D.meta.aris_total}</span>
      ARIS projects for ZAG and <span class="mono">${D.meta.researchers}</span> researchers across
      ${GROUPS.length} research groups. The <span class="mono">${PROJ.length}</span> projects listed
      here are those with a public record that names the title, the funder, the years and the ZAG
      leader. The rest are older or not individually published.</p></div>

    <div class="sec">Known gaps</div>
    <ul class="plain">
      <li>No photographs. Image files could not be fetched from the environment this was built in, so
        nothing is illustrated rather than illustrated wrongly.</li>
      <li>There is no terrain shading. No digital elevation model was reachable from the environment
        this was built in. The Natural Earth landform polygons were tried and rejected: at this scale
        they place Triglav, the highest peak in the country, in the lowland, and they place Ljubljana,
        which sits in a basin, inside the Dinaric Alps. Shading from them would have looked physical
        and been wrong. Triglav itself is drawn because its own coordinate in that dataset is correct.</li>
      <li>Municipality names arrived with the Slovenian diacritics corrupted, so the geometry is kept
        and the names are not shown.</li>
      <li>ZAG publishes no named project list for its commercial testing work, and its annual reports
        describe that work by category rather than by structure.</li>
      <li>AI generated web summaries claim ZAG involvement in structures the primary records do not
        support. The Puch Bridge at Ptuj is one such case and is kept as context, with the reason stated
        on its page.</li>
      <li>Two papers give different dimensions for the Ravbarkomanda viaduct. Both are shown rather than
        silently picking one.</li>
    </ul>

    <div class="sec">Everything cited</div>
    <div class="grp"><button class="row" data-view="sources"><b>All ${Object.keys(SRC).length} sources</b>${CHEV}</button></div>
    <p class="note">Built ${esc(D.meta.built)}. Base data from geoBoundaries, Eurostat Nuts2json and Natural Earth.</p>`;
  wire();
}

/* =============================== controls ================================ */
function setDom(k){
  dom=k;
  const f=$('filters');
  if(f) [...f.children].forEach(x=>x.setAttribute('aria-pressed',x.dataset.dom===k));
  sel=null; paint();
  announce(visible().length+' entries shown');
}
function buildChips(){
  const f=$('filters');
  f.textContent='';
  const add=(k,label)=>{
    const b=document.createElement('button');
    b.className='chip'; b.setAttribute('aria-pressed',k===dom); b.dataset.dom=k;
    b.innerHTML=(k==='all'?'':`<i style="background:var(--d-${k})"></i>`)+esc(label)+' <u></u>';
    if(k!=='all') b.dataset.np=projCount(k);
    b.title = k==='all' ? 'Show every sector'
      : `${projCount(k)} projects, ${mapCount(k)} on the map. ${(DOMS[k]||{}).d||''}`;
    b.onclick=()=>{
      setDom(k);
      const cur=stack[stack.length-1];
      if(k!=='all'&&mapCount(k)===0) go({t:'projects'},true);
      else if(cur.t==='list'||cur.t==='projects') enter(cur,true);
    };
    f.appendChild(b);
  };
  add('all','All');
  const SHORT={bridge:'Bridges',ai:'AI & data',energy:'Hydropower',geo:'Geotechnics',
               fire:'Fire safety',mat:'Materials',inst:'Institutions',
               build:'Buildings',herit:'Heritage'};
  DOMKEYS.forEach(k=>add(k,SHORT[k]||domName(k)));
}
buildChips();
$('layersbtn').onclick=()=>go({t:'layers'});
{
  const box=$('searchbox'), inp=$('q');
  let t0;
  inp.addEventListener('input',()=>{
    query=inp.value; box.classList.toggle('has',!!query);
    clearTimeout(t0);
    t0=setTimeout(()=>{
      paint();
      const cur=stack[stack.length-1];
      if(cur.t==='projects') enter(cur,true);
      else if(query) go({t:'list'},true);
      else if(cur.t==='list') enter(cur,true);
    },140);
  });
  $('qclr').onclick=()=>{inp.value='';query='';box.classList.remove('has');paint();go({t:'home'},true);inp.focus();};
}

/* ============================== tabs and tips ============================ */
{
  const t=$('tabs');
  TABS.forEach(([k,label])=>{
    const b=document.createElement('button');
    b.setAttribute('role','tab'); b.dataset.tab=k;
    b.setAttribute('aria-selected', k==='detail'); b.textContent=label;
    b.onclick=()=>{
      if(k==='detail'&&sel) go({t:'entry',id:sel},true);
      else go(TABROOT[k],true);
    };
    t.appendChild(b);
  });
}
(function(){
  const tip=$('tip'), wrap=$('mapwrap');
  if(!tip||!wrap) return;
  let raf2=0;
  function show(txt,cx,cy){
    const r=wrap.getBoundingClientRect();
    tip.textContent=txt;
    tip.style.left=(cx-r.left)+'px'; tip.style.top=(cy-r.top)+'px';
    tip.classList.add('on');
  }
  svg.addEventListener('pointermove',e2=>{
    if(phone()||drag||pinch){tip.classList.remove('on');return;}
    cancelAnimationFrame(raf2);
    raf2=requestAnimationFrame(()=>{
      const t0=hitAt(e2.clientX,e2.clientY);
      if(!t0){tip.classList.remove('on');svg.style.cursor='';return;}
      const mk=t0.closest('.mk'), cl=t0.closest('.cl'),
            rv=t0.closest('.rivhit'), rg=t0.closest('.regfill');
      if(mk){ const e=entries.find(x=>x.id===mk.dataset.id);
        if(e) show(e.n+', '+domName(e.dom),e2.clientX,e2.clientY); }
      else if(cl){ const ns=cl.__names||[];
        show(ns.slice(0,3).join(', ')+(ns.length>3?' and '+(ns.length-3)+' more':''),e2.clientX,e2.clientY); }
      else if(rv){ show(rv.getAttribute('aria-label'),e2.clientX,e2.clientY); }
      else if(rg){ show(rg.getAttribute('aria-label'),e2.clientX,e2.clientY); }
      else tip.classList.remove('on');
      svg.style.cursor='pointer';
    });
  });
  svg.addEventListener('pointerleave',()=>{tip.classList.remove('on');svg.style.cursor='';});
  svg.addEventListener('pointerdown',()=>tip.classList.remove('on'));
})();

/* ================================= boot ================================== */
try{ const t=localStorage.getItem('zag-theme');
  if(t&&t!=='auto') document.documentElement.setAttribute('data-theme',t); }catch(_){}
drawMarkers();
paintMapLegend();
setDetent(phone()?'mid':'full',false);
measureSheet();
snapHome();
paint();
enter(stack[0],true);
requestAnimationFrame(()=>{measureSheet();snapHome();paint();});
(function(){
  const h=decodeURIComponent(location.hash.replace('#',''));
  if(h && entries.some(e=>e.id===h)) setTimeout(()=>go({t:'entry',id:h}),80);
})();

</script>

</body>
</html>
