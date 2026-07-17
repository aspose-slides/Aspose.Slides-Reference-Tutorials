---
date: '2026-07-17'
description: Pelajari cara menambahkan sunburst charts di PowerPoint menggunakan Aspose
  Slides for Java. Panduan langkah demi langkah mencakup penyiapan, pembuatan chart,
  kustomisasi, dan contoh penggunaan dunia nyata.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Cara menambahkan sunburst charts di PowerPoint menggunakan Aspose
  Slides for Java. Ikuti tutorial ini untuk menyiapkan library, membuat chart, menyesuaikan
  data points, dan menerapkannya pada proyek nyata.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Cara Menambahkan Sunburst Charts di PowerPoint dengan Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Cara Menambahkan Sunburst Charts di PowerPoint dengan Aspose (Java)
url: /id/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menambahkan Diagram Sunburst di PowerPoint dengan Aspose (Java)

## Pendahuluan

Menambahkan diagram sunburst ke dalam deck PowerPoint dapat langsung mengubah tabel data datar menjadi hierarki visual yang menarik. Dalam tutorial ini Anda akan belajar **cara menambahkan sunburst** diagram di PowerPoint menggunakan Aspose.Slides untuk Java, mulai dari penyiapan lingkungan hingga penyetelan warna dan label. Baik Anda membuat dasbor penjualan, rincian tugas proyek, atau deck slide edukasi, langkah‑langkah di bawah ini akan memberikan solusi siap produksi.

**Apa yang Akan Anda Pelajari**
- Cara mengkonfigurasi Aspose.Slides dalam proyek Maven atau Gradle  
- Cara membuat presentasi baru dan menyisipkan diagram sunburst  
- Cara menyesuaikan titik data, label, dan warna isi  
- Skenario dunia nyata di mana diagram sunburst bersinar  

Mari kita mulai dan lihat betapa mudahnya mengubah data hierarki mentah menjadi visual PowerPoint yang halus.

## Jawaban Cepat
- **Perpustakaan utama?** Aspose.Slides for Java  
- **Jenis diagram yang didukung?** Sunburst (hierarki radial)  
- **Versi Java minimum?** JDK 16  
- **Waktu implementasi tipikal?** 10‑15 menit untuk diagram dasar  
- **Lisensi diperlukan untuk produksi?** Ya, lisensi Aspose yang valid  

## Apa itu Diagram Sunburst?
Diagram sunburst adalah diagram radial yang memvisualisasikan data hierarki dengan menumpuk cincin ke luar dari titik pusat. Ini sempurna untuk menampilkan hubungan multi‑level seperti struktur organisasi, kategori produk, atau pohon sistem file. Setiap cincin konsentris mewakili satu level hierarki, dan ukuran setiap segmen mencerminkan nilai kuantitatifnya, memungkinkan penonton dengan cepat memahami baik struktur maupun besarnya.

## Mengapa Menggunakan Aspose.Slides untuk Java?
Aspose.Slides mendukung **50+ jenis diagram** dan dapat memanipulasi presentasi dengan **hingga 10.000 slide** tanpa memuat seluruh file ke memori, memberikan kinerja tinggi untuk pelaporan skala perusahaan. Ia bekerja lintas‑platform, menawarkan cakupan API yang luas, dan menyertakan opsi lisensi yang kuat yang menghilangkan batas evaluasi, menjadikannya ideal untuk lingkungan produksi.

## Prasyarat
- **Java Development Kit (JDK)** 16 atau lebih baru  
- **IDE** – IntelliJ IDEA, Eclipse, atau editor kompatibel Java apa pun  
- Pemahaman dasar tentang sintaks Java dan alat build Maven/Gradle  

## Menyiapkan Aspose.Slides untuk Java

