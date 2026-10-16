
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>FileForge - Free File Tools</title>
<style>
*{box-sizing:border-box}
body{margin:0;background:#0b1020;color:#fff;font-family:Arial,sans-serif}
header{text-align:center;padding:30px 15px;background:#151e35}
h1{margin:0;color:#a99aff;font-size:34px}
header p{color:#c1c8db}
main{max-width:900px;margin:auto;padding:20px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:15px}
.card,#workspace{background:#151e35;border:1px solid #303d5b;border-radius:15px;padding:20px}
.card h3{margin-top:0}
.card p{color:#bdc7db;min-height:42px}
button{background:#8874ff;color:white;border:0;padding:12px;border-radius:9px;cursor:pointer;font-weight:bold}
button:hover{background:#7059f5}
.card button{width:100%}
#workspace{margin-top:20px}
input,select,textarea{max-width:100%;margin:10px 0;padding:10px;background:#0b1020;color:white;border:1px solid #465475;border-radius:8px}
textarea{width:100%}
#status{margin-top:15px;color:#8df0ba;overflow-wrap:anywhere}
a{color:#b8adff}
footer{text-align:center;padding:25px;color:#aab4ca}
</style>
</head>
<body>
<header>
<h1>FileForge ⚡</h1>
<p>All your file tools in one place — free and simple.</p>
</header>
<main>
<div class="grid">
<div class="card"><h3>🖼️ Image to PDF</h3><p>Convert multiple images into one PDF.</p><button onclick="openTool('pdf')">Open Tool</button></div>
<div class="card"><h3>📉 Compress Image</h3><p>Reduce photo size and quality.</p><button onclick="openTool('compress')">Open Tool</button></div>
<div class="card"><h3>🔄 Image Converter</h3><p>Convert JPG, PNG and WebP.</p><button onclick="openTool('convert')">Open Tool</button></div>
<div class="card"><h3>🗜️ ZIP Creator</h3><p>Combine files into one ZIP archive.</p><button onclick="openTool('zip')">Open Tool</button></div>
<div class="card"><h3>📝 Text to PDF</h3><p>Create a PDF from your text.</p><button onclick="openTool('text')">Open Tool</button></div>
</div>

<section id="workspace" hidden>
<h2 id="heading">File Tool</h2>
<div id="controls"></div>
<div id="status"></div>
</section>
</main>
<footer>FileForge © 2026 · Free File Tools</footer>

<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.10.1/jszip.min.js"></script>
<script>
const $=id=>document.getElementById(id);
let tool='';

function openTool(t){
 tool=t;
 $('workspace').hidden=false;
 $('status').textContent='';
 const configs={
 pdf:['Image to PDF',`<input id="files" type="file" accept="image/*" multiple><br><button onclick="makePDF()">Convert to PDF</button>`],
 compress:['Compress Image',`<input id="files" type="file" accept="image/*"><br>Quality: <input id="quality" type="range" min="10" max="95" value="65"><br><button onclick="convertImage(true)">Compress Image</button>`],
 convert:['Image Converter',`<input id="files" type="file" accept="image/*"><br><select id="format"><option value="image/jpeg">JPG</option><option value="image/png">PNG</option><option value="image/webp">WebP</option></select><br><button onclick="convertImage(false)">Convert Image</button>`],
 zip:['ZIP Creator',`<input id="files" type="file" multiple><br><button onclick="makeZIP()">Create ZIP</button>`],
 text:['Text to PDF',`<textarea id="words" rows="8" placeholder="Type your text here..."></textarea><br><button onclick="makeTextPDF()">Create PDF</button>`]
 };
 $('heading').textContent=configs[t][0];
 $('controls').innerHTML=configs[t][1];
 $('workspace').scrollIntoView({behavior:'smooth'});
}

function status(s){$('status').textContent=s}
function download(blob,name){
 const url=URL.createObjectURL(blob);
 const a=document.createElement('a');
 a.href=url;a.download=name;
 a.textContent='Download '+name;
 a.style.display='block';a.style.marginTop='15px';
 $('status').replaceChildren(a);
 a.click();
 setTimeout(()=>URL.revokeObjectURL(url),60000);
}
function getFiles(){
 const files=$('files').files;
 if(!files.length)throw Error('Please select a file first.');
 return [...files];
}
function loadImage(file){
 return new Promise((resolve,reject)=>{
 const url=URL.createObjectURL(file),img=new Image();
 img.onload=()=>{URL.revokeObjectURL(url);resolve(img)};
 img.onerror=()=>reject(Error('Cannot open this image.'));
 img.src=url;
 });
}

async function convertImage(compress){
 try{
 const f=getFiles()[0],img=await loadImage(f);
 const canvas=document.createElement('canvas');
 let w=img.naturalWidth,h=img.naturalHeight;
 if(compress&&w>1600){h=Math.round(h*1600/w);w=1600}
 canvas.width=w;canvas.height=h;
 const ctx=canvas.getContext('2d');
 const fmt=compress?'image/jpeg':$('format').value;
 if(fmt==='image/jpeg'){ctx.fillStyle='white';ctx.fillRect(0,0,w,h)}
 ctx.drawImage(img,0,0,w,h);
 const quality=compress?+$('quality').value/100:.9;
 const blob=await new Promise(resolve=>canvas.toBlob(resolve,fmt,quality));
 if(!blob)throw Error('Conversion failed.');
 const ext=fmt.split('/')[1].replace('jpeg','jpg');
 download(blob,'converted.'+ext);
 }catch(e){status(e.message)}
}

async function makePDF(){
 try{
 const files=getFiles();
 if(!window.jspdf)throw Error('PDF library unavailable. Check internet.');
 const {jsPDF}=window.jspdf;
 const pdf=new jsPDF();
 for(let i=0;i<files.length;i++){
 const img=await loadImage(files[i]);
 if(i)pdf.addPage();
 const ratio=Math.min(190/img.naturalWidth,270/img.naturalHeight);
 const w=img.naturalWidth*ratio,h=img.naturalHeight*ratio;
 const c=document.createElement('canvas');
 c.width=img.naturalWidth;c.height=img.naturalHeight;
 const ctx=c.getContext('2d');
 ctx.fillStyle='white';ctx.fillRect(0,0,c.width,c.height);
 ctx.drawImage(img,0,0);
 pdf.addImage(c.toDataURL('image/jpeg',.9),'JPEG',(210-w)/2,(297-h)/2,w,h);
 }
 pdf.save('images.pdf');status('PDF created!');
 }catch(e){status(e.message)}
}

async function makeZIP(){
 try{
 const files=getFiles();
 if(!window.JSZip)throw Error('ZIP library unavailable. Check internet.');
 const zip=new JSZip();
 for(const f of files)zip.file(f.name,f);
 status('Creating ZIP...');
 const blob=await zip.generateAsync({type:'blob',compression:'DEFLATE'});
 download(blob,'files.zip');
 }catch(e){status(e.message)}
}

function makeTextPDF(){
 try{
 const text=$('words').value;
 if(!text.trim())throw Error('Enter some text first.');
 if(!window.jspdf)throw Error('PDF library unavailable. Check internet.');
 const {jsPDF}=window.jspdf,pdf=new jsPDF();
 const lines=pdf.splitTextToSize(text,180);
 let y=15;
 for(const line of lines){
 if(y>280){pdf.addPage();y=15}
 pdf.text(line,15,y);y+=7;
 }
 pdf.save('document.pdf');status('PDF created!');
 }catch(e){status(e.message)}
}
</script>
</body>
</html>
