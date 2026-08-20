---
date: '2026-07-27'
description: Cara menyesuaikan diagram menggunakan Aspose.Slides for Java. Pelajari
  cara membuat diagram PowerPoint, menata seri scatter, dan menyimpan presentasi secara
  efisien.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Cara menyesuaikan diagram dengan Aspose.Slides for Java. Panduan ini
  menunjukkan cara membuat diagram PowerPoint, menata titik scatter, dan mengekspor
  presentasi.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Cara Menyesuaikan Diagram: Scatter Chart Aspose di Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Cara Menyesuaikan Diagram: Scatter Chart Aspose di Java'
url: /id/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Sesuaikan Diagram Sebar Aspose di Java

Dalam tutorial ini Anda akan menemukan **cara menyesuaikan diagram** — khususnya diagram sebar — menggunakan pustaka Aspose.Slides untuk Java yang kuat. Kami akan membahas penyiapan proyek, membuat diagram sebar, menyesuaikan tipe seri dan penanda, serta akhirnya menyimpan presentasi. Pada akhir tutorial, Anda akan dapat menghasilkan diagram sebar dengan tampilan profesional secara programatik dan menyesuaikan setiap detail visual agar sesuai dengan merek atau kebutuhan pelaporan Anda.

## Jawaban Cepat
- **Perpustakaan apa yang saya butuhkan?** Aspose.Slides for Java (v25.4+).  
- **Versi Java mana yang didukung?** JDK 8 atau lebih tinggi.  
- **Bisakah saya mengubah bentuk penanda?** Ya – gunakan `MarkerStyleType` untuk memilih bintang, lingkaran, dll.  
- **Bagaimana cara menyimpan file?** Panggil `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Apakah lisensi diperlukan?** Uji coba gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.

## Cara Menyesuaikan Diagram di Java dengan Aspose.Slides?
`Presentation` adalah kelas Aspose.Slides yang mewakili seluruh file PowerPoint dalam memori. Muat `Presentation` baru, tambahkan diagram sebar pada slide pertama, konfigurasikan seri dan gaya penanda, lalu panggil `save`. Alur kerja tunggal itu membuat diagram yang sepenuhnya bergaya hanya dalam beberapa baris kode Java, siap untuk dimasukkan ke dalam presentasi PowerPoint apa pun.

## Apa itu “customize scatter chart aspose”?
Menyesuaikan diagram sebar dengan Aspose berarti mendefinisikan data, tampilan, dan perilaku diagram secara programatik—semua mulai dari koordinat titik hingga simbol penanda—tanpa membuka PowerPoint secara manual. Pendekatan ini ideal untuk pelaporan otomatis, presentasi berbasis data, atau skenario apa pun yang memerlukan visualisasi berulang dengan kualitas tinggi.

## Mengapa menyesuaikan diagram sebar dengan Aspose.Slides?
Aspose.Slides memberikan pengembang kontrol programatik penuh atas tampilan diagram, memungkinkan pembuatan visualisasi berkualitas tinggi secara otomatis, integrasi mulus ke dalam alur pelaporan, dan kemampuan menyesuaikan setiap elemen visual tanpa membuka PowerPoint secara manual, yang menghemat waktu dan memastikan konsistensi di seluruh presentasi.

- **Kontrol penuh** – ubah tipe seri, gaya penanda, warna, dan lain-lain melalui kode Java.  
- **Otomasi** – hasilkan puluhan diagram secara dinamis untuk dasbor atau laporan batch.  
- **Lintas‑platform** – berfungsi pada sistem operasi apa pun yang mendukung Java, tanpa memerlukan instalasi Office.  
- **Kinerja** – API ringan yang memproses **150+ tipe diagram** dan menangani presentasi ratusan halaman tanpa memuat seluruh file ke memori.

## Prasyarat

Untuk mengikuti tutorial ini, pastikan Anda memiliki:

- **Aspose.Slides for Java** (v25.4 atau lebih baru).  
- **Java Development Kit (JDK)** 8 + terpasang.  
- Maven atau Gradle untuk manajemen dependensi (atau Anda dapat mengunduh JAR secara manual).  
- Pengetahuan dasar Java dan familiaritas dengan alat build pilihan Anda.

## Menyiapkan Aspose.Slides untuk Java

Integrasikan pustaka ke dalam proyek Anda menggunakan salah satu metode di bawah ini.

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

Atau dapatkan rilis terbaru dari [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Perolehan Lisensi
- **Uji Coba Gratis** – evaluasi 30‑hari.  
- **Lisensi Sementara** – periode pengujian yang diperpanjang.  
- **Lisensi Penuh** – penggunaan produksi dengan dukungan premium.

## Panduan Langkah‑demi‑Langkah untuk Menyesuaikan Diagram Sebar Aspose

### 1️⃣ Siapkan folder untuk file presentasi Anda
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*Mengapa ini penting:* Memastikan folder output ada mencegah `FileNotFoundException` saat Anda menyimpan PPTX nanti.

### 2️⃣ Buat presentasi baru dan ambil slide pertama
`Presentation` mewakili dokumen PowerPoint dan menyediakan akses ke slide serta bentuk. Kelas `Presentation` mewakili seluruh file PowerPoint dalam memori.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Tambahkan diagram sebar dengan garis halus
`ChartType.ScatterWithSmoothLines` membuat diagram sebar di mana titik-titik dihubungkan dengan garis halus.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Bersihkan semua seri default dan tambahkan milik Anda
`IChartSeries` mewakili seri data dalam sebuah diagram.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ Isi seri pertama dengan titik data
`addDataPointForScatterSeries` menambahkan satu titik X‑Y ke seri sebar.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Sesuaikan tipe seri dan tampilan penanda
`Marker` mengontrol simbol visual yang digunakan untuk setiap titik data dalam seri diagram.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ Simpan presentasi
`save` menulis presentasi ke file dalam format yang ditentukan.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Kasus Penggunaan Umum untuk Diagram Sebar yang Disesuaikan
- **Dasbor Keuangan** – plot harga saham vs. volume.  
- **Penelitian Ilmiah** – tampilkan pengukuran eksperimental dengan penanda kesalahan.  
- **Manajemen Proyek** – bandingkan upaya yang direncanakan vs. aktual pada setiap tugas.  

## Tips Kinerja
- Panggil `pres.dispose()` setelah menyimpan untuk melepaskan memori native.  
- Untuk set data besar, isi workbook terlebih dahulu lalu hubungkan seri untuk menghindari penyegaran UI berulang.  
- Gunakan kembali satu instance `IChartDataWorkbook` saat menambahkan banyak seri untuk menjaga penggunaan memori tetap rendah.

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana cara mengubah warna penanda?**  
A: Gunakan `series.getMarker().getFillFormat().setFillColor(Color)` dimana `Color` adalah instance `java.awt.Color` seperti `Color.RED`.

**Q: Bisakah saya menambahkan lebih dari dua seri ke diagram sebar?**  
A: Ya. Panggil `chart.getChartData().getSeries().add(...)` untuk setiap seri tambahan dan isi titiknya sesuai.

**Q: Apakah memungkinkan untuk mengatur legenda khusus untuk setiap seri?**  
A: Tentu saja. Setelah membuat seri, panggil `series.getLegend().setText("Your Legend Text")` untuk mengganti nama default.

**Q: Bagaimana saya dapat mengekspor diagram sebagai gambar alih-alih PPTX?**  
A: Panggil `chart.getImage().save("chart.png", ImageFormat.Png)` setelah mengonfigurasi diagram. Ini menghasilkan file PNG terpisah.

**Q: Bagaimana jika saya perlu memberi animasi pada titik sebar?**  
A: Aspose.Slides mendukung efek animasi. Gunakan `chart.getTimeline().getMainSequence().addEffect(...)` untuk menambahkan animasi masuk atau penekanan pada diagram atau seri individual.

---

**Terakhir Diperbarui:** 2026-07-27  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Buat dan Sesuaikan Diagram PowerPoint di Java Menggunakan Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Cara Membuat Diagram Bubble di PowerPoint Menggunakan Aspose.Slides untuk Java (Tutorial)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Buat dan Sesuaikan Diagram dengan Garis Tren di Aspose.Slides untuk Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}