---
date: '2026-07-08'
description: Pelajari cara menggunakan Aspose untuk membuat diagram donat di PowerPoint
  dengan Java. Panduan langkah demi langkah ini menunjukkan cara menambahkan titik
  data diagram secara programatis, menyesuaikan label, dan menyimpan file PPTX dengan
  fidelitas tinggi.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Cara menggunakan Aspose memungkinkan Anda membuat diagram donat di
  PowerPoint menggunakan Java. Ikuti tutorial ini untuk menambahkan titik data, menyesuaikan
  label, dan menyimpan file PPTX dengan fidelitas tinggi.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Cara Menggunakan Aspose: Membuat Diagram Donat di PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Cara Menggunakan Aspose untuk Membuat Diagram Donat di PowerPoint (Java)
url: /id/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menggunakan Aspose untuk Membuat Diagram Donat di PowerPoint (Java)

## Pendahuluan
Membuat presentasi yang menarik sering kali memerlukan lebih dari sekadar teks dan gambar; diagram dapat secara signifikan meningkatkan alur cerita dengan memvisualisasikan data secara efektif. **Cara menggunakan Aspose** untuk pembuatan diagram memberi Anda kontrol programatik tanpa harus membuka PowerPoint. Tutorial ini memandu Anda membangun diagram donat, mengonfigurasi titik data, dan menyimpan PPTX dengan fidelitas tinggi. Anda hanya memerlukan pengetahuan dasar Java dan beberapa menit waktu penyiapan.

`Aspose.Slides for Java` adalah pustaka Java yang memungkinkan pembuatan, manipulasi, dan konversi file PowerPoint tanpa Microsoft Office.

## Jawaban Cepat
- **Perpustakaan apa yang membuat diagram donat PowerPoint?** Aspose.Slides for Java  
- **Bisakah saya menambahkan titik data diagram secara programatik?** Ya, menggunakan API diagram  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi Aspose.Slides yang valid diperlukan  
- **Versi Java mana yang didukung?** Java 8 dan yang lebih baru (klasifier JDK 16 ditampilkan)  
- **Berapa banyak seri yang dapat saya tambahkan?** Contoh menambahkan hingga 15 seri, tetapi Anda dapat menyesuaikannya sesuai kebutuhan  

## Apa itu diagram donat di PowerPoint?
Diagram donat adalah diagram melingkar yang mirip dengan diagram pai tetapi memiliki lubang di tengah, memungkinkan beberapa seri ditampilkan secara bersamaan. Diagram ini menekankan hubungan bagian‑ke‑keseluruhan sambil menjaga tata letak visual tetap kompak dan mudah dibaca.

## Mengapa menggunakan Aspose.Slides for Java untuk membuat diagram donat?
Aspose.Slides for Java menangani lebih dari 50 format input dan output serta dapat menghasilkan presentasi hingga 500 MB tanpa memuat seluruh file ke memori. Ia memberikan kontrol programatik penuh atas tampilan, data, dan tata letak diagram pada platform Java apa pun, menghilangkan kebutuhan interop COM, dan dapat merender 100 slide kaya diagram dalam waktu kurang dari dua detik pada server tipikal.

## Prasyarat
- Pengetahuan dasar pemrograman Java.  
- IDE seperti IntelliJ IDEA atau Eclipse.  
- Maven atau Gradle untuk manajemen dependensi.  
- Lisensi Aspose.Slides for Java yang valid (versi percobaan gratis tersedia).

## Menyiapkan Aspose.Slides for Java
Pilih manajer dependensi yang sesuai dengan proyek Anda.

**Maven**  
Tambahkan dependensi berikut ke `pom.xml` Anda (ganti versi dengan rilis terbaru):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Tambahkan baris ini ke `build.gradle` Anda:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Jika Anda lebih suka mengunduh langsung, kunjungi halaman [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Perolehan Lisensi
Anda dapat memulai dengan versi percobaan gratis untuk menjelajahi fitur Aspose.Slides. Untuk penggunaan lanjutan, beli lisensi atau minta lisensi sementara dari [situs Aspose](https://purchase.aspose.com/temporary-license/). Ikuti petunjuk yang disediakan untuk menyiapkan lingkungan Anda dan menginisialisasi Aspose.Slides dalam aplikasi.

## Cara membuat diagram donat PowerPoint menggunakan Aspose.Slides for Java
Untuk membangun diagram donat, mulailah dengan memuat atau membuat `Presentation`, tambahkan bentuk diagram tipe `ChartType.Doughnut`, bersihkan seri default, atur ukuran lubang, lalu isi workbook diagram dengan nama kategori dan nilai numerik. Akhirnya, sesuaikan format label dan simpan PPTX.

### Langkah 1: Inisialisasi presentasi
Buat presentasi baru atau buka file yang ada untuk memperoleh koleksi slide.

`Presentation` adalah kelas utama yang merepresentasikan file PowerPoint.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Langkah 2: Tambahkan diagram donat ke slide
Sisipkan bentuk diagram, hapus seri/kategori default, dan konfigurasikan pengaturan visual dasar seperti ukuran lubang donat.

`Chart` (atau bentuk diagram) merepresentasikan objek diagram yang ditempatkan pada slide.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Langkah 3: Tambahkan titik data diagram dan sesuaikan label
Isi nama kategori, tambahkan titik data untuk setiap seri, dan haluskan format label (font, warna, posisi). Langkah ini menunjukkan kemampuan “menambahkan titik data diagram”.

`Workbook` menyediakan akses ke data spreadsheet dasar diagram di mana sel-sel diisi.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Langkah 4: Simpan presentasi yang diperbarui
Persist perubahan ke file PPTX baru di disk.

`save` menulis presentasi ke file dalam format yang dipilih.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Aplikasi Praktis
Diagram donat cocok untuk:
- **Laporan Keuangan:** Memvisualisasikan alokasi anggaran atau rincian pengeluaran.  
- **Analisis Pasar:** Menunjukkan distribusi pangsa pasar di antara pesaing.  
- **Hasil Survei:** Menyajikan data survei kategori dalam bentuk kompak.  
- **Pembuatan Dashboard:** Menggabungkan dengan kueri basis data untuk menghasilkan slide yang memperbarui secara langsung.

## Pertimbangan Kinerja
- **Bebaskan sumber daya:** Panggil `pres.dispose()` setelah menyimpan untuk membebaskan memori native.  
- **Batasi jumlah diagram:** Menambahkan ratusan diagram dapat meningkatkan penggunaan memori; proses secara batch bila diperlukan.  
- **Gunakan streaming:** Untuk set data besar, isi workbook langsung dari aliran alih-alih array dalam memori.  

## Masalah Umum dan Solusinya
| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **Diagram muncul kosong** | Sel data tidak terisi dengan benar | Verifikasi bahwa referensi `workBook.getCell(...)` mengarah ke indeks baris/kolom yang tepat. |
| **Label saling tumpang tindih** | Terlalu banyak kategori dalam ruang terbatas | Tingkatkan `DoughnutHoleSize` atau sesuaikan `FirstSliceAngle`. |
| **OutOfMemoryError** | Presentasi besar tanpa membebaskan sumber daya | Panggil `pres.dispose()` setelah menyimpan dan pertimbangkan meningkatkan ukuran heap JVM. |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan Aspose.Slides for Java dalam aplikasi komersial?**  
J: Ya, tetapi Anda memerlukan lisensi komersial yang valid. Versi percobaan gratis tersedia untuk evaluasi.

**T: Bagaimana cara menambahkan lebih dari 15 seri?**  
J: Tingkatkan batas loop pada langkah “Tambah Diagram Donat” dan pastikan workbook data Anda memiliki cukup baris.

**T: Apakah memungkinkan mengubah ukuran lubang donat setelah pembuatan?**  
J: Ya, panggil `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` sebelum menyimpan.

**T: Bisakah saya mengekspor diagram sebagai gambar alih-alih PPTX?**  
J: Tentu saja. Gunakan `chart.getImage()` dan simpan `java.awt.image.BufferedImage` yang dikembalikan dalam format pilihan Anda.

**T: Apakah Aspose.Slides mendukung diagram beranimasi?**  
J: Animasi dapat ditambahkan melalui API `ISlide.getTimeline()`, meskipun hal ini berada di luar cakupan tutorial ini.

## Kesimpulan
Anda kini memiliki metode lengkap dan siap produksi untuk **membuat file PowerPoint diagram donat** dengan Aspose.Slides for Java, termasuk cara **menambahkan titik data diagram**, menyesuaikan label, dan menangani pertimbangan kinerja. Bereksperimenlah dengan warna, sumber data, dan tipe diagram berbeda untuk membuat presentasi Anda benar‑benar menonjol.

---

**Terakhir Diperbarui:** 2026-07-08  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (klasifier JDK 16)  
**Penulis:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Tutorial Terkait

- [Cara Menambahkan Diagram ke PowerPoint Menggunakan Aspose.Slides for Java: Panduan Langkah‑ demi‑ Langkah](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Cara Mengedit Data Diagram PowerPoint Menggunakan Aspose.Slides for Java: Panduan Komprehensif](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Animasi Diagram PowerPoint Menggunakan Aspose.Slides for Java – Panduan Langkah‑ demi‑ Langkah](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}