---
date: '2026-09-12'
description: Pelajari cara menggunakan Maven Aspose Slides untuk menambahkan dan menyesuaikan
  grafik saham dinamis di PowerPoint dengan Java. Includes setup, penambahan data
  series, formatting lines, dan penyimpanan.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Tutorial Maven Aspose Slides menunjukkan cara membuat dan menyesuaikan
  grafik saham dinamis di PowerPoint menggunakan Java, mencakup data series, formatting
  lines, dan penyimpanan.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Panduan Maven Aspose Slides: buat grafik saham dinamis di PowerPoint'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: buat grafik saham dinamis di PowerPoint dengan Java'
url: /id/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: buat grafik saham dinamis di PowerPoint dengan Java

## Pendahuluan

**Maven Aspose Slides** memungkinkan Anda menghasilkan presentasi PowerPoint yang canggih secara programatis dari Java. Dalam tutorial ini Anda akan belajar cara membuat grafik saham dinamis, menambahkan dan memformat seri data, menyesuaikan garis grafik, dan akhirnya menyimpan file. Baik Anda seorang analis keuangan yang menyiapkan laporan triwulanan atau pengembang yang membangun deck slide otomatis, langkah‑langkah di bawah ini memberikan solusi lengkap yang siap produksi.

**Apa yang akan Anda pelajari**
- Cara menyiapkan Maven dengan Aspose.Slides untuk Java  
- Cara menambahkan grafik saham dan menghapus data default  
- Cara **menambahkan seri data grafik** dan **memformat garis grafik**  
- Cara **menyesuaikan elemen visual khusus java** pada grafik  
- Cara menyimpan presentasi yang telah diperbarui

Siap mengubah angka mentah menjadi visual saham yang menarik? Mari kita mulai!

## Jawaban Cepat
- **Artefak Maven mana yang saya perlukan?** `aspose-slides` versi 25.4 (atau lebih baru).  
- **Apakah saya dapat menjalankannya di sistem operasi apa pun?** Ya – perpustakaan ini murni Java dan berfungsi di Windows, macOS, dan Linux.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi percobaan gratis cukup untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Jenis grafik apa yang didukung?** Lebih dari 70 jenis grafik bawaan, termasuk Stock, Line, dan Bar.  
- **Seberapa besar presentasi yang dapat saya proses?** Aspose.Slides dapat menangani file dengan 500+ slide tanpa memuat seluruh file ke memori.

## Apa itu Maven Aspose Slides?

`Aspose.Slides for Java` adalah API Java yang memungkinkan pembuatan, manipulasi, dan konversi file PowerPoint tanpa Microsoft Office. Integrasi Maven menyederhanakan manajemen dependensi, memungkinkan Anda menarik perpustakaan langsung dari Maven Central.

## Mengapa menggunakan Maven Aspose Slides untuk grafik saham?

Aspose.Slides mendukung **lebih dari 70 jenis grafik** dan dapat merender presentasi ratusan halaman dalam kurang dari satu detik pada perangkat keras server standar. Fitur **garis tinggi‑rendah** dan **batang naik/turun** memberikan kontrol presisi atas visualisasi keuangan, jauh melampaui apa yang ditawarkan UI PowerPoint.

## Prasyarat

- **Java Development Kit (JDK)** – versi 11 atau lebih tinggi.  
- **IDE** – IntelliJ IDEA, Eclipse, atau editor apa pun yang Anda sukai.  
- **Aspose.Slides for Java** – versi 25.4 (yang terbaru saat penulisan).  

### Menyiapkan Aspose.Slides untuk Java

#### Maven
Untuk mengintegrasikan Aspose.Slides ke dalam proyek Anda menggunakan Maven, tambahkan dependensi berikut ke `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Bagi pengguna Gradle, sertakan ini di `build.gradle` Anda:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Unduhan Langsung
Sebagai alternatif, unduh JAR terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Perolehan lisensi** – mulailah dengan percobaan gratis atau minta lisensi sementara. Untuk penggunaan komersial, beli lisensi penuh.

Untuk referensi API detail, lihat [Aspose.Slides documentation](https://docs.aspose.com/slides/java/).

## Cara membuat grafik saham dinamis langkah demi langkah

Muat presentasi Anda, tambahkan grafik saham, hapus data default, lalu sisipkan seri dan kategori Anda sendiri. Jawaban langsung untuk pertanyaan inti adalah:

> Muat PPTX yang ada dengan `new Presentation("template.pptx")`, tambahkan `Chart` bertipe `ChartType.Stock`, bersihkan seri dan kategori defaultnya, kemudian isi dengan titik data dan opsi pemformatan Anda. Akhirnya, panggil `presentation.save("output.pptx", SaveFormat.Pptx)`.

### Inisialisasi presentasi
#### Gambaran Umum
Mulailah dengan memuat file PowerPoint yang ada sehingga Anda dapat memodifikasinya secara langsung.

#### Langkah demi Langkah
1. **Impor perpustakaan** – kelas `Presentation` adalah titik masuk untuk semua operasi slide.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Muat file presentasi** – berikan jalur ke template PPTX Anda.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Tambahkan grafik saham ke slide
#### Gambaran Umum
Sisipkan grafik Stock pada slide pertama presentasi.

Kelas `Chart` mewakili bentuk grafik yang dapat ditambahkan ke slide.

#### Jawaban langsung
Anda menambahkan grafik saham dengan memanggil `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. Ini membuat objek grafik yang dapat langsung Anda manipulasi.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Hapus seri data dan kategori yang ada di grafik
#### Gambaran Umum
Hapus semua seri atau kategori yang sudah terisi sehingga Anda dapat memulai dengan kumpulan data bersih.

Objek `ChartData` menyimpan seri dan kategori untuk sebuah grafik.

#### Jawaban langsung
Panggil `chart.getChartData().getSeries().clear()` dan `chart.getChartData().getCategories().clear()` untuk menghapus konten default sebelum menambahkan data Anda sendiri.

   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Tambahkan kategori ke data grafik
#### Gambaran Umum
Tentukan kategori sumbu X (misalnya, tanggal) yang mengelompokkan nilai saham Anda.

`ChartCategory` mewakili label sumbu X untuk sebuah grafik.

#### Jawaban langsung
Buat `ChartCategory` baru untuk setiap label menggunakan `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")`, ulangi untuk setiap bulan atau periode.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Tambahkan seri data ke grafik
#### Gambaran Umum
Tambahkan empat seri penting: Open, High, Low, dan Close.

`ChartSeries` menyimpan koleksi titik data untuk sebuah seri tertentu dalam grafik.

#### Jawaban langsung
Untuk setiap seri, panggil `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. Ini mendaftarkan seri ke workbook data grafik.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Tambahkan titik data ke seri
#### Gambaran Umum
Isi setiap seri dengan nilai numerik yang mewakili harga saham.

`DataPoint` mewakili satu nilai dalam sebuah seri.

#### Jawaban langsung
Iterasikan koleksi data Anda dan gunakan `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (atau metode yang sesuai untuk tipe seri) untuk menyisipkan setiap titik.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Format garis tinggi‑rendah dan batang naik/turun
#### Gambaran Umum
Sesuaikan gaya visual penghubung tinggi‑rendah dan isian batang naik/turun.

`Marker` mendefinisikan simbol visual untuk sebuah titik data.

#### Jawaban langsung
Setel `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` dan konfigurasikan `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` untuk mengontrol ketebalan dan warna garis.

   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Tampilkan batang naik/turun
Gunakan metode `setShowUpDownBars(true)` pada grafik untuk menampilkan batang naik/turun.

   ```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Sesuaikan label data pada garis tinggi‑rendah
#### Gambaran Umum
Tampilkan nilai numerik langsung pada garis tinggi‑rendah untuk referensi cepat.

`DataLabel` mengontrol tampilan label yang terpasang pada titik data.

#### Jawaban langsung
Aktifkan label data dengan `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` dan gaya sesuai kebutuhan.

   ```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Atur warna isi batang naik/turun
#### Gambaran Umum
Berikan batang naik isi hijau dan batang turun isi merah untuk menyampaikan pergerakan pasar secara intuitif.

Objek `UpDownBars` memberikan akses ke pemformatan batang naik dan turun.

#### Jawaban langsung
Terapkan `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` dan setel warna solid ke `Color.GREEN`; ulangi untuk batang turun dengan `Color.RED`.

   ```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### Simpan file PowerPoint
#### Gambaran Umum
Persist perubahan Anda ke file PPTX baru.

Metode `save` menulis presentasi ke disk dalam format yang ditentukan.

#### Jawaban langsung
Panggil `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – ini menulis presentasi yang telah dimodifikasi ke disk dalam format PowerPoint standar.

   ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Masalah umum dan pemecahan masalah

- **Grafik tidak muncul** – pastikan koordinat X/Y dan dimensi grafik berada dalam batas slide.  
- **Titik data hilang** – verifikasi bahwa indeks sel workbook data cocok dengan seri/baris yang ingin Anda isi.  
- **Pengecualian lisensi** – lisensi percobaan sementara berakhir setelah 30 hari; ganti dengan lisensi permanen untuk build produksi.  
- **Penurunan kinerja pada file besar** – gunakan `Presentation.setCacheSize(0)` untuk menonaktifkan caching jika Anda memproses ribuan slide dalam satu batch.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan kode ini dalam aplikasi web?**  
J: Ya. Perpustakaan ini murni Java, sehingga dapat dijalankan di kontainer servlet apa pun atau layanan Spring Boot.

**T: Apakah Aspose.Slides mendukung jenis grafik lain selain Stock?**  
J: Tentu. Ia mendukung lebih dari 70 jenis grafik, termasuk Line, Bar, Pie, dan Radar.

**T: Bagaimana cara menambahkan judul grafik secara programatis?**  
J: Gunakan `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` lalu format judul sesuai kebutuhan.

**T: Apakah ada batas jumlah titik data per seri?**  
J: Secara praktis, Anda dapat menambahkan puluhan ribu titik; penggunaan memori berskala linear, dan perpustakaan melakukan streaming data untuk menjaga jejak memori tetap rendah.

**T: Koordinat Maven mana yang harus saya gunakan untuk versi terbaru?**  
J: Versi terbaru selalu tersedia di bawah `com.aspose:aspose-slides:25.4` (atau lebih baru) di Maven Central.

---

**Terakhir Diperbarui:** 2026-09-12  
**Diuji Dengan:** Aspose.Slides for Java 25.4  
**Penulis:** Aspose

## Tutorial Terkait

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Create Format Powerpoint Charts Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}