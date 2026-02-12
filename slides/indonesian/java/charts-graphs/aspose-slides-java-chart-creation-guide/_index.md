---
date: '2026-02-12'
description: Pelajari cara membuat diagram dan mengelola diagram menggunakan Aspose.Slides
  untuk Java. Tutorial ini menunjukkan cara membuat diagram kolom berkelompok, menangani
  seri data, dan menyesuaikan visualisasi.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'Cara Membuat Grafik di Java dengan Aspose.Slides: Panduan Komprehensif'
url: /id/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Diagram di Java dengan Aspose.Slides

## Cara Membuat Diagram di Java: Pendahuluan
Membuat presentasi dinamis sering melibatkan visualisasi data melalui diagram. Dengan **Aspose.Slides for Java**, Anda dapat dengan mudah **how to create chart** objek, meningkatkan kejelasan, dan memberikan dampak yang lebih kuat pada audiens Anda. Tutorial ini memandu Anda melalui penyiapan pustaka, menambahkan **create clustered column chart**, mengelola seri, dan secara kondisional membalikkan titik data negatif.

**Apa yang Akan Anda Pelajari**
- Cara menyiapkan Aspose.Slides for Java.
- Langkah-langkah untuk **create clustered column chart** dalam presentasi Anda.
- Teknik untuk mengelola seri diagram dan titik data.
- Metode untuk secara kondisional membalikkan titik data negatif untuk visualisasi yang lebih baik.
- Cara menyimpan presentasi dengan aman.

### Jawaban Cepat
- **Perpustakaan apa yang digunakan?** Aspose.Slides for Java.
- **Jenis diagram apa yang ditunjukkan?** Clustered column chart.
- **Bisakah saya membalikkan nilai negatif?** Ya, menggunakan `invertIfNegative`.
- **Versi Java apa yang diperlukan?** JDK 16 atau lebih baru.
- **Apakah lisensi diperlukan untuk produksi?** Ya, lisensi Aspose yang valid.

## Apa itu Diagram Kolom Berkelompok?
Diagram kolom berkelompok menampilkan beberapa seri data berdampingan untuk setiap kategori, memudahkan perbandingan nilai antar grup. Ini ideal untuk laporan keuangan, dasbor penjualan, dan skenario apa pun yang memerlukan kontras beberapa metrik.

## Mengapa Menggunakan Aspose.Slides untuk Pembuatan Diagram?
- **Kontrol penuh** atas tampilan diagram tanpa bergantung pada UI PowerPoint.
- **Generasi programatik** memungkinkan pipeline pelaporan otomatis.
- **Dukungan lintas‑platform** memastikan kode Anda berjalan di sistem apa pun yang kompatibel dengan Java.
- **API kaya** untuk penyesuaian detail (warna, label data, pembalikan, dll.).

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

## Panduan Langkah‑per‑Langkah

### Langkah 1: Buat Presentasi dan Tambahkan Diagram Kolom Berkelompok
Pada langkah ini kami **how to create chart** objek dan menempatkan **create clustered column chart** pada slide pertama.

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

### Langkah 2: Kelola Seri Diagram
Sekarang kami akan menghapus semua seri default, menambahkan seri baru, dan mengisinya dengan nilai positif dan negatif.

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

### Langkah 3: Membalikkan Titik Data Negatif Secara Kondisional
Secara default, Aspose.Slides tidak membalikkan nilai negatif. Kami akan mengaktifkan pembalikan hanya untuk titik-titik yang memerlukannya.

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

### Kesalahan Umum & Tips
- **Lupa membuang objek `Presentation`?** Selalu panggil `dispose()` dalam blok `finally` untuk membebaskan sumber daya native.
- **Nilai negatif tidak tampil terbalik?** Pastikan Anda memanggil `invertIfNegative(true)` **setelah** menambahkan titik data.
- **Masalah ukuran diagram:** Koordinat (X, Y) dan dimensi (lebar, tinggi) dalam satuan poin; sesuaikan agar cocok dengan tata letak slide Anda.

## Pertanyaan yang Sering Diajukan

**Q: Can I create other chart types with the same approach?**  
A: Yes, simply replace `ChartType.ClusteredColumn` with any other `ChartType` enum value (e.g., `Line`, `Pie`).  

**Q: Do I need a license for development builds?**  
A: A temporary or evaluation license is required for full feature access; otherwise, the library works in trial mode with watermark limitations.  

**Q: How do I export the presentation to PDF after adding charts?**  
A: Use `pres.save("output.pdf", SaveFormat.Pdf);` after you finish chart manipulation.  

**Q: Is it possible to style individual columns (color, border)?**  
A: Yes, each `IChartDataPoint` provides formatting options such as `getFillFormat().setFillType(FillType.Solid)` and `getLineFormat()`.  

**Q: What if I need to update the chart data after the presentation is saved?**  
A: Load the presentation again with `new Presentation("file.pptx")`, modify the chart data, and re‑save.  

---

**Terakhir Diperbarui:** 2026-02-12  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (JDK 16)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}