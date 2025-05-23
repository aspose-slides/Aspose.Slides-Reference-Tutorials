---
"date": "2025-04-17"
"description": "Pelajari cara membuat diagram garis dengan penanda di Java menggunakan Aspose.Slides. Tutorial ini mencakup pembuatan diagram, penambahan seri, dan penyimpanan presentasi secara efektif."
"title": "Membuat Grafik Garis dengan Penanda Default Menggunakan Aspose.Slides untuk Java"
"url": "/id/java/charts-graphs/create-line-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat Grafik Garis dengan Penanda Default Menggunakan Aspose.Slides untuk Java
## Perkenalan
Membuat diagram yang menarik secara visual dan informatif sangat penting untuk presentasi, laporan, dan dasbor. Mengotomatiskan proses ini dalam pengembangan perangkat lunak menghemat waktu dan memastikan konsistensi di seluruh dokumen. Tutorial ini menunjukkan cara membuat diagram garis dengan penanda menggunakan Aspose.Slides untuk Java.
**Aspose.Slides untuk Java** adalah pustaka canggih yang memungkinkan pengembang untuk memanipulasi presentasi PowerPoint secara terprogram tanpa perlu menginstal Microsoft Office. Pustaka ini menyederhanakan tugas-tugas seperti membuat, mengedit, dan mengekspor slide, menjadikannya alat penting untuk pembuatan dokumen otomatis.
**Apa yang Akan Anda Pelajari:**
- Cara menginisialisasi Aspose.Slides untuk Java
- Langkah-langkah membuat diagram garis dengan penanda
- Menambahkan seri dan kategori ke bagan
- Mengonfigurasi legenda bagan
- Menyimpan presentasi
Siap untuk memulai? Pastikan Anda telah menyiapkan semuanya terlebih dahulu!
## Prasyarat
Sebelum kita memulai, pastikan lingkungan pengembangan Anda siap:
1. **Perpustakaan & Ketergantungan:**
   - Aspose.Slides untuk pustaka Java (versi 25.4 direkomendasikan)
   - Java Development Kit (JDK) versi 16 atau lebih tinggi
2. **Pengaturan Lingkungan:**
   - IDE Anda harus mendukung alat pembangunan Maven atau Gradle.
   - Pastikan Anda memiliki berkas lisensi yang valid jika diperlukan.
3. **Prasyarat Pengetahuan:**
   - Pemahaman dasar tentang pemrograman Java
   - Keakraban dengan membangun proyek menggunakan Maven atau Gradle
Jika semua ini sudah tersedia, mari kita siapkan Aspose.Slides untuk proyek Anda!
## Menyiapkan Aspose.Slides untuk Java
Untuk menggunakan Aspose.Slides untuk Java, Anda perlu menyertakannya sebagai dependensi dalam proyek Anda. Bergantung pada apakah Anda menggunakan Maven atau Gradle, pengaturannya akan sedikit berbeda.
### Pakar
Tambahkan dependensi berikut ke `pom.xml` mengajukan:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Bahasa Inggris Gradle
Sertakan ini di dalam `build.gradle` mengajukan:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Unduh Langsung
Atau, Anda dapat mengunduh versi terbaru dari [Aspose.Slides untuk rilis Java](https://releases.aspose.com/slides/java/).
**Langkah-langkah Memperoleh Lisensi:**
- Untuk uji coba gratis, kunjungi [halaman uji coba gratis](https://releases.aspose.com/slides/java/).
- Untuk mendapatkan lisensi sementara, navigasikan ke [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).
- Beli lisensi penuh melalui mereka [portal pembelian](https://purchase.aspose.com/buy).
**Inisialisasi Dasar:**
Berikut ini cara menginisialisasi Aspose.Slides di aplikasi Java Anda:
```java
import com.aspose.slides.Presentation;
// Inisialisasi objek presentasi baru
Presentation pres = new Presentation();
```
Sekarang, mari kita mulai membuat grafik!
## Panduan Implementasi
### Fitur 1: Pembuatan Bagan dengan Penanda Default
Bagian ini menunjukkan cara membuat diagram garis yang dilengkapi dengan penanda. Fitur ini penting untuk memvisualisasikan tren data secara efektif.
#### Menambahkan Diagram Garis
Untuk menambahkan diagram garis dengan penanda:
```java
import com.aspose.slides.*;
// Akses slide pertama
ISlide slide = pres.getSlides().get_Item(0);
// Tambahkan diagram garis dengan penanda ke slide pada posisi (10, 10) dengan ukuran (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```
#### Seri dan Kategori Kliring
Untuk memulai yang baru:
```java
// Bersihkan seri dan kategori yang ada untuk memastikan tampilan yang bersih
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Dapatkan buku kerja data grafik untuk manipulasi lebih lanjut
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```
### Fitur 2: Menambahkan Seri dan Kategori
Menambahkan seri dan kategori sangat penting untuk mengisi diagram Anda dengan data yang bermakna.
#### Membuat Seri Baru
Untuk menambahkan seri baru bernama "Seri 1":
```java
// Tambahkan seri baru ke bagan
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Akses seri pertama untuk populasi data
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```
#### Mengisi Kategori dan Titik Data
Untuk menambahkan kategori dan titik data terkait:
```java
// Tambahkan nama kategori dan titik datanya masing-masing
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Menangani titik data nol dengan baik
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```
### Fitur 3: Menambahkan Seri Kedua dan Mengisi Titik Data
Menambahkan seri tambahan akan memberi kedalaman lebih pada bagan Anda.
#### Membuat dan Mengisi Seri Kedua
Untuk menambahkan "Seri 2":
```java
// Tambahkan seri lain bernama 'Seri 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Akses seri kedua untuk populasi data
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Tambahkan titik data untuk 'Seri 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```
### Fitur 4: Mengonfigurasi Legenda Bagan
Mengonfigurasi legenda meningkatkan keterbacaan bagan.
#### Menyesuaikan Pengaturan Legenda
Untuk mengonfigurasi:
```java
// Aktifkan legenda dan atur agar tidak melapisi titik data
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```
### Fitur 5: Menyimpan Presentasi
Setelah bagan Anda siap, simpan presentasi ke sebuah berkas.
```java
try {
    // Simpan presentasi yang dimodifikasi ke direktori yang ditentukan
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```
## Aplikasi Praktis
1. **Pelaporan Bisnis:**
   - Gunakan bagan dalam laporan keuangan untuk menggambarkan tren dari waktu ke waktu.
2. **Analisis Data:**
   - Visualisasikan pola dan korelasi data selama fase analisis.
3. **Materi Pendidikan:**
   - Membuat slide informatif untuk kuliah atau presentasi akademis.
4. **Manajemen Proyek:**
   - Tingkatkan jadwal proyek dengan elemen bagan visual.
5. **Presentasi Pemasaran:**
   - Pamerkan tren penjualan dan hasil kampanye secara efektif menggunakan bagan.
## Kesimpulan
Anda telah mempelajari cara membuat diagram garis dengan penanda di Java menggunakan Aspose.Slides, menambahkan seri dan kategori, mengonfigurasi legenda, dan menyimpan presentasi. Keterampilan ini sangat berharga untuk membuat konten visual yang dinamis di berbagai aplikasi profesional.
Untuk menjelajahi lebih lanjut tentang fitur Aspose.Slides atau mencari dukungan komunitas, kunjungi [dokumentasi resmi](https://docs.aspose.com/slides/java/) atau bergabung dengan forum seperti Stack Overflow.
Selamat membuat kode!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}