### Dependensi Maven
Add the Aspose.Slides Maven artifact to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Dependensi Gradle
If you prefer Gradle, include the following line in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduhan Langsung
You can also download the latest JAR directly from the official releases page: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Perolehan Lisensi
To run without evaluation limits, obtain a license:
- **Uji coba gratis** – lisensi sementara untuk evaluasi cepat.  
- **Lisensi sementara** – minta satu dari [situs Aspose](https://purchase.aspose.com/temporary-license).  
- **Pembelian penuh** – beli langganan untuk penggunaan produksi tak terbatas.  

### Inisialisasi Dasar
The `Presentation` class is the entry point for creating or opening PowerPoint files.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Panduan Implementasi

### Cara menambahkan diagram sunburst ke presentasi PowerPoint menggunakan Aspose.Slides untuk Java?

Load a new `Presentation`, add a slide, insert an `IChart` of type `ChartType.Sunburst`, and call `save`. This concise three‑step pattern creates a fully functional sunburst chart ready for further customization.

#### Langkah 1: Inisialisasi Presentasi
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Langkah 2: Tambahkan Diagram Sunburst
The `IChart` interface defines a chart object that can be placed on any slide. Here we add a sunburst chart at coordinates (100, 100) with a size of 450 × 400 points.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Langkah 3: Simpan Presentasi
Always persist your changes by calling `save`. You can choose PPTX, PDF, or any of the 50+ supported output formats.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Modifikasi Titik Data dalam Diagram

#### Gambaran Umum
You can tailor every slice of the sunburst—labels, colors, and visibility—through the chart’s data point collection.

#### Langkah 1: Akses Koleksi Titik Data
The first series of the chart holds a collection of `IChartDataPoint` objects that represent each slice.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Langkah 2: Tampilkan Nilai untuk Titik Data Tertentu
Set `IsValueShown` to `true` on the desired data point to display its numeric value directly on the slice.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Langkah 3: Modifikasi Format Label
Adjust label visibility, font color, and background to improve readability.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Langkah 4: Atur Warna Isi untuk Titik Data
Customize the fill color of individual slices to match your brand palette or to highlight key segments.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Langkah 5: Simpan Presentasi yang Dimodifikasi
Persist the customized chart by saving the presentation again.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Aplikasi Praktis

1. **Analitik Bisnis** – Visualisasikan penjualan berdasarkan wilayah → lini produk → SKU dalam satu tampilan radial.  
2. **Manajemen Proyek** – Tampilkan struktur rincian kerja, menelusuri dari fase ke tugas ke subtugas.  
3. **Pendidikan** – Pemetaan hierarki kurikulum, seperti departemen → mata kuliah → modul.  

## Pertimbangan Kinerja

- **Efisiensi Memori:** Aspose.Slides men-stream data, sehingga bahkan deck 500‑halaman dengan banyak diagram tetap di bawah 200 MB RAM.  
- **Pengumpulan Sampah:** Lepaskan objek slide (`slide.dispose()`) ketika tidak lagi diperlukan untuk menghindari kebocoran memori.  

## Pertanyaan yang Sering Diajukan

**Q: Apa itu diagram sunburst?**  
A: Diagram sunburst memvisualisasikan data hierarki dalam cincin konsentris, dengan setiap cincin mewakili level hierarki.

**Q: Bagaimana cara menginstal Aspose.Slides untuk Java menggunakan Maven?**  
A: Tambahkan dependensi Maven yang ditunjukkan pada bagian “Dependensi Maven” ke `pom.xml` Anda dan jalankan `mvn clean install`.

**Q: Bisakah saya menyesuaikan jenis diagram lain dengan Aspose.Slides?**  
A: Ya, perpustakaan ini mendukung lebih dari 50 jenis diagram, termasuk kolom, garis, pai, dan radar.

**Q: Presentasi saya tidak tersimpan—apa yang harus saya periksa?**  
A: Pastikan jalur file benar, direktori ada, dan Anda memiliki izin menulis. Juga, pastikan metode `Presentation.save()` dipanggil.

**Q: Di mana saya dapat mendapatkan bantuan atau contoh lebih lanjut?**  
A: Kunjungi [Aspose forum](https://forum.aspose.com/c/slides/11) atau konsultasikan [referensi resmi Aspose.Slides](https://reference.aspose.com/slides/java/).

## Sumber Daya
- **Dokumentasi:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Referensi (lowercase):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Forum Komunitas:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **Unduhan:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**Terakhir Diperbarui:** 2026-07-17  
**Diuji Dengan:** Aspose.Slides for Java 24.12  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Menambahkan Diagram ke PowerPoint Menggunakan Aspose.Slides untuk Java: Panduan Langkah demi Langkah](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animasi Diagram PowerPoint Menggunakan Aspose.Slides untuk Java – Panduan Langkah demi Langkah](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Buat diagram di Java dengan Aspose.Slides – Tambah & Validasi Diagram](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}