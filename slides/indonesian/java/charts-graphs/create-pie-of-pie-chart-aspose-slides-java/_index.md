---
date: '2026-07-17'
description: Pelajari cara menambahkan diagram ke PowerPoint dengan membuat diagram
  Pie of Pie menggunakan Aspose.Slides untuk Java. Termasuk pengaturan, kode, penyesuaian,
  dan penyimpanan sebagai PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Tambahkan diagram ke PowerPoint dengan Aspose.Slides untuk Java. Panduan
  ini menunjukkan cara membuat, menyesuaikan, dan menyimpan diagram Pie of Pie sebagai
  PPTX dalam hitungan menit.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Tambahkan Diagram ke PowerPoint – Buat Diagram Pie of Pie di Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Tambahkan Diagram ke PowerPoint – Buat Diagram Pie of Pie di Java dengan Aspose.Slides
url: /id/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tambahkan Diagram ke PowerPoint – Buat Diagram Pie of Pie di Java dengan Aspose.Slides

## Diagram & Grafik

### Pendahuluan

Dalam presentasi modern yang berbasis data, **menambahkan diagram ke PowerPoint** sering menjadi cara tercepat untuk mengubah angka mentah menjadi wawasan visual. Diagram pie standar bekerja baik untuk beberapa kategori, tetapi ketika beberapa irisan sangat kecil menjadi tidak terbaca. Diagram *Pie of Pie* menyelesaikan masalah ini dengan mengekstrak irisan kecil ke dalam pie sekunder, menjaga diagram utama tetap bersih dan detail dapat diakses.

Di tutorial ini Anda akan belajar cara **menambahkan diagram ke PowerPoint** dengan membuat diagram Pie of Pie menggunakan Aspose.Slides untuk Java. Kami akan membahas penyiapan lingkungan, pembuatan diagram, penyesuaian label, penyetelan posisi split, dan akhirnya menyimpan presentasi sebagai file PPTX. Pada akhir tutorial Anda siap menyematkan diagram canggih ke dalam slide apa pun.

## Jawaban Cepat
Di Aspose.Slides, `Presentation` mewakili file PPTX, `ChartType.PieOfPie` memilih diagram Pie of Pie, `setShowValue(true)` menampilkan nilai pada label, dan `save` menulis file.

- **Apa kelas utama untuk manipulasi PowerPoint?** `Presentation` – mewakili seluruh file PPTX dalam memori.  
- **Jenis diagram mana yang membuat pie sekunder untuk irisan kecil?** `ChartType.PieOfPie`.  
- **Bagaimana cara menampilkan nilai pada setiap irisan?** Set `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **Bisakah Anda menyimpan file langsung sebagai PPTX?** Ya – panggil `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Apakah Anda memerlukan lisensi untuk pengembangan?** Versi percobaan gratis 30‑hari cukup untuk pengujian; lisensi permanen menghapus watermark evaluasi.

## Apa Itu Diagram Pie of Pie?
**Diagram Pie of Pie** adalah visualisasi pie dua tingkat yang memisahkan satu atau lebih irisan kecil ke dalam pie terpisah yang terhubung, sehingga lebih mudah dibaca. Aspose.Slides mendukung jenis diagram ini secara bawaan, memungkinkan Anda mengontrol ukuran split, posisi, dan format label.

## Mengapa menambahkan diagram ke PowerPoint dengan Aspose.Slides?
Aspose.Slides dapat menghasilkan, mengedit, dan merender file PowerPoint tanpa perlu menginstal Microsoft Office. Ia mendukung **lebih dari 50 format input dan output**, memproses presentasi dengan **hingga 500 slide** dalam kurang dari satu detik pada perangkat keras server standar, dan menyediakan **kontrol API penuh** atas gaya diagram, label data, dan tata letak—sempurna untuk pipeline pelaporan otomatis.

## Prasyarat

- **Java Development Kit (JDK) 16+** terpasang.
- IDE seperti **IntelliJ IDEA**, **Eclipse**, atau **NetBeans**.
- Maven atau Gradle untuk manajemen dependensi (lihat bagian di bawah).
- Pengetahuan dasar Java dan familiaritas dengan pembangunan proyek.

## Menyiapkan Aspose.Slides untuk Java

### Informasi Instalasi

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Unduhan Langsung:** Anda dapat mengunduh versi terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Langkah-langkah Akuisisi Lisensi
- **Percobaan Gratis:** Mulai dengan percobaan 30‑hari untuk menjelajahi semua fitur.  
- **Lisensi Sementara:** Minta kunci sementara untuk evaluasi yang diperpanjang.  
- **Pembelian:** Dapatkan lisensi permanen untuk penggunaan produksi guna menghapus watermark evaluasi.

### Inisialisasi dan Penyiapan Dasar
`Presentation` adalah objek utama untuk membuat file PowerPoint, dan `Chart` mewakili bentuk diagram dalam sebuah slide.

```java
Presentation presentation = new Presentation();
```  

Ini membuat presentasi kosong yang siap untuk slide dan diagram.

