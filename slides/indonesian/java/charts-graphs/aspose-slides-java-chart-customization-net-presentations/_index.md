---
date: '2026-06-08'
description: Pelajari cara menambahkan seri ke diagram dan menyesuaikan diagram kolom
  bertumpuk dalam presentasi .NET menggunakan Aspose.Slides for Java.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Menambahkan Seri ke Diagram dengan Aspose.Slides for Java di .NET
url: /id/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Menguasai Kustomisasi Diagram dalam Presentasi .NET Menggunakan Aspose.Slides untuk Java

## Pendahuluan
Dalam dunia presentasi berbasis data, diagram merupakan alat yang tak tergantikan yang mengubah angka mentah menjadi cerita visual yang menarik. Ketika Anda perlu **menambahkan seri ke diagram** secara programatik, terutama di dalam file presentasi .NET, tugas tersebut dapat terasa berat. Untungnya, **Aspose.Slides for Java** menyediakan API yang kuat dan tidak bergantung pada bahasa yang membuat pembuatan dan kustomisasi diagram menjadi sederhana—bahkan ketika format target Anda adalah .NET PPTX. Panduan ini akan memandu Anda melalui penambahan seri, membangun diagram kolom bertumpuk, dan menyesuaikan aspek visual seperti lebar celah, sehingga Anda dapat menghasilkan slide dinamis yang kaya data, tampak rapi dan profesional.

## Jawaban Cepat
Kelas `Presentation` mewakili file PPTX, dan `slide.getShapes().addChart(...)` menyisipkan bentuk diagram. Gunakan `chart.getChartData().getSeries().add(...)` untuk menambahkan seri, dan `setGapWidth()` mengatur jarak.

- **Apa kelas utama untuk memulai sebuah presentasi?** `Presentation` – itu mewakili file PPTX dalam memori.  
- **Metode mana yang menambahkan diagram ke slide?** `slide.getShapes().addChart(...)` membuat objek diagram pada slide.  
- **Bagaimana cara menambahkan seri baru?** `chart.getChartData().getSeries().add(...)` menyisipkan seri data baru.  
- **Bisakah Anda mengubah lebar celah antara batang?** Ya—panggil `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (nilai dalam persentase).  
- **Apakah saya memerlukan lisensi untuk produksi?** Tentu—lisensi Aspose.Slides for Java yang valid membuka semua fitur dan menghapus watermark evaluasi.

## Apa itu “menambahkan seri ke diagram”?
Menambahkan seri ke diagram berarti menyisipkan kumpulan titik data baru yang diagram tampilkan sebagai elemen visual yang terpisah (misalnya, grup kolom terpisah). Setiap seri dapat memiliki nilai, warna, dan pemformatan masing‑masing, memungkinkan perbandingan berdampingan dari beberapa kumpulan data.

## Mengapa menggunakan Aspose.Slides untuk Java untuk memodifikasi presentasi .NET?
Aspose.Slides untuk Java memungkinkan Anda menghasilkan atau mengedit file PPTX yang sepenuhnya kompatibel dengan penampil PowerPoint .NET, tanpa memerlukan instalasi Microsoft Office apa pun. Gunakan Aspose.Slides untuk Java ketika Anda memerlukan solusi sisi‑server, lintas‑platform yang membuat atau memperbarui file .NET PPTX, mendukung lebih dari 50 jenis diagram, dan memproses file hingga 500 MB tanpa memuat seluruh dokumen ke dalam memori. API‑nya bekerja di Java, Kotlin, Scala, atau bahasa JVM apa pun, menghasilkan output yang sama seperti yang diharapkan pengembang .NET.

## Prasyarat
- **Pustaka Aspose.Slides untuk Java** (versi 25.4 atau lebih baru).  
- Maven, Gradle, atau unduhan JAR manual.  
- Pengetahuan dasar Java dan pemahaman tentang struktur file PPTX.  

## Menyiapkan Aspose.Slides untuk Java
### Instalasi Maven
Tambahkan dependensi berikut ke `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalasi Gradle
Sertakan baris ini dalam file `build.gradle` Anda:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduhan Langsung
Sebagai alternatif, dapatkan JAR terbaru dari halaman rilis resmi: [Rilis Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/).

**Perolehan Lisensi**  
Mulailah dengan percobaan gratis dengan mengunduh lisensi sementara dari [sini](https://purchase.aspose.com/temporary-license/). Untuk penggunaan produksi, beli lisensi penuh untuk membuka semua fitur dan menghapus watermark evaluasi.

## Panduan Implementasi Langkah‑per‑Langkah
Di bawah setiap langkah Anda akan menemukan potongan kode singkat (tidak diubah dari tutorial asli) diikuti oleh penjelasan tentang apa yang dilakukannya.

### Langkah 1: Buat Presentasi Kosong
`Presentation` adalah kelas titik masuk yang mewakili file PowerPoint dalam memori.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*Kami memulai dengan file PPTX bersih, yang memberi kami kanvas untuk menambahkan diagram.*

### Langkah 2: Tambahkan Diagram Kolom Bertumpuk ke Slide
`Chart` mewakili bentuk diagram dalam sebuah slide. `ChartType.StackedColumn` menentukan diagram kolom bertumpuk.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*Metode `addChart` membuat **diagram kolom bertumpuk** dan menempatkannya di sudut kiri‑atas slide.*

### Langkah 3: Tambahkan Seri ke Diagram (Tujuan Utama)
`Series` mengenkapsulasi satu seri data dalam diagram.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Di sini kami **menambahkan seri ke diagram** – setiap pemanggilan membuat seri data baru yang akan muncul sebagai grup kolom terpisah.*

### Langkah 4: Tambahkan Kategori ke Diagram
`Category` mendefinisikan label sumbu X untuk data diagram.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Kategori berfungsi sebagai label sumbu X, memberi makna pada setiap kolom.*

### Langkah 5: Isi Data Seri
`DataPoint` menyimpan nilai numerik untuk sebuah seri pada kategori tertentu.  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*Titik data memberikan setiap seri nilai numeriknya, yang akan dirender diagram sebagai tinggi batang.*

### Langkah 6: Atur Lebar Celah untuk Grup Seri Diagram
`SeriesGroup` mengontrol properti tata letak untuk grup seri, seperti lebar celah.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Menyesuaikan lebar celah meningkatkan keterbacaan, terutama ketika banyak kategori hadir.*

## Kasus Penggunaan Umum
- **Pelaporan keuangan** – membandingkan pendapatan kuartalan antar unit bisnis.  
- **Dasbor proyek** – menampilkan persentase penyelesaian tugas per tim.  
- **Analitik pemasaran** – memvisualisasikan kinerja kampanye berdampingan.  
Skenario ini mendapat manfaat dari **contoh diagram kolom bertumpuk** karena menyoroti kontribusi masing‑masing kategori terhadap total.

## Tips Kinerja
- **Gunakan kembali objek `Presentation`** saat membuat beberapa diagram untuk mengurangi beban memori.  
- **Batasi jumlah titik data** hanya pada yang diperlukan untuk cerita visual; Aspose.Slides dapat menangani 10.000 titik, tetapi kecepatan rendering menurun setelah ~5.000.  
- **Buang objek** (`presentation.dispose()`) setelah menyimpan untuk membebaskan sumber daya dan menghindari kebocoran memori.

## Pertanyaan yang Sering Diajukan
**T: Bisakah saya menambahkan jenis diagram lain selain kolom bertumpuk?**  
J: Ya, Aspose.Slides mendukung diagram garis, pai, area, radar, gelembung, dan lebih dari 50 jenis diagram lainnya, semuanya dapat diakses melalui metode `addChart` yang sama.

**T: Apakah saya memerlukan lisensi terpisah untuk output .NET?**  
J: Tidak, lisensi Java yang sama berfungsi untuk semua format output, termasuk file .NET PPTX.

**T: Bagaimana cara mengubah palet warna diagram?**  
J: Gunakan `series.getFormat().getFill().setFillType(FillType.Solid)` lalu atur objek `Color` yang diinginkan untuk setiap seri.

**T: Apakah memungkinkan menambahkan label data secara programatik?**  
J: Tentu saja. Panggil `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` untuk menampilkan nilai numerik pada setiap kolom.

**T: Bagaimana jika saya perlu memperbarui presentasi yang sudah ada?**  
J: Muat file dengan `new Presentation("existing.pptx")`, modifikasi diagram menggunakan panggilan API yang sama, dan simpan kembali ke disk.

## Kesimpulan
Anda kini memiliki panduan lengkap, dari awal hingga akhir, tentang cara **menambahkan seri ke diagram**, membuat **diagram kolom bertumpuk**, dan menyesuaikan tampilannya dalam presentasi .NET menggunakan Aspose.Slides untuk Java. Bereksperimenlah dengan berbagai jenis diagram, warna, dan sumber data untuk membangun laporan visual yang menarik, mengesankan pemangku kepentingan, dan mendorong keputusan berbasis data.

---

**Terakhir Diperbarui:** 2026-06-08  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (JDK 16)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Membuat Diagram Kolom Bertumpuk Berbasis Persentase di .NET menggunakan Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Penguasaan Pembuatan dan Manipulasi Seri Diagram dengan Aspose.Slides .NET untuk Visualisasi Data yang Efektif](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Menghapus Titik Data Seri Diagram Spesifik dengan Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}