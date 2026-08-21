---
date: '2026-08-21'
description: Pelajari cara membuat box plot java menggunakan Aspose.Slides, menambahkan
  chart ke slide, dan menghasilkan chart box‑and‑whisker di PowerPoint. Ideal untuk
  pengembang Java.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: Pelajari cara membuat box plot java menggunakan Aspose.Slides, menambahkan
  chart ke slide, dan menghasilkan chart box‑and‑whisker di PowerPoint. Sempurna untuk
  pengembang Java.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: Cara membuat box plot java dengan Aspose.Slides untuk PowerPoint
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: Cara membuat box plot java dengan Aspose.Slides untuk PowerPoint
url: /id/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Box Plot Java dengan Aspose.Slides untuk PowerPoint

Dalam panduan ini Anda akan **membuat box plot java** dengan Aspose.Slides, lalu menyematkan diagram langsung ke slide PowerPoint. Membuat diagram box‑and‑whisker secara programatik memungkinkan Anda mengubah data statistik mentah menjadi wawasan visual yang jelas tanpa meninggalkan kode Java Anda. Jika Anda perlu mengotomatiskan pelaporan PowerPoint, Aspose.Slides untuk Java menyediakan API yang andal dan berperforma tinggi.

## Apa yang akan Anda pelajari

- Menyiapkan lingkungan Anda untuk Aspose.Slides for Java
- Langkah-langkah untuk **menambahkan diagram ke slide** dan menghasilkan diagram box‑whisker di PowerPoint menggunakan Java
- Praktik terbaik untuk mengoptimalkan kinerja saat bekerja dengan Aspose.Slides
- Aplikasi dunia nyata dari diagram box‑and‑whisker

## Jawaban Cepat
- **Perpustakaan apa yang membuat box plot di Java?** Aspose.Slides for Java.  
- **Jenis diagram apa yang digunakan?** `ChartType.BoxAndWhisker`.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya menambahkan beberapa seri?** Ya – ulangi blok pembuatan seri untuk setiap kumpulan data.  
- **Format apa file akhir?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## Apa itu box plot dan mengapa menggunakannya di Java?

Diagram box‑and‑whisker (sering disebut *box plot*) memvisualisasikan distribusi data—median, kuartil, dan outlier—dalam bentuk yang kompak. Di Java, menghasilkan diagram ini secara programatik memungkinkan Anda menyematkan wawasan statistik langsung ke dalam deck PowerPoint, menghilangkan kebutuhan pembuatan diagram manual. Ini sangat berguna untuk membandingkan distribusi di berbagai kategori, seperti nilai ujian antar kelas atau angka penjualan antar wilayah. Dengan menghasilkan diagram di Java, Anda dapat mengintegrasikannya ke dalam pipeline pelaporan otomatis, memastikan data terbaru selalu tercermin dalam presentasi Anda.

## Mengapa menambahkan diagram ke slide dengan Aspose.Slides?

Aspose.Slides menyederhanakan detail OpenXML tingkat rendah, memberikan Anda API yang fluida untuk membuat, menata, dan mengekspor diagram. Ini berarti Anda dapat mengotomatisasi pembuatan laporan, menghasilkan branding yang konsisten, dan mengintegrasikan diagram ke dalam alur kerja Java yang lebih besar. Perpustakaan ini juga mendukung opsi penataan seperti warna, font, dan marker, memungkinkan Anda menyesuaikan dengan identitas perusahaan. Selain itu, ia menangani tugas kompleks seperti binding data dan penyegaran diagram tanpa memerlukan Microsoft Office.

## Cara menambahkan diagram slide dengan Java menggunakan Aspose.Slides?

Muat atau buat sebuah `Presentation`, sisipkan `Chart` bertipe `BoxAndWhisker`, beri data Anda, dan simpan file—semua dalam beberapa baris kode Java. API menangani tata letak, skala, dan rendering, sehingga Anda tidak perlu memanipulasi XML secara manual. Anda juga dapat mengatur judul diagram dan label sumbu secara programatik untuk memberikan konteks kepada pemirsa.

