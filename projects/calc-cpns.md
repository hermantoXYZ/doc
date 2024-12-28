# Calc-CPNS

Berikut ini dokumentasi mengenail Calc CPNS, sebuah app untuk Menghitung peluang, Posisi Skor SKD & SKB CPNS. Tidak menggunakan Backend seperti `django` ataupun yang lain. Saya hanya menggunakan `HTML` dan `JS` .

Saat ini project atau web app yang simple tersebut telah diakses oleh ribuan pengguna, Calon ASN untuk menghitung peluang dari Seleksi Kompetensi Dasar (SKD) dan Seleksi Kompetensi Bidang (SKB).

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption><p>Pictures 1: Ini penampakan dari pengguna project tersebut</p></figcaption></figure>

Saya menggunakan vercel `Vercel's Frontend Cloud provides the developer experience and infrastructure to build, scale, and secure a faster, more personalized web.` tentu sebagai penyedia hosting gratis, menggunakan vercel memudahkan user untuk mengakses tanpa kita harus menyewa sebuah layanan untuk project yang kita kembangkan.

Silahkan jika ingin mengakses dan menghitung skor SKD dan SKB untuk Kementrian yang kalian lamar, di bawah saya akan membagikan capture untuk menggunakannya.

## 1.1 Link Project: Calc CPNS (Kalkutor SKD danSKB)

{% embed url="https://calc-cpns.vercel.app/" %}
Silahkan diklik dan kalian bisa akses dan gunakan.
{% endembed %}

## 1.2 Repository Github

{% embed url="https://github.com/hermantoXYZ/calcCPNS" %}
Silahkan diakses dan gunakan dengan bijak ya..
{% endembed %}

## 1.3 Capture gambar project (Kemdikbud Dosen)

<figure><img src="../.gitbook/assets/calc-cpns.vercel.app_ (1).png" alt=""><figcaption><p>Pictures 2: Ini adalah halaman home, ketika kalian baru mengunjungi pertama kali..</p></figcaption></figure>

<figure><img src="../.gitbook/assets/calc-cpns.vercel.app_dosen_.png" alt=""><figcaption><p>Pictures 3: Tampak gambar untuk menambahkan peserta 1 atau peserta 2 dengan menampilkan jumlah formasinya</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption><p>Pictures 4: Hasil dari perbandingan Nilai Peserta (Hitung Nilai SKD dan SKB Kemdikbud)</p></figcaption></figure>

## 1.4 Capturen Project untuk Formasi Umum

<figure><img src="../.gitbook/assets/calc-cpns.vercel.app_umum_.png" alt=""><figcaption><p>Pictures 5: Untuk untuk menghitung SKB dan SKD formasi umum</p></figcaption></figure>

## 1.5 Code (index.html)

{% code overflow="wrap" %}
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="google-adsense-account" content="ca-pub-3291178252600005">
  <title>CalcCPNS - Perbandingan Nilai Peserta</title>
  <link rel="icon" href="/icon-32x32.png" type="image/x-icon">
  <link href='/style.css' rel='stylesheet'>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>

