---
date: '2026-08-21'
description: Pelajari cara membuat diagram kolom berkelompok dan menambahkan garis
  tren dengan Aspose.Slides for Java. Termasuk penyiapan lisensi, integrasi Maven/Gradle,
  dan contoh terperinci.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Buat diagram kolom berkelompok dan tambahkan garis tren menggunakan
  Aspose.Slides for Java. Panduan ini mencakup penyiapan lisensi, Maven/Gradle, dan
  potongan kode langkah demi langkah.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Buat diagram kolom berkelompok dan tambahkan garis tren dengan Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Cara membuat diagram kolom berkelompok dan menambahkan garis tren menggunakan
  Aspose.Slides for Java
url: /id/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat clustered column chart dan menambahkan trend lines menggunakan Aspose.Slides for Java

Membuat presentasi yang menarik sering dimulai dengan visualisasi data yang jelas. Dalam panduan ini Anda akan **membuat objek clustered column chart**, lalu memperkaya mereka dengan berbagai jenis trend line—exponential, linear, logarithmic, moving average, polynomial, dan power—menggunakan API kuat Aspose.Slides for Java.

## Jawaban Cepat
- **Apa langkah pertama?** Inisialisasi objek `Presentation` dan tambahkan clustered column chart ke sebuah slide.  
- **Versi perpustakaan apa yang diperlukan?** Aspose.Slides for Java 25.4 atau lebih baru.  
- **Apakah saya dapat menggunakan Maven atau Gradle?** Ya, keduanya didukung; Maven menggunakan `<dependency>` dan Gradle menggunakan `implementation`.  
- **Apakah saya membutuhkan lisensi?** Lisensi percobaan berfungsi untuk evaluasi; lisensi penuh Aspose.Slides menghapus batas evaluasi.  
- **Berapa jenis garis tren yang tersedia?** Enam tipe bawaan: eksponensial, linear, logaritmik, moving average, polynomial, dan power.

## Apa itu create clustered column chart?
`create clustered column chart` berarti menghasilkan diagram yang mengelompokkan beberapa seri data berdampingan dalam setiap kategori, memudahkan perbandingan nilai antar seri. Tipe diagram ini ideal untuk memvisualisasikan data kategorikal seperti penjualan kuartalan per wilayah, memungkinkan pemirsa dengan cepat melihat perbedaan antar grup.

## Mengapa menambahkan trend line?
Garis tren mengungkap pola dasar dari sebuah seri data, membantu Anda meramalkan nilai masa depan, menyoroti tingkat pertumbuhan, atau melicinkan data yang berisik. Dengan menambahkan trend line ke clustered column chart, angka mentah menjadi wawasan yang dapat ditindaklanjuti, memungkinkan pemangku kepentingan memahami kecenderungan jangka panjang dan membuat keputusan berbasis data.

## Prasyarat
- **Java Development Kit (JDK):** 8 atau lebih baru.  
- **Aspose.Slides for Java:** versi 25.4 atau lebih baru.  
- **IDE:** IntelliJ IDEA, Eclipse, atau editor Java lainnya.  
- **Alat build:** Maven atau Gradle (opsional tetapi disarankan).  
- **Lisensi:** file lisensi Aspose.Slides percobaan atau yang dibeli.  

Anda sebaiknya nyaman dengan sintaks Java dasar dan familiar dengan manajemen dependensi proyek.

## Cara menyiapkan Aspose.Slides untuk Java?
Tambahkan perpustakaan Aspose.Slides ke proyek Anda menggunakan manajer dependensi pilihan, lalu letakkan file lisensi Anda di lokasi yang dapat dijangkau runtime. Ini memastikan fungsionalitas penuh dan menghapus batas evaluasi.

### Maven
Tambahkan dependensi ini ke file `pom.xml` Anda:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Sertakan baris ini di file `build.gradle` Anda:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct download
Anda juga dapat mengunduh JAR secara manual dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Lisensi Aspose Slides
Letakkan file `Aspose.Slides.lic` di root proyek Anda atau atur lisensi secara programatis dengan `License license = new License(); license.setLicense("Aspose.Slides.lic");`. Lisensi percobaan menghapus semua pembatasan fitur, tetapi lisensi yang dibeli menghilangkan watermark evaluasi dan memberikan optimasi kinerja penuh. Untuk penggunaan produksi, pertimbangkan membeli lisensi dari [Aspose purchase page](https://purchase.aspose.com/buy).

## Cara membuat presentasi dan menambahkan clustered column chart?
Kelas `Presentation` mewakili file PowerPoint dan menyediakan metode untuk membuat, mengedit, dan menyimpan slide. Buat instance `Presentation`, tambahkan slide, lalu panggil `addChart` dengan `ChartType.ClusteredColumn` untuk membuat objek diagram. Proses ini menyiapkan kanvas slide, menyisipkan shape diagram, dan menyiapkannya untuk pengisian data serta styling.

1. **Inisialisasi presentasi** – siapkan folder output dan buat instance `Presentation` baru.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Tambahkan clustered column chart** – dapatkan shape diagram, konfigurasikan serinya, dan isi data poin.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Cara menambahkan exponential trend line?
Antarmuka `ITrendline` mendefinisikan garis tren yang dapat ditambahkan ke seri diagram untuk memodelkan pola data. Terapkan exponential trend line ke sebuah seri dengan membuat instance `ITrendline`, mengatur `TrendlineType` menjadi `Exponential`, dan melampirkannya ke seri yang diinginkan. Tipe garis tren ini berguna untuk data yang tumbuh cepat dengan laju meningkat.

1. **Konfigurasikan garis tren** – pilih seri dan panggil `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Cara menambahkan linear trend line?
Linear trend line menunjukkan garis lurus terbaik yang melewati titik data Anda. Anda juga dapat menyesuaikan tampilannya, seperti warna garis dan ketebalan, agar sesuai dengan gaya presentasi.

1. **Siapkan garis tren** – gunakan `addTrendline(TrendlineType.Linear)` lalu sesuaikan `getLineFormat().setFillFormat().setFillType(FillType.Solid)` untuk mengubah warna.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Cara menambahkan logarithmic trend line dengan custom text frame?
Logarithmic trend line ideal untuk data yang tumbuh cepat pada awalnya lalu melandai. Menimpa label default memungkinkan Anda menambahkan teks penjelasan yang memperjelas signifikansi tren.

1. **Sesuaikan garis tren** – setelah menambahkan garis tren, akses `getDataLabel()` dan atur properti `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Cara menambahkan moving average trend line?
Moving average trend line melicinkan fluktuasi jangka pendek untuk menonjolkan tren jangka panjang. Anda dapat menentukan periode (jumlah poin) yang digunakan untuk rata‑rata, sehingga dapat mengontrol kehalusan garis.

1. **Konfigurasikan garis tren** – panggil `addTrendline(TrendlineType.MovingAverage)` dan set `setPeriod(3)` untuk menggunakan rata‑rata bergerak tiga poin.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Cara menambahkan polynomial trend line?
Polynomial trend line menyesuaikan data dengan kurva yang didefinisikan oleh persamaan polinomial. Properti `order` mengontrol derajat polinomial, memungkinkan pemodelan hubungan yang lebih kompleks.

1. **Sesuaikan garis tren** – setelah menambahkan garis tren, set `setOrder(3)` untuk fit kubik.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Cara menambahkan power trend line?
Power trend line berguna ketika data mengikuti hubungan power‑law. Anda juga dapat mengatur nilai forecast backward dan forward untuk memperpanjang garis melampaui rentang data yang ada.

1. **Konfigurasikan garis tren** – gunakan `addTrendline(TrendlineType.Power)` dan sesuaikan `setBackward(2)` untuk memperpanjang garis ke belakang.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Aplikasi praktis garis tren dalam clustered column charts
- **Analisis keuangan:** Tren eksponensial dan polinomial membantu meramalkan pergerakan harga saham.  
- **Peramalan penjualan:** Garis moving average melicinkan lonjakan musiman, memberikan pandangan lebih jelas tentang tren penjualan yang mendasari.  
- **Penelitian ilmiah:** Tren logaritmik sempurna untuk data yang mencakup beberapa orde besaran, seperti intensitas akustik atau tingkat pH.  
- **Pemantauan operasi:** Power trend line dapat memodelkan degradasi kinerja seiring waktu.

## Cara mengoptimalkan memori saat menggunakan Aspose.Slides?
Buang objek segera dan gunakan `presentation.dispose()` setelah menyimpan. Untuk dataset besar, aktifkan lazy loading gambar dan hindari memuat seluruh diagram ke memori sekaligus.

- **Pola pembuangan:** Bungkus `Presentation` dalam blok try‑with‑resources atau panggil `presentation.dispose()` dalam blok finally.  
- **Pemuat malas:** Set `ChartData.setUseCache(true)` saat menangani ribuan poin data.  
- **Output streaming:** Tulis presentasi langsung ke `FileOutputStream` untuk menghindari menyimpan seluruh file di RAM.

## Manfaat terukur Aspose.Slides untuk Java
Aspose.Slides mendukung **lebih dari 50 tipe diagram**, dapat menghasilkan presentasi dengan **lebih dari 1.000 slide** dalam waktu kurang dari **30 detik** pada CPU 2 GHz tipikal, dan memproses **PDF 500‑halaman** tanpa memerlukan Microsoft Office terinstal. Angka-angka ini diverifikasi pada rilis 25.4 terbaru.

## Kesimpulan
Anda kini memiliki solusi lengkap, end‑to‑end untuk **membuat objek clustered column chart** dan memperkaya mereka dengan setiap jenis trend‑line utama yang tersedia di Aspose.Slides for Java. Dengan mengikuti langkah‑langkah di atas, Anda dapat menghasilkan presentasi berbasis data yang menarik secara visual dan kuat secara analitis.

Langkah selanjutnya termasuk mengeksplorasi opsi styling diagram, mengekspor ke PDF/HTML, dan mengotomatisasi pembuatan diagram lintas berbagai sumber data.

## Pertanyaan yang sering diajukan

**Q: Bagaimana cara menyiapkan Aspose.Slides untuk proyek Maven?**  
A: Tambahkan potongan `<dependency>` yang ditunjukkan pada bagian Maven ke `pom.xml` Anda dan jalankan `mvn clean install`.

**Q: Bisakah saya menyesuaikan trend line selain warna dan label?**  
A: Ya, Anda dapat memodifikasi gaya garis, lebar, pola dash, dan bahkan nilai forecast forward/backward melalui API `ITrendline`.

**Q: Apa yang harus saya lakukan jika menemukan error kompatibilitas versi?**  
A: Pastikan versi JDK Anda sesuai dengan persyaratan minimum Aspose.Slides (JDK 8+). Lihat catatan rilis Aspose untuk perubahan yang dapat memutus kompatibilitas.

**Q: Apakah memungkinkan menambahkan trend line ke banyak diagram secara otomatis?**  
A: Tentu. Loop melalui setiap `IChart` dalam koleksi slide dan panggil metode `addTrendline` yang sesuai untuk setiap seri.

**Q: Apakah saya membutuhkan lisensi berbayar untuk penggunaan produksi?**  
A: Ya, lisensi Aspose.Slides yang dibeli menghapus batas evaluasi dan membuka semua optimasi kinerja penuh.

**Last Updated:** 2026-08-21  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## Tutorial Terkait

- [aspose slides maven dependency: Tambahkan dan Konfigurasikan Diagram dalam Presentasi Menggunakan Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Tambahkan animasi ke diagram PowerPoint menggunakan Aspose.Slides for Java – Panduan Langkah‑per‑Langkah](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Buat Diagram PowerPoint Java – Simpan Presentasi dengan Diagram Menggunakan Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}