## Prasyarat

- **Java Development Kit (JDK)**: JDK 8 atau lebih tinggi.  
- **Aspose.Slides for Java Library**: Diperlukan untuk manipulasi PowerPoint.  
- **IDE**: IntelliJ IDEA, Eclipse, atau editor Java lainnya.

## Menyiapkan Aspose.Slides untuk Java

Tambahkan perpustakaan sebagai dependensi Maven, Gradle, atau manual.

### Maven

Tambahkan dependensi berikut di `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Di `build.gradle` Anda, sertakan:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduhan Langsung

Sebagai alternatif, unduh versi terbaru dari [rilis Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/).

#### Akuisisi Lisensi

- **Versi percobaan gratis** – jelajahi fitur tanpa biaya.  
- **Lisensi sementara** – gunakan untuk evaluasi jangka pendek.  
- **Pembelian** – buka semua fungsi untuk beban kerja produksi.

Untuk menginisialisasi Aspose.Slides, pastikan JAR berada di classpath Anda dan atur file lisensi apa pun sebagaimana dijelaskan dalam dokumentasi.

## Panduan Implementasi

Berikut adalah walkthrough langkah‑demi‑langkah. Setiap blok dijelaskan sebelum potongan kode sehingga Anda tahu persis apa yang dilakukannya.

### Apa itu kelas `Presentation`?

Kelas `Presentation` adalah objek pusat di Aspose.Slides yang mewakili seluruh file PowerPoint dalam memori. Ia memberikan akses ke slide, diagram, bentuk, dan elemen slide lainnya, memungkinkan Anda membuat, memodifikasi, dan menyimpan presentasi secara programatik. Dengan menggunakan kelas ini, Anda dapat menambahkan slide baru, menyisipkan gambar, dan mengatur urutan slide dengan panggilan API sederhana.

### Langkah 1: buat atau buka presentasi

Pertama, buka file PPTX yang ada atau buat yang baru:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Pro tip:** Jika file tidak ada, Aspose.Slides akan secara otomatis membuat presentasi kosong baru.

### Langkah 2: tambahkan diagram box‑and‑whisker ke slide

Tempatkan diagram di lokasi yang Anda butuhkan dengan menentukan posisi dan ukuran (dalam poin):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Langkah 3: bersihkan data yang ada

Sebelum memberi data baru, hapus semua kategori atau seri placeholder:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Langkah 4: konfigurasikan kategori

Tambahkan kategori (label sumbu X) yang akan muncul di bawah setiap kotak:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Catatan:** Sesuaikan teks label agar cocok dengan domain data Anda (misalnya, “Q1”, “Product A”).

### Langkah 5: buat dan sesuaikan seri

Sekarang buat sebuah seri, atur opsi visual, dan beri titik data numerik:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Anda dapat mengganti array `int[] data` dengan nilai yang dibaca dari basis data, file CSV, atau sumber lain apa pun.

### Langkah 6: simpan presentasi

Persist perubahan ke file PPTX baru:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Langkah 7: bersihkan sumber daya

Selalu dispose objek `Presentation` untuk membebaskan sumber daya native:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Aplikasi Praktis

Diagram box‑and‑whisker sangat berharga dalam analisis statistik dan penyajian data. Berikut beberapa skenario di mana mereka bersinar:

1. **Analisis keuangan** – visualisasikan distribusi pendapatan di seluruh wilayah.  
2. **Kontrol kualitas** – temukan outlier dalam pengukuran manufaktur.  
3. **Penelitian akademik** – tunjukkan variabilitas hasil eksperimen.  
4. **Riset pasar** – bandingkan kinerja produk di berbagai demografis.

Menyematkan diagram ini langsung ke dalam deck PowerPoint memungkinkan pemangku kepentingan memahami data kompleks sekilas.

## Pertimbangan Kinerja

Aspose.Slides dapat menangani presentasi dengan **500+ slide** dan diagram dengan **100 000+ titik data** sambil menjaga penggunaan memori di bawah 200 MB pada server tipikal. Untuk tetap berada dalam batas tersebut:

- **Manajemen memori** – segera dispose objek `Presentation`.  
- **Penanganan data** – muat hanya data yang diperlukan; hindari memasukkan set data besar secara langsung ke workbook diagram.  
- **Pemuat malas** – saat menghasilkan banyak slide, buat diagram hanya untuk yang akan ditampilkan.

## Masalah Umum dan Solusinya

| Masalah | Penyebab | Solusi |
|-------|-------|----------|
| **Diagram muncul kosong** | Sel data tidak terisi dengan benar | Verifikasi bahwa `wb.getCell` merujuk ke baris/kolom yang benar dan nilai tidak `null`. |
| **Outlier tidak ditampilkan** | `setShowOutlierPoints` diatur ke `false` | Pastikan `series.setShowOutlierPoints(true)` dipanggil. |
| **Kebocoran memori** | Presentation tidak di-dispose | Selalu bungkus penggunaan dalam `try/finally` dan panggil `dispose()`. |
| **Kuartil tidak tepat** | Menggunakan metode `Inclusive` default | Beralih ke `Exclusive` melalui `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Pertanyaan yang Sering Diajukan

