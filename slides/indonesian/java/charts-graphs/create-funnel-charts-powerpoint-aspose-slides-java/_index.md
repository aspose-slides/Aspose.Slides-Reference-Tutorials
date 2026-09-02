---
date: '2026-09-02'
description: Pelajari cara membuat diagram corong di PowerPoint menggunakan Aspose.Slides
  for Java. Panduan langkah demi langkah ini mencakup pengaturan data diagram, penyesuaian
  warna, dan mengekspor presentasi.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Pelajari cara membuat diagram corong di PowerPoint menggunakan Aspose.Slides
  for Java. Panduan ini memandu Anda melalui penyiapan data, penyesuaian warna, dan
  mengekspor presentasi akhir.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Buat diagram corong di PowerPoint dengan Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Buat diagram corong di PowerPoint dengan Aspose.Slides for Java
url: /id/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menguasai pembuatan diagram corong di PowerPoint dengan Aspose.Slides for Java

## Pendahuluan
Membuat presentasi yang menarik adalah seni yang memadukan visualisasi data, desain, dan storytelling. Salah satu visual yang kuat dan langsung memperjelas proses multi‑tahap adalah diagram corong. Baik Anda perlu menggambarkan pipeline penjualan, alur konversi, atau bottleneck produksi, diagram corong yang dirancang dengan baik mengubah angka mentah menjadi narasi yang intuitif. Dalam tutorial ini Anda akan belajar cara **membuat diagram corong** di PowerPoint secara programatis menggunakan Aspose.Slides for Java, mengonfigurasi datanya, menyesuaikan warna tiap segmen, dan mengekspor deck yang selesai.

**Apa yang akan Anda pelajari**
- Cara menambahkan Aspose.Slides for Java ke proyek Maven atau Gradle  
- Cara menginstansiasi objek `Presentation` dan mengakses slide‑nya  
- Cara menyisipkan diagram corong, mendefinisikan kategori, dan mengisi data seri  
- Cara menata setiap irisan corong dengan isian padat atau warna khusus merek  
- Cara menyimpan presentasi sebagai file PPTX atau mengekspor slide sebagai gambar  

## Jawaban Cepat
- **Apa perpustakaan utama untuk visualisasi data java?** Aspose.Slides for Java.  
- **Bagaimana cara membuat diagram corong di PowerPoint?** Panggil `slide.addChart(ChartType.Funnel, …)` pada slide target.  
- **API mana yang mengatur sumber data diagram?** Gunakan `IChartDataWorkbook` bersama dengan `chart.getChartData()`.  
- **Bisakah Anda menyesuaikan warna untuk tiap segmen corong?** Ya—atur `FillFormat.setFillType(FillType.Solid)` dan tetapkan `java.awt.Color`.  
- **Apakah Anda memerlukan lisensi untuk penggunaan produksi?** Lisensi Aspose.Slides yang dibeli diperlukan untuk penyebaran komersial.

## Apa itu visualisasi data Java?
Visualisasi data Java adalah praktik mengubah data mentah menjadi diagram, grafik, atau grafik interaktif langsung dari aplikasi Java. Aspose.Slides for Java adalah perpustakaan terkemuka yang memungkinkan pengembang menghasilkan lebih dari 100 tipe diagram—termasuk diagram corong—tanpa pernah meluncurkan PowerPoint secara manual, mendukung presentasi dengan hingga 500 slide sambil menjaga penggunaan memori tetap rendah.

## Mengapa menggunakan diagram corong di PowerPoint?
Diagram corong secara instan mengungkapkan tingkat penurunan antar tahapan berurutan, menjadikannya ideal untuk pipeline penjualan, analisis konversi, atau tinjauan efisiensi proses. Aspose.Slides memberi Anda kontrol pixel‑perfect atas tata letak, warna segmen, dan label data, sehingga Anda dapat mempertahankan konsistensi merek dan menghindari upaya manual mengedit diagram di UI PowerPoint.

## Prasyarat (H2)

### Perpustakaan yang diperlukan, versi, dan dependensi
Untuk mengimplementasikan Aspose.Slides for Java dalam proyek Anda, sertakan koordinat Maven atau Gradle yang sesuai. Perpustakaan ini bekerja dengan Java 8‑21 dan tidak memerlukan dependensi native eksternal.

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

Anda juga dapat mengunduh JAR secara langsung dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Persyaratan penyiapan lingkungan
Pastikan Anda memiliki JDK 8 atau yang lebih baru terpasang dan `JAVA_HOME` mengarah ke direktori JDK yang tepat. Aspose.Slides berjalan pada sistem operasi apa pun yang mendukung JDK, termasuk Windows, macOS, dan Linux.

### Prasyarat pengetahuan
Familiaritas dasar dengan sintaks Java, pemrograman berorientasi objek, dan konsep file presentasi akan membantu, namun potongan kode dijelaskan sepenuhnya untuk pengembang dengan tingkat pengalaman apa pun.

## Menyiapkan Aspose.Slides for Java (H2)

1. **Tambahkan dependensi** – Gunakan cuplikan Maven atau Gradle di atas.  
2. **Dapatkan lisensi** –  
   - **Uji coba gratis** – Unduh lisensi sementara dari [Aspose's website](https://purchase.aspose.com/temporary-license/) untuk evaluasi.  
   - **Lisensi penuh** – Beli lisensi produksi melalui [halaman pembelian](https://purchase.aspose.com/buy).  
3. **Inisialisasi dasar** –  

`Presentation` adalah kelas inti Aspose.Slides yang mewakili file PowerPoint dalam memori. Ia menyediakan akses ke slide, shape, dan objek diagram.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

Kode di atas membuat instance `Presentation` baru, siap untuk manipulasi slide, dan menjamin sumber daya dibebaskan dengan `dispose()`.

## Panduan Implementasi

Kami akan menelusuri setiap fitur yang diperlukan untuk membangun diagram corong lengkap, menambahkan teks penjelasan singkat sebelum setiap placeholder kode.

### Fitur 1: membuat presentasi (H2)

#### Ikhtisar
Mulailah dengan membuat instance kelas `Presentation`. Objek ini adalah titik masuk untuk semua operasi selanjutnya.

`Presentation` adalah objek tingkat‑atas Aspose.Slides yang menyimpan koleksi slide dan pengaturan dokumen global.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

Cuplikan ini membuka presentasi kosong, yang kemudian dapat Anda simpan sebagai file `.pptx`.

### Fitur 2: menambahkan diagram corong ke slide (H2)

#### Ikhtisar
Sisipkan diagram corong pada slide pertama, tentukan ukurannya, dan atur tipe diagram.

`ChartType.Funnel` memberi tahu Aspose.Slides untuk merender visualisasi bergaya corong alih‑alih diagram batang atau garis.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

Pemanggilan `addChart` membuat shape diagram, menempatkannya pada titik `(50, 50)`, dan memberi lebar `500` serta tinggi `400`.

### Fitur 3: membersihkan data diagram (H2)

#### Ikhtisar
Sebelum mengisi diagram, bersihkan semua kategori placeholder atau seri yang mungkin ada pada templat.

`chart.getChartData().getCategories().clear()` menghapus semua entri kategori yang ada, sementara `chart.getChartData().getSeries().clear()` menghapus semua seri yang telah terisi sebelumnya.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

Ini memastikan kanvas bersih sehingga data khusus Anda muncul persis seperti yang diharapkan.

### Fitur 4: menyiapkan workbook data diagram (H2)

#### Ikhtisar
Objek `IChartDataWorkbook` menyimpan nilai mentah yang menggerakkan diagram. Menginisialisasinya memungkinkan Anda menulis data langsung ke sel.

`IChartDataWorkbook` adalah spreadsheet ringan dalam memori yang digunakan Aspose.Slides untuk memberi data pada seri dan kategori diagram.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

Kode ini menghapus semua sel yang ada, menyiapkan workbook untuk entri baru.

### Fitur 5: menambahkan kategori ke diagram (H2)

#### Ikhtisar
Definisikan label teks yang muncul di sisi kiri corong—ini mewakili tiap tahapan proses Anda.

`chart.getChartData().getCategories().add()` membuat objek kategori baru yang terhubung ke sel workbook tertentu.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Di sini kami menambahkan tiga tahapan: “Prospects”, “Qualified Leads”, dan “Closed Deals”.

### Fitur 6: menambahkan seri data ke diagram (H2)

#### Ikhtisar
Isi corong dengan nilai numerik dan opsional beri warna unik pada tiap irisan.

`IDataPoint` mewakili satu titik data dalam seri diagram.  

`chart.getChartData().getSeries().add()` membuat seri yang menampung titik data numerik; tiap `IDataPoint` dapat menerima warna isian sendiri.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

Loop ini menunjukkan cara mengatur isian padat untuk tiap poin, menggunakan konstanta `java.awt.Color` khusus merek atau warna acak untuk variasi visual.

## Kasus penggunaan umum & tips (H2)

- **Pelaporan pipeline penjualan** – Tampilkan berapa banyak prospek yang bergerak dari tahap prospect ke closed‑won di tiap tahapan.  
- **Analisis efisiensi proses** – Visualisasikan kehilangan material atau penundaan waktu di tiap langkah manufaktur.  
- **Tinjauan funnel pemasaran** – Bandingkan tingkat konversi antar kampanye atau sumber lalu lintas.  

**Tips pro:** Alih‑alih menggunakan warna acak, gunakan palet merek perusahaan Anda (misalnya `new Color(0, 112, 192)`) untuk menjaga konsistensi presentasi dengan aset pemasaran lainnya.

## Pertanyaan yang sering diajukan (H2)

**T: Bagaimana cara mengubah orientasi diagram corong?**  
J: Atur properti `ChartOrientation` pada objek `IChart` ke `ChartOrientation.Vertical` atau `ChartOrientation.Horizontal`.

**T: Bisakah saya mengekspor slide sebagai gambar setelah menambahkan diagram?**  
J: Ya—panggil `pres.getSlides().get_Item(0).getThumbnail(1, 1)` dan tulis `java.awt.image.BufferedImage` yang dihasilkan ke file PNG atau JPEG.

**T: Bagaimana jika saya memerlukan lebih dari tiga kategori?**  
J: Cukup tambahkan kategori tambahan menggunakan `chart.getChartData().getCategories().add(...)` dan sediakan titik data yang cocok untuk tiap kategori baru.

**T: Apakah ada cara menyembunyikan legenda?**  
J: Gunakan `chart.getChartTitle().setVisible(false)` dan `chart.getLegend().setVisible(false)` untuk menghilangkan judul dan legenda dari visual.

**T: Apakah saya memerlukan lisensi untuk build pengembangan?**  
J: Lisensi sementara cukup untuk evaluasi; lisensi komersial penuh diperlukan untuk penyebaran produksi.

---

**Terakhir diperbarui:** 2026-09-02  
**Diuji dengan:** Aspose.Slides for Java 25.4 (jdk16)  
**Penulis:** Aspose

## Tutorial Terkait

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Edit PowerPoint Chart Data Using Aspose.Slides for Java: A Comprehensive Guide](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}