## Panduan Implementasi

### Bagaimana cara menambahkan diagram ke PowerPoint menggunakan Aspose.Slides untuk Java?

Muat `Presentation` baru, tambahkan slide, dan sisipkan `Chart` tipe `PieOfPie`. Rantai pemanggilan API singkat: buat diagram, isi data seri, sesuaikan visibilitas label, konfigurasikan ukuran pie sekunder, dan akhirnya simpan. Seluruh proses biasanya kurang dari 20 baris kode, menjadikannya ideal untuk pembuatan laporan otomatis.

### Membuat Diagram 'Pie of Pie'

#### Ikhtisar
Kita akan membangun diagram Pie of Pie pada slide pertama, memisahkan irisan terkecil, dan memberi label setiap segmen dengan nilainya.

#### Langkah 1: Buat Instance dari Kelas Presentation
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Ini menginisialisasi kontainer untuk semua slide dan diagram selanjutnya.

#### Langkah 2: Tambahkan Diagram 'Pie of Pie' pada Slide Pertama
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Di sini kami menentukan `ChartType.PieOfPie` dan mendefinisikan posisi diagram (X, Y) serta ukuran (lebar, tinggi) pada kanvas slide.

#### Langkah 3: Atur Label Data untuk Menampilkan Nilai pada Seri
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Mengaktifkan `showValue` membuat setiap irisan menampilkan nilai numeriknya, yang penting untuk interpretasi data cepat.

#### Langkah 4: Konfigurasikan Ukuran Pie Kedua dan Split berdasarkan Persentase
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Opsi ini memungkinkan Anda menentukan berapa banyak diagram yang dialokasikan ke pie sekunder dan irisan mana yang dipindahkan berdasarkan ambang persentase.

#### Langkah 5: Simpan Presentasi ke Disk dalam Format PPTX
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Tip pro:** Gunakan path absolut atau `Paths.get()` Java untuk menghindari pemisah khusus platform.

## Masalah Umum dan Solusinya

`License` class memuat file lisensi untuk menghapus pembatasan evaluasi.

- **Peringatan lisensi hilang:** Jika Anda melihat “Evaluation Only” pada diagram, pastikan Anda telah menerapkan file lisensi yang valid melalui `License license = new License(); license.setLicense("Aspose.Slides.lic");`.
- **Split irisan tidak tepat:** Verifikasi bahwa properti `splitBy` diatur ke `SplitBy.Percentage` dan `secondPieSize` bernilai antara 0 dan 100.
- **Data tidak ditampilkan:** Pastikan seri diagram memiliki setidaknya satu titik data; jika tidak, diagram akan kosong.

## Pertanyaan yang Sering Diajukan

`IChart` mewakili objek diagram yang dapat ditambahkan ke slide.

**T: Bisakah saya menghasilkan beberapa diagram dalam satu presentasi?**  
J: Ya, buat instance `IChart` baru untuk setiap slide atau lokasi; API memungkinkan objek diagram tak terbatas per file.

`SaveFormat.Pdf` menentukan format output PDF untuk penyimpanan.

**T: Apakah Aspose.Slides mendukung penyimpanan sebagai PDF juga?**  
J: Tentu – panggil `presentation.save("output.pdf", SaveFormat.Pdf)` untuk mengekspor deck slide yang sama ke PDF.

`IPortion` mewakili irisan individual dari diagram pie.

**T: Berapa jumlah maksimum titik data yang dapat ditangani oleh diagram Pie of Pie?**  
J: Perpustakaan mendukung hingga **10.000** titik data per seri, terbatas hanya oleh memori yang tersedia.

**T: Apakah memungkinkan menyesuaikan warna irisan individual?**  
J: Ya, akses setiap `IPortion` melalui `chart.getChartData().getSeries().get_Item(0).getPortions()` dan set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**T: Bagaimana cara menyematkan PPTX yang dihasilkan ke dalam aplikasi web?**  
J: Setelah menyimpan file, alirkan langsung ke klien menggunakan `HttpServletResponse` dengan `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Kesimpulan

Anda kini memiliki resep lengkap dan siap produksi untuk **menambahkan diagram ke PowerPoint** dengan membuat diagram Pie of Pie menggunakan Aspose.Slides untuk Java. Bereksperimenlah dengan ambang split yang berbeda, format label, dan skema warna untuk menyesuaikan pedoman merek Anda. Selanjutnya, jelajahi jenis diagram lain—seperti bar bertumpuk atau radar—untuk memperkaya deck slide otomatis Anda.

---

**Terakhir Diperbarui:** 2026-07-17  
**Diuji Dengan:** Aspose.Slides for Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Diagram Dinamis Java – Tutorial Diagram PowerPoint untuk Aspose.Slides](/slides/java/charts-graphs/)
- [Cara menambahkan diagram pie PowerPoint dengan Aspose.Slides untuk Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Cara Menambahkan Diagram ke PowerPoint Menggunakan Aspose.Slides untuk Java: Panduan Langkah‑per‑Langkah](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}