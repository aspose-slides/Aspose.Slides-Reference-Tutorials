---
date: '2026-02-22'
description: Pelajari cara membuat diagram kolom bertumpuk di Java menggunakan Aspose.Slides.
  Tutorial ini mencakup dependensi Maven Aspose Slides, menambahkan diagram bertumpuk
  persentase, memformat label data diagram, dan menyimpan presentasi sebagai PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Cara membuat diagram kolom bertumpuk di Java dengan Aspose.Slides – Panduan
  Komprehensif
url: /id/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara membuat diagram kolom bertumpuk di Java dengan Aspose.Slides – Panduan Komprehensif

## Pendahuluan

Tingkatkan presentasi Anda dengan menggabungkan visualisasi data yang mendalam menggunakan kekuatan Aspose.Slides untuk Java. Dalam panduan ini Anda akan **membuat diagram kolom bertumpuk** yang tampak profesional, baik saat menyiapkan laporan bisnis maupun menampilkan statistik proyek. Pada akhir tutorial ini Anda akan dapat:

- Menyiapkan lingkungan Anda dengan dependensi Aspose Slides Maven
- Membuat presentasi dari awal
- **Menambahkan diagram bertumpuk persentase** dan menyesuaikan tampilannya
- **Memformat label data diagram** dan **mengubah format sumbu vertikal**
- **Menyimpan presentasi sebagai PPTX** dengan satu baris kode

Mari kita jalani setiap langkah sehingga Anda dapat mulai membuat presentasi yang menarik segera.

## Jawaban Cepat
- **Perpustakaan apa yang saya butuhkan?** `aspose-slides` dependensi Maven/Gradle (lihat “aspose slides maven dependency” di bawah)  
- **Jenis diagram apa yang digunakan?** `ChartType.PercentsStackedColumn` untuk diagram kolom bertumpuk persentase  
- **Bagaimana cara mengubah format angka sumbu?** Gunakan `IAxis.setNumberFormat()` dan nonaktifkan penautan ke sumber  
- **Bisakah saya menyesuaikan label data?** Ya – iterasi melalui objek `IChartDataPoint` dan atur `ITextFrame` khusus  
- **Bagaimana cara menyimpan file?** Panggil `presentation.save("output.pptx", SaveFormat.Pptx)`

## Apa itu diagram kolom bertumpuk?
Diagram kolom bertumpuk menampilkan beberapa rangkaian data yang ditumpuk di atas satu sama lain dalam kolom vertikal. Ketika Anda menggunakan varian **bertumpuk persentase**, setiap kolom selalu berjumlah 100 %, memudahkan perbandingan kontribusi proporsional antar kategori.

## Mengapa menggunakan Aspose.Slides untuk Java?
Aspose.Slides menyediakan API murni‑Java yang berfungsi di platform apa pun tanpa perlu menginstal Microsoft Office. Ia menawarkan kontrol detail atas objek diagram, mendukung berbagai format, dan memungkinkan Anda menghasilkan presentasi secara programatik—sempurna untuk pelaporan otomatis atau pembuatan dokumen sisi‑server.

## Prasyarat
- **Java Development Kit (JDK):** 8 atau lebih tinggi  
- **IDE:** IntelliJ IDEA, Eclipse, atau editor kompatibel Java apa pun  
- **Alat Build:** Maven atau Gradle (opsional tetapi disarankan)  
- **Pengetahuan dasar Java** – Anda harus nyaman dengan kelas dan metode  

## Menyiapkan Aspose.Slides untuk Java
Untuk memulai, tambahkan pustaka Aspose.Slides ke proyek Anda.

### Dependensi Aspose Slides Maven
Tambahkan berikut ke `pom.xml` Anda (ini adalah **aspose slides maven dependency** yang Anda perlukan):

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
Anda dapat memulai dengan percobaan gratis untuk menjelajahi fitur Aspose.Slides. Untuk menghapus batasan evaluasi, pertimbangkan memperoleh lisensi sementara atau lisensi berbayar.

- **Percobaan Gratis:** Akses fitur terbatas tanpa biaya langsung.  
- **Lisensi Sementara:** Minta melalui [situs Aspose](https://purchase.aspose.com/temporary-license/).  
- **Pembelian:** Kunjungi halaman pembelian untuk akses penuh.

### Inisialisasi Dasar
Berikut cuplikan minimal yang menunjukkan cara membuat objek `Presentation`:

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

### Menambahkan Diagram Kolom Bertumpuk Persentase ke Slide
**Gambaran Umum:**  
Sekarang kita akan menempatkan **diagram bertumpuk persentase** ke slide pertama.

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
Untuk keterbacaan yang lebih baik, kita akan **mengubah format sumbu vertikal** agar menampilkan persentase.

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
Berikan setiap seri warna yang berbeda untuk membuat diagram lebih mudah dibaca.

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

**Q: Bisakah saya menggunakan kode ini dengan Java 11 atau yang lebih baru?**  
A: Ya. Pustaka mendukung JDK 8+; cukup gunakan classifier yang sesuai (mis., `jdk16` untuk JDK 16 atau lebih baru).

**Q: Bagaimana cara mengekspor diagram sebagai gambar alih-alih PPTX?**  
A: Gunakan `chart.getImage().save("chart.png", ImageFormat.Png);` setelah menambahkan diagram ke slide.

**Q: Apakah memungkinkan menambahkan legenda ke diagram kolom bertumpuk?**  
A: Tentu saja. Panggil `chart.getChartTitle().addTextFrameForOverriding("My Chart");` dan konfigurasikan `chart.getLegend()` sesuai kebutuhan.

**Q: Bagaimana jika saya perlu memperbarui data setelah presentasi dihasilkan?**  
A: Anda dapat memodifikasi sel `ChartDataWorkbook` lalu memanggil `chart.refresh();` untuk memperbarui perubahan.

**Q: Apakah Aspose.Slides bekerja di server Linux?**  
A: Ya. Pustaka ini murni Java dan berjalan di sistem operasi apa pun dengan JRE yang kompatibel.

## Kesimpulan
Dengan mengikuti panduan ini Anda telah belajar cara **membuat diagram kolom bertumpuk** dalam presentasi menggunakan Aspose.Slides untuk Java, mulai dari penyiapan lingkungan hingga penataan visual yang halus. Bereksperimenlah dengan kumpulan data, warna, dan format label yang berbeda untuk membuat laporan Anda benar‑benar menonjol.

---

**Terakhir Diperbarui:** 2026-02-22  
**Diuji Dengan:** Aspose.Slides 25.4 (jdk16 classifier)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}