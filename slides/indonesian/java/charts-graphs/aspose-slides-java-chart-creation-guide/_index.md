---
date: '2026-06-03'
description: Pelajari cara membuat diagram kolom berkelompok di Java menggunakan Aspose.Slides.
  Panduan ini mencakup Maven dependency, chart creation steps, dan data handling.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Buat Diagram Kolom Berkelompok di Java dengan Aspose.Slides
url: /id/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Buat Clustered Column Chart di Java dengan Aspose.Slides

## Cara Membuat Chart di Java: Pendahuluan
Membuat presentasi dinamis sering melibatkan visualisasi data melalui chart. Dengan **Aspose.Slides for Java**, Anda dapat dengan mudah **create clustered column chart** objek, meningkatkan kejelasan, dan memberikan dampak yang lebih kuat pada audiens Anda. Tutorial ini memandu Anda melalui penyiapan library, menambahkan clustered column chart, mengelola series, dan secara kondisional membalikkan data poin negatif.

**Apa yang Akan Anda Pelajari**
- Cara menyiapkan Aspose.Slides for Java.
- Langkah-langkah untuk **create clustered column chart** dalam presentasi Anda.
- Teknik untuk mengelola series chart dan data point.
- Metode untuk secara kondisional membalikkan data point negatif untuk visualisasi yang lebih baik.
- Cara menyimpan presentasi dengan aman.

## Jawaban Cepat
- **Library apa yang digunakan?** Aspose.Slides for Java.  
- **Tipe chart apa yang ditunjukkan?** Clustered column chart.  
- **Bisakah saya membalikkan nilai negatif?** Ya, menggunakan `invertIfNegative`.  
- **Versi Java apa yang diperlukan?** JDK 16 atau lebih baru.  
- **Apakah lisensi diperlukan untuk produksi?** Ya, lisensi Aspose yang valid.

## Apa itu Clustered Column Chart?
Clustered column chart adalah representasi visual yang menempatkan beberapa series data berdampingan untuk setiap kategori, memungkinkan perbandingan cepat antar grup. Ini sempurna untuk laporan keuangan, dasbor penjualan, dan skenario apa pun di mana Anda perlu membandingkan beberapa metrik sekaligus.

## Mengapa Menggunakan Aspose.Slides untuk Pembuatan Chart?
Aspose.Slides memungkinkan Anda menghasilkan dan sepenuhnya menyesuaikan chart secara programatis, menghilangkan kebutuhan untuk mengedit PowerPoint secara manual. Ini mendukung **70+ format input dan output** dan dapat memproses presentasi dengan **hingga 10.000 slide** tanpa memuat seluruh file ke memori, memastikan kinerja tinggi untuk pelaporan skala besar.

## Prasyarat
1. **Perpustakaan yang Diperlukan**  
   - Aspose.Slides for Java (versi 25.4 atau lebih baru).  

2. **Lingkungan**  
   - JDK 16 atau lebih baru.  
   - Maven atau Gradle untuk manajemen dependensi.  

3. **Pengetahuan**  
   - Pemrograman Java dasar.  
   - Familiaritas dengan alat build (Maven/Gradle).  

## Menyiapkan Aspose.Slides untuk Java
### Instalasi Maven
Tambahkan dependensi berikut ke file `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalasi Gradle
Tambahkan baris berikut ke file `build.gradle` Anda:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduhan Langsung
Sebagai alternatif, unduh versi terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Akuisisi Lisensi
- **Free Trial:** Jelajahi fitur tanpa lisensi.  
- **Temporary License:** Gunakan selama evaluasi.  
- **Full License:** Beli untuk penerapan produksi.

### Inisialisasi Dasar
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Bagaimana cara menambahkan clustered column chart ke slide?
`Presentation` adalah kelas inti yang mewakili file PowerPoint. Muat `Presentation` baru, tambahkan slide, dan panggil `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`. Panggilan tunggal ini membuat clustered column chart yang berfungsi penuh yang ditempatkan pada koordinat yang ditentukan. Anda kemudian dapat mengakses objek chart untuk memodifikasi series, data point, dan gaya visual.

## Panduan Langkah‑per‑Langkah

### Langkah 1: Buat Presentation dan Tambahkan Clustered Column Chart
`Presentation` class mewakili dokumen PowerPoint dan memungkinkan pembuatan slide.  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Langkah 2: Kelola Series Chart
Sekarang kita akan menghapus semua series default, menambahkan yang baru, dan mengisinya dengan nilai positif dan negatif.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Langkah 3: Membalikkan Data Point Negatif Secara Kondisional
Metode `invertIfNegative` memungkinkan pembalikan nilai negatif dalam series chart.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## Kesalahan Umum & Tips
- **Lupa memanggil `dispose()` pada objek `Presentation`?** Selalu panggil `dispose()` dalam blok `finally` untuk membebaskan sumber daya native.  
- **Nilai negatif tidak tampil terbalik?** Pastikan Anda memanggil `invertIfNegative(true)` **setelah** menambahkan data point.  
- **Masalah ukuran chart:** Koordinat (X, Y) dan dimensi (lebar, tinggi) dalam satuan point; sesuaikan agar cocok dengan tata letak slide Anda.  

## Pertanyaan yang Sering Diajukan

**Q:** Bisakah saya membuat tipe chart lain dengan pendekatan yang sama?  
A: Ya, cukup ganti `ChartType.ClusteredColumn` dengan nilai enum `ChartType` lainnya (mis., `Line`, `Pie`).  

**Q:** Apakah saya memerlukan lisensi untuk build pengembangan?  
A: Lisensi sementara atau evaluasi diperlukan untuk akses penuh ke fitur; jika tidak, library berfungsi dalam mode trial dengan batasan watermark.  

**Q:** Bagaimana cara mengekspor presentasi ke PDF setelah menambahkan chart?  
`SaveFormat.Pdf` menentukan PDF sebagai format output untuk menyimpan presentasi. Gunakan `pres.save("output.pdf", SaveFormat.Pdf);` setelah Anda selesai memanipulasi chart.  

**Q:** Apakah memungkinkan menata kolom individual (warna, border)?  
`IChartDataPoint` mewakili satu data point dalam chart dan memungkinkan pemformatan. Setiap `IChartDataPoint` menyediakan opsi seperti `getFillFormat().setFillType(FillType.Solid)` dan `getLineFormat()`.  

**Q:** Bagaimana jika saya perlu memperbarui data chart setelah presentasi disimpan?  
A: Muat kembali presentasi dengan `new Presentation("file.pptx")`, modifikasi data chart, dan simpan kembali.  

---

**Terakhir Diperbarui:** 2026-06-03  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (JDK 16)  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara membuat stacked column chart di Java dengan Aspose.Slides – Panduan Komprehensif](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Cara Membuat Chart di Java dengan Aspose.Slides – Menguasai Pembuatan dan Validasi Chart](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Buat & Format Chart di Java Menggunakan Aspose.Slides: Panduan Komprehensif](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}