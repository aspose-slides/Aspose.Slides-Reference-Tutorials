---
date: '2026-01-14'
description: Pelajari cara membuat diagram kolom berkelompok di Java menggunakan Aspose.Slides.
  Panduan langkah demi langkah yang mencakup presentasi kosong, menambahkan diagram
  ke presentasi, dan mengelola seri.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: Cara membuat diagram kolom berkelompok di Java dengan Aspose.Slides
url: /id/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Menguasai Pembuatan Diagram di Java dengan Aspose.Slides

## Cara Membuat dan Mengelola Diagram Menggunakan Aspose.Slides untuk Java

### Pendahuluan
Membuat presentasi dinamis sering melibatkan visualisasi data melalui diagram. Dengan **Aspose.Slides for Java**, Anda dapat dengan mudah **membuat diagram kolom berkelompok** dan mengelola berbagai tipe diagram, meningkatkan kejelasan serta dampak visual. Tutorial ini akan memandu Anda melalui pembuatan presentasi kosong, penambahan diagram kolom berkelompok, pengelolaan seri, dan penyesuaian pembalikan titik data—semua menggunakan Aspose.Slides for Java.

**Apa yang Akan Anda Pelajari:**
- Cara menyiapkan Aspose.Slides untuk Java.
- Langkah‑langkah **membuat presentasi kosong** dan menambahkan diagram ke presentasi.
- Teknik mengelola seri diagram dan titik data secara efektif.
- Metode membalikkan titik data negatif secara kondisional untuk visualisasi yang lebih baik.
- Cara menyimpan presentasi dengan aman.

Mari kita lihat prasyarat sebelum memulai.

## Jawaban Cepat
- **Apa kelas utama untuk memulai?** `Presentation` dari `com.aspose.slides`.
- **Tipe diagram mana yang membuat diagram kolom berkelompok?** `ChartType.ClusteredColumn`.
- **Bagaimana cara menambahkan diagram ke slide?** Gunakan `addChart()` pada koleksi shape slide.
- **Bisakah Anda membalikkan nilai negatif?** Ya, dengan `invertIfNegative(true)` pada sebuah titik data.
- **Versi apa yang diperlukan?** Aspose.Slides for Java 25.4 atau yang lebih baru.

## Apa itu diagram kolom berkelompok?
Diagram kolom berkelompok menampilkan beberapa seri data berdampingan untuk setiap kategori, sehingga ideal untuk membandingkan nilai antar grup. Aspose.Slides memungkinkan Anda menghasilkan diagram ini secara programatik tanpa membuka PowerPoint.

## Mengapa menggunakan Aspose.Slides untuk Java untuk menambahkan diagram ke presentasi?
- **Kontrol penuh** atas data, tampilan, dan tata letak diagram.
- **Tidak memerlukan instalasi Office** pada server.
- **Mendukung semua tipe diagram utama**, termasuk diagram kolom berkelompok.
- **Integrasi mudah** dengan build Maven/Gradle.

## Prasyarat
Sebelum Anda mulai, pastikan Anda memiliki hal‑hal berikut:

1. **Perpustakaan yang Diperlukan:**
   - Aspose.Slides for Java (versi 25.4 atau lebih baru).

2. **Persyaratan Penyiapan Lingkungan:**
   - Versi JDK yang kompatibel (misalnya, JDK 16).
   - Maven atau Gradle terpasang jika Anda lebih suka mengelola dependensi.

3. **Prasyarat Pengetahuan:**
   - Pemahaman dasar pemrograman Java.
   - Familiaritas dengan penanganan dependensi di lingkungan pengembangan Anda.

## Menyiapkan Aspose.Slides untuk Java
Untuk mulai menggunakan Aspose.Slides, ikuti langkah‑langkah berikut:

**Instalasi Maven:**  
Tambahkan dependensi berikut ke file `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Instalasi Gradle:**  
Tambahkan baris berikut ke file `build.gradle` Anda:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Unduhan Langsung:**  
Sebagai alternatif, unduh versi terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Perolehan Lisensi
- **Uji Coba Gratis:** Anda dapat memulai dengan uji coba gratis untuk menjelajahi fitur.  
- **Lisensi Sementara:** Dapatkan lisensi sementara untuk akses penuh selama periode evaluasi Anda.  
- **Pembelian:** Pertimbangkan membeli lisensi jika Anda menemukan bahwa produk ini cocok untuk kebutuhan jangka panjang Anda.

### Inisialisasi Dasar
Berikut adalah kode minimal yang diperlukan untuk membuat instance presentasi baru:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Panduan Implementasi
Sekarang, mari kita uraikan setiap fitur menjadi langkah‑langkah yang dapat dikelola.

### Membuat Presentasi dengan Diagram Kolom Berkelompok
#### Ikhtisar
Bagian ini menunjukkan cara **membuat presentasi kosong**, menambahkan **diagram kolom berkelompok**, dan menempatkannya pada slide pertama.

**Langkah:**
1. **Inisialisasi Objek Presentation** – buat `Presentation` baru.
2. **Tambahkan Diagram Kolom Berkelompok** – panggil `addChart()` dengan tipe dan dimensi yang sesuai.

**Contoh Kode:**
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

### Mengelola Seri Diagram
#### Ikhtisar
Pelajari cara menghapus seri default, menambahkan seri baru, dan mengisinya dengan nilai positif serta negatif.

**Langkah:**
1. **Hapus Seri yang Ada** – hapus data yang sudah dipopulasi sebelumnya.
2. **Tambahkan Seri Baru** – gunakan sel workbook sebagai nama seri.
3. **Masukkan Titik Data** – tambahkan nilai, termasuk nilai negatif, untuk memperlihatkan pembalikan nanti.

**Contoh Kode:**
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

### Membalikkan Titik Data Seri Berdasarkan Kondisi
#### Ikhtisar
Secara default, Aspose.Slides dapat membalikkan nilai negatif. Anda dapat mengontrol perilaku ini secara global dan per titik data.

**Langkah:**
1. **Setel Pembalikan Global** – nonaktifkan pembalikan otomatis untuk seluruh seri.
2. **Terapkan Pembalikan Kondisional** – aktifkan pembalikan hanya untuk titik negatif tertentu.

**Contoh Kode:**
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

### Masalah Umum dan Solusinya
| Masalah | Solusi |
|---------|--------|
| Diagram muncul kosong | Pastikan indeks slide (`0`) ada dan dimensi diagram berada dalam batas slide. |
| Nilai negatif tidak terbalik | Verifikasi `invertIfNegative(false)` telah diatur pada seri dan `invertIfNegative(true)` pada titik data spesifik. |
| Pengecualian lisensi | Terapkan lisensi Aspose yang valid sebelum membuat objek `Presentation`. |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menambahkan tipe diagram lain selain kolom berkelompok?**  
J: Ya, Aspose.Slides mendukung diagram garis, pai, batang, area, dan banyak tipe diagram lainnya.

**T: Apakah saya memerlukan lisensi untuk pengembangan?**  
J: Uji coba gratis dapat digunakan untuk evaluasi, tetapi lisensi komersial diperlukan untuk penggunaan produksi.

**T: Bagaimana cara mengekspor diagram sebagai gambar?**  
J: Gunakan `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` setelah proses rendering.

**T: Apakah memungkinkan untuk menata diagram (warna, font)?**  
J: Tentu saja. Setiap `IChartSeries` dan `IChartDataPoint` menyediakan properti styling.

**T: Bagaimana jika saya ingin menambahkan diagram ke file PPTX yang sudah ada?**  
J: Muat file dengan `new Presentation("existing.pptx")`, lalu tambahkan diagram ke slide yang diinginkan.

## Kesimpulan
Dalam tutorial ini, Anda telah mempelajari cara **membuat diagram kolom berkelompok** di Java, mengelola seri, dan membalikkan titik data negatif secara kondisional menggunakan Aspose.Slides. Dengan teknik ini, Anda dapat membangun presentasi berbasis data yang menarik secara programatik.

**Langkah Selanjutnya:**
- Bereksperimen dengan tipe diagram lain yang ditawarkan oleh Aspose.Slides untuk Java.  
- Menyelami opsi styling lanjutan seperti warna khusus, label data, dan format sumbu.  
- Mengintegrasikan pembuatan diagram ke dalam pipeline pelaporan atau analitik Anda.

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}