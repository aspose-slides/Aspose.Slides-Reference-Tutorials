---
date: '2026-01-17'
description: Pelajari cara membuat diagram di Java menggunakan Aspose.Slides, menambahkan
  diagram kolom berkelompok, dan menyimpan presentasi sebagai pptx. Panduan langkah
  demi langkah untuk pengembang Java.
keywords:
- Aspose.Slides for Java
- chart manipulation in presentations
- Java presentation library
title: Cara Membuat Diagram di Java dengan Aspose.Slides untuk Java
url: /id/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara membuat chart di java dengan Aspose.Slides untuk Java

## Perkenalan
Membuat pengalaman **membuat grafik di java** yang terlihat profesional tidak harus menjadi masalah. Dengan **Aspose.Slides for Java**, Anda dapat menambahkan, menata, dan menyimpan bagan—seperti bagan kolom berkerumun—langsung di dalam presentasi PowerPoint secara terprogram. Dalam tutorial ini kami akan menjelaskan cara menyiapkan pustaka, menginisialisasi presentasi, menyisipkan bagan kolom berkerumun, menyesuaikan plot area, dan terakhir menyimpan file sebagai PPTX. Pada akhir tutorial, Anda akan memiliki potongan kode yang dapat digunakan kembali dan dapat dimasukkan ke dalam proyek Java mana pun.

**Apa yang Akan Anda Pelajari**
- Cara menyiapkan dependensi Aspose.Slides Maven atau Gradle
- Cara **membuat bagan di java** dan menambahkan bagan kolom berkerumun
- Cara mengonfigurasi area plot (posisi, ukuran, tata letak)
- Cara **menyimpan presentasi sebagai pptx** dengan penanganan sumber daya yang tepat

Siap membuat data Anda berbicara secara visual? Mari kita mulai!

## Jawaban Cepat
- **Perpustakaan apa yang saya perlukan?** Aspose.Slides untuk Java (Maven/Gradle).
- **Jenis bagan manakah yang diperlihatkan?** Bagan kolom tergugus.
- **Bagaimana cara menyimpan file?** Gunakan `presentation.save(..., SaveFormat.Pptx)`.
- **Apakah saya memerlukan lisensi?** Versi trial gratis dapat digunakan untuk pengembangan; lisensi penuh diperlukan untuk produksi.
- **Dapatkah saya mengubah area plot?** Ya, Anda dapat mengatur tipe target X,Y, lebar, tinggi dan tata letak.

## Apa itu membuat grafik di java?
Membuat bagan di Java berarti menggunakan pustaka untuk menghasilkan objek bagan, mengisi data, dan menyematkannya ke dalam dokumen—dalam hal ini, slide PowerPoint. Aspose.Slides menyembunyikan detail rendah Office Open XML, sehingga Anda dapat fokus pada hasil visual.

## Mengapa menambahkan bagan kolom berkerumun dengan Aspose.Slides?
Bagan kolom terklaster sangat cocok untuk membandingkan beberapa seri data secara berdampingan. Chart ini banyak digunakan dalam laporan bisnis, dasbor, dan presentasi. Aspose.Slides memberi Anda kontrol penuh atas warna, marker, sumbu, dan tata letak tanpa harus membuka PowerPoint secara manual.

## Prasyarat
- Perpustakaan **Aspose.Slides untuk Java** (versi 25.4 atau lebih baru).
- **JDK 16** (atau lebih baru) terpasang.
- IDE seperti IntelliJ IDEA atau Eclipse.
- Familiaritas dasar dengan sintaks Java.

