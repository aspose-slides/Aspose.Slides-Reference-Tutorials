---
date: '2026-06-03'
description: Pelajari cara membuat grafik dalam presentasi .NET dan menambahkan grafik
  ke slide dengan Aspose.Slides for Java. Ikuti panduan langkah demi langkah ini untuk
  visualisasi data.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Buat grafik di .NET menggunakan Aspose.Slides for Java
url: /id/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Buat diagram dalam .NET menggunakan Aspose.Slides untuk Java

## Pendahuluan
Membuat presentasi yang menarik sering melibatkan integrasi representasi data visual seperti diagram untuk meningkatkan pemahaman dan keterlibatan audiens. **Jika Anda ingin membuat diagram dalam .NET**, Aspose.Slides for Java memberikan Anda API yang kuat dan tidak tergantung bahasa yang bekerja mulus di dalam aplikasi .NET. Dalam tutorial ini Anda akan belajar cara menginisialisasi presentasi, menambahkan berbagai jenis diagram, mengelola workbook data diagram, dan memformat data seri—termasuk penanganan nilai negatif. Pada akhir tutorial Anda akan dapat menghasilkan diagram dalam file presentasi secara programatis dan menambahkan diagram ke slide dengan hanya beberapa baris kode.

## Jawaban Cepat
- **Apa tujuan utama?** Membuat diagram dalam presentasi .NET menggunakan Aspose.Slides untuk Java.  
- **Versi perpustakaan mana yang diperlukan?** Aspose.Slides for Java 25.4 atau lebih baru.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya menggunakan Maven atau Gradle?** Ya—kedua sistem build didukung.  
- **Jenis diagram apa yang tersedia?** Kolom berkelompok, garis, pai, batang, area, dan lainnya.

## Cara membuat diagram dalam presentasi .NET dengan Aspose.Slides untuk Java?
`Presentation` class mewakili file PowerPoint dan menyediakan metode untuk memanipulasi slide-nya. Muat objek `Presentation` baru, panggil `slides.addEmptySlide()` untuk mendapatkan sebuah slide, kemudian gunakan `slide.getShapes().addChart()` untuk menyisipkan jenis diagram yang diinginkan pada koordinat yang Anda tentukan. Setelah diagram ditambahkan, isi workbook data diagram dengan seri dan kategori, terapkan format apa pun (seperti warna untuk nilai negatif), dan akhirnya simpan presentasi ke file .pptx. Alur ini memungkinkan Anda **membuat diagram dalam .NET** dengan serangkaian panggilan API yang singkat.

## Apa itu Aspose.Slides untuk Java?
Aspose.Slides for Java adalah API lintas‑platform yang memungkinkan pengembang untuk membuat, memodifikasi, dan merender file PowerPoint tanpa Microsoft Office. Ini mendukung **50+ format input dan output** dan dapat memproses presentasi dengan ribuan slide sambil menjaga penggunaan memori di bawah 200 MB.

## Mengapa menggunakan Aspose.Slides untuk Java dalam proyek .NET?
Aspose.Slides untuk Java berjalan di Java Virtual Machine dan dapat dipanggil dari .NET melalui wrapper native, memberikan pengembang .NET akses ke mesin diagram yang matang, pemrosesan berperforma tinggi untuk set data besar, dan kompatibilitas penuh dengan kode Java yang ada tanpa menulis ulang logika.

## Prasyarat
Sebelum menyelami pembuatan diagram dengan Aspose.Slides untuk Java, mari kita rangkum apa yang Anda perlukan:

### Perpustakaan dan Versi yang Diperlukan
- **Aspose.Slides for Java**: Versi 25.4 atau lebih baru.

### Persyaratan Penyiapan Lingkungan
- Lingkungan pengembangan yang mendukung aplikasi .NET.  
- Pemahaman dasar tentang konsep pemrograman Java.

### Prasyarat Pengetahuan
- Familiaritas dengan pembuatan presentasi dalam konteks aplikasi .NET.  
- Memahami dependensi Java dan pengelolaannya (Maven/Gradle).

## Menyiapkan Aspose.Slides untuk Java
Untuk mulai menggunakan Aspose.Slides, Anda perlu menyertakannya sebagai dependensi dalam proyek Anda. Berikut cara melakukannya:

### Maven
The Maven dependency snippet adds Aspose.Slides for Java to your project.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Include this line in your `build.gradle` file to pull the library from Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduhan Langsung
Alternatively, you can download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Langkah-langkah Akuisisi Lisensi
- **Free Trial**: Mulai dengan lisensi sementara untuk menjelajahi fitur.  
- **Purchase**: Beli lisensi untuk penggunaan produksi tanpa batas.

#### Inisialisasi dan Penyiapan Dasar
Inisialisasi `Slides` memerlukan penetapan lisensi dan pembuatan instance `Presentation`.

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

### Inisialisasi Presentasi
**Gambaran Umum:**  
Membuat instance presentasi menyiapkan panggung untuk semua operasi selanjutnya. Fitur ini menunjukkan cara memulai dari awal menggunakan Aspose.Slides.

#### Langkah 1: Impor Paket yang Diperlukan
`Presentation` dan kelas terkait merupakan bagian dari namespace `com.aspose.slides`.

```java
import com.aspose.slides.Presentation;
```

#### Langkah 2: Buat Objek Presentation Baru
Instansiasi objek `Presentation` dan bungkus dalam blok try‑with‑resources untuk menjamin pembuangan.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*Ini memastikan bahwa objek presentasi dibuang dengan benar setelah penggunaan, mencegah kebocoran memori.*

### Menambahkan Diagram ke Slide
**Gambaran Umum:**  
Menambahkan diagram ke slide Anda dapat membuat visualisasi data lebih efektif dan menarik.

#### Langkah 1: Impor Paket yang Diperlukan
Kelas `Chart` mewakili bentuk diagram yang dapat ditempatkan pada slide dan disesuaikan.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Langkah 2: Inisialisasi Presentasi dan Tambahkan Diagram
Buat slide, lalu panggil `addChart` dengan `ChartType.ClusteredColumn` serta posisi dan ukuran yang diinginkan.

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

*Di sini, kami menambahkan diagram kolom berkelompok ke slide pertama pada koordinat dan dimensi yang ditentukan.*

### Mengelola Workbook Data Diagram
**Gambaran Umum:**  
Mengelola workbook data diagram Anda secara efisien memungkinkan manipulasi seri dan kategori dengan mulus.

#### Langkah 1: Impor Paket yang Diperlukan
`IChartDataWorkbook` menyediakan akses ke workbook mirip Excel yang mendasari yang digunakan oleh diagram.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Langkah 2: Akses dan Bersihkan Workbook Data
Ambil workbook dari diagram dan bersihkan semua data yang ada untuk memulai dari awal.

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

### Menambahkan Seri dan Kategori ke Diagram
**Gambaran Umum:**  
Fitur ini menunjukkan cara menambahkan titik data yang bermakna dengan mengelola seri dan kategori.

#### Langkah 1: Tambahkan Seri dan Kategori
Gunakan `chart.getChartData().getSeries().add()` dan `chart.getChartData().getCategories().add()` untuk mendefinisikan struktur.

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

*Menambahkan seri dan kategori memungkinkan presentasi data yang lebih terorganisir.*

### Mengisi Data Seri dan Memformat
**Gambaran Umum:**  
Isi diagram Anda dengan titik data dan format tampilan untuk meningkatkan keterbacaan, terutama saat menangani nilai negatif.

#### Langkah 1: Isi Data Seri
Tetapkan nilai numerik ke setiap sel di workbook dan terapkan isian merah untuk angka negatif.

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

*Bagian ini menunjukkan cara mengisi data dan menerapkan pemformatan warna untuk visualisasi yang lebih baik.*

## Masalah Umum dan Solusinya
- **LicenseNotFoundException** – Pastikan jalur file lisensi benar dan file dapat diakses pada runtime.  
- **NullPointerException on chart data** – Selalu bersihkan workbook sebelum menambahkan seri baru untuk menghindari data sisa.  
- **Chart not rendering in .NET** – Verifikasi bahwa Anda menggunakan versi Aspose.Slides JAR yang kompatibel dengan .NET dan bahwa runtime Java dikonfigurasi dengan benar dalam proyek .NET Anda.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menghasilkan diagram dalam file presentasi tanpa GUI?**  
A: Ya, Aspose.Slides untuk Java sepenuhnya headless dan berfungsi pada server tanpa komponen grafis apa pun.

**Q: Versi .NET mana yang didukung?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, dan .NET 6 semuanya didukung.

**Q: Berapa banyak jenis diagram yang dapat saya tambahkan?**  
A: Lebih dari 20 jenis diagram tersedia, termasuk kolom, garis, pai, area, dan diagram radar.

**Q: Apakah memungkinkan untuk menata titik data individu?**  
A: Tentu – Anda dapat mengatur warna isi, batas, dan penanda untuk setiap titik data melalui API `IDataPoint`.

**Q: Apakah saya perlu mengonversi objek Java ke tipe .NET secara manual?**  
A: Tidak, wrapper .NET Aspose.Slides untuk Java menangani konversi tipe secara otomatis.

**Terakhir Diperbarui:** 2026-06-03  
**Diuji Dengan:** Aspose.Slides for Java 25.4  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Menyematkan Diagram dalam Presentasi .NET Menggunakan Aspose.Slides untuk Visualisasi Data yang Efektif](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Cara Mengambil Tipe Sumber Data Diagram Menggunakan Aspose.Slides untuk .NET - Diagram & Grafik](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Menguasai Pembuatan dan Manipulasi Seri Diagram dengan Aspose.Slides .NET untuk Visualisasi Data yang Efektif](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}