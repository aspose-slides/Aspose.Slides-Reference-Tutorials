---
date: '2026-07-22'
description: Pelajari Aspose Slides Maven Dependency untuk membuat stacked column
  chart di Java, menambahkan data labels, mengubah format angka sumbu vertikal, dan
  mengekspor hasilnya sebagai file PPTX.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency memungkinkan Anda membangun stacked
  column chart di Java, menyesuaikan data labels, mengatur format sumbu vertikal,
  dan menyimpan sebagai PPTX – semua dengan kode yang ringkas dan siap produksi.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Stacked Column Chart di Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Stacked Column Chart di Java'
url: /id/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dependensi Maven Aspose Slides: Diagram Kolom Bertumpuk di Java

## Pendahuluan

Tingkatkan presentasi Anda dengan memasukkan visualisasi data yang mendalam menggunakan kekuatan **Aspose.Slides for Java**. Dalam panduan ini Anda akan **membuat diagram kolom bertumpuk** yang tampak profesional, baik saat menyiapkan laporan bisnis maupun menampilkan statistik proyek. Pada akhir tutorial ini Anda akan dapat:

- Siapkan lingkungan Anda dengan **dependensi Maven Aspose Slides**
- Buat presentasi dari awal
- **Tambahkan diagram persentase‑bertumpuk** dan sesuaikan tampilannya
- **Format label data diagram** dan **ubah format angka sumbu vertikal**
- **Simpan presentasi sebagai PPTX** dengan satu baris kode

## Jawaban Cepat
- **Perpustakaan apa yang saya perlukan?** Tambahkan dependensi Maven/Gradle `aspose-slides` (lihat “Dependensi Maven Aspose Slides” di bawah).  
- **Jenis diagram apa yang menghasilkan tampilan bertumpuk?** Gunakan `ChartType.PercentsStackedColumn` untuk diagram kolom persentase‑bertumpuk.  
- **Bagaimana cara mengubah format angka sumbu?** Panggil `IAxis.setNumberFormat()` dan atur `setNumberFormatLinkedToSource(false)`.  
- **Bisakah saya menyesuaikan label data?** Ya – iterasi setiap `IChartDataPoint` dan tetapkan `ITextFrame` khusus.  
- **Bagaimana cara menyimpan file?** Panggil `presentation.save("output.pptx", SaveFormat.Pptx)`.

## Apa itu diagram kolom bertumpuk?
Diagram kolom bertumpuk memvisualisasikan beberapa seri data yang ditumpuk secara vertikal dalam setiap kolom kategori, dengan varian **persentase‑bertumpuk** menormalkan setiap kolom menjadi 100 % untuk perbandingan proporsi yang mudah. Format ini memungkinkan penonton dengan cepat menilai bagaimana setiap komponen berkontribusi pada keseluruhan di berbagai kategori, menjadikan tren dan ukuran relatif langsung terlihat.

## Mengapa menggunakan Aspose.Slides untuk Java?
Aspose.Slides untuk Java memungkinkan Anda menghasilkan, mengedit, dan mengonversi file PowerPoint **tanpa memerlukan Microsoft Office** serta mendukung **lebih dari 50 format output** di Windows, Linux, dan macOS. Perpustakaan ini berjalan sepenuhnya pada JRE, memungkinkan otomatisasi sisi server dan pelaporan berkapasitas tinggi. Ia juga menyediakan kontrol detail atas objek diagram, tata letak slide, dan properti dokumen, menjadikannya ideal untuk pembuatan presentasi tingkat perusahaan.

## Prasyarat
- **Java Development Kit (JDK):** 8 atau lebih tinggi  
- **IDE:** IntelliJ IDEA, Eclipse, atau editor kompatibel Java apa pun  
- **Alat Build:** Maven atau Gradle (opsional tetapi disarankan)  
- **Pengetahuan dasar Java** – Anda harus nyaman dengan kelas dan metode  

## Menyiapkan Aspose.Slides untuk Java
Untuk memulai, tambahkan perpustakaan Aspose.Slides ke proyek Anda.

### Dependensi Maven Aspose Slides
Tambahkan berikut ke `pom.xml` Anda (ini adalah **dependensi Maven Aspose Slides** yang Anda perlukan):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Alternatif Gradle
Jika Anda lebih suka Gradle, sertakan baris ini di `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduhan Langsung
Sebagai alternatif, unduh JAR terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Perolehan Lisensi
Anda dapat memulai dengan percobaan gratis untuk menjelajahi fitur Aspose.Slides. Untuk menghapus batasan evaluasi, pertimbangkan memperoleh lisensi sementara atau berbayar.

- **Percobaan Gratis:** Akses fitur terbatas tanpa biaya langsung.  
- **Lisensi Sementara:** Minta melalui [situs Aspose](https://purchase.aspose.com/temporary-license/).  
- **Pembelian:** Kunjungi halaman pembelian untuk akses penuh.

### Inisialisasi Dasar
`Presentation` adalah kelas inti Aspose.Slides yang mewakili file PowerPoint dalam memori. Potongan kode minimal berikut menunjukkan cara membuat objek `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Panduan Implementasi

### Membuat Presentasi dan Menambahkan Slide
**Gambaran Umum:**  
Pertama, kita akan membuat presentasi kosong dan memverifikasi bahwa slide ada.

#### Langkah 1: Inisialisasi Objek Presentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Langkah 2: Simpan Presentasi
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Menambahkan Diagram Kolom Persentase‑Bertumpuk ke Slide
**Gambaran Umum:**  
Sekarang kita akan menempatkan **diagram persentase‑bertumpuk** pada slide pertama.

`ChartType.PercentsStackedColumn` menentukan jenis diagram kolom persentase‑bertumpuk.

#### Langkah 1: Inisialisasi dan Akses Slide
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Langkah 2: Tambahkan Diagram ke Slide
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Menyesuaikan Format Angka Sumbu Diagram
**Gambaran Umum:**  
Untuk keterbacaan yang lebih baik, kita akan **mengubah format sumbu vertikal** menjadi menampilkan persentase.

`IAxis` adalah antarmuka yang mewakili sumbu diagram, memungkinkan penyesuaian format dan skala.

#### Langkah 1: Tambahkan dan Akses Diagram
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Langkah 2: Atur Format Angka Kustom
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Menambahkan Seri dan Titik Data ke Diagram
**Gambaran Umum:**  
Kita akan mengisi diagram dengan contoh seri data.

#### Langkah 1: Inisialisasi Presentasi dan Diagram
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Langkah 2: Tambahkan Seri Data
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Memformat Warna Isi Seri
**Gambaran Umum:**  
Berikan setiap seri warna yang berbeda agar diagram lebih mudah dibaca.

#### Langkah 1: Inisialisasi dan Akses Diagram
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Langkah 2: Atur Warna Isi
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Memformat Label Data
**Gambaran Umum:**  
Sekarang kita akan **memformat label data diagram** sehingga menampilkan teks khusus.

`IChartDataPoint` mewakili titik data individual dalam seri diagram, dan `ITextFrame` menyimpan teks label.

#### Langkah 1: Akses Seri Diagram dan Titik Data
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Langkah 2: Sesuaikan Label Data
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Masalah Umum dan Solusinya
- **Diagram muncul kosong:** Pastikan Anda telah menambahkan setidaknya satu seri data dan titik data sebelum menyimpan.  
- **Angka sumbu tidak menampilkan persentase:** Ingat untuk mengatur `verticalAxis.setNumberFormatLinkedToSource(false)`; jika tidak, format kustom akan diabaikan.  
- **Pesan evaluasi lisensi:** Terapkan file lisensi yang valid sebelum membuat objek `Presentation` untuk menekan banner evaluasi.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan kode ini dengan Java 11 atau lebih baru?**  
**J:** Ya. Perpustakaan mendukung JDK 8+; cukup gunakan classifier yang sesuai (mis., `jdk16` untuk JDK 16 atau lebih baru).

**T: Bagaimana cara mengekspor diagram sebagai gambar bukan PPTX?**  
**J:** Gunakan `chart.getImage().save("chart.png", ImageFormat.Png);` setelah menambahkan diagram ke slide.

**T: Apakah memungkinkan menambahkan legenda ke diagram kolom bertumpuk?**  
**J:** Tentu saja. Panggil `chart.getChartTitle().addTextFrameForOverriding("My Chart");` dan konfigurasikan `chart.getLegend()` sesuai kebutuhan.

**T: Bagaimana jika saya perlu memperbarui data setelah presentasi dihasilkan?**  
**J:** Anda dapat memodifikasi sel `ChartDataWorkbook` dan kemudian memanggil `chart.refresh();` untuk mencerminkan perubahan.

**T: Apakah Aspose.Slides bekerja di server Linux?**  
**J:** Ya. Perpustakaan ini murni Java dan berjalan di sistem operasi apa pun dengan JRE yang kompatibel.

## Kesimpulan
Dengan mengikuti panduan ini, Anda telah belajar cara **membuat diagram kolom bertumpuk** di Java menggunakan **dependensi Maven Aspose Slides**, mulai dari penyiapan lingkungan hingga penataan visual yang detail. Bereksperimenlah dengan set data, warna, dan format label yang berbeda untuk membuat laporan Anda benar‑benar menonjol.

---

**Terakhir Diperbarui:** 2026-07-22  
**Diuji Dengan:** Aspose.Slides 25.4 (classifier jdk16)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara membuat diagram kolom berkelompok di Java dengan Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Cara Mengatur Format Angka pada Titik Data Diagram Menggunakan Aspose.Slides untuk Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Cara Menambahkan dan Mengonfigurasi Diagram dalam Presentasi Menggunakan Aspose.Slides untuk Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}