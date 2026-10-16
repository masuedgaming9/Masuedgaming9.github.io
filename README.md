
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#090914">
<title>FORGE X — Ultimate File Tools</title>
<style>
*{box-sizing:border-box}
:root{--bg:#090914;--card:#121225;--line:#292747;--purple:#9b7bff;--cyan:#53e7ff;--text:#f7f5ff;--muted:#aaa7c5}
body{margin:0;background:var(--bg);color:var(--text);font-family:Inter,system-ui,Arial,sans-serif}
body:before{content:"";position:fixed;inset:0;z-index:-1;pointer-events:none;background:radial-gradient(ellipse at 10% 0%,#45217c44,transparent 40%),radial-gradient(ellipse at 90% 25%,#004e6840,transparent 35%)}
header{display:flex;align-items:center;justify-content:space-between;gap:15px;padding:20px 5%;border-bottom:1px solid #ffffff12;background:#090914d9;backdrop-filter:blur(16px);position:sticky;top:0;z-index:5}
.logo{font-weight:1000;font-size:25px;letter-spacing:-1.5px}.logo span{color:var(--purple)}
.tag{border:1px solid #53e7ff55;color:var(--cyan);border-radius:50px;padding:7px 12px;font-size:11px;font-weight:800;letter-spacing:1px}
main{max-width:1120px;margin:auto;padding:25px 18px 55px}
.hero{text-align:center;padding:55px 0 35px}
.eyebrow{color:var(--cyan);font-size:12px;letter-spacing:3px;font-weight:900}
h1{font-size:clamp(40px,8vw,76px);line-height:1.02;letter-spacing:-4px;margin:18px 0}
.gradient{background:linear-gradient(90deg,#a78bfa,#53e7ff,#ff86dc);background-clip:text;color:transparent}
.hero p{max-width:600px;margin:0 auto;color:var(--muted);line-height:1.8}
.stats{display:flex;justify-content:center;gap:10px;flex-wrap:wrap;margin-top:25px}
.stat{padding:8px 13px;border:1px solid var(--line);background:#ffffff05;border-radius:50px;font-size:12px;color:#d8d4f5}
.search{display:block;width:100%;padding:16px 18px;background:#121225;border:1px solid var(--line);border-radius:14px;color:white;font-size:15px;outline:none;margin:12px 0 22px}
.search:focus{border-color:var(--purple);box-shadow:0 0 20px #9b7bff20}
.sectionhead{display:flex;justify-content:space-between;align-items:center;gap:10px;margin:30px 0 15px}
.sectionhead h2{margin:0;font-size:20px}
.sectionhead small{color:var(--muted)}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(min(100%,225px),1fr));gap:15px}
.card{position:relative;overflow:hidden;background:linear-gradient(145deg,#17172d,#10101d);border:1px solid var(--line);border-radius:18px;padding:21px;transition:.25s}
.card:before{content:"";position:absolute;top:0;left:15%;width:70%;height:1px;background:linear-gradient(90deg,transparent,var(--purple),transparent);opacity:.7}
.card:hover{transform:translateY(-5px);border-color:#8f77ed;box-shadow:0 15px 45px #0007,0 0 22px #9b7bff12}
.ico{width:49px;height:49px;display:grid;place-items:center;border-radius:14px;background:linear-gradient(135deg,#6c43d744,#34cce522);font-size:25px;margin-bottom:18px}
.card h3{margin:0 0 8px;font-size:17px}
.card p{color:var(--muted);font-size:13px;line-height:1.7;min-height:43px;margin:0 0 18px}
button{font:inherit;cursor:pointer}
.btn{border:0;background:linear-gradient(100deg,#8b65f7,#5b9bff);color:white;font-weight:850;padding:12px 15px;border-radius:10px;width:100%;transition:.2s}
.btn:hover{filter:brightness(1.15);box-shadow:0 5px 20px #886aff33}
.workspace{margin-top:24px;padding:24px;border:1px solid #6550a5;background:linear-gradient(145deg,#17172c,#10101d);border-radius:20px}
.workspace h2{margin-top:0}
#controls{margin-top:18px}
input,select,textarea{max-width:100%;padding:11px;background:#090914;color:white;border:1px solid #393657;border-radius:10px;margin:8px 0}
textarea{width:100%}
.drop{border:2px dashed #6550a5;border-radius:16px;padding:24px;text-align:center;background:#9b7bff08;margin:12px 0}
.drop p{color:var(--muted);font-size:13px}
.action{width:auto;margin-top:12px}
#status{margin-top:17px;color:#81f4c0;overflow-wrap:anywhere}
#status a{display:inline-block;margin:8px;color:var(--cyan);font-weight:bold}
.notice{margin-top:25px;border:1px solid #ffffff13;background:#ffffff05;border-radius:15px;padding:17px;color:var(--muted);font-size:13px;line-height:1.8}
footer{border-top:1px solid #ffffff12;text-align:center;padding:28px 15px;color:var(--muted);font-size:12px;line-height:2}
footer strong{color:white}footer .credit{color:var(--purple);font-weight:900}
[hidden]{display:none!important}
@media(max-width:550px){header{padding:15px}.logo{font-size:20px}.tag{font-size:9px;padding:6px 8px}.hero{padding:40px 0 25px}h1{letter-spacing:-2px}.workspace{padding:17px}}
</style>
</head>
<body>
<header>
  <div class="logo">FORGE <span>X</span> ⚡</div>
  <div class="tag">✦ FREE FILE LAB</div>
</header>

<main>
<section class="hero">
  <div class="eyebrow">THE ULTIMATE FILE TOOLKIT</div>
  <h1>Your files.<br><span class="gradient">Your rules.</span></h1>
  <p>Convert. Compress. Create. One powerful workspace for your everyday file tasks, right inside your browser.</p>
  <div class="stats">
    <div class="stat">⚡ Fast browser processing</div>
    <div class="stat">🔒 Files stay on your device</div>
    <div class="stat">💎 Free to use</div>
  </div>
</section>

<input class="search" id="search" placeholder="⌕  Search tools... (PDF, image, ZIP)" oninput="filterTools()">

<div class="sectionhead"><h2>⚡ All Tools</h2><small id="count">5 tools</small></div>
<section class="grid" id="grid">
  <article class="card" data-name="image to pdf photo convert">
    <div class="ico">📄</div><h3>Image → PDF</h3>
    <p>Turn multiple photos into one portable PDF document.</p>
    <button class="btn" onclick="openTool('pdf')">Launch Tool ↗</button>
  </article>
  <article class="card" data-name="compress image photo size">
    <div class="ico">🗜️</div><h3>Image Compressor</h3>
    <p>Reduce image file size with adjustable quality.</p>
    <button class="btn" onclick="openTool('compress')">Launch Tool ↗</button>
  </article>
  <article class="card" data-name="image converter jpg png webp">
    <div class="ico">🔄</div><h3>Image Converter</h3>
    <p>Convert images into JPG, PNG, or WebP formats.</p>
    <button class="btn" onclick="openTool('convert')">Launch Tool ↗</button>
  </article>
  <article class="card" data-name="zip archive files compress">
    <div class="ico">📦</div><h3>ZIP Creator</h3>
    <p>Bundle several files into one downloadable ZIP archive.</p>
    <button class="btn" onclick="openTool('zip')">Launch Tool ↗</button>
  </article>
  <article class="card" data-name="text to pdf document notes">
    <div class="ico">✍️</div><h3>Text → PDF</h3>
    <p>Transform typed notes into a clean PDF document.</p>
    <button class="btn" onclick="openTool('text')">Launch Tool ↗</button>
  </article>
</section>

<section class="workspace" id="workspace" hidden>
  <div class="eyebrow">TOOL WORKSPACE</div>
  <h2 id="heading">Ready to create?</h2>
  <div id="controls"></div>
  <div id="status"></div>
</section>

<div class="notice">
  <strong>🔐 Privacy-first processing</strong><br>
  Supported operations run locally in your browser. PDF and ZIP tools load their libraries from a CDN, so an internet connection is needed. Very large files may use a lot of your device's memory.
</div>
</main>

<footer>
  <strong>FORGE X</strong> · Ultimate File Tools<br>
  Created by <span class="credit">Masud Gaming 9</span><br>
  Made with ❤️ by <strong>ChatGPT AI</strong><br>
  © 2026 · Free to use
</footer>

<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.10.1/jszip.min.js"></script>
<script>
const $=id=>document.getElementById(id);

function filterTools(){
 const q=$('search').value.toLowerCase();
 let n=0;
 document.querySelectorAll('.card').forEach(c=>{
  const show=(c.dataset.name+' '+c.innerText).toLowerCase().includes(q);
  c.hidden=!show;if(show)n++;
 });
 $('count').textContent=n+' tool'+(n===1?'':'s');
}

function openTool(t){
 $('workspace').hidden=false;$('status').textContent='';
 const configs={
 pdf:['Image to PDF',`<div class="drop">📂<br>Choose your images<p>Select multiple images in the order you want them in the PDF.</p><input id="files" type="file" accept="image/*" multiple></div><button class="btn action" onclick="makePDF()">⚡ Create PDF</button>`],
 compress:['Image Compressor',`<div class="drop">📷<br><input id="files" type="file" accept="image/*"></div><label>Quality: <span id="qval">65%</span></label><br><input id="quality" type="range" min="10" max="95" value="65" oninput="qval.textContent=this.value+'%'"><br><button class="btn action" onclick="convertImage(true)">🗜️ Compress Image</button>`],
 convert:['Image Converter',`<div class="drop">🖼️<br><input id="files" type="file" accept="image/*"></div><label>Output format</label><br><select id="format"><option value="image/jpeg">JPG</option><option value="image/png">PNG</option><option value="image/webp">WebP</option></select><br><button class="btn action" onclick="convertImage(false)">🔄 Convert Image</button>`],
 zip:['ZIP Creator',`<div class="drop">📁<br><input id="files" type="file" multiple><p>Choose one or more files to bundle.</p></div><button class="btn action" onclick="makeZIP()">📦 Create ZIP</button>`],
 text:['Text to PDF',`<textarea id="words" rows="8" placeholder="Write or paste your notes here..."></textarea><br><button class="btn action" onclick="makeTextPDF()">📄 Generate PDF</button>`]
 };
 $('heading').textContent=configs[t][0];$('controls').innerHTML=configs[t][1];
 $('workspace').scrollIntoView({behavior:'smooth',block:'start'});
}

function status(s){$('status').textContent=s}
function download(blob,name){
 const url=URL.createObjectURL(blob),a=document.createElement('a');
 a.href=url;a.download=name;a.textContent='⬇ Download '+name;
 $('status').replaceChildren(document.createTextNode('✅ Ready! '),a);
 a.click();setTimeout(()=>URL.revokeObjectURL(url),60000);
}
function getFiles(){
 const f=$('files').files;
 if(!f.length)throw Error('⚠ Please select a file first.');
 return [...f];
}
function loadImage(file){
 return new Promise((resolve,reject)=>{
  const url=URL.createObjectURL(file),img=new Image();
  img.onload=()=>{URL.revokeObjectURL(url);resolve(img)};
  img.onerror=()=>reject(Error('Could not open this image.'));
  img.src=url;
 });
}

async function convertImage(compress){
 try{
  const f=getFiles()[0],img=await loadImage(f);
  let w=img.naturalWidth,h=img.naturalHeight;
  if(compress&&w>1600){h=Math.round(h*1600/w);w=1600}
  const canvas=document.createElement('canvas');canvas.width=w;canvas.height=h;
  const ctx=canvas.getContext('2d'),fmt=compress?'image/jpeg':$('format').value;
  if(fmt==='image/jpeg'){ctx.fillStyle='#fff';ctx.fillRect(0,0,w,h)}
  ctx.drawImage(img,0,0,w,h);
  const blob=await new Promise(resolve=>canvas.toBlob(resolve,fmt,compress?+$('quality').value/100:.9));
  if(!blob)throw Error('Conversion failed. Try another format.');
  const ext=fmt.split('/')[1].replace('jpeg','jpg');
  download(blob,(compress?'compressed-':'converted-')+f.name.replace(/\.[^.]+$/,'')+'.'+ext);
 }catch(e){status(e.message)}
}

async function makePDF(){
 try{
  const files=getFiles();
  if(!window.jspdf)throw Error('PDF library unavailable. Check your internet.');
  const {jsPDF}=window.jspdf;let pdf;
  for(let i=0;i<files.length;i++){
   const img=await loadImage(files[i]);
   if(!pdf)pdf=new jsPDF();else pdf.addPage();
   const ratio=Math.min(190/img.naturalWidth,270/img.naturalHeight);
   const w=img.naturalWidth*ratio,h=img.naturalHeight*ratio;
   const c=document.createElement('canvas');c.width=img.naturalWidth;c.height=img.naturalHeight;
   const ctx=c.getContext('2d');ctx.fillStyle='#fff';ctx.fillRect(0,0,c.width,c.height);ctx.drawImage(img,0,0);
   pdf.addImage(c.toDataURL('image/jpeg',.9),'JPEG',(210-w)/2,(297-h)/2,w,h);
  }
  pdf.save('ForgeX-images.pdf');status('✅ Your PDF has been created!');
 }catch(e){status(e.message)}
}

async function makeZIP(){
 try{
  const files=getFiles();
  if(!window.JSZip)throw Error('ZIP library unavailable. Check your internet.');
  const zip=new JSZip();files.forEach(f=>zip.file(f.name,f));
  status('⚡ Building your archive...');
  const blob=await zip.generateAsync({type:'blob',compression:'DEFLATE',compressionOptions:{level:6}});
  download(blob,'ForgeX-files.zip');
 }catch(e){status(e.message)}
}

function makeTextPDF(){
 try{
  const text=$('words').value;
  if(!text.trim())throw Error('Write something first.');
  if(!window.jspdf)throw Error('PDF library unavailable. Check your internet.');
  const {jsPDF}=window.jspdf,pdf=new jsPDF();
  const lines=pdf.splitTextToSize(text,180);let y=15;
  lines.forEach(line=>{if(y>280){pdf.addPage();y=15}pdf.text(line,15,y);y+=7});
  pdf.save('ForgeX-document.pdf');status('✅ Your document is ready!');
 }catch(e){status(e.message)}
}
</script>
</body>
</html>
