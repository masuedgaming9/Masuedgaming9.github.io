<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>All-in-One File Converter</title>
<!-- Tailwind CSS for modern design -->
<script src="https://cdn.tailwindcss.com"></script>
<!-- jsPDF Library for Image to PDF conversion -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
</head>
<body class="bg-gray-50 min-h-screen text-gray-800">
​<div class="max-w-4xl mx-auto px-4 py-8">
<header class="text-center mb-10">
<h1 class="text-3xl font-bold text-indigo-600 mb-2">📁 All-in-One File Converter</h1>
<p class="text-gray-600">अपनी सभी फाइलों को आसानी से कंवर्ट और कंप्रेस करें - पूरी तरह सुरक्षित (आपके ब्राउज़र में)</p>
</header>
​<div class="grid grid-cols-1 md:grid-cols-3 gap-4 mb-8">
<button onclick="switchTab('pdf')" id="tab-pdf" class="py-3 px-4 rounded-xl font-semibold bg-indigo-600 text-white shadow transition">1. Image to PDF</button>
<button onclick="switchTab('compress')" id="tab-compress" class="py-3 px-4 rounded-xl font-semibold bg-white text-gray-700 shadow border border-gray-200 transition">2. Image Compressor</button>
<button onclick="switchTab('format')" id="tab-format" class="py-3 px-4 rounded-xl font-semibold bg-white text-gray-700 shadow border border-gray-200 transition">3. Format Converter</button>
</div>
​<!-- Tool 1: Image to PDF Section -->
<div id="section-pdf" class="bg-white p-6 rounded-2xl shadow-md">
<h2 class="text-xl font-bold text-indigo-700 mb-4">फोटो को PDF में बदलें</h2>
<p class="text-sm text-gray-500 mb-4">आप एक या एक से ज़्यादा फोटो चुन सकते हैं जो एक ही PDF में जुड़ जाएंगी।</p>
<input type="file" id="imageInput" accept="image/*" multiple class="block w-full text-sm text-gray-500 file:mr-4 file:py-2 file:px-4 file:rounded-lg file:border-0 file:text-sm file:font-semibold file:bg-indigo-50 file:text-indigo-700 hover:file:bg-indigo-100 mb-4">
<button onclick="convertToPDF()" class="w-full bg-indigo-600 text-white font-bold py-3 px-4 rounded-xl hover:bg-indigo-700 transition">PDF डाउनलोड करें</button>
</div>
​<!-- Tool 2: Image Compressor Section -->
<div id="section-compress" class="bg-white p-6 rounded-2xl shadow-md hidden">
<h2 class="text-xl font-bold text-indigo-700 mb-4">फोटो का साइज़ कम करें (Compress)</h2>
<p class="text-sm text-gray-500 mb-4">यह टूल आपकी फोटो की क्वालिटी बरकरार रखते हुए उसका फाइल साइज़ घटा देगा।</p>
<input type="file" id="compressInput" accept="image/*" class="block w-full text-sm text-gray-500 file:mr-4 file:py-2 file:px-4 file:rounded-lg file:border-0 file:text-sm file:font-semibold file:bg-indigo-50 file:text-indigo-700 hover:file:bg-indigo-100 mb-4">
<button onclick="compressImage()" class="w-full bg-indigo-600 text-white font-bold py-3 px-4 rounded-xl hover:bg-indigo-700 transition">फोटो कंप्रेस करें</button>
<div id="compressResult" class="mt-4 text-center"></div>
</div>
​<!-- Tool 3: Format Converter Section -->
<div id="section-format" class="bg-white p-6 rounded-2xl shadow-md hidden">
<h2 class="text-xl font-bold text-indigo-700 mb-4">फोटो का फॉर्मेट बदलें</h2>
<p class="text-sm text-gray-500 mb-4">JPG को PNG या WEBP में आसानी से बदलें।</p>
<input type="file" id="formatInput" accept="image/*" class="block w-full text-sm text-gray-500 file:mr-4 file:py-2 file:px-4 file:rounded-lg file:border-0 file:text-sm file:font-semibold file:bg-indigo-50 file:text-indigo-700 hover:file:bg-indigo-100 mb-4">
<label class="block text-sm font-medium text-gray-700 mb-2">नया फॉर्मेट चुनें:</label>
<select id="formatSelect" class="w-full p-3 border border-gray-300 rounded-xl mb-4 focus:outline-none focus:ring-2 focus:ring-indigo-500">
<option value="image/jpeg">JPG फॉर्मेट</option>
<option value="image/png">PNG फॉर्मेट</option>
<option value="image/webp">WEBP फॉर्मेट</option>
</select>
<button onclick="convertFormat()" class="w-full bg-indigo-600 text-white font-bold py-3 px-4 rounded-xl hover:bg-indigo-700 transition">फॉर्मेट बदलें और डाउनलोड करें</button>
</div>
</div>
​<script>
// Tab switching logic
function switchTab(tabName) {
['pdf', 'compress', 'format'].forEach(t => {
document.getElementById(section-${t}).classList.add('hidden');
document.getElementById(tab-${t}).className = "py-3 px-4 rounded-xl font-semibold bg-white text-gray-700 shadow border border-gray-200 transition";
});
document.getElementById(section-${tabName}).classList.remove('hidden');
document.getElementById(tab-${tabName}).className = "py-3 px-4 rounded-xl font-semibold bg-indigo-600 text-white shadow transition";
}
​// 1. Image to PDF Generator
async function convertToPDF() {
const { jsPDF } = window.jspdf;
const fileInput = document.getElementById('imageInput');
const files = fileInput.files;
​if (files.length === 0) {
alert("कृपया कम से कम एक फोटो चुनें!");
return;
}
​const pdf = new jsPDF();
​for (let i = 0; i < files.length; i++) {
const file = files[i];
const imageUrl = URL.createObjectURL(file);
​if (i > 0) pdf.addPage();
​pdf.addImage(imageUrl, 'JPEG', 10, 10, 190, 0);
}
​pdf.save("converted-images.pdf");
}
​// 2. Image Compressor
function compressImage() {
const fileInput = document.getElementById('compressInput');
const file = fileInput.files[0];
​if (!file) {
alert("कृपया कोई फोटो चुनें!");
return;
}
​const reader = new FileReader();
reader.readAsDataURL(file);
​reader.onload = function (event) {
const img = new Image();
img.src = event.target.result;
​img.onload = function () {
const canvas = document.createElement('canvas');
const ctx = canvas.getContext('2d');
​canvas.width = img.width;
canvas.height = img.height;
​ctx.drawImage(img, 0, 0, img.width, img.height);
​const compressedUrl = canvas.toDataURL('image/jpeg', 0.6);
​const resultDiv = document.getElementById('compressResult');
resultDiv.innerHTML = <p class="text-green-600 font-semibold mb-2">फोटो सफलतापूर्व कंप्रेस हो गई है!</p> <a href="${compressedUrl}" download="compressed_image.jpg"> <button class="bg-green-600 text-white font-bold py-2 px-6 rounded-lg hover:bg-green-700 transition">कंप्रेस्ड फोटो डाउनलोड करें</button> </a>;
};
};
}
​// 3. Convert Image Format
function convertFormat() {
const fileInput = document.getElementById('formatInput');
const formatSelect = document.getElementById('formatSelect').value;
const file = fileInput.files[0];
​if (!file) {
alert("कृपया एक फोटो चुनें!");
return;
}
​const reader = new FileReader();
reader.readAsDataURL(file);
​reader.onload = function (event) {
const img = new Image();
img.src = event.target.result;
​img.onload = function () {
const canvas = document.createElement('canvas');
canvas.width = img.width;
canvas.height = img.height;
​const ctx = canvas.getContext('2d');
ctx.drawImage(img, 0, 0);
​const newImageData = canvas.toDataURL(formatSelect);
const ext = formatSelect.split('/')[1];
​const a = document.createElement('a');
a.href = newImageData;
a.download = converted_image.${ext};
a.click();
};
};
}
</script>
</body>
</html>