## Menyiapkan Aspose.Slide untuk Java
### Pakar
Tambahkan dependensi ke `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Sertakan pustaka dalam `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduh Langsung
Atau, unduh rilis terbaru dari [situs resmi Aspose](https://releases.aspose.com/slides/java/).

#### Akuisisi Lisensi
Gunakan lisensi uji coba gratis atau lisensi sementara untuk pengujian. Beli lisensi penuh untuk penggunaan produksi.

### Inisialisasi dan Pengaturan Dasar
Buat kelas Java baru dan impor kelas inti:

```java
import com.aspose.slides.Presentation;
```

## Panduan Penerapan
Kami akan membahas setiap langkah dengan penjelasan yang jelas.

### Inisialisasi Presentasi dan Manipulasi Slide
#### Ringkasan
Pertama, buat presentasi baru dan ambil slide pertama tempat chart akan ditempatkan.

**1. Membuat dan Inisialisasi Presentasi**

```java
Presentation presentation = new Presentation();
```

**2. Akses Slide Pertama**

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Tambahkan Bagan Kolom Tergugus**

```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

> **Kiat profesional:** Selalu bungkus penggunaan `Presentation` dalam blok `try‑finally` dan panggil `presentation.dispose()` di dalam `finally` untuk membebaskan sumber daya native.

### Konfigurasi Area Petak
#### Ringkasan
Sesuaikan area plot chart untuk mengontrol dimana data divisualisasikan dalam slide.

**1. Tetapkan Posisi dan Ukuran**

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
```

**2. Tentukan Jenis Target Tata Letak**

```java
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

### Menyimpan Presentasi
#### Ringkasan
Setelah menyesuaikan bagan, simpan presentasi sebagai file PPTX.

**1. Simpan ke Berkas**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **Peringatan:** Pastikan direktori output ada dan aplikasi memiliki izin menulis; jika tidak, operasi penyimpanan akan gagal.

## Kasus Penggunaan Umum
- **Laporan Bisnis:** Menyematkan tren penjualan dan KPI keuangan.
- **Slide Edukasi:** Memvisualisasikan hasil eksperimen atau data statistik.
- **Proposal Proyek:** Menyoroti tonggak sejarah dan alokasi sumber daya.
- **Marketing Decks:** Menampilkan kinerja kampanye dengan chart yang hidup.
- **Perencanaan Acara:** Menampilkan demografi atau rincian jadwal.

## Pertimbangan Kinerja
- Segera buang objek `Presentation` untuk menghindari kebocoran memori.
- Untuk kumpulan data besar, isi seri chart secara bertahap daripada memuat semuanya sekaligus.
- Gunakan alat profil bawaan Java untuk menyatukan penggunaan heap selama pembuatan chart.

## Pertanyaan yang Sering Diajukan

**T: Bagaimana cara menambahkan jenis bagan lainnya?**
A: Gunakan enum `ChartType` (misalnya `ChartType.Pie`, `ChartType.Line`) saat memanggil `addChart`.

**T: Dapatkah saya menyesuaikan warna bagan?**
A: Ya, modifikasi format isi seri atau palet chart melalui API `IChart`.

**T: Presentasi saya tidak dapat disimpan—apa yang salah?**
A: Pastikan `YOUR_OUTPUT_DIRECTORY` sudah benar, ada, dan dapat ditulisi. Periksa juga apakah ada file kunci yang masih aktif.

**T: Bagaimana cara menangani presentasi berukuran sangat besar secara efisien?**
A: Proses slide secara batch, buang setiap `Presentation` setelah selesai, dan tahan untuk meningkatkan ukuran heap JVM bila diperlukan.

**T: Apakah Aspose.Slides gratis untuk proyek komersial?**
J: Versi uji coba tersedia untuk evaluasi, tetapi lisensi berbayar diperlukan untuk penggunaan komersial.

## Sumber daya
- [Dokumentasi](https://reference.aspose.com/slides/java/)
- [Unduh Aspose.Slides](https://releases.aspose.com/slides/java/)
- [Lisensi Pembelian](https://purchase.aspose.com/buy)
- [Uji Coba Gratis](https://releases.aspose.com/slides/java/)
- [Lisensi Sementara](https://purchase.aspose.com/temporary-license/)
- [Forum Dukungan](https://forum.aspose.com/c/slides/11)

Mulailah membuat presentasi yang menakjubkan secara visual dengan Aspose.Slides untuk Java hari ini!

---

**Terakhir Diperbarui:** 2026-01-17
**Diuji Dengan:** Aspose.Slides untuk Java 25.4 (JDK16)
**Penulis:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