<body>
  <nav class="navbar">
    <div class="logo">
      <a href="/" style="text-decoration: none; color: inherit;">
          <i class="fas fa-calculator"></i>
          <span>CalcCPNS</span>
      </a>
      <div class="quote">"Menghitung peluang, Posisi Skor SKD & SKB CPNS."</div>
  </div>
  </nav>
  
  <section class="comparison-section">
    <h1 style="text-align: center;">Kalkulator Integrasi SKD SKB Kemdikbud</h1>
    <div class="logo-container">
      <img src="https://casn.kemdikbud.go.id/assets/cpns/img/logo/kemdikbud.svg" alt="Logo" class="logo">
    </div>    
    <p style="text-align: center;"> Kalkulator yang dapat digunakan untuk menghitung nilai akhir berdasarkan bobot 40% untuk SKD dan 60% untuk SKB dan menampilkan posisi peserta berdasarkan nilai akhir.</p>
    <form id="nilaiForm">
      <div id="pesertaContainer">
        <div class="peserta">
          <h3>Peserta 1</h3>
          <label for="nama">Nama Peserta:</label>
          <input type="text" class="nama" placeholder="Nama Peserta" required>
  
          <label for="twk">TWK:</label>
          <input type="number" class="twk" placeholder="Nilai TWK" required>
  
          <label for="tiu">TIU:</label>
          <input type="number" class="tiu" placeholder="Nilai TIU" required>
  
          <label for="tkp">TKP:</label>
          <input type="number" class="tkp" placeholder="Nilai TKP" required>
  
          <label for="cat">CAT BKN:</label>
          <input type="number" class="cat" placeholder="Nilai CAT" required>
  
          <label for="ww">Wawancara:</label>
          <input type="number" class="ww" placeholder="Nilai Wawancara" required>
  
          <label for="mt">Microteaching:</label>
          <input type="number" class="mt" placeholder="Nilai Microteaching" required>
        </div>
      </div>
  
      <div class="form-buttons">
        <button type="button" onclick="tambahPeserta()">
            <i class="fas fa-user-plus"></i> Tambah Peserta
        </button>
        <button type="button" onclick="bandingkanNilai()">
            <i class="fas fa-chart-bar"></i> Bandingkan Nilai
        </button>
    </div>
    

      <input style="margin-left:20px; max-width: 120px;" type="number" id="formasi" placeholder="Jumlah Formasi" required>
    </form>
  
    <div id="output" class="output" style="display: none;"></div>
  </section>
  

  <footer class="footer">
    <div class="footer-container">
      <div class="footer-logo">
        <i class="fas fa-calculator"></i>
        <span>CalcCPNS</span>
      </div>
  

    </div>
    <div class="footer-bottom">
      <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-3291178252600005"
     crossorigin="anonymous"></script>
         <!-- Histats.com  (div with counter) --><div id="histats_counter"></div>
