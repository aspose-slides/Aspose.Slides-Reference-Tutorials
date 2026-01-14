---
date: '2026-01-14'
description: Pelajari cara menambahkan diagram kolom berkelompok dan menambahkan diagram
  ke slide dalam presentasi .NET menggunakan Aspose.Slides untuk Java. Ikuti panduan
  langkah demi langkah ini dengan contoh kode lengkap.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: Tambahkan diagram kolom berkelompok ke slide .NET Aspose.Slides Java
url: /id/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat Grafik dalam Presentasi .NET Menggunakan Aspose.Slides untuk Java
## Pendahuluan
Membuat presentasi yang menarik sering melibatkan integrasi representasi data visual seperti grafik untuk meningkatkan pemahaman dan keterlibatan audiens. Jika Anda seorang pengembang yang ingin menambahkan grafik dinamis dan dapat disesuaikan ke presentasi .NET Anda menggunakan Aspose.Slides untuk Java, tutorial ini dirancang khusus untuk Anda. Kami akan membahas cara menginisialisasi presentasi, menambahkan berbagai jenis grafik, mengelola data grafik, dan memformat data seri secara efektif.

**Apa yang Akan Anda Pelajari:**
- Cara menyiapkan dan menggunakan Aspose.Slides untuk Java di lingkungan .NET Anda.
- Menginisialisasi presentasi baru menggunakan Aspose.Slides.
- Menambahkan dan menyesuaikan grafik dalam slide.
- Mengelola workbook data grafik.
- Memformat data seri, terutama menangani nilai negatif.

Berpindah ke bagian prasyarat akan memastikan Anda siap mengikuti tutorial ini dengan mudah.

## Jawaban Cepat
- **Apa tujuan utama?** Menambahkan grafik kolom berkelompok ke slide .NET.
- **Perpustakaan mana yang diperlukan?** Aspose.Slides untuk Java (v25.4+).
- **Bisakah saya menggunakannya dalam proyek .NET?** Ya – perpustakaan Java berfungsi melalui jembatan Java‑to‑.NET.
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk grafik dasar.

## Apa itu grafik kolom berkelompok?
Grafik kolom berkelompok menampilkan beberapa seri data berdampingan untuk setiap kategori, memudahkan perbandingan nilai antar grup. Visual ini sangat cocok untuk dasbor bisnis, laporan kinerja, dan skenario apa pun di mana Anda perlu membandingkan beberapa metrik.

## Mengapa menambahkan grafik ke slide dengan Aspose.Slides untuk Java?
Dengan menggunakan Aspose.Slides, Anda dapat menghasilkan, memodifikasi, dan menyimpan presentasi tanpa harus menginstal Microsoft PowerPoint. Ini memberikan kontrol penuh atas jenis grafik, data, dan gaya, sehingga Anda dapat mengotomatisasi pembuatan laporan langsung dari aplikasi .NET Anda.

## Prasyarat
Sebelum menyelami pembuatan grafik dengan Aspose.Slides untuk Java, berikut hal‑hal yang Anda perlukan:

### Perpustakaan dan Versi yang Diperlukan
- **Aspose.Slides untuk Java**: Versi 25.4 atau lebih baru.

### Persyaratan Penyiapan Lingkungan
- Lingkungan pengembangan yang mendukung aplikasi .NET.
- Pemahaman dasar tentang konsep pemrograman Java.

### Prasyarat Pengetahuan
- Familiaritas dengan pembuatan presentasi dalam konteks aplikasi .NET.
- Memahami dependensi Java dan cara mengelolanya (Maven/Gradle).

## Menyiapkan Aspose.Slides untuk Java
Untuk mulai menggunakan Aspose.Slides, Anda perlu menambahkannya sebagai dependensi dalam proyek Anda. Berikut caranya:

### Maven
Tambahkan dependensi berikut ke file `pom.xml` Anda:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Sertakan ini dalam file `build.gradle` Anda:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduhan Langsung
Sebagai alternatif, Anda dapat mengunduh versi terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Langkah Akuisisi Lisensi
- **Percobaan Gratis**: Mulai dengan lisensi sementara untuk menjelajahi fitur.
- **Pembelian**: Pertimbangkan membeli lisensi untuk penggunaan intensif.

#### Inisialisasi dan Penyiapan Dasar
Berikut cara menginisialisasi Aspose.Slides dalam kode Anda:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
Penyiapan ini memastikan manajemen sumber daya ditangani secara efektif.

## Panduan Implementasi
Kami akan memandu Anda melalui implementasi fitur langkah demi langkah.

### Menginisialisasi Presentasi
**Gambaran Umum:**  
Membuat instance presentasi menyiapkan panggung untuk semua operasi selanjutnya. Fitur ini menunjukkan cara memulai dari nol menggunakan Aspose.Slides.

#### Langkah 1: Impor Paket yang Diperlukan
```java
import com.aspose.slides.Presentation;
```

#### Langkah 2: Buat Objek Presentasi Baru
Berikut cara melakukannya:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Ini memastikan objek presentasi dibuang dengan benar setelah penggunaan, mencegah kebocoran memori.*

### Menambahkan Grafik ke Slide
**Gambaran Umum:**  
Menambahkan grafik ke slide Anda dapat membuat visualisasi data lebih efektif dan menarik.

#### Langkah 1: Impor Paket yang Diperlukan
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Langkah 2: Inisialisasi Presentasi dan Tambahkan Grafik
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*Di sini, kami menambahkan grafik kolom berkelompok ke slide pertama pada koordinat dan dimensi yang ditentukan.*

### Mengelola Workbook Data Grafik
**Gambaran Umum:**  
Mengelola workbook data grafik secara efisien memungkinkan Anda memanipulasi seri dan kategori dengan lancar.

#### Langkah 1: Impor Paket yang Diperlukan
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Langkah 2: Akses dan Bersihkan Workbook Data
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*Membersihkan workbook sangat penting untuk memulai dengan kondisi bersih saat menambahkan seri dan kategori baru.*

### Menambahkan Seri dan Kategori ke Grafik
**Gambaran Umum:**  
Fitur ini menunjukkan cara menambahkan titik data yang bermakna dengan mengelola seri dan kategori.

#### Langkah 1: Tambahkan Seri dan Kategori
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*Menambahkan seri dan kategori memungkinkan penyajian data yang lebih teratur.*

### Mengisi Data Seri dan Memformat
**Gambaran Umum:**  
Isi grafik Anda dengan titik data dan format tampilannya untuk meningkatkan keterbacaan, terutama saat menangani nilai negatif.

#### Langkah 1: Isi Data Seri
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*Bagian ini memperlihatkan cara mengisi data dan menerapkan pemformatan warna untuk visualisasi yang lebih baik.*

## Masalah Umum dan Solusinya
- **Kebocoran memori:** Selalu panggil `dispose()` pada objek `Presentation` dalam blok `finally`.
- **Jenis grafik salah:** Pastikan Anda menggunakan `ChartType.ClusteredColumn` ketika menginginkan grafik kolom berkelompok; jenis lain akan menghasilkan tampilan visual yang berbeda.
- **Warna nilai negatif tidak diterapkan:** Verifikasi bahwa nilai `IDataPoint` telah dikonversi dengan benar ke `Number` sebelum perbandingan.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan Aspose.Slides untuk Java dalam proyek .NET murni tanpa Java?**  
J: Ya. Perpustakaan ini berfungsi melalui jembatan Java‑to‑.NET, memungkinkan Anda memanggil API Java dari bahasa .NET.

**T: Apakah percobaan gratis mendukung pembuatan grafik?**  
J: Versi percobaan mencakup semua fungsi grafik, tetapi file yang dihasilkan berisi watermark evaluasi kecil.

**T: Versi .NET mana yang kompatibel?**  
J: Semua versi .NET yang dapat berinteroperasi dengan Java 16+, termasuk .NET Framework 4.6+, .NET Core 3.1+, dan .NET 5/6/7.

**T: Bagaimana cara menangani presentasi besar dengan banyak grafik?**  
J: Gunakan kembali instance `IChartDataWorkbook` yang sama bila memungkinkan dan buang setiap `Presentation` segera untuk membebaskan memori.

**T: Apakah memungkinkan mengekspor grafik sebagai gambar?**  
J: Ya. Gunakan metode `chart.getImage()` atau `chart.exportChartImage()` untuk memperoleh representasi PNG/JPEG.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-01-14  
**Diuji Dengan:** Aspose.Slides untuk Java 25.4  
**Penulis:** Aspose