**Q1: Apa itu diagram box‑and‑whisker?**  
Diagram box‑and‑whisker, yang juga dikenal sebagai box plot, menampilkan distribusi data berdasarkan lima statistik ringkasan: minimum, kuartil pertama, median, kuartil ketiga, dan maksimum, serta outlier apa pun.

**Q2: Bisakah saya menyesuaikan tampilan diagram box‑and‑whisker?**  
Ya. Aspose.Slides memungkinkan Anda mengubah warna, gaya garis, bentuk marker, dan menambahkan label data melalui API format diagram.

**Q3: Apakah memungkinkan menangani beberapa seri dalam satu diagram?**  
Tentu saja. Ulangi blok pembuatan seri untuk setiap kumpulan data yang ingin Anda visualisasikan.

**Q4: Bagaimana cara mengatasi masalah data yang tidak tampil dengan benar?**  
Pastikan data ditulis dengan benar ke sel workbook dan properti visibilitas seperti `setShowMeanLine` diaktifkan.

**Q5: Di mana saya dapat mendapatkan dukungan jika mengalami masalah?**  
Kunjungi [forum Aspose.Slides](https://forum.aspose.com/c/slides/11) untuk bantuan komunitas, atau konsultasikan dokumentasi resmi.

**Q6: Apakah Aspose.Slides mendukung tipe diagram lain?**  
Ya, ia mendukung lebih dari 50 tipe diagram—termasuk line, bar, pie, scatter, radar, dan funnel—sehingga Anda dapat memilih visual terbaik untuk data Anda.

**Q7: Bisakah saya menghasilkan diagram di lingkungan server tanpa UI?**  
Perpustakaan ini berfungsi sepenuhnya dalam skenario sisi‑server; tidak diperlukan UI atau instalasi Microsoft Office.

## Sumber Daya

- **Dokumentasi**: Jelajahi referensi API detail di [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Unduh**: Akses halaman rilis Aspose.Slides [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)  
- **Pembelian**: Beli lisensi untuk membuka semua fitur [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Versi percobaan gratis & lisensi sementara**: Mulai dengan versi percobaan gratis atau minta lisensi sementara [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

Dengan mengikuti panduan ini, Anda kini siap untuk secara programatik menghasilkan diagram box‑and‑whisker yang informatif dalam aplikasi Java Anda dan menyematkannya langsung ke dalam presentasi PowerPoint. Selamat coding!

---

**Terakhir Diperbarui:** 2026-08-21  
**Diuji Dengan:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menambahkan Diagram ke PowerPoint Menggunakan Aspose.Slides untuk Java: Panduan Langkah‑ demi‑Langkah](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java membuat diagram PowerPoint menggunakan Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Menambahkan animasi ke diagram PowerPoint menggunakan Aspose.Slides untuk Java – Panduan Langkah‑ demi‑Langkah](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}