<!-- Histats.com  START  (aync)-->
<script type="text/javascript">var _Hasync= _Hasync|| [];
  _Hasync.push(['Histats.startgif', '1,4916513,4,10048,"div#histatsC {position: absolute;top:0px;left:0px;}body>div#histatsC {position: fixed;}"']);
  _Hasync.push(['Histats.fasi', '1']);
  _Hasync.push(['Histats.track_hits', '']);
  (function() {
  var hs = document.createElement('script'); hs.type = 'text/javascript'; hs.async = true;
  hs.src = ('//s10.histats.com/js15_gif_as.js');
  (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(hs);
  })();</script>
  <noscript><a href="/" alt="" target="_blank" ><div id="histatsC"><img border="0" src="//s4is.histats.com/stats/i/4916513.gif?4916513&103"></div></a>
  </noscript>
  <!-- Histats.com  END  -->

      <p>© 2024 CalcCPNS. Developed by <a href="https://www.instagram.com/hermanto.xyz/" style="text-decoration: none; color: inherit;" >HermantoXYZ</a></p>
  </div>
  </footer>
  <div class="whatsapp-float"><a href="https://api.whatsapp.com/send/?phone=6289512402404&amp;text=Halo+Kak" target="_blank"><img src="https://inviteku.com/media/logo/favicon/WhatsApp_icon.png" alt="Chat Admin"><span class="notification-dot"></span><!-- Dot Merah --></a></div>
  
  <script defer type="text/javascript" src="/main.js"></script>
  <script defer type="text/javascript" src="/toggle.js"></script>
  

</body>
</html>
```
{% endcode %}

## Code 2 (Javascripts)

{% code fullWidth="true" %}
```javascript

let pesertaCount = 1;

function tambahPeserta() {
  pesertaCount++;
  const container = document.getElementById('pesertaContainer');
  const div = document.createElement('div');
  div.classList.add('peserta');
  div.innerHTML = `
    <h3>Peserta ${pesertaCount}</h3>
    <label for="nama">Nama Peserta:</label>
    <input type="text" class="nama" placeholder="Nama Peserta" required>

    <label for="twk">TWK:</label>
    <input type="number" class="twk" placeholder="Nilai TWK" required>

    <label for="tiu">TIU:</label>
    <input type="number" class="tiu" placeholder="Nilai TIU" required>

    <label for="tkp">TKP:</label>
    <input type="number" class="tkp" placeholder="Nilai TKP" required>

    <label for="cat">CAT BKN:</label>
    <input type="number" class="cat" placeholder="Nilai CAT" required>

    <label for="ww">Wawancara:</label>
    <input type="number" class="ww" placeholder="Nilai Wawancara" required>

    <label for="mt">Microteaching:</label>
    <input type="number" class="mt" placeholder="Nilai Microteaching" required>
  `;
  container.appendChild(div);
}

function bandingkanNilai() {
const pesertaElements = document.querySelectorAll('.peserta');
const formasi = parseInt(document.getElementById('formasi').value) || 0; // Ambil jumlah formasi
const pesertaData = [];

pesertaElements.forEach((peserta) => {
const nama = peserta.querySelector('.nama').value;
const twk = parseFloat(peserta.querySelector('.twk').value) || 0;
const tiu = parseFloat(peserta.querySelector('.tiu').value) || 0;
const tkp = parseFloat(peserta.querySelector('.tkp').value) || 0;
const cat = parseFloat(peserta.querySelector('.cat').value) || 0;
const ww = parseFloat(peserta.querySelector('.ww').value) || 0;
const mt = parseFloat(peserta.querySelector('.mt').value) || 0;

const maxSKD = 550;
const maxCAT = 400;
const maxWW = 25;
const maxMT = 25;

const totalSKD = twk + tiu + tkp;
const skala100SKD = (totalSKD / maxSKD) * 100;
const skd40 = skala100SKD * 0.4;

const wwSkor = (ww / maxWW) * 10;
const mtSkor = (mt / maxMT) * 10;
const catSkor = (cat / maxCAT) * 80;
const totalSKB = wwSkor + mtSkor + catSkor;
const skb60 = totalSKB * 0.6;

const nilaiAkhir = skd40 + skb60;

pesertaData.push({
  nama,
  twk, tiu, tkp, cat, ww, mt,
  totalSKD,
  totalSKB,
  nilaiAkhir,
  status: 'Lulus', // Default "Lulus", akan diupdate berdasarkan formasi nanti
  gagal: mt < 12.5, // Tandai jika gagal karena nilai MT
});
});

// Urutkan peserta berdasarkan nilai akhir secara descending
pesertaData.sort((a, b) => b.nilaiAkhir - a.nilaiAkhir);

// Tandai peserta yang "Tidak Lulus" karena nilai MT
pesertaData.forEach((peserta) => {
if (peserta.gagal) {
  peserta.status = 'Tidak Lulus (MT < 12.5)';
}
});

// Perhatikan jumlah formasi
let lulusCount = 0;
pesertaData.forEach((peserta) => {
if (!peserta.gagal && lulusCount < formasi) {
  peserta.status = 'Lulus';
  lulusCount++;
} else if (!peserta.gagal) {
  peserta.status = 'Tidak Lulus (Di luar formasi)';
}
});

// Buat baris tabel untuk semua peserta
const pesertaLulus = pesertaData.map((peserta, index) => {
return `<tr>
  <td>${index + 1}</td>
  <td>${peserta.nama}</td>
  <td>${peserta.twk}</td>
  <td>${peserta.tiu}</td>
  <td>${peserta.tkp}</td>
  <td>${peserta.cat}</td>
  <td>${peserta.ww}</td>
  <td>${peserta.mt}</td>
  <td>${peserta.totalSKD.toFixed(2)}</td>
  <td>${peserta.totalSKB.toFixed(2)}</td>
  <td>${peserta.nilaiAkhir.toFixed(2)}</td>
  <td>${peserta.status}</td>
</tr>`;
}).join('');

// Tampilkan hasil dalam tabel
const outputDiv = document.getElementById('output');
outputDiv.style.display = 'block';
outputDiv.innerHTML = `
<h3>Hasil Perbandingan Nilai Peserta</h3>
<div class="table-container">
<table style="width: 100%; border-collapse: collapse;">
  <thead>
    <tr>
      <th>No</th>
      <th>Nama</th>
      <th>TWK</th>
      <th>TIU</th>
      <th>TKP</th>
      <th>CAT BKN</th>
      <th>Wawancara</th>
      <th>Microteaching</th>
      <th>Total SKD</th>
      <th>Total SKB</th>
      <th>Nilai Akhir</th>
      <th>Status</th>
    </tr>
  </thead>
  <tbody>
    ${pesertaLulus}
  </tbody>
</table>
</div>
`;
}
```
{% endcode %}







