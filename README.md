```html
<!DOCTYPE html>
<html lang="en" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FLEXVERT ⚡ | Ultimate Gen-Z File Converter Studio</title>
    
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brand: {
                            purple: '#a855f7',
                            cyan: '#06b6d4',
                            pink: '#ec4899',
                            dark: '#0b0f19',
                            card: 'rgba(17, 24, 39, 0.7)'
                        }
                    },
                    fontFamily: {
                        sans: ['Plus Jakarta Sans', 'sans-serif']
                    }
                }
            }
        }
    </script>

    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;700;800&display=swap" rel="stylesheet">
    
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <!-- Essential Libraries for Client-Side Conversions -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/pdf-lib/1.17.1/pdf-lib.min.js"></script>

    <style>
        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: #080a11;
            color: #f3f4f6;
            background-image: 
                radial-gradient(at 0% 0%, rgba(168, 85, 247, 0.15) 0px, transparent 50%),
                radial-gradient(at 100% 100%, rgba(6, 182, 212, 0.15) 0px, transparent 50%);
            background-attachment: fixed;
        }

        .glass-panel {
            background: rgba(15, 23, 42, 0.65);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }

        .glass-panel:hover {
            border-color: rgba(168, 85, 247, 0.3);
        }

        .glow-btn {
            background: linear-gradient(135deg, #a855f7 0%, #06b6d4 100%);
            box-shadow: 0 0 20px rgba(168, 85, 247, 0.35);
            transition: all 0.3s ease;
        }

        .glow-btn:hover {
            box-shadow: 0 0 30px rgba(6, 182, 212, 0.6);
            transform: translateY(-2px);
        }

        .tab-btn.active {
            background: linear-gradient(135deg, rgba(168, 85, 247, 0.2) 0%, rgba(6, 182, 212, 0.2) 100%);
            border-color: #a855f7;
            color: #ffffff;
            box-shadow: 0 0 15px rgba(168, 85, 247, 0.25);
        }

        .drag-zone {
            background-image: url("data:image/svg+xml,%3csvg width='100%25' height='100%25' xmlns='http://www.w3.org/2000/svg'%3e%3crect width='100%25' height='100%25' fill='none' rx='16' ry='16' stroke='%23374151FF' stroke-width='2' stroke-dasharray='8%2c 8' stroke-dashoffset='0' stroke-linecap='square'/%3e%3c/svg%3e");
        }

        .drag-zone.dragover {
            background-image: url("data:image/svg+xml,%3csvg width='100%25' height='100%25' xmlns='http://www.w3.org/2000/svg'%3e%3crect width='100%25' height='100%25' fill='none' rx='16' ry='16' stroke='%23A855F7FF' stroke-width='2' stroke-dasharray='8%2c 8' stroke-dashoffset='0' stroke-linecap='square'/%3e%3c/svg%3e");
            background-color: rgba(168, 85, 247, 0.05);
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between">

    <!-- Top Navigation -->
    <header class="sticky top-0 z-50 glass-panel border-b border-gray-800/80">
        <div class="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center">
            <div class="flex items-center gap-3">
                <div class="bg-gradient-to-tr from-purple-600 to-cyan-500 p-2.5 rounded-2xl shadow-lg shadow-purple-500/20">
                    <i data-lucide="zap" class="w-6 h-6 text-white"></i>
                </div>
                <div>
                    <span class="text-2xl font-black tracking-wider bg-clip-text text-transparent bg-gradient-to-r from-purple-400 via-pink-400 to-cyan-400">
                        FLEXVERT
                    </span>
                    <span class="block text-[10px] font-semibold text-cyan-400 tracking-widest uppercase">GitHub Pages Edition</span>
                </div>
            </div>

            <div class="flex items-center gap-3">
                <span class="hidden sm:inline-flex items-center gap-2 bg-purple-950/60 border border-purple-500/30 px-3 py-1.5 rounded-full text-xs font-semibold text-purple-300">
                    <span class="w-2 h-2 rounded-full bg-cyan-400 animate-ping"></span>
                    100% Client-Side Private
                </span>
            </div>
        </div>
    </header>

    <!-- Main Container -->
    <main class="max-w-6xl mx-auto px-4 py-8 w-full flex-grow">
        
        <!-- Hero Title -->
        <div class="text-center mb-10">
            <h1 class="text-4xl sm:text-6xl font-extrabold tracking-tight mb-3">
                CONVERT EVERYTHING. <br class="hidden sm:inline"/>
                <span class="bg-clip-text text-transparent bg-gradient-to-r from-purple-400 via-pink-500 to-cyan-400">
                    ZERO SERVER UPLOADS 🔥
                </span>
            </h1>
            <p class="text-gray-400 text-sm sm:text-base max-w-xl mx-auto">
                Lightning fast, private client-side converters built for GitHub Pages. Drop your files and flex your productivity.
            </p>
        </div>

        <!-- Navigation Tabs -->
        <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-6 gap-3 mb-8">
            <button onclick="switchTab('img2pdf')" id="tab-img2pdf" class="tab-btn active glass-panel p-3.5 rounded-2xl border border-gray-800 flex flex-col items-center gap-2 text-gray-300 font-semibold text-xs sm:text-sm transition">
                <i data-lucide="file-check" class="w-5 h-5 text-purple-400"></i>
                <span>Photo ➔ PDF</span>
            </button>
            <button onclick="switchTab('compress')" id="tab-compress" class="tab-btn glass-panel p-3.5 rounded-2xl border border-gray-800 flex flex-col items-center gap-2 text-gray-400 font-semibold text-xs sm:text-sm transition hover:text-white">
                <i data-lucide="shrink" class="w-5 h-5 text-cyan-400"></i>
                <span>Compressor</span>
            </button>
            <button onclick="switchTab('imgformat')" id="tab-imgformat" class="tab-btn glass-panel p-3.5 rounded-2xl border border-gray-800 flex flex-col items-center gap-2 text-gray-400 font-semibold text-xs sm:text-sm transition hover:text-white">
                <i data-lucide="image" class="w-5 h-5 text-pink-400"></i>
                <span>Img Format</span>
            </button>
            <button onclick="switchTab('pdfops')" id="tab-pdfops" class="tab-btn glass-panel p-3.5 rounded-2xl border border-gray-800 flex flex-col items-center gap-2 text-gray-400 font-semibold text-xs sm:text-sm transition hover:text-white">
                <i data-lucide="layers" class="w-5 h-5 text-yellow-400"></i>
                <span>PDF Merge/Split</span>
            </button>
            <button onclick="switchTab('audio')" id="tab-audio" class="tab-btn glass-panel p-3.5 rounded-2xl border border-gray-800 flex flex-col items-center gap-2 text-gray-400 font-semibold text-xs sm:text-sm transition hover:text-white">
                <i data-lucide="music" class="w-5 h-5 text-emerald-400"></i>
                <span>Audio Engine</span>
            </button>
            <button onclick="switchTab('textconv')" id="tab-textconv" class="tab-btn glass-panel p-3.5 rounded-2xl border border-gray-800 flex flex-col items-center gap-2 text-gray-400 font-semibold text-xs sm:text-sm transition hover:text-white">
                <i data-lucide="file-text" class="w-5 h-5 text-indigo-400"></i>
                <span>Text / Doc</span>
            </button>
        </div>

        <!-- Tool Panels Window -->
        <div class="glass-panel p-6 sm:p-8 rounded-3xl min-h-[400px] shadow-2xl relative overflow-hidden">

            <!-- 1. Photo to PDF -->
            <div id="panel-img2pdf" class="tool-panel">
                <div class="mb-6">
                    <h2 class="text-2xl font-bold text-white flex items-center gap-2">
                        <i data-lucide="file-check" class="text-purple-400"></i> Photo to PDF Studio
                    </h2>
                    <p class="text-xs sm:text-sm text-gray-400 mt-1">Convert single or multiple images (JPG, PNG, WEBP, BMP) into a high-quality PDF.</p>
                </div>

                <div class="drag-zone p-8 rounded-2xl text-center mb-6 transition cursor-pointer" id="drop-img2pdf" onclick="document.getElementById('file-img2pdf').click()">
                    <input type="file" id="file-img2pdf" accept="image/*" multiple class="hidden" onchange="updateFileList(this, 'list-img2pdf')">
                    <i data-lucide="upload-cloud" class="w-12 h-12 text-purple-400 mx-auto mb-3"></i>
                    <p class="font-bold text-gray-200">Click or Drag & Drop Photos Here</p>
                    <p class="text-xs text-gray-500 mt-1">Supports batch photo uploads</p>
                </div>

                <div id="list-img2pdf" class="text-xs font-mono text-purple-300 mb-6 space-y-1"></div>

                <button onclick="convertImagesToPdf()" class="glow-btn w-full py-4 rounded-xl font-bold text-white tracking-wide text-base flex items-center justify-center gap-2">
                    <span>GENERATE PDF DOCUMENT</span>
                    <i data-lucide="arrow-right" class="w-5 h-5"></i>
                </button>
            </div>

            <!-- 2. Image Compressor -->
            <div id="panel-compress" class="tool-panel hidden">
                <div class="mb-6">
                    <h2 class="text-2xl font-bold text-white flex items-center gap-2">
                        <i data-lucide="shrink" class="text-cyan-400"></i> Smart Image Compressor
                    </h2>
                    <p class="text-xs sm:text-sm text-gray-400 mt-1">Squeeze image filesize down instantly without downloading server software.</p>
                </div>

                <div class="drag-zone p-8 rounded-2xl text-center mb-6 transition cursor-pointer" id="drop-compress" onclick="document.getElementById('file-compress').click()">
                    <input type="file" id="file-compress" accept="image/*" class="hidden" onchange="updateFileList(this, 'list-compress')">
                    <i data-lucide="image" class="w-12 h-12 text-cyan-400 mx-auto mb-3"></i>
                    <p class="font-bold text-gray-200">Select Image to Compress</p>
                    <p class="text-xs text-gray-500 mt-1">Supports JPG, PNG, WEBP</p>
                </div>

                <div id="list-compress" class="text-xs font-mono text-cyan-300 mb-6"></div>

                <div class="mb-6 bg-gray-900/60 p-4 rounded-2xl border border-gray-800">
                    <div class="flex justify-between text-xs font-bold mb-2">
                        <span class="text-gray-400">Compression Quality:</span>
                        <span id="quality-val" class="text-cyan-400">70%</span>
                    </div>
                    <input type="range" id="quality-slider" min="0.1" max="0.9" step="0.05" value="0.7" oninput="document.getElementById('quality-val').innerText = Math.round(this.value*100) + '%'" class="w-full accent-cyan-400 cursor-pointer">
                </div>

                <button onclick="compressImage()" class="glow-btn w-full py-4 rounded-xl font-bold text-white tracking-wide text-base flex items-center justify-center gap-2">
                    <span>COMPRESS IMAGE SIZE</span>
                    <i data-lucide="zap" class="w-5 h-5"></i>
                </button>
                <div id="res-compress" class="mt-6 text-center"></div>
            </div>

            <!-- 3. Image Format Swapper -->
            <div id="panel-imgformat" class="tool-panel hidden">
                <div class="mb-6">
                    <h2 class="text-2xl font-bold text-white flex items-center gap-2">
                        <i data-lucide="image" class="text-pink-400"></i> Image Format Converter
                    </h2>
                    <p class="text-xs sm:text-sm text-gray-400 mt-1">Swap between JPG, PNG, WEBP, GIF, and BMP image formats.</p>
                </div>

                <div class="drag-zone p-8 rounded-2xl text-center mb-6 transition cursor-pointer" id="drop-format" onclick="document.getElementById('file-format').click()">
                    <input type="file" id="file-format" accept="image/*" class="hidden" onchange="updateFileList(this, 'list-format')">
                    <i data-lucide="refresh-cw" class="w-12 h-12 text-pink-400 mx-auto mb-3"></i>
                    <p class="font-bold text-gray-200">Select Image File</p>
                </div>

                <div id="list-format" class="text-xs font-mono text-pink-300 mb-6"></div>

                <div class="mb-6">
                    <label class="block text-xs font-bold text-gray-400 mb-2 uppercase tracking-wider">Select Output Format:</label>
                    <select id="target-format" class="w-full bg-gray-900 border border-gray-800 rounded-xl p-3 text-white text-sm focus:outline-none focus:border-pink-500">
                        <option value="image/jpeg">JPG / JPEG (.jpg)</option>
                        <option value="image/png">PNG (.png)</option>
                        <option value="image/webp">WEBP (.webp)</option>
                        <option value="image/bmp">BMP (.bmp)</option>
                    </select>
                </div>

                <button onclick="convertImageFormat()" class="glow-btn w-full py-4 rounded-xl font-bold text-white tracking-wide text-base flex items-center justify-center gap-2">
                    <span>CONVERT FORMAT NOW</span>
                    <i data-lucide="sparkles" class="w-5 h-5"></i>
                </button>
            </div>

            <!-- 4. PDF Merger & Splitter -->
            <div id="panel-pdfops" class="tool-panel hidden">
                <div class="mb-6">
                    <h2 class="text-2xl font-bold text-white flex items-center gap-2">
                        <i data-lucide="layers" class="text-yellow-400"></i> PDF Merge & Split Studio
                    </h2>
                    <p class="text-xs sm:text-sm text-gray-400 mt-1">Combine multiple PDFs into one document or split single PDFs.</p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <!-- Merge -->
                    <div class="bg-gray-900/50 p-5 rounded-2xl border border-gray-800">
                        <h3 class="font-bold text-yellow-400 mb-3 text-sm flex items-center gap-2"><i data-lucide="combine" class="w-4 h-4"></i> Merge PDFs</h3>
                        <input type="file" id="file-pdfmerge" accept=".pdf" multiple class="block w-full text-xs text-gray-400 file:mr-3 file:py-2 file:px-3 file:rounded-xl file:border-0 file:text-xs file:font-semibold file:bg-yellow-500/10 file:text-yellow-400 hover:file:bg-yellow-500/20 mb-4">
                        <button onclick="mergePDFs()" class="w-full bg-yellow-500/20 hover:bg-yellow-500/30 text-yellow-300 font-bold py-2.5 rounded-xl border border-yellow-500/30 transition text-xs">
                            Merge PDF Files
                        </button>
                    </div>

                    <!-- Split -->
                    <div class="bg-gray-900/50 p-5 rounded-2xl border border-gray-800">
                        <h3 class="font-bold text-yellow-400 mb-3 text-sm flex items-center gap-2"><i data-lucide="scissors" class="w-4 h-4"></i> Extract First Page</h3>
                        <input type="file" id="file-pdfsplit" accept=".pdf" class="block w-full text-xs text-gray-400 file:mr-3 file:py-2 file:px-3 file:rounded-xl file:border-0 file:text-xs file:font-semibold file:bg-yellow-500/10 file:text-yellow-400 hover:file:bg-yellow-500/20 mb-4">
                        <button onclick="splitPDF()" class="w-full bg-yellow-500/20 hover:bg-yellow-500/30 text-yellow-300 font-bold py-2.5 rounded-xl border border-yellow-500/30 transition text-xs">
                            Extract Front Page
                        </button>
                    </div>
                </div>
            </div>

            <!-- 5. Audio Extractor & Converter -->
            <div id="panel-audio" class="tool-panel hidden">
                <div class="mb-6">
                    <h2 class="text-2xl font-bold text-white flex items-center gap-2">
                        <i data-lucide="music" class="text-emerald-400"></i> Audio Extractor & Converter
                    </h2>
                    <p class="text-xs sm:text-sm text-gray-400 mt-1">Extract or convert audio from media files directly into high-fidelity WAV format in browser.</p>
                </div>

                <div class="drag-zone p-8 rounded-2xl text-center mb-6 transition cursor-pointer" id="drop-audio" onclick="document.getElementById('file-audio').click()">
                    <input type="file" id="file-audio" accept="audio/*,video/*" class="hidden" onchange="updateFileList(this, 'list-audio')">
                    <i data-lucide="headphones" class="w-12 h-12 text-emerald-400 mx-auto mb-3"></i>
                    <p class="font-bold text-gray-200">Upload Video or Audio File</p>
                    <p class="text-xs text-gray-500 mt-1">Extracts clean sound tracks instantly</p>
                </div>

                <div id="list-audio" class="text-xs font-mono text-emerald-300 mb-6"></div>

                <button onclick="processAudioConversion()" class="glow-btn w-full py-4 rounded-xl font-bold text-white tracking-wide text-base flex items-center justify-center gap-2">
                    <span>CONVERT & EXTRACT AUDIO (.WAV)</span>
                    <i data-lucide="disc" class="w-5 h-5"></i>
                </button>
                <div id="res-audio" class="mt-6 text-center"></div>
            </div>

            <!-- 6. Text / Document Converter -->
            <div id="panel-textconv" class="tool-panel hidden">
                <div class="mb-6">
                    <h2 class="text-2xl font-bold text-white flex items-center gap-2">
                        <i data-lucide="file-text" class="text-indigo-400"></i> Text & Document Converter
                    </h2>
                    <p class="text-xs sm:text-sm text-gray-400 mt-1">Type text or drop TXT files to convert directly into PDF or HTML documents.</p>
                </div>

                <textarea id="text-content" rows="6" placeholder="Paste or type text content here..." class="w-full bg-gray-900 border border-gray-800 rounded-2xl p-4 text-white text-xs sm:text-sm focus:outline-none focus:border-indigo-500 mb-4 font-mono"></textarea>

                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <button onclick="convertTextToPdf()" class="bg-indigo-600/30 hover:bg-indigo-600/40 border border-indigo-500/40 text-indigo-200 font-bold py-3 rounded-xl transition text-xs sm:text-sm flex items-center justify-center gap-2">
                        <i data-lucide="file-down" class="w-4 h-4"></i> Export as PDF
                    </button>
                    <button onclick="convertTextToHtml()" class="bg-indigo-600/30 hover:bg-indigo-600/40 border border-indigo-500/40 text-indigo-200 font-bold py-3 rounded-xl transition text-xs sm:text-sm flex items-center justify-center gap-2">
                        <i data-lucide="code" class="w-4 h-4"></i> Export as HTML
                    </button>
                </div>
            </div>

        </div>

    </main>

    <!-- Footer Required by User -->
    <footer class="border-t border-gray-800/80 bg-gray-950/80 py-6 text-center text-xs sm:text-sm text-gray-400">
        <p class="font-bold tracking-wide">
            Made by AI <span class="text-pink-500">|</span> The Owner Masood Gaming 9 🔥
        </p>
        <p class="text-[11px] text-gray-600 mt-1">Ready for GitHub Pages • 100% Client-Side Engine</p>
    </footer>

    <!-- Logic Engine Script -->
    <script>
        // Initialize Lucide Icons
        lucide.createIcons();

        // Tab Switching Logic
        function switchTab(tabId) {
            document.querySelectorAll('.tool-panel').forEach(p => p.classList.add('hidden'));
            document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));

            document.getElementById(`panel-${tabId}`).classList.remove('hidden');
            document.getElementById(`tab-${tabId}`).classList.add('active');
        }

        // Display Selected Files Info
        function updateFileList(input, listId) {
            const list = document.getElementById(listId);
            if (input.files && input.files.length > 0) {
                const names = Array.from(input.files).map(f => `📁 ${f.name} (${(f.size/1024).toFixed(1)} KB)`).join('<br>');
                list.innerHTML = names;
            } else {
                list.innerHTML = '';
            }
        }

        // Drag & Drop Styling
        ['drop-img2pdf', 'drop-compress', 'drop-format', 'drop-audio'].forEach(id => {
            const el = document.getElementById(id);
            if(!el) return;
            ['dragenter', 'dragover'].forEach(eventName => {
                el.addEventListener(eventName, (e) => { e.preventDefault(); el.classList.add('dragover'); });
            });
            ['dragleave', 'drop'].forEach(eventName => {
                el.addEventListener(eventName, (e) => { e.preventDefault(); el.classList.remove('dragover'); });
            });
        });

        // Helper: Convert File to Base64
        function fileToBase64(file) {
            return new Promise((resolve, reject) => {
                const reader = new FileReader();
                reader.readAsDataURL(file);
                reader.onload = () => resolve(reader.result);
                reader.onerror = err => reject(err);
            });
        }

        // 1. Photo to PDF Conversion
        async function convertImagesToPdf() {
            const input = document.getElementById('file-img2pdf');
            if(!input.files || input.files.length === 0) return alert('Please select at least one photo!');

            const { jsPDF } = window.jspdf;
            const pdf = new jsPDF();

            for (let i = 0; i < input.files.length; i++) {
                const base64 = await fileToBase64(input.files[i]);
                if (i > 0) pdf.addPage();
                pdf.addImage(base64, 'JPEG', 10, 10, 190, 0);
            }

            pdf.save('photos_converted.pdf');
        }

        // 2. Compress Image
        async function compressImage() {
            const input = document.getElementById('file-compress');
            const quality = parseFloat(document.getElementById('quality-slider').value);
            if(!input.files || !input.files[0]) return alert('Select an image file first!');

            const file = input.files[0];
            const base64 = await fileToBase64(file);

            const img = new Image();
            img.src = base64;
            img.onload = () => {
                const canvas = document.createElement('canvas');
                canvas.width = img.width;
                canvas.height = img.height;
                const ctx = canvas.getContext('2d');
                ctx.drawImage(img, 0, 0);

                const compressedData = canvas.toDataURL('image/jpeg', quality);
                const res = document.getElementById('res-compress');
                res.innerHTML = `
                    <a href="${compressedData}" download="compressed_${file.name}" class="glow-btn inline-block py-3 px-8 rounded-xl font-bold text-white text-xs sm:text-sm">
                        DOWNLOAD COMPRESSED FILE 🔥
                    </a>
                `;
            };
        }

        // 3. Format Swapper
        async function convertImageFormat() {
            const input = document.getElementById('file-format');
            const format = document.getElementById('target-format').value;
            if(!input.files || !input.files[0]) return alert('Select an image to convert format!');

            const file = input.files[0];
            const base64 = await fileToBase64(file);

            const img = new Image();
            img.src = base64;
            img.onload = () => {
                const canvas = document.createElement('canvas');
                canvas.width = img.width;
                canvas.height = img.height;
                const ctx = canvas.getContext('2d');
                ctx.drawImage(img, 0, 0);

                const convertedData = canvas.toDataURL(format);
                const ext = format.split('/')[1];

                const a = document.createElement('a');
                a.href = convertedData;
                a.download = `flexvert_image.${ext}`;
                a.click();
            };
        }

        // 4. Merge PDFs
        async function mergePDFs() {
            const input = document.getElementById('file-pdfmerge');
            if(!input.files || input.files.length < 2) return alert('Select at least 2 PDF files to merge!');

            const mergedPdf = await PDFLib.PDFDocument.create();

            for (let file of input.files) {
                const bytes = await file.arrayBuffer();
                const pdf = await PDFLib.PDFDocument.load(bytes);
                const pages = await mergedPdf.copyPages(pdf, pdf.getPageIndices());
                pages.forEach(page => mergedPdf.addPage(page));
            }

            const mergedBytes = await mergedPdf.save();
            const blob = new Blob([mergedBytes], { type: 'application/pdf' });
            const url = URL.createObjectURL(blob);

            const a = document.createElement('a');
            a.href = url;
            a.download = 'merged_documents.pdf';
            a.click();
        }

        // Split PDF (Extract Front Page)
        async function splitPDF() {
            const input = document.getElementById('file-pdfsplit');
            if(!input.files || !input.files[0]) return alert('Select a PDF file!');

            const bytes = await input.files[0].arrayBuffer();
            const pdf = await PDFLib.PDFDocument.load(bytes);
            
            const newPdf = await PDFLib.PDFDocument.create();
            const [firstPage] = await newPdf.copyPages(pdf, [0]);
            newPdf.addPage(firstPage);

            const splitBytes = await newPdf.save();
            const blob = new Blob([splitBytes], { type: 'application/pdf' });
            const url = URL.createObjectURL(blob);

            const a = document.createElement('a');
            a.href = url;
            a.download = 'extracted_page_1.pdf';
            a.click();
        }

        // 5. Audio Extractor & Converter
        async function processAudioConversion() {
            const input = document.getElementById('file-audio');
            if(!input.files || !input.files[0]) return alert('Select an audio/video file!');

            const file = input.files[0];
            const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            const buffer = await file.arrayBuffer();

            try {
                const audioBuffer = await audioCtx.decodeAudioData(buffer);
                const wavBlob = audioBufferToWav(audioBuffer);
                const url = URL.createObjectURL(wavBlob);

                const res = document.getElementById('res-audio');
                res.innerHTML = `
                    <a href="${url}" download="extracted_sound.wav" class="glow-btn inline-block py-3 px-8 rounded-xl font-bold text-white text-xs sm:text-sm">
                        DOWNLOAD WAV AUDIO 🎵
                    </a>
                `;
            } catch(e) {
                alert('Error processing audio format.');
            }
        }

        // WAV Encoding helper
        function audioBufferToWav(buffer) {
            let numOfChan = buffer.numberOfChannels,
                length = buffer.length * numOfChan * 2 + 44,
                out = new DataView(new ArrayBuffer(length)),
                channels = [], i, sample, offset = 0, pos = 0;

            function setUint16(data) { out.setUint16(pos, data, true); pos += 2; }
            function setUint32(data) { out.setUint32(pos, data, true); pos += 4; }

            setUint32(0x46464952); setUint32(length - 8); setUint32(0x45564157);
            setUint32(0x20746d66); setUint32(16); setUint16(1); setUint16(numOfChan);
            setUint32(buffer.sampleRate); setUint32(buffer.sampleRate * 2 * numOfChan);
            setUint16(numOfChan * 2); setUint16(16); setUint32(0x61746164); setUint32(length - pos - 4);

            for (i = 0; i < buffer.numberOfChannels; i++) channels.push(buffer.getChannelData(i));

            while (pos < length) {
                for (i = 0; i < numOfChan; i++) {
                    sample = Math.max(-1, Math.min(1, channels[i][offset]));
                    sample = (0.5 + sample < 0 ? sample * 32768 : sample * 32767) | 0;
                    out.setInt16(pos, sample, true); pos += 2;
                }
                offset++;
            }
            return new Blob([out], { type: "audio/wav" });
        }

        // 6. Text to PDF
        function convertTextToPdf() {
            const text = document.getElementById('text-content').value;
            if(!text.trim()) return alert('Type or paste text content first!');

            const { jsPDF } = window.jspdf;
            const pdf = new jsPDF();
            const lines = pdf.splitTextToSize(text, 180);
            pdf.text(lines, 10, 10);
            pdf.save('document.pdf');
        }

        // Text to HTML
        function convertTextToHtml() {
            const text = document.getElementById('text-content').value;
            if(!text.trim()) return alert('Type or paste text content first!');

            const htmlContent = `<!DOCTYPE html>\n<html>\n<head>\n<title>Exported Doc</title>\n</head>\n<body style="font-family:sans-serif;padding:20px;">\n<pre>${text}</pre>\n</body>\n</html>`;
            const blob = new Blob([htmlContent], { type: 'text/html' });
            const url = URL.createObjectURL(blob);

            const a = document.createElement('a');
            a.href = url;
            a.download = 'document.html';
            a.click();
        }
    </script>
</body>
</html>
```
