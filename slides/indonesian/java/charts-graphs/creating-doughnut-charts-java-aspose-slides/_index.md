---
"date": "2025-04-17"
"description": "Pelajari cara membuat dan menyesuaikan bagan donat dalam presentasi Java dengan Aspose.Slides, termasuk menyiapkan lingkungan Anda dan menyesuaikan estetika bagan."
"title": "Cara Membuat Grafik Donat di Java Menggunakan Aspose.Slides untuk Presentasi"
"url": "/id/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Grafik Donat di Java Menggunakan Aspose.Slides untuk Presentasi

## Perkenalan
Membuat presentasi yang menarik secara visual sangat penting untuk menyampaikan informasi secara efektif. Bagan merupakan elemen penting yang meningkatkan pemahaman distribusi data. Tutorial ini memandu Anda membuat bagan donat yang dapat disesuaikan menggunakan Aspose.Slides untuk Java, yang memungkinkan pembuatan bagan dengan mudah dengan opsi penyesuaian yang luas seperti ukuran dan posisi lubang.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan Aspose.Slides untuk Java
- Membuat dan mengonfigurasi diagram donat dalam presentasi
- Menyesuaikan estetika grafik seperti ukuran lubang
- Menyimpan presentasi dengan bagan baru Anda

Mari kita mulai dengan menyiapkan lingkungan kita!

## Prasyarat
Sebelum memulai, pastikan Anda telah memenuhi prasyarat berikut:

### Pustaka dan Versi yang Diperlukan
Untuk bekerja dengan Aspose.Slides untuk Java, sertakan dalam proyek Anda melalui Maven atau Gradle, atau unduh langsung.

#### Persyaratan Pengaturan Lingkungan
- Java Development Kit (JDK) yang berfungsi, sebaiknya versi 8 atau lebih tinggi.
- Lingkungan Pengembangan Terpadu (IDE) seperti IntelliJ IDEA atau Eclipse.

### Prasyarat Pengetahuan
Pemahaman terhadap Java dan konsep pemrograman dasar akan sangat membantu. Pengetahuan dasar tentang Maven atau Gradle akan membantu menyederhanakan proses penyiapan.

## Menyiapkan Aspose.Slides untuk Java
Memasukkan Aspose.Slides ke dalam proyek Anda dapat dilakukan dengan beberapa cara:

**Pakar:**
Tambahkan ketergantungan ini ke `pom.xml` mengajukan:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradasi:**
Sertakan ini di dalam `build.gradle` mengajukan:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Unduh Langsung:**
Atau, unduh versi terbaru dari [Aspose.Slides untuk rilis Java](https://releases.aspose.com/slides/java/).

### Akuisisi Lisensi
- **Uji Coba Gratis**: Mulailah dengan mengunduh versi uji coba untuk menjelajahi fitur Aspose.Slides.
- **Lisensi Sementara**: Dapatkan lisensi sementara untuk fungsionalitas yang diperluas tanpa batasan.
- **Pembelian**:Untuk penggunaan berkelanjutan, pembelian lisensi diperlukan.

Setelah Anda menyiapkan perpustakaan dan lingkungan Anda, mari kita lanjutkan ke penerapan diagram donat kita.

## Panduan Implementasi

### Membuat Bagan Donat
Membuat presentasi dengan bagan donat yang disesuaikan menggunakan Aspose.Slides melibatkan beberapa langkah. Kami akan menguraikannya untuk kejelasan:

#### Inisialisasi Objek Presentasi
Mulailah dengan membuat contoh `Presentation` kelas, yang mewakili dokumen PowerPoint Anda.
```java
// Buat instance kelas Presentasi untuk mewakili dokumen PPTX
Presentation presentation = new Presentation();
```
Langkah ini menginisialisasi presentasi Anda di mana Anda dapat menambahkan slide dan bagan.

#### Tambahkan Bagan Donat ke Slide
Akses slide pertama (atau buat satu jika perlu) dan tambahkan diagram donat:
```java
// Akses slide pertama dalam presentasi
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Posisi di (50, 50) dengan ukuran 400x400
```
Potongan kode ini menambahkan diagram donat ke slide pertama. Parameter menentukan posisi dan dimensinya pada slide.

#### Konfigurasikan Ukuran Lubang Donat
Untuk memberikan tampilan unik pada bagan donat Anda, sesuaikan ukuran lubang:
```java
// Atur ukuran lubang untuk diagram donat menjadi 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```
Di sini, kami menetapkan ukuran lubang menjadi 90%, sehingga menjadi hampir lingkaran penuh. Sesuaikan nilai ini berdasarkan kebutuhan desain Anda.

#### Simpan Presentasi
Setelah mengonfigurasi bagan Anda, simpan presentasinya:
```java
// Simpan presentasi ke disk dalam format PPTX di direktori yang ditentukan
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```
Baris ini menuliskan perubahan Anda ke file bernama `DoughnutHoleSize_out.pptx` di direktori yang Anda tunjuk.

#### Bersihkan Sumber Daya
Terakhir, pastikan Anda membuang objek presentasi:
```java
// Buang objek presentasi ke sumber daya gratis
if (presentation != null) presentation.dispose();
```
Langkah ini penting untuk manajemen sumber daya dan menghindari kebocoran memori.

### Aplikasi Praktis
Bagan donat bersifat serbaguna. Berikut beberapa skenario yang dapat digunakan:
1. **Alokasi Anggaran**: Menampilkan bagaimana anggaran didistribusikan di seluruh departemen.
2. **Hasil Survei**: Visualisasikan tanggapan terhadap pertanyaan dengan jawaban pilihan ganda.
3. **Sumber Lalu Lintas Situs Web**: Menampilkan persentase lalu lintas yang berasal dari berbagai sumber.

### Pertimbangan Kinerja
Saat bekerja dengan Aspose.Slides, pertimbangkan kiat-kiat berikut untuk kinerja yang optimal:
- Kelola memori dengan membuang objek saat tidak lagi diperlukan.
- Gunakan aliran untuk set data besar untuk meminimalkan penggunaan memori.
- Optimalkan kode Anda dengan menggunakan kembali instance jika memungkinkan.

## Kesimpulan
Selamat! Anda telah mempelajari cara membuat dan menyesuaikan diagram donat menggunakan Aspose.Slides untuk Java. Tutorial ini membahas cara menyiapkan pustaka, menambahkan diagram ke presentasi, dan mengubah tampilannya.

Untuk terus mengeksplorasi kemampuan Aspose.Slides, pertimbangkan untuk bereksperimen dengan jenis bagan lain atau mendalami lebih jauh fitur otomatisasi presentasi.

**Langkah Berikutnya:**
- Bereksperimenlah dengan konfigurasi grafik yang berbeda.
- Jelajahi dokumentasi Aspose.Slides tambahan untuk fitur yang lebih canggih.

Siap membuat diagram donat Anda sendiri? Coba terapkan solusi ini pada proyek Anda berikutnya!

## Bagian FAQ
1. **Bisakah saya menyesuaikan warna segmen diagram donat saya?**
   Ya, Anda dapat menyesuaikan warna segmen menggunakan `chart.getChartData().getSeries(i).getDataPointsForBarChart().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid);` untuk mengatur jenis isian padat dan menentukan warna yang Anda inginkan.

2. **Bagaimana cara menambahkan label data ke bagan saya?**
   Menggunakan `chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category"));` dan metode serupa untuk menambahkan titik data dan label secara terprogram.

3. **Apakah mungkin untuk menyimpan grafik dalam format selain PPTX?**
   Tentu saja! Aspose.Slides mendukung berbagai format output seperti PDF, XPS, dan format gambar seperti PNG atau JPEG.

4. **Bagaimana jika saya mengalami kesalahan saat menyimpan presentasi?**
   Pastikan jalur direktori Anda benar dan Anda memiliki izin menulis untuk lokasi yang ditentukan. Periksa apakah versi Aspose.Slides yang Anda gunakan mendukung format file yang ingin Anda simpan.

5. **Dapatkah saya mengotomatiskan pembaruan grafik dengan sumber data langsung?**
   Ya, dengan mengintegrasikan API atau database ke dalam aplikasi Java Anda, Anda dapat memperbarui data bagan secara dinamis dan menyegarkan presentasi sesuai kebutuhan.

## Sumber daya
- **Dokumentasi**:Jelajahi referensi API terperinci di [Aspose.Slides untuk Java](https://reference.aspose.com/slides/java/).
- **Unduh**: Dapatkan versi perpustakaan terbaru dari [Rilis Aspose.Slides](https://releases.aspose.com/slides/java/).
- **Pembelian**:Untuk akses penuh, beli lisensi di [Aspose Pembelian](https://purchase.aspose.com/buy).
- **Uji Coba Gratis**: Uji coba Aspose.Slides dengan uji coba gratis tersedia di halaman unduhan mereka.
- **Lisensi Sementara**Dapatkan lisensi sementara untuk pengujian lanjutan tanpa batasan.
- **Mendukung**: Ada pertanyaan? Kunjungi [Forum Aspose](https://forum.aspose.com/c/slides/11) untuk bantuan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}