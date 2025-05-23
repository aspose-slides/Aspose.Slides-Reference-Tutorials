---
"date": "2025-04-23"
"description": "Pelajari cara membuat dan menyesuaikan grafik SmartArt di PowerPoint menggunakan Aspose.Slides untuk Python, menyempurnakan presentasi Anda dengan bagan organisasi yang dinamis."
"title": "Cara Membuat dan Menyesuaikan SmartArt di PowerPoint Menggunakan Aspose.Slides untuk Python"
"url": "/id/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat dan Menyesuaikan SmartArt di PowerPoint Menggunakan Aspose.Slides untuk Python

## Perkenalan

Presentasi merupakan alat penting untuk merepresentasikan struktur organisasi atau sesi curah pendapat secara visual. Dengan Aspose.Slides untuk Python, Anda dapat membuat dan menyesuaikan grafik SmartArt dengan mudah. Tutorial ini akan memandu Anda menambahkan grafik SmartArt bagan organisasi ke slide PowerPoint Anda.

**Apa yang Akan Anda Pelajari:**
- Menambahkan grafik SmartArt di PowerPoint menggunakan Aspose.Slides untuk Python.
- Menyesuaikan tata letak simpul SmartArt Anda.
- Menyimpan dan mengekspor presentasi secara efisien.

Mari mulai menyiapkan lingkungan Anda!

## Prasyarat

Sebelum mulai membuat grafik SmartArt, pastikan Anda memiliki prasyarat berikut:

### Perpustakaan yang Diperlukan
- **Aspose.Slides untuk Python**: Instal pustaka ini menggunakan pip jika belum dilakukan.

### Persyaratan Pengaturan Lingkungan
- Instalasi Python yang berfungsi (disarankan 3.x).
- Pemahaman dasar tentang pemrograman Python.
- Kemampuan menggunakan Microsoft PowerPoint akan membantu namun tidaklah wajib.

## Menyiapkan Aspose.Slides untuk Python

Untuk memulai, atur pustaka Aspose.Slides di lingkungan Python Anda:

**Pemasangan Pipa:**
```bash
pip install aspose.slides
```

### Langkah-langkah Memperoleh Lisensi
Aspose menawarkan berbagai pilihan lisensi:
- **Uji Coba Gratis**: Unduh lisensi sementara untuk mengevaluasi fitur lengkap.
- **Lisensi Sementara**: Dapatkan lisensi sementara gratis untuk penggunaan jangka pendek.
- **Pembelian**Pertimbangkan untuk membeli langganan untuk proyek jangka panjang.

### Inisialisasi dan Pengaturan Dasar

Setelah terinstal, inisialisasi skrip Python Anda dengan Aspose.Slides seperti ini:

```python
import aspose.slides as slides

# Inisialisasi kelas Presentasi\dengan slides.Presentation() sebagai presentasi:
    # Kode Anda untuk menambahkan SmartArt akan ada di sini
```

## Panduan Implementasi

Sekarang mari kita uraikan proses penambahan dan penyesuaian SmartArt di PowerPoint menggunakan Aspose.Slides untuk Python.

### Menambahkan Grafik SmartArt

#### Ringkasan
Buat slide baru dan tambahkan grafik SmartArt jenis bagan organisasi ke dalamnya:

```python
import aspose.slides as slides

# Buat instance presentasi\dengan slides.Presentation() sebagai presentasi:
    # Tambahkan SmartArt dengan dimensi yang ditentukan pada posisi (10, 10)
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### Parameter dan Tujuan Metode
- **x, dan y**: Posisi grafik SmartArt pada slide.
- **lebar tinggi**: Dimensi untuk visibilitas yang tepat.
- **tata letak_jenis**: Menentukan jenis tata letak SmartArt, dalam hal ini, bagan organisasi.

### Menyesuaikan Tata Letak Bagan Organisasi

#### Ringkasan
Sesuaikan node pertama dalam grafik SmartArt kita dengan mengatur tata letaknya ke LEFT_HANGING:

```python
# Atur node pertama ke tata letak yang menggantung di sebelah kiri
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### Penjelasan Opsi Konfigurasi Utama
- **Jenis Tata Letak Bagan Organisasi**Menentukan bagaimana node ditampilkan, meningkatkan keterbacaan dan daya tarik estetika.

### Menyimpan Presentasi

Terakhir, simpan presentasi Anda ke direktori yang ditentukan:

```python
# Simpan presentasi dengan SmartArt\presentation.save("YOUR_OUTPUT_DIRECTORY/smart_art_organization_chart_layout_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}