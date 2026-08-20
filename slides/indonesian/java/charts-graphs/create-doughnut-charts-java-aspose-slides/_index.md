---
date: '2026-08-16'
description: Pelajari cara menambahkan diagram donat di Java menggunakan Aspose.Slides.
  Panduan langkah demi langkah ini mencakup penyiapan dependensi Maven, konfigurasi
  diagram, warna, label, dan penyimpanan file PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Cara menambahkan diagram donat di Java menggunakan Aspose.Slides.
  Ikuti panduan ini untuk menyiapkan Maven, menyesuaikan warna, label, dan menghasilkan
  file PPTX.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Cara menambahkan diagram donat di Java dengan Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Cara menambahkan diagram donat di Java dengan Aspose.Slides
url: /id/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara menambahkan diagram donat di Java dengan Aspose.Slides

## Pendahuluan

Membuat **diagram donat** secara programatik dapat mengubah angka mentah menjadi visual yang menarik dan langsung menceritakan sebuah kisah. Di Java, **Aspose.Slides** membuat proses ini sederhana, memungkinkan Anda menghasilkan diagram siap presentasi tanpa harus membuka PowerPoint. Dalam tutorial ini Anda akan belajar **cara menambahkan diagram donat** ke file PPTX langkah demi langkah— mulai dari menyiapkan dependensi Maven Aspose Slides hingga menyesuaikan seri, kategori, warna, dan label, serta akhirnya menyimpan presentasi.

Pada akhir panduan ini Anda akan dapat menyematkan diagram donat dinamis ke dalam file PPTX apa pun, cocok untuk laporan, dasbor, atau deck slide otomatis.

### Jawaban Cepat
- **Perpustakaan apa yang digunakan?** Aspose.Slides for Java  
- **Tugas utama?** Add a doughnut chart in a PPTX file  
- **Bagaimana cara menambahkan perpustakaan?** Use the Maven Aspose Slides dependency (or Gradle)  
- **Versi Java minimum?** JDK 16 or higher  
- **Bisakah saya menyesuaikan warna dan label?** Yes, the API provides full formatting control  

## Apa itu diagram donat dan mengapa menggunakannya?

Diagram donat adalah variasi dari diagram pai dengan pusat yang kosong, memungkinkan beberapa seri data ditampilkan sebagai cincin konsentris. **Diagram ini memvisualisasikan bagian‑dari‑keseluruhan di beberapa kategori sambil mempertahankan ruang untuk informasi tambahan di tengah.** Hal ini membuatnya ideal untuk membandingkan penjualan per wilayah selama beberapa kuartal, alokasi anggaran antar departemen, atau skenario apa pun di mana Anda perlu menampilkan data proporsi hierarkis.

## Mengapa menggunakan Aspose.Slides untuk Java?

Anda dapat menambahkan diagram donat tanpa menginstal Microsoft Office, dan perpustakaan ini memproses **lebih dari 50 + format input dan output** sambil menangani presentasi yang melebihi 500 slide. Aspose.Slides memberikan **rendering hingga 3× lebih cepat** dibandingkan otomatisasi Office native pada perangkat keras yang sama, dan dapat berjalan di Windows, Linux, dan macOS. Manfaat terukur ini berarti Anda dapat menghasilkan deck slide besar di server tanpa tampilan (headless) dengan kinerja yang dapat diprediksi.

## Prasyarat

- **Perpustakaan yang dibutuhkan**  
  - Aspose.Slides for Java 25.4 or later (the library that enables you to add doughnut charts).  

- **Lingkungan**  
  - JDK 16 or higher installed on your machine.  
  - An IDE such as IntelliJ IDEA, Eclipse or NetBeans.  

- **Pengetahuan**  
  - Basic Java syntax and object‑oriented concepts.  
  - Familiarity with Maven or Gradle for dependency management.  

## Dependensi Maven Aspose Slides

Tambahkan dependensi Maven berikut ke `pom.xml` Anda. Ini adalah **dependensi maven aspose slides** yang Anda perlukan untuk memasukkan perpustakaan ke dalam proyek Anda.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Jika Anda lebih suka Gradle, gunakan potongan kode setara di bawah ini.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Anda juga dapat mengunduh JAR secara langsung dari halaman rilis resmi:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Mendapatkan lisensi

Untuk menghapus watermark evaluasi dan membuka semua fitur:

- **Uji coba gratis** – mulai dengan lisensi sementara.  
- **Lisensi sementara** – minta satu dari [situs Aspose](https://purchase.aspose.com/temporary-license/).  
- **Lisensi komersial** – beli untuk penggunaan produksi.

Terapkan lisensi dalam kode Anda:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Panduan Implementasi

### Menginisialisasi presentasi dan menambahkan diagram donat

`Presentation` adalah kelas Aspose.Slides yang mewakili presentasi PowerPoint.  
Muat PPTX yang ada atau buat objek `Presentation` baru, lalu tambahkan diagram donat ke slide pertama.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Mengonfigurasi workbook data diagram dan membersihkan data yang ada

Workbook adalah spreadsheet internal yang menyimpan data diagram.  
Dapatkan workbook yang mendasari diagram, lalu bersihkan semua seri atau kategori default sehingga Anda dapat memulai dengan kondisi bersih.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Menambahkan seri ke diagram

Sebuah seri mewakili kumpulan titik data yang dipetakan pada diagram.  
Anda dapat menambahkan hingga 15 seri. Setiap seri dapat disesuaikan—di sini kami mengatur ledakan, ukuran lubang donat, dan sudut irisan pertama.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Menambahkan kategori dan titik data

Kategori adalah label untuk setiap titik data sepanjang sumbu diagram.  
Buat 15 kategori dan isi setiap seri dengan satu titik data. Seri terakhir menerima pemformatan label khusus.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Menyesuaikan warna dan label data

`FillType.Solid` menentukan warna isi padat untuk elemen diagram.  
Atur warna isi padat untuk setiap seri dan aktifkan label data. Untuk seri terakhir kami juga mengubah warna font label.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Menyimpan presentasi

`save` menulis presentasi ke file dalam format yang dipilih.  
Tuliskan presentasi yang diperbarui ke disk dalam format PPTX, atau ekspor ke PDF jika diperlukan.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Masalah umum dan solusi

- **Lisensi tidak ditemukan** – Verifikasi bahwa jalur ke `license.lic` sudah benar dan file dapat dibaca.  
- **Diagram muncul kosong** – Pastikan Anda telah membersihkan seri/kategori yang ada sebelum menambahkan yang baru.  
- **Warna tidak tepat** – Pastikan `FillType.Solid` diatur untuk format isi dan garis.  
- **Kinerja dengan banyak seri** – Batasi jumlah seri/kategori atau gunakan kembali sel workbook untuk menjaga penggunaan memori tetap terkendali.  

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menghasilkan diagram donat tanpa file PPTX yang sudah ada?**  
A: Ya, buat instance `new Presentation()` untuk memulai dari deck slide kosong, lalu tambahkan diagram seperti yang ditunjukkan di atas.

**Q: Apakah Aspose.Slides mendukung ekspor ke PDF?**  
A: Tentu saja. Setelah membuat diagram, panggil `pres.save("output.pdf", SaveFormat.Pdf);` untuk mendapatkan versi PDF dari slide.

**Q: Bagaimana cara mengubah ukuran lubang donat?**  
A: Gunakan `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` dimana `value` berada dalam rentang 0 hingga 100.

**Q: Apakah memungkinkan menambahkan label data ke semua seri, bukan hanya yang terakhir?**  
A: Ya, pindahkan blok pemformatan label keluar dari kondisi `if (i == ...)` dan terapkan ke setiap `dataPoint`.

**Q: Versi Java apa yang didukung?**  
A: Aspose.Slides 25.4 mendukung JDK 16 dan yang lebih baru. JDK yang lebih lama memerlukan classifier yang sesuai dalam dependensi Maven.

---

**Terakhir Diperbarui:** 2026-08-16  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Penulis:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

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

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Tutorial Terkait

- [Cara Menambahkan Diagram ke PowerPoint Menggunakan Aspose.Slides untuk Java: Panduan Langkah‑Demi‑Langkah](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Cara Menyesuaikan Warna Diagram Pai di Java dengan Aspose.Slides – Panduan Lengkap](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Animasi Kategori Diagram PowerPoint dengan Aspose.Slides untuk Java | Panduan Langkah‑Demi‑Langkah](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}