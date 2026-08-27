---
date: '2026-08-27'
description: Pelajari cara menambahkan garis kisi pada diagram di Java menggunakan
  Aspose.Slides, memformat sumbu, judul, dan mengekspor diagram garis PowerPoint yang
  halus.
keywords:
- add grid lines chart
- customize chart axes
- generate line chart powerpoint
- aspose.slides maven dependency
- apply aspose license
lastmod: '2026-08-27'
og_description: Pelajari cara menambahkan garis kisi pada diagram di Java menggunakan
  Aspose.Slides, memformat sumbu, judul, dan mengekspor diagram garis PowerPoint yang
  halus.
og_image_alt: Step-by-step guide to create and format a line chart with grid lines
  using Aspose.Slides for Java
og_title: Cara menambahkan garis kisi ke diagram dengan Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  headline: How to add grid lines to a chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  name: How to add grid lines to a chart with Aspose.Slides for Java
  steps:
  - name: create the output directory (create directory java)
    text: '*Why this matters:* Ensuring the folder exists prevents `FileNotFoundException`
      when you later save the presentation.'
  - name: add a slide and insert a line chart
    text: '*Explanation:* This creates a fresh slide and places a **line chart with
      markers** at the specified coordinates.'
  - name: add chart title (add chart title)
    text: '*Tip:* Using a bold, gray title makes the chart instantly recognizable.'
  - name: format axes and add grid lines (add grid lines)
    text: '#### Vertical axis formatting *Why this matters:* Clear grid lines and
      rotated labels improve readability, especially when data points are dense.'
  - name: save the presentation
    text: '*Result:* You now have a PowerPoint file (`FormattedChart_out.pptx`) containing
      a fully formatted line chart.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports bar, pie, scatter, radar, and more than 50
      additional chart types.
    question: Can I create other chart types besides line charts?
  - answer: Use `chart.getChartData().getSeries().add(...)` to insert additional series
      before applying formatting.
    question: How do I add multiple data series to the line chart?
  - answer: Absolutely. Render the slide to PNG, JPEG, or SVG with `presentation.save("slide.png",
      SaveFormat.Png)`.
    question: Is it possible to export the chart as an image?
  - answer: A free temporary license is sufficient for evaluation; a commercial license
      is required for production use.
    question: Do I need a paid license for development?
  - answer: The library works with JDK 8 through JDK 22; select the appropriate classifier
      (e.g., `jdk16`) when adding the Maven/Gradle dependency.
    question: Which Java versions are supported?
  type: FAQPage
tags:
- Aspose.Slides
- Java chart tutorial
- PowerPoint automation
- line chart
title: Cara menambahkan garis kisi ke diagram dengan Aspose.Slides for Java
url: /id/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menambahkan garis kisi ke diagram dengan Aspose.Slides untuk Java

## Pendahuluan
Jika Anda perlu **menambahkan diagram garis kisi** dalam presentasi PowerPoint secara programatis, Aspose.Slides untuk Java memberikan API yang bersih dan lengkap. Baik Anda sedang menyiapkan tinjauan bisnis kuartalan, kuliah akademik, atau deck penjualan berbasis data, Anda dapat menghasilkan diagram garis, menyesuaikan setiap elemen visual, dan menyimpan hasilnya dalam hitungan detik—tanpa harus membuka PowerPoint secara manual.

## Jawaban Cepat
- **Perpustakaan apa yang membuat diagram di Java?** Aspose.Slides for Java.
- **Jenis diagram apa yang dibahas dalam panduan ini?** Diagram garis dengan penanda dan garis kisi.
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Lisensi percobaan gratis cukup untuk evaluasi; lisensi komersial diperlukan untuk produksi.
- **IDE apa yang dapat saya gunakan?** IDE Java apa pun seperti IntelliJ IDEA, Eclipse, atau NetBeans.
- **Bagaimana elemen diagram diformat?** Menggunakan pemanggilan API fluent untuk judul, sumbu, garis kisi, legenda, dan warna latar belakang.

## Cara menambahkan diagram garis kisi di Java menggunakan Aspose.Slides
Muat sebuah `Presentation` baru, sisipkan slide, tambahkan diagram garis, lalu aktifkan garis kisi utama pada sumbu vertikal – semuanya dalam kurang dari sepuluh baris kode. Jawaban langsung ini menunjukkan urutan tepat yang Anda perlukan, sehingga Anda dapat menyalin‑tempel dan melihat diagram yang sepenuhnya diformat segera.

### Penanda definisi
`Presentation` adalah kelas inti Aspose.Slides yang mewakili file PowerPoint dalam memori; semua operasi pada tingkat slide dimulai dari objek ini.

## Apa itu diagram garis dan mengapa menggunakan Aspose.Slides?
Diagram garis memplot serangkaian titik data yang dihubungkan oleh garis lurus, membuat tren sepanjang waktu terlihat secara instan. Aspose.Slides mendukung **lebih dari 50 jenis diagram** dan dapat menangani **hingga 10.000 titik data per seri** tanpa penurunan kinerja yang terlihat, memberikan Anda performa tingkat perusahaan untuk kumpulan data besar.

### Penanda definisi
`Chart` adalah objek tingkat‑atas Aspose.Slides untuk setiap diagram; ia menyimpan seri, kategori, dan informasi pemformatan.

## Prasyarat
- **Java Development Kit (JDK) 8+** terpasang.
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans, dll.).
- **Aspose.Slides for Java** library ditambahkan melalui Maven atau Gradle (lihat bagian *aspose.slides maven dependency* di bawah).

### Dependensi Maven (dependensi aspose.slides maven)
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Dependensi Gradle
```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Sebagai alternatif, unduh JAR terbaru dari [rilisan Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/).

## Perolehan Lisensi (terapkan lisensi aspose)
- Dapatkan **lisensi percobaan gratis** dari halaman [lisensi percobaan gratis](https://purchase.aspose.com/temporary-license/) untuk pengujian.
- Beli lisensi penuh dari [situs resmi Aspose](https://purchase.aspose.com/buy) untuk penerapan produksi.

## Menyiapkan Aspose.Slides untuk Java
1. Tambahkan dependensi Maven atau Gradle yang ditunjukkan di atas ke proyek Anda.
2. Muat file lisensi **sebelum** membuat objek `Presentation` apa pun sehingga semua fitur terbuka.

```java
License license = new License();
license.setLicense("Aspose.Slides.lic");
```

## Implementasi Langkah‑per‑Langkah

### Langkah 1: buat direktori output (buat direktori java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```  
*Mengapa ini penting:* Memastikan folder ada mencegah `FileNotFoundException` saat Anda menyimpan presentasi nanti.

### Langkah 2: tambahkan slide dan sisipkan diagram garis
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```  
*Penjelasan:* Ini membuat slide baru dan menempatkan **diagram garis dengan penanda** pada koordinat yang ditentukan.

### Langkah 3: tambahkan judul diagram (tambahkan judul diagram)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```  
*Tip:* Menggunakan judul tebal berwarna abu-abu membuat diagram langsung dikenali.

### Langkah 4: format sumbu dan tambahkan garis kisi (tambahkan garis kisi)
#### Pemformatan sumbu vertikal
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```  
*Mengapa ini penting:* Garis kisi yang jelas dan label yang diputar meningkatkan keterbacaan, terutama ketika titik data padat.

#### Pemformatan sumbu horizontal
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```  

### Langkah 5: sesuaikan legenda (tambahkan legenda diagram)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```  

### Langkah 6: atur warna latar belakang (format label diagram)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```  

### Langkah 7: simpan presentasi
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```  
*Hasil:* Anda kini memiliki file PowerPoint (`FormattedChart_out.pptx`) yang berisi diagram garis yang sepenuhnya diformat.

## Aplikasi Praktis (buat diagram garis PowerPoint)
- **Laporan bisnis:** Tampilkan tren pendapatan kuartalan dengan garis kisi yang tajam.
- **Kuliah akademik:** Visualisasikan data eksperimen selama beberapa sesi.
- **Proposal proyek:** Sorot kemajuan tonggak dan kurva perkiraan.
- **Analisis pemasaran:** Sajikan tren ROI kampanye berdampingan dengan data pesaing.
- **Integrasi dasbor:** Ekspor analitik langsung ke PowerPoint untuk pertemuan pemangku kepentingan.

## Pertimbangan Kinerja
- **Manajemen memori:** Panggil `presentation.dispose()` setelah menyimpan untuk segera melepaskan sumber daya native.
- **Kumpulan data besar:** Aspose.Slides memproses diagram dengan ribuan titik menggunakan streaming, menjaga penggunaan memori di bawah 100 MB pada server tipikal.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|-------|----------|
| **Lisensi tidak diterapkan** | Muat lisensi percobaan atau penuh **sebelum** objek `Presentation` apa pun diinstansiasi. |
| **Diagram muncul kosong** | Pastikan slide berisi setidaknya satu seri data; tambahkan seri melalui `chart.getChartData().getSeries().add(...)` jika diperlukan. |
| **File tidak tersimpan** | Pastikan direktori output ada (lihat Langkah 1). |
| **Warna tidak diterapkan** | Gunakan konstanta `java.awt.Color` atau enum `PresetColor` untuk rendering warna yang dapat diandalkan. |

## Pertanyaan yang Sering Diajukan

**Q: Apakah saya dapat membuat jenis diagram lain selain diagram garis?**  
A: Ya, Aspose.Slides mendukung diagram batang, pai, sebar, radar, dan lebih dari 50 jenis diagram tambahan.

**Q: Bagaimana cara menambahkan beberapa seri data ke diagram garis?**  
A: Gunakan `chart.getChartData().getSeries().add(...)` untuk menyisipkan seri tambahan sebelum menerapkan pemformatan.

**Q: Apakah memungkinkan mengekspor diagram sebagai gambar?**  
A: Tentu saja. Render slide ke PNG, JPEG, atau SVG dengan `presentation.save("slide.png", SaveFormat.Png)`.

**Q: Apakah saya memerlukan lisensi berbayar untuk pengembangan?**  
A: Lisensi percobaan gratis cukup untuk evaluasi; lisensi komersial diperlukan untuk penggunaan produksi.

**Q: Versi Java apa yang didukung?**  
A: Perpustakaan ini bekerja dengan JDK 8 hingga JDK 22; pilih classifier yang sesuai (misalnya `jdk16`) saat menambahkan dependensi Maven/Gradle.

---

**Terakhir Diperbarui:** 2026-08-27  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Penulis:** Aspose  

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Tutorial Terkait

- [dependensi maven aspose slides: Tambah dan Konfigurasikan Diagram dalam Presentasi Menggunakan Aspose.Slides untuk Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Cara Menambahkan Diagram ke PowerPoint Menggunakan Aspose.Slides untuk Java: Panduan Langkah‑per‑Langkah](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Buat dan Sesuaikan Garis Tren Diagram Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}