---
date: '2026-02-19'
description: Pelajari cara membuat grafik pai di Java dengan Aspose.Slides, menyesuaikan
  warna grafik pai, menambahkan seri grafik, bekerja dengan lembar kerja data grafik,
  dan mengatur sudut rotasi.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Cara Menyesuaikan Warna Diagram Lingkaran di Java dengan Aspose.Slides – Panduan
  Lengkap
url: /id/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

Also there is a backtop button shortcode after.

We must ensure we keep all markdown formatting.

Let's produce final translation.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat Diagram Lingkaran dengan Aspose.Slides untuk Java: Tutorial Lengkap

## Pendahuluan
Membuat presentasi yang dinamis dan menarik secara visual sangat penting untuk menyampaikan informasi yang berdampak. Dengan Aspose.Slides untuk Java, Anda dapat dengan mulus mengintegrasikan diagram kompleks seperti diagram lingkaran ke dalam slide Anda, **menyesuaikan warna diagram lingkaran**, dan meningkatkan visualisasi data dengan mudah. Panduan komprehensif ini akan memandu Anda melalui proses pembuatan dan penyesuaian diagram lingkaran menggunakan Aspose.Slides Java, menyelesaikan tantangan presentasi umum dengan mudah.

**Apa yang Akan Anda Pelajari:**
- Menginisialisasi presentasi dan menambahkan slide.
- Membuat dan mengonfigurasi diagram lingkaran pada slide Anda.
- Menetapkan judul diagram, label data, dan **menyesuaikan warna diagram lingkaran**.
- Mengoptimalkan kinerja dan mengelola sumber daya secara efektif.
- Mengintegrasikan Aspose.Slides ke dalam proyek Java menggunakan Maven atau Gradle.

Mari kita mulai dengan memastikan Anda memiliki semua alat dan pengetahuan yang diperlukan untuk mengikuti tutorial ini!

## Jawaban Cepat
- **Apa kelas utama untuk memulai sebuah presentasi?** `Presentation` dari `com.aspose.slides`.
- **Metode mana yang menambahkan diagram lingkaran ke slide?** `addChart(ChartType.Pie, …)`.
- **Bagaimana cara mengaktifkan warna berbeda untuk setiap irisan?** Atur `setColorVaried(true)` pada grup seri.
- **Apakah diagram lingkaran dapat diputar?** Ya, gunakan `setRotationAngle(double)` pada objek diagram.
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi Aspose.Slides diperlukan untuk penerapan komersial.

## Apa itu “menyesuaikan warna diagram lingkaran”?
Menyesuaikan warna diagram lingkaran berarti memberikan warna isi yang berbeda untuk setiap irisan diagram, meningkatkan keterbacaan dan dampak visual. Di Aspose.Slides Anda dapat melakukannya dengan mengaktifkan warna beragam dan kemudian menetapkan warna isi solid untuk masing‑masing titik data.

## Mengapa menggunakan Aspose.Slides untuk Java dalam membuat diagram lingkaran?
- **Kontrol penuh** atas tampilan diagram tanpa memerlukan Microsoft Office.
- **Kompatibilitas lintas‑platform** – berfungsi di Windows, Linux, dan macOS.
- **API kaya** untuk binding data, styling, dan mengekspor ke PPTX, PDF, atau gambar.
- **Fleksibilitas lisensi** – mulai dengan percobaan gratis dan tingkatkan ketika Anda membutuhkan semua fitur.

## Prasyarat
Sebelum menyelami tutorial ini, pastikan Anda telah menyiapkan hal‑hal berikut:

### Perpustakaan, Versi, dan Dependensi yang Diperlukan
- **Aspose.Slides untuk Java**: versi 25.4 atau lebih baru.
- **Java Development Kit (JDK)**: versi 16 atau lebih tinggi.

### Persyaratan Penyiapan Lingkungan
- Lingkungan pengembangan dengan Java terpasang dan terkonfigurasi.
- Integrated Development Environment (IDE) seperti IntelliJ IDEA, Eclipse, atau NetBeans.

### Prasyarat Pengetahuan
- Pemahaman dasar pemrograman Java.
- Familiaritas dengan Maven atau Gradle untuk manajemen dependensi.

## Menyiapkan Aspose.Slides untuk Java
Untuk mulai menggunakan Aspose.Slides dalam proyek Java Anda, tambahkan perpustakaan sebagai dependensi. Berikut cara melakukannya dengan berbagai alat build:

**Maven**  
Tambahkan potongan berikut ke file `pom.xml` Anda:
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
Jika Anda lebih memilih tidak menggunakan alat build, unduh rilis terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Langkah‑langkah Akuisisi Lisensi
- **Percobaan Gratis**: Mulai dengan percobaan gratis untuk menjelajahi fitur Aspose.Slides.  
- **Lisensi Sementara**: Dapatkan lisensi sementara untuk penggunaan lebih lama tanpa batasan.  
- **Pembelian**: Pertimbangkan membeli jika Anda memerlukan akses jangka panjang.

**Inisialisasi Dasar dan Penyiapan**  
Untuk mulai menggunakan Aspose.Slides, inisialisasi proyek Anda dengan membuat objek presentasi baru:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Panduan Implementasi
Sekarang mari kita uraikan proses penambahan dan penyesuaian diagram lingkaran menjadi langkah‑langkah yang dapat dikelola.

### Inisialisasi Presentasi dan Slide
Mulailah dengan menyiapkan presentasi baru dan mengakses slide pertama. Ini adalah kanvas Anda untuk membuat diagram:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Tambahkan Diagram Lingkaran ke Slide
Sisipkan diagram lingkaran pada posisi yang ditentukan dengan set data default:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Tetapkan Judul Diagram
Sesuaikan diagram Anda dengan menetapkan dan memusatkan judul:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Konfigurasi Label Data untuk Seri
Pastikan label data menampilkan nilai untuk kejelasan:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Siapkan Worksheet Data Diagram
Atur worksheet data diagram Anda dengan membersihkan seri dan kategori yang ada:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Tambahkan Kategori ke Diagram
Definisikan kategori untuk diagram lingkaran Anda:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Tambahkan Seri dan Isi Titik Data
Buat seri dan isi dengan titik data – inilah tempat kami **menambahkan seri diagram**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Sesuaikan Warna dan Garis Batas Seri
Tingkatkan daya tarik visual dengan menetapkan warna dan menyesuaikan garis batas – ini secara langsung **menyesuaikan warna diagram lingkaran**:
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
Sesuaikan label untuk masing‑masing titik data:
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

### Tetapkan Sudut Rotasi dan Simpan Presentasi
Selesaikan diagram lingkaran Anda dengan **menetapkan sudut rotasi** dan menyimpan file:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Masalah Umum dan Solusinya
| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **Semua irisan muncul dengan warna yang sama** | `setColorVaried(true)` tidak dipanggil | Pastikan Anda mengaktifkan warna beragam pada grup seri. |
| **Label data tidak muncul** | Flag `showValue` dinonaktifkan | Panggil `setShowValue(true)` pada format label yang sesuai. |
| **Rotasi tidak berpengaruh** | Menggunakan versi Aspose.Slides yang lebih lama | Tingkatkan ke versi 25.4 atau lebih baru. |
| **Pengecualian lisensi saat runtime** | File lisensi hilang atau tidak valid | Muat lisensi Anda dengan `License license = new License(); license.setLicense("Aspose.Slides.lic");` sebelum membuat `Presentation`. |

## Pertanyaan yang Sering Diajukan

**T: Bagaimana cara mendapatkan lisensi Aspose.Slides untuk Java?**  
J: Anda dapat meminta percobaan gratis dari situs Aspose, lalu membeli lisensi permanen. Muat lisensi tersebut pada runtime seperti yang ditunjukkan pada tabel Masalah Umum.

**T: Bisakah saya menggunakan kode ini dengan versi JDK yang lebih lama?**  
J: API memerlukan JDK 16 atau lebih tinggi; versi yang lebih lama tidak didukung.

**T: Apakah memungkinkan mengekspor diagram sebagai gambar alih‑alih PPTX?**  
J: Ya, panggil `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` setelah rendering.

**T: Bagaimana jika saya perlu menambahkan lebih dari satu seri ke diagram lingkaran?**  
J: Diagram lingkaran biasanya menampilkan satu seri; untuk beberapa seri pertimbangkan diagram donat sebagai gantinya.

**T: Apakah perpustakaan ini bekerja di server Linux?**  
J: Tentu – Aspose.Slides untuk Java bersifat platform‑independen dan berjalan di OS apa pun dengan JDK yang kompatibel.

---

**Terakhir Diperbarui:** 2026-02-19  
**Diuji Dengan:** Aspose.Slides untuk Java 25.4 (jdk16)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}