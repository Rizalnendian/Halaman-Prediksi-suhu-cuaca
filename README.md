# Halaman Prediksi Suhu Cuaca 🌤️

Proyek ini menyajikan halaman web statis untuk menampilkan prediksi suhu cuaca. Dikembangkan menggunakan HTML dasar dan JavaScript untuk mengambil data cuaca secara real-time dari API Open-Meteo, proyek ini ideal untuk tujuan pembelajaran, demo antarmuka cuaca, atau sebagai dasar untuk pengembangan lebih lanjut.

## 🚀 Fitur Utama

*   **Tampilan Prediksi Cuaca**: Menampilkan data suhu cuaca (dalam Celsius) untuk lokasi tertentu (Jakarta).
*   **Pengambilan Data Real-time**: Menggunakan JavaScript `fetch()` API untuk mengambil data cuaca dari [Open-Meteo API](https://open-meteo.com/).
*   **Struktur Sederhana**: Dibangun dengan HTML murni untuk antarmuka pengguna dan JavaScript untuk fungsionalitas pengambilan data.
*   **Responsif Dasar**: Tampilan tabel yang terpusat dan dapat diskalakan.
*   **Siap Dikembangkan**: Kode dirancang agar mudah diperluas dengan fitur-fitur tambahan.

## 🛠️ Tumpukan Teknologi

*   **HTML**: Untuk struktur konten halaman web.
*   **JavaScript**: Untuk logika pengambilan data dari API dan manipulasi DOM.
*   **Open-Meteo API**: Sumber data prakiraan cuaca.

## ⚙️ Instalasi

Proyek ini adalah aplikasi web statis dan tidak memerlukan instalasi khusus.

1.  **Kloning Repositori**: 
    ```bash
    git clone https://github.com/Rizalnendian/Halaman-Prediksi-suhu-cuaca.git
    cd Halaman-Prediksi-suhu-cuaca
    ```
2.  **Buka File HTML**: Buka file `index.html` di browser web Anda.

## 💡 Cara Penggunaan

Proyek ini dirancang untuk menampilkan prakiraan suhu cuaca di Jakarta.

1.  **Buka `index.html`**: Jalankan file `index.html` menggunakan browser web pilihan Anda.
2.  **Lihat Data Cuaca**: Halaman akan secara otomatis mengambil dan menampilkan data prakiraan suhu per jam untuk Jakarta dari Open-Meteo API.

### Contoh Penggunaan:

Halaman ini secara langsung menampilkan tabel data suhu: 

```html
<!DOCTYPE html> 
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Data Prakiraan Cuaca di Jakarta</title>
</head>
<body>
    <h1 style="text-align: center">Data Prakiraan Cuaca di Jakarta</h1>
    <div style="display: flex; justify-content: center;">
        <table border="1" style="width: 100%; max-width: 800px;">
            <thead>
                <tr>
                    <th>Waktu</th>
                    <th>suhu (Celcius)</th>
                </tr>
            </thead>
            <tbody id="bodyCuaca">
                <!-- Data cuaca akan dimuat di sini -->
            </tbody>
        </table>
    </div>

    <script>
        const API_URL ="https://api.open-meteo.com/v1/forecast?latitude=-6.2&longitude=106.8&hourly=temperature_2m";

        async function loadWeather(){
            const response = await fetch(API_URL);
            const data = await response.json();

            const times = data.hourly.time;
            const temps = data.hourly.temperature_2m;

            const tbody = document.getElementById("bodyCuaca");

            for (let i = 0; i < times.length; i++){
                let row = document.createElement("tr");

                let timecell = document.createElement("td");
                timecell.textContent = times[i];

                let tempcell = document.createElement("td");
                tempcell.textContent = temps[i];

                row.appendChild(timecell);
                row.appendChild(tempcell);

                tbody.appendChild(row);
            }
        }

        loadWeather();
    </script>
</body>
</html>
```

## 📁 Struktur Proyek

```
Halaman-Prediksi-suhu-cuaca/
├── index.html         
├── Tugas 2 PBM/
│   └── Cuaca.html     
└── (opsional) style.css 
└── (opsional) assets/
```

*   `index.html`: File utama yang menampilkan data prakiraan cuaca dan memuat skrip JavaScript.
*   `Tugas 2 PBM/Cuaca.html`: Salinan dari `index.html`, kemungkinan untuk tujuan pengorganisasian tugas.
*   `style.css` (tidak ada dalam analisis tetapi disebutkan dalam README asli): Berkas CSS untuk menata tampilan halaman.
*   `assets/` (tidak ada dalam analisis): Direktori opsional untuk menyimpan aset statis seperti gambar atau ikon.

## 🚀 Pengembangan Lebih Lanjut

*   **Integrasi CSS**: Menambahkan dan menyempurnakan file `style.css` untuk antarmuka yang lebih menarik dan responsif.
*   **Penanganan Kesalahan**: Mengimplementasikan penanganan kesalahan untuk panggilan API.
*   **Lokasi Dinamis**: Mengizinkan pengguna untuk memilih lokasi atau mendeteksi lokasi mereka secara otomatis.
*   **Visualisasi Data**: Menggunakan library charting (seperti Chart.js) untuk memvisualisasikan data suhu.
*   **Ikon Cuaca**: Menambahkan ikon cuaca yang sesuai berdasarkan kondisi yang dilaporkan.

## 📜 Lisensi

Tidak ada lisensi yang ditentukan untuk repositori ini.

## 👤 Penulis

*   **Rizalnendian** - Pemilik Repositori
    *   [Profil GitHub](https://github.com/Rizalnendian)

## 🌟 Berkontribusi

Kontribusi diterima! Jika Anda memiliki saran untuk perbaikan, silakan fork repositori dan buat pull request. Anda juga bisa membuka isu dengan tag 'enhancement' atau 'bug'.

1.  Fork repositori.
2.  Buat branch fitur Anda (`git checkout -b feature/AmazingFeature`).
3.  Commit perubahan Anda (`git commit -m 'Add some AmazingFeature'`).
4.  Push ke branch (`git push origin feature/AmazingFeature`).
5.  Buka Pull Request.

## 🔗 Tautan Penting

*   **Repositori Asli**: [https://github.com/Rizalnendian/Halaman-Prediksi-suhu-cuaca](https://github.com/Rizalnendian/Halaman-Prediksi-suhu-cuaca)

---

_Dibuat dengan ❤️ oleh Rizalnendian. ⭐ Beri bintang, 🍴 Fork, atau laporkan isu jika Anda menemukan masalah!_


---
**<p align="center">Generated by [ReadmeCodeGen](https://www.readmecodegen.com/)</p>**