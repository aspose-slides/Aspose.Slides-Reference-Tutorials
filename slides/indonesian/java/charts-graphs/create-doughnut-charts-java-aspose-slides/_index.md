---
date: '2026-03-07'
description: Pelajari cara membuat diagram donat di Java menggunakan Aspose.Slides.
  Panduan langkah demi langkah ini mencakup penyiapan dependensi Maven Aspose Slides,
  konfigurasi diagram, dan penyimpanan presentasi.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Panduan Membuat Diagram Donat Java dengan Aspose.Slides
url: /id/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Buat Diagram Donat Java dengan Panduan Aspose.Slides

## Introduction

Membuat **doughnut chart** secara programatik dapat mengubah angka mentah menjadi visual yang menarik dan langsung menceritakan sebuah kisah. Di Java, **Aspose.Slides** membuat proses ini sederhana, memungkinkan Anda menghasilkan diagram siap presentasi tanpa harus membuka PowerPoint. Dalam tutorial ini Anda akan belajar cara **create doughnut chart java** langkah demi langkah— mulai dari menyiapkan dependensi Maven Aspose Slides hingga menyesuaikan series, kategori, dan akhirnya menyimpan presentasi.

Pada akhir panduan ini Anda akan dapat menyematkan diagram donat dinamis ke dalam file PPTX apa pun, sempurna untuk laporan, dasbor, atau deck slide otomatis.

### Quick Answers
- **Perpustakaan apa yang digunakan?** Aspose.Slides for Java  
- **Tugas utama?** Create doughnut chart java in a PPTX file  
- **Bagaimana cara menambahkan perpustakaan?** Use the Maven Aspose Slides dependency (or Gradle)  
- **Versi Java minimum?** JDK 16 or higher  
- **Bisakah saya menyesuaikan warna dan label?** Yes, the API provides full formatting control  

## Apa itu Diagram Donat dan Mengapa Menggunakannya?

Diagram donat adalah variasi dari diagram pai dengan pusat yang kosong, memungkinkan Anda menampilkan beberapa seri data dalam cincin konsentrik. Ini menjadikannya ideal untuk membandingkan bagian dari keseluruhan di beberapa kategori—misalnya penjualan per wilayah selama beberapa kuartal atau alokasi anggaran antar departemen.

## Mengapa Menggunakan Aspose.Slides untuk Java?

- **Tidak memerlukan instalasi Office** – menghasilkan file PPTX di server mana pun.  
- **Rich API** – kontrol penuh atas tipe diagram, titik data, dan styling.  
- **High performance** – dioptimalkan untuk presentasi besar.  
- **Cross‑platform** – bekerja di Windows, Linux, dan macOS.

## Prerequisites

- **Perpustakaan yang Diperlukan:**  
  - Aspose.Slides for Java versi 25.4 atau lebih baru.  

- **Pengaturan Lingkungan:**  
  - JDK 16 atau lebih tinggi.  
  - IDE favorit Anda (IntelliJ IDEA, Eclipse, NetBeans, dll.).  

- **Prasyarat Pengetahuan:**  
  - Pemrograman Java dasar.  
  - Familiaritas dengan Maven atau Gradle untuk manajemen dependensi.

## Maven Aspose Slides Dependency

Tambahkan dependensi Maven berikut ke `pom.xml` Anda. Ini adalah **maven aspose slides dependency** yang Anda perlukan untuk menarik perpustakaan ke dalam proyek.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Jika Anda lebih suka Gradle, gunakan cuplikan setara di bawah ini.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Anda juga dapat mengunduh JAR secara langsung dari halaman rilis resmi:  
[ Rilis Aspose.Slides untuk Java ](https://releases.aspose.com/slides/java/)

### Mendapatkan Lisensi

Untuk menghapus watermark evaluasi dan membuka seluruh set fitur:

- **Free trial** – mulai dengan lisensi sementara.  
- **Temporary license** – minta satu dari [Aspose website](https://purchase.aspose.com/temporary-license/).  
- **Commercial license** – beli untuk penggunaan produksi.

Terapkan lisensi dalam kode Anda:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Implementation Guide

### Initializing Presentation and Adding a Doughnut Chart

Pertama, buat atau muat sebuah presentasi dan tambahkan diagram donat ke slide pertama.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configuring the Chart Data Workbook and Clearing Existing Data

Selanjutnya, dapatkan workbook yang mendasari diagram dan bersihkan semua series atau kategori default.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Adding Series to the Chart

Sekarang kita akan menambahkan hingga 15 series. Setiap series dapat disesuaikan—di sini kami mengatur ledakan, ukuran lubang donat, dan sudut irisan pertama.

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Adding Categories and Data Points

Kami akan membuat 15 kategori dan mengisi setiap series dengan satu titik data. Series terakhir menerima format label khusus.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Saving the Presentation

Akhirnya, tulis presentasi yang telah diperbarui ke disk.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Common Issues and Solutions

- **License not found** – Verifikasi bahwa jalur ke `license.lic` sudah benar dan file dapat dibaca.  
- **Chart appears blank** – Pastikan Anda telah membersihkan series/kategori yang ada sebelum menambahkan yang baru.  
- **Incorrect colors** – Periksa bahwa `FillType.Solid` telah diatur untuk format isi dan garis.  
- **Performance with many series** – Batasi jumlah series/kategori atau gunakan kembali sel workbook.

## Frequently Asked Questions

**Q: Bisakah saya menghasilkan diagram donat tanpa file PPTX yang sudah ada?**  
A: Ya, instantiate `new Presentation()` untuk memulai dari deck slide kosong.

**Q: Apakah Aspose.Slides mendukung ekspor ke PDF?**  
A: Tentu saja. Setelah membuat diagram, panggil `pres.save("output.pdf", SaveFormat.Pdf);`.

**Q: Bagaimana cara mengubah ukuran lubang donat?**  
A: Gunakan `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` dimana nilai berada di antara 0‑100.

**Q: Apakah memungkinkan menambahkan label data ke semua series, bukan hanya yang terakhir?**  
A: Ya, pindahkan blok format label keluar dari kondisi `if (i == ...)` dan terapkan ke setiap `dataPoint`.

**Q: Versi Java apa yang didukung?**  
A: Aspose.Slides 25.4 mendukung JDK 16 dan yang lebih baru. JDK sebelumnya memerlukan classifier yang sesuai.

---

**Terakhir Diperbarui:** 2026-03-07  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}