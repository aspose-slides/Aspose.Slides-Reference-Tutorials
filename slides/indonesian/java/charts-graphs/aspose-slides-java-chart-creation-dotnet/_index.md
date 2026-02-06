---
date: '2026-02-06'
description: Pelajari cara menginisialisasi presentasi Aspose Slides dan menyesuaikan
  diagram kolom berkelompok di .NET menggunakan Aspose.Slides untuk Java. Ikuti panduan
  langkah demi langkah ini untuk meningkatkan visualisasi data.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 'Inisialisasi Presentasi dengan Aspose Slides: Grafik .NET'
url: /id/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat Diagram dalam Presentasi .NET Menggunakan Aspose.Slides untuk Java

## Introduction
Dalam tutorial ini Anda akan **initialize presentation Aspose Slides** dan mempelajari cara menyematkan diagram yang dinamis dan dapat disesuaikan ke dalam slide .NET Anda. Data visual—seperti diagram kolom berkelompok—membantu audiens Anda memahami tren secara instan, dan Aspose.Slides untuk Java memberi Anda kontrol programatik penuh bahkan ketika Anda menargetkan lingkungan .NET. Kami akan memandu Anda melalui penyiapan pustaka, membuat presentasi baru, menambahkan diagram, mengisi data, serta menerapkan trik pemformatan seperti memberi warna pada nilai negatif.

**What You’ll Learn**
- Cara menyiapkan Aspose.Slides untuk Java dalam proyek .NET.  
- Cara **initialize presentation Aspose Slides** dan menambahkan diagram.  
- Cara **customize clustered column chart** series dan categories.  
- Mengelola workbook data diagram dan menerapkan pemformatan bersyarat.  

### Quick Answers
- **What is the first step?** Initialize a `Presentation` object.  
- **Which chart type is used in the example?** `ClusteredColumn`.  
- **Can I format negative values differently?** Yes, using conditional fill colors.  
- **Do I need a license for testing?** A free trial license works for development.  
- **Which Maven artifact is required?** `com.aspose:aspose-slides:25.4` with `jdk16` classifier.

## What is “initialize presentation Aspose Slides”?
Menginisialisasi sebuah presentasi membuat file PPTX dalam memori yang dapat Anda manipulasi sebelum disimpan. Aspose.Slides mengabstraksi format file, memungkinkan Anda menambahkan slide, shape, dan diagram tanpa harus berurusan dengan struktur OPC tingkat rendah.

## Why customize a clustered column chart?
Diagram kolom berkelompok ideal untuk membandingkan beberapa seri data lintas kategori. Menyesuaikan warna, titik data, dan label memungkinkan Anda menyoroti wawasan utama—seperti menekankan nilai negatif dengan merah dan nilai positif dengan hijau—sehingga slide Anda lebih menarik.

## Prerequisites
- **Aspose.Slides for Java** ≥ 25.4  
- Lingkungan pengembangan .NET (Visual Studio, .NET 6+ disarankan)  
- Pengetahuan dasar Java (Anda akan menulis kode Java yang berjalan di JVM dan dipanggil dari .NET melalui JNI atau lapisan jembatan)  

### Required Libraries and Versions
- **Aspose.Slides for Java**: Versi 25.4 atau lebih baru.

### Environment Setup Requirements
- Runtime Java yang kompatibel dengan .NET (misalnya AdoptOpenJDK 16).  
- Maven atau Gradle untuk manajemen dependensi.

### Knowledge Prerequisites
- Familiarity with creating presentations in a .NET context.  
- Understanding of Java project configuration (Maven/Gradle).

## Setting Up Aspose.Slides for Java
Tambahkan pustaka ke proyek Anda menggunakan alat build pilihan Anda.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Anda juga dapat mengunduh JAR terbaru dari halaman rilis resmi: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition Steps
- **Free Trial** – menghasilkan file lisensi sementara untuk pengembangan.  
- **Purchase** – memperoleh lisensi penuh untuk penyebaran produksi.

#### Basic Initialization and Setup
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
Blok `try/finally` menjamin bahwa sumber daya native dilepaskan, mencegah kebocoran memori.

## How to initialize presentation Aspose Slides
Berikut kami menjelaskan langkah‑langkah konkret untuk membuat presentasi baru dan menyiapkannya untuk penyisipan diagram.

### Initializing Presentation
**Overview:**  
Membuat instance presentasi menyiapkan panggung untuk semua operasi selanjutnya.

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
```

#### Step 2: Create a New Presentation Object
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Ini memastikan bahwa objek presentasi dibuang dengan benar setelah penggunaan, mencegah kebocoran memori.*

## How to customize clustered column chart
Setelah presentasi siap, mari tambahkan dan sesuaikan diagram kolom berkelompok.

### Adding Chart to Slide
**Overview:**  
Menambahkan diagram menghidupkan data pada slide.

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Step 2: Initialize Presentation and Add Chart
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

### Managing Chart Data Workbook
**Overview:**  
Mengelola workbook data diagram secara efisien memungkinkan Anda memanipulasi series dan kategori dengan mulus.

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Step 2: Access and Clear Data Workbook
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
*Membersihkan workbook penting untuk memulai dengan lembar bersih saat menambahkan series dan kategori baru.*

### Adding Series and Categories to Chart
**Overview:**  
Langkah ini menunjukkan cara menambahkan titik data yang bermakna dengan mengelola series dan kategori.

#### Step 1: Add Series and Categories
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
*Menambahkan series dan kategori memungkinkan penyajian data yang lebih terstruktur.*

### Populating Series Data and Formatting
**Overview:**  
Isi diagram Anda dengan titik data dan format tampilan untuk meningkatkan keterbacaan, terutama saat menangani nilai negatif.

#### Step 1: Populate Series Data
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
*Bagian ini mendemonstrasikan cara mengisi data dan menerapkan pemformatan warna untuk visualisasi yang lebih baik.*

## Common Issues and Solutions
- **Memory leaks** – Selalu bungkus objek `Presentation` dalam blok `try/finally` seperti yang ditunjukkan untuk menjamin pembuangan.  
- **Incorrect cell coordinates** – Ingat bahwa baris dan kolom berindeks nol; indeks yang tidak cocok dapat menyebabkan `NullPointerException`.  
- **License not found** – Letakkan file lisensi di direktori kerja aplikasi atau tetapkan jalur secara eksplisit melalui `License.setLicense("Aspose.Slides.Java.lic")`.

## Frequently Asked Questions

**Q: Can I use this approach with .NET Core?**  
A: Yes. Aspose.Slides for Java runs on any JVM, and you can call the Java code from .NET Core using a bridge such as IKVM or JNI.

**Q: Do I need a paid license for development?**  
A: A free trial license is sufficient for development and testing. Production deployments require a purchased license.

**Q: How do I change the chart type after creation?**  
A: You can call `chart.getChartData().setChartType(ChartType.Pie)` to switch to a different chart type.

**Q: Is it possible to add data labels programmatically?**  
A: Yes. Use `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)` to display values on the chart.

**Q: What formats can I save the presentation in?**  
A: Aspose.Slides supports PPTX, PPT, PDF, XPS, and several image formats like PNG and JPEG.

---

**Last Updated:** 2026-02-06  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}