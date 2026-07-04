---
date: '2026-03-23'
description: Pelajari cara menggunakan Aspose.Slides for Java untuk membuat diagram
  garis dengan penanda, menambahkan seri kedua, dan menangani data null dalam presentasi
  PowerPoint.
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 'Cara Menggunakan Aspose.Slides untuk Java: Membuat Diagram Garis dengan Penanda
  Default'
url: /id/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Buat Diagram Garis dengan Penanda Default Menggunakan Aspose.Slides untuk Java

## Introduction
Jika Anda bertanya-tanya **cara menggunakan Aspose** untuk mengotomatiskan pembuatan PowerPoint, Anda berada di tempat yang tepat. Pada tutorial ini kami akan membahas cara membuat **diagram garis dengan penanda**, menambahkan seri kedua, dan menangani data null—semua dengan Aspose.Slides untuk Java. Pada akhir tutorial Anda akan memiliki potongan kode siap‑jalankan yang menghasilkan diagram tampak profesional tanpa pernah membuka PowerPoint secara manual.

### Quick Answers
- **Perpustakaan apa yang saya butuhkan?** Aspose.Slides untuk Java (versi terbaru disarankan)  
- **Bisakah saya menambahkan seri kedua?** Ya – API memungkinkan Anda menambahkan beberapa seri dengan mudah.  
- **Bagaimana data null ditangani?** Gunakan `null` pada nilai sel; diagram akan melewatkan titik tersebut.  
- **Apakah saya memerlukan Maven?** Maven atau Gradle dapat digunakan; lihat bagian *aspose slides maven* di bawah.  
- **Apakah lisensi diperlukan?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.

## How to Use Aspose.Slides for Java to Create Line Charts
Membuat diagram secara programatik menghemat berjam‑jam pemformatan manual dan menjamin konsistensi di seluruh presentasi. Baik Anda membangun fitur **create powerpoint chart** dalam alat pelaporan atau menghasilkan deck slide secara dinamis, Aspose.Slides memberi Anda kontrol penuh dari kode Java.

## Prerequisites
Sebelum memulai, pastikan lingkungan pengembangan Anda siap:

1. **Libraries & Dependencies**
   - Perpustakaan Aspose.Slides untuk Java (versi 25.4 disarankan) – mencakup skenario *aspose slides maven*.
   - Java Development Kit (JDK) versi 16 atau lebih tinggi.
2. **Environment Setup**
   - IDE dengan dukungan Maven atau Gradle.
   - File lisensi Aspose yang valid jika Anda berencana menjalankan kode di luar masa percobaan.
3. **Knowledge Prerequisites**
   - Pemrograman Java dasar.
   - Familiaritas dengan file build Maven atau Gradle.

## Setting Up Aspose.Slides for Java
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
### Direct Download
Sebagai alternatif, Anda dapat mengunduh versi terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**License Acquisition Steps:**
- Untuk percobaan gratis, kunjungi [free trial page](https://releases.aspose.com/slides/java/).
- Untuk memperoleh lisensi sementara, buka [temporary license page](https://purchase.aspose.com/temporary-license/).
- Beli lisensi penuh melalui [purchase portal](https://purchase.aspose.com/buy).

**Basic Initialization:**
Berikut cara menginisialisasi Aspose.Slides dalam aplikasi Java Anda:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

Sekarang, mari kita mulai membuat diagram!

## Implementation Guide
### Feature 1: Chart Creation with Default Markers
Bagian ini menunjukkan cara membuat **diagram garis dengan penanda**, yang ideal untuk menyoroti titik data individu pada garis tren.

#### Adding a Line Chart
Untuk menambahkan diagram garis dengan penanda:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### Clearing Series and Categories
Untuk memulai dari awal:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### Feature 2: Adding Series and Categories
Menambahkan seri dan kategori sangat penting untuk mengisi diagram Anda dengan data yang bermakna.

#### Creating a New Series
Untuk menambahkan seri baru bernama "Series 1":
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Populating Categories and Data Points
Untuk menambahkan kategori dan titik data yang bersesuaian:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### Feature 3: Adding Second Series and Populating Data Points
Menambahkan seri tambahan memberikan kedalaman lebih pada analisis visual Anda.

#### Creating and Populating a Second Series
Untuk menambahkan "Series 2":
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### Feature 4: Configuring Chart Legend
Mengonfigurasi legenda meningkatkan keterbacaan diagram, terutama ketika Anda **add second series**.

#### Adjusting Legend Settings
Untuk mengonfigurasi:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### Feature 5: Saving the Presentation
Setelah diagram Anda siap, Anda ingin **create powerpoint chart** yang dapat dibagikan atau diedit lebih lanjut.

```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## Practical Applications
1. **Business Reporting:** Gunakan diagram garis dengan penanda untuk menggambarkan tren keuangan per kuartal.  
2. **Data Analysis:** Visualisasikan data eksperimen di mana setiap penanda menyoroti titik pengukuran.  
3. **Educational Materials:** Buat slide kuliah yang menampilkan perubahan langkah‑demi‑langkah dalam suatu proses.  
4. **Project Management:** Lacak tonggak proyek pada garis waktu dengan penanda khusus untuk tanggal penting.  
5. **Marketing Presentations:** Tampilkan lonjakan kinerja kampanye dengan simbol penanda yang jelas.

## Common Issues and Solutions
- **Null data points cause errors:** Kirim `null` sebagai nilai sel (seperti yang ditunjukkan) – Aspose akan mengabaikan titik tersebut.  
- **Chart appears without markers:** Pastikan Anda menggunakan `ChartType.LineWithMarkers` bukan `ChartType.Line`.  
- **Legend overlaps data:** Atur `chart.getLegend().setOverlay(false)` agar legenda terpisah dari data.  

## Frequently Asked Questions

**Q: Can I use this approach to generate charts in a web service?**  
A: Tentu saja. Perpustakaan ini bekerja di lingkungan Java apa pun, termasuk aplikasi sisi server.

**Q: Do I need a license for development builds?**  
A: Versi percobaan gratis dapat digunakan untuk pengembangan dan pengujian. Lisensi komersial diperlukan untuk penggunaan produksi.

**Q: How does Aspose handle large datasets?**  
A: API memproses data secara efisien; namun, tetap jaga jumlah titik data agar tidak terlalu besar sehingga ukuran file tidak membengkak.

**Q: Is there support for other chart types?**  
A: Ya – Aspose.Slides mendukung bar, pie, scatter, dan banyak jenis diagram lainnya.

**Q: Can I customize marker shapes and colors?**  
A: Anda dapat memodifikasi format penanda melalui properti `Marker` pada setiap titik data.

## Conclusion
Anda kini tahu **cara menggunakan Aspose** untuk membuat diagram garis dengan penanda default, menambahkan seri kedua, menangani data null, dan menyimpan hasilnya sebagai file PowerPoint. Teknik ini memungkinkan Anda mengotomatisasi pembuatan laporan, meningkatkan narasi data, dan menjaga konsistensi presentasi.

Untuk pendalaman lebih lanjut, jelajahi [official documentation](https://docs.aspose.com/slides/java/) atau bergabung dengan forum komunitas seperti Stack Overflow.

---

**Last Updated:** 2026-03-23  
**Tested With:** Aspose.Slides untuk Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}