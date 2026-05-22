---
date: '2026-03-20'
description: Pelajari cara menambahkan diagram kolom berkelompok ke presentasi PowerPoint,
  menyesuaikan diagram PowerPoint, dan menyisipkan diagram seri data menggunakan Aspose.Slides
  untuk Java.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Cara menambahkan diagram kolom berkelompok di PowerPoint menggunakan Aspose.Slides
  untuk Java
url: /id/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara menambahkan diagram kolom berkelompok di PowerPoint menggunakan Aspose.Slides untuk Java

## Introduction

Ketika Anda perlu **menambahkan diagram kolom berkelompok** ke dalam deck PowerPoint, visual yang jelas dapat mengubah angka mentah menjadi cerita yang langsung dipahami. Melakukan ini secara manual di PowerPoint dapat memakan waktu, terutama ketika Anda harus menghasilkan banyak slide secara programatis. **Aspose.Slides untuk Java** menghilangkan gesekan – ia memungkinkan Anda membuat, menyesuaikan diagram PowerPoint, dan menyisipkan diagram seri data dengan hanya beberapa baris kode.

Dalam tutorial ini Anda akan belajar cara:
- Menginisialisasi presentasi PowerPoint baru dengan Aspose.Slides untuk Java.
- **Menambahkan diagram ke slide** dan mengkonfigurasikannya sebagai diagram kolom berkelompok.
- **Membuat diagram kolom berkelompok** dengan mendefinisikan tingkat pengelompokan untuk kategori.
- **Menyisipkan diagram seri data** sehingga data Anda ditampilkan dengan benar.
- Menyimpan presentasi selesai sebagai file PPTX.

Mari pastikan Anda memiliki semua yang diperlukan sebelum kita menyelam ke dalam kode.

## Quick Answers
- **Apa kelas utama?** `Presentation` dari `com.aspose.slides`.
- **Jenis diagram apa yang digunakan?** `ChartType.ClusteredColumn`.
- **Apakah saya memerlukan lisensi untuk pengujian?** Versi percobaan gratis berfungsi, tetapi lisensi menghapus batas evaluasi.
- **Versi Java apa yang didukung?** JDK 16 atau lebih baru (contoh menggunakan JDK 16).
- **Bagaimana cara menjalankan contoh?** Tambahkan dependensi Maven/Gradle, kompilasi, dan jalankan metode `main`.

## Apa itu “menambahkan diagram kolom berkelompok”?

*Diagram kolom berkelompok* (juga disebut diagram kolom bergrup) menampilkan beberapa seri data berdampingan untuk setiap kategori, memudahkan perbandingan nilai antar grup. Di PowerPoint, jenis diagram ini ideal untuk penjualan kuartalan, hasil survei, atau skenario apa pun di mana Anda perlu membandingkan beberapa kumpulan data dalam kategori yang sama.

## Mengapa menggunakan Aspose.Slides untuk menambahkan diagram kolom berkelompok?

- **Otomatisasi penuh** – menghasilkan puluhan slide tanpa usaha manual.
- **Kustomisasi detail** – mengontrol warna, label, tingkat pengelompokan, dan lainnya.
- **Lintas platform** – bekerja pada sistem operasi apa pun yang mendukung Java.
- **Tidak memerlukan instalasi Office** – menghasilkan file PPTX di server atau pipeline CI.

## Prerequisites

- **Pustaka Aspose.Slides untuk Java** (versi terbaru disarankan).  
- JDK 16 atau yang lebih baru.  
- Alat build Maven atau Gradle (atau Anda dapat menambahkan JAR secara manual).  
- IDE atau editor teks untuk menjalankan kode Java.

## Setting Up Aspose.Slides for Java

Tambahkan pustaka ke proyek Anda menggunakan salah satu skrip build berikut.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Sebagai alternatif, Anda dapat langsung mengunduh rilis terbaru dari [rilisan Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/).

### License Acquisition

Sebelum menerapkan ke produksi, dapatkan lisensi:
- **Percobaan gratis** – jelajahi semua fitur tanpa pembelian.
- **Lisensi sementara** – evaluasi kemampuan tambahan untuk periode singkat.
- **Lisensi penuh** – membuka penggunaan tak terbatas. Dapatkan dari [halaman pembelian Aspose](https://purchase.aspose.com/buy).

## Implementation Guide

Kami akan melangkah melalui setiap tahap, menjelaskan **cara menambahkan diagram** dan **menyesuaikan diagram PowerPoint** sepanjang proses.

### Initialize Presentation

Pertama, buat objek `Presentation` baru dan ambil slide default.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Add Chart to Slide

Sekarang kita **menambahkan diagram ke slide** menggunakan tipe `ClusteredColumn` dan menghapus data default apa pun.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Prepare Chart Data Workbook

Diagram menyimpan datanya dalam workbook internal. Kami mengosongkannya untuk memulai dari awal.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Add Categories with Grouping Levels

Mengelompokkan kategori menciptakan efek **diagram kolom bergrup**. Setiap kategori dapat menjadi bagian dari grup logis.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Add Data Series to Chart

Di sini kami **menyisipkan entri diagram seri data** yang akan divisualisasikan sebagai kolom terpisah.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Save Presentation with Chart

Akhirnya, tulis file PPTX ke disk.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Practical Applications

- **Laporan Bisnis** – membandingkan pendapatan kuartalan antar wilayah.  
- **Penelitian Akademik** – menampilkan hasil eksperimen yang dikelompokkan berdasarkan kondisi uji.  
- **Manajemen Proyek** – memvisualisasikan tingkat penyelesaian tugas untuk beberapa tim dalam satu slide.

## Performance Considerations

- **Manajemen memori** – lepaskan workbook besar setelah penggunaan.  
- **Operasi batch** – hindari memperbarui diagram di dalam loop ketat; kumpulkan data terlebih dahulu, lalu terapkan.  
- **Optimasi bawaan** – Aspose.Slides menyediakan metode seperti `Presentation.optimize()` untuk file besar.

## Common Pitfalls & Tips

- **Pitfall:** Lupa mengosongkan seri/kategori yang ada dapat menyebabkan data duplikat.  
  **Tip:** Selalu panggil `clear()` sebelum mengisi data baru.  
- **Pitfall:** Menggunakan alamat sel yang salah (misalnya, `"c2"` alih‑alih `"C2"`).  
  **Tip:** Referensi sel tidak sensitif huruf, tetapi pertahankan konsistensi untuk keterbacaan.  
- **Tip:** Gunakan `setGroupingItem` untuk membuat label grup yang bermakna; mereka akan muncul otomatis di legenda diagram.

## Frequently Asked Questions

**Q1: Bagaimana cara menambahkan beberapa seri ke diagram saya?**  
A1: Panggil `ch.getChartData().getSeries().add()` berulang kali, memberikan nama unik dan titik data untuk setiap seri.

**Q2: Apa saja masalah umum dengan diagram Aspose.Slides?**  
A2: Masalah sering muncul karena rentang data yang tidak cocok atau sel workbook yang hilang. Pastikan setiap kategori dan titik data memiliki sel yang bersesuaian.

**Q3: Bisakah saya menggunakan Aspose.Slides dengan bahasa pemrograman lain?**  
A3: Ya, Aspose menyediakan pustaka setara untuk .NET, C++, Python, dan lainnya.

**Q4: Bagaimana cara memperbarui diagram yang sudah ada dalam presentasi?**  
A4: Muat presentasi, temukan diagram melalui `slide.getShapes().get_Item(index)`, lalu modifikasi seri atau formatnya sesuai kebutuhan.

**Q5: Apakah ada batasan pada jenis diagram dengan Aspose.Slides?**  
A5: Pustaka mendukung berbagai jenis diagram, tetapi selalu periksa dokumentasi terbaru untuk jenis yang baru ditambahkan atau yang sudah usang.

## Resources

- **Documentation**: [Referensi Aspose.Slides](https://reference.aspose.com/slides/java/)
- **Download**: [Rilis Terbaru](https://releases.aspose.com/slides/java/)
- **Purchase**: [Beli Aspose.Slides](https://purchase.aspose.com/buy)
- **Free Trial**: [Mulai Percobaan Gratis Anda](https://releases.aspose.com/slides/java/)
- **Temporary License**: [Minta Lisensi Sementara](https://purchase.aspose.com/temporary-license/)
- **Support Forum**: [Dukungan Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Slides untuk Java 25.4 (JDK 16)  
**Author:** Aspose