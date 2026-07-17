---
date: '2026-07-17'
description: Pelajari cara memutar pie chart, menyesuaikan warna pie chart, dan mengekspor
  slide ke PDF menggunakan Aspose.Slides for Java – panduan visualisasi data lengkap.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Putar pie chart dan menyesuaikan warna pie chart menggunakan Aspose.Slides
  for Java. Pelajari cara mengekspor slide ke PDF dan bekerja dengan chart data worksheet.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Putar Pie Chart dan Menyesuaikan Warna di Java – Panduan Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Cara Memutar Pie Chart dan Menyesuaikan Warna di Java dengan Aspose.Slides
url: /id/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat Diagram Pai dengan Aspose.Slides untuk Java: Tutorial Lengkap

## Pendahuluan
Dalam panduan ini Anda akan belajar cara **rotate pie chart** elemen, menyesuaikan warna tiap irisan, dan mengekspor slide akhir ke PDF—semua dengan Aspose.Slides untuk Java. Baik Anda membangun dasbor penjualan, laporan keuangan, atau presentasi berbasis data apa pun, menguasai teknik ini memungkinkan Anda menyajikan visual yang jelas dan menarik tanpa bergantung pada Microsoft Office. Mari siapkan alatnya dan mulai.

## Jawaban Cepat
- **Kelas apa yang memulai presentasi baru?** `Presentation` dari `com.aspose.slides`.
- **Panggilan API mana yang menambahkan diagram pai?** `slide.addChart(ChartType.Pie, …)`.
- **Bagaimana cara memberi setiap irisan warna unik?** Panggil `series.setColorVaried(true)` dan atur isian solid per titik data.
- **Metode apa yang memutar diagram?** `chart.setRotationAngle(double)` – gunakan derajat dari 0 hingga 360.
- **Apakah slide dapat diekspor ke PDF?** Ya, panggil `presentation.save("output.pdf", SaveFormat.Pdf)`.

## Apa itu “customize pie chart colors”?
Menyesuaikan warna diagram pai berarti memberikan warna isian yang berbeda untuk setiap irisan pai, meningkatkan keterbacaan dan dampak visual. Di Aspose.Slides Anda melakukannya dengan mengaktifkan warna beragam dan kemudian mengatur warna isian solid untuk masing‑masing titik data. Pendekatan ini memastikan setiap segmen data terlihat jelas dalam presentasi.

## Mengapa menggunakan Aspose.Slides untuk Java untuk membuat diagram pai?
Aspose.Slides mendukung **lebih dari 150 jenis diagram** dan dapat merender presentasi 300 halaman dalam waktu kurang dari **5 detik** pada server standar, tanpa memerlukan Microsoft Office terpasang. Perpustakaan ini berjalan di Windows, Linux, dan macOS, memberi Anda fleksibilitas lintas‑platform untuk proyek visualisasi data berbasis Java apa pun.

## Prasyarat
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 atau lebih baru
- IDE seperti IntelliJ IDEA, Eclipse, atau NetBeans
- Pengetahuan dasar Java dan familiar dengan Maven atau Gradle

## Menyiapkan Aspose.Slides untuk Java
Tambahkan perpustakaan ke konfigurasi build Anda.

**Maven**  
Tambahkan potongan ini ke file `pom.xml` Anda:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Sertakan yang berikut dalam file `build.gradle` Anda:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Unduhan Langsung**  
Jika Anda lebih suka pendekatan manual, unduh JAR terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Langkah-langkah Akuisisi Lisensi
- **Free Trial** – explore all features without cost.  
- **Temporary License** – extend trial limits for a short period.  
- **Purchase** – obtain a permanent license for production use.

**Basic Initialization and Setup**  
Kelas `Presentation` mewakili file PowerPoint dalam memori dan menyediakan metode untuk memanipulasi slide.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Panduan Implementasi
Berikut adalah langkah‑demi‑langkah yang mencakup semua mulai dari membuat slide hingga memutar diagram pai akhir.

### Inisialisasi Presentasi dan Slide
Buat instance `Presentation` baru dan ambil slide pertama sebagai kanvas diagram.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Tambahkan Diagram Pai ke Slide
`addChart` menambahkan bentuk diagram dengan tipe yang ditentukan ke slide pada koordinat yang diberikan.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Atur Judul Diagram
`setTitle` menetapkan judul teks ke diagram dan memposisikannya secara sentral.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Konfigurasi Label Data untuk Seri
`setShowValue(true)` mengaktifkan label nilai numerik pada tiap titik data seri.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Siapkan Worksheet Data Diagram
`ChartDataWorkbook` menyimpan tabel data dasar yang memberi makan seri dan kategori diagram.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Tambahkan Kategori ke Diagram
`addCategory` membuat label kategori baru untuk seri data diagram.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Tambahkan Seri dan Isi Titik Data
`addSeries` membuat seri data, dan `addDataPointForBarSeries` menyisipkan nilai numerik untuk tiap kategori.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Sesuaikan Warna dan Garis Batas Seri
`setColorVaried(true)` mengaktifkan warna per‑irisan, dan `setFillFormat` menetapkan isian solid ke tiap titik data.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Konfigurasi Label Data Kustom
`setDataLabelFormat` menyesuaikan tampilan label, posisi, dan font untuk anotasi diagram yang lebih jelas.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Atur Sudut Rotasi dan Simpan Presentasi
`setRotationAngle` memutar seluruh diagram pai, dan `save` menulis presentasi ke file.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Cara memutar diagram pai?
Muat objek diagram, panggil `chart.setRotationAngle(45.0)` (atau nilai derajat lain), lalu simpan presentasi. Memutar diagram pai menggeser sudut awal, memungkinkan Anda menekankan segmen tertentu tanpa mengubah data. Metode tunggal ini bekerja untuk setiap instance `Chart` di Aspose.Slides. Anda juga dapat menggabungkan rotasi dengan warna irisan beragam untuk menyorot poin data terpenting.

## Masalah Umum dan Solusinya
| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **Semua irisan muncul dengan warna yang sama** | `setColorVaried(true)` tidak dipanggil | Pastikan Anda mengaktifkan warna beragam pada grup seri. |
| **Label data tidak muncul** | `showValue` flag dinonaktifkan | Panggil `setShowValue(true)` pada format label. |
| **Rotasi tidak berpengaruh** | Menggunakan versi Aspose.Slides yang lebih lama | Tingkatkan ke versi 25.4 atau yang lebih baru. |
| **Pengecualian lisensi saat runtime** | File lisensi tidak ada atau tidak valid | Muat lisensi Anda dengan `License license = new License(); license.setLicense("Aspose.Slides.lic");` sebelum membuat `Presentation`. |

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana cara saya mendapatkan lisensi Aspose.Slides untuk Java?**  
A: Minta uji coba gratis dari situs Aspose, kemudian beli lisensi permanen. Muat lisensi tersebut saat runtime seperti yang ditunjukkan pada tabel Masalah Umum.

**Q: Bisakah saya menggunakan kode ini dengan versi JDK yang lebih lama?**  
A: API memerlukan JDK 16 atau lebih tinggi; versi yang lebih lama tidak didukung.

**Q: Apakah memungkinkan mengekspor diagram sebagai gambar alih-alih PPTX?**  
A: Ya—setelah rendering, panggil `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**Q: Bagaimana jika saya membutuhkan lebih dari satu seri dalam diagram pai?**  
A: Diagram pai dirancang untuk satu seri data; untuk beberapa seri, pertimbangkan menggunakan diagram donat.

**Q: Apakah Aspose.Slides berjalan di server Linux?**  
A: Tentu—Aspose.Slides untuk Java bersifat platform‑independen dan bekerja pada OS apa pun dengan JDK yang kompatibel.

**Terakhir Diperbarui:** 2026-07-17  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (JDK 16)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Membuat Diagram Pai dalam Presentasi Java Menggunakan Aspose.Slides: Panduan Komprehensif](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Menguasai Diagram Pai di Java Menggunakan Aspose.Slides: Panduan Komprehensif](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Memutar Teks Diagram di Java dengan Aspose.Slides: Panduan Komprehensif](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}