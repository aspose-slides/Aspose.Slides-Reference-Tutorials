---
date: '2026-07-27'
description: Pelajari cara membuat doughnut chart java menggunakan Aspose.Slides –
  panduan cepat untuk menyiapkan library, menambahkan doughnut chart yang dapat disesuaikan,
  mengatur hole size, dan menyimpan presentation.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Pelajari cara membuat doughnut chart java menggunakan Aspose.Slides
  – panduan cepat untuk menyiapkan library, menambahkan doughnut chart yang dapat
  disesuaikan, mengatur hole size, dan menyimpan presentation.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Buat doughnut chart Java – Langkah demi Langkah dengan Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Buat doughnut chart Java – Langkah demi Langkah dengan Aspose.Slides
url: /id/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Diagram Donat di Java Menggunakan Aspose.Slides untuk Presentasi

## Pendahuluan
Membuat presentasi yang menarik secara visual sangat penting untuk menyampaikan informasi secara efektif. **Create doughnut chart java** adalah kebutuhan umum ketika Anda perlu menggambarkan data proporsional dengan tampilan modern. Dalam tutorial ini Anda akan belajar cara menyiapkan Aspose.Slides untuk Java, membuat diagram donat, menyesuaikan ukuran lubang dan warnanya, serta akhirnya menyimpan file presentasi. Pada akhir tutorial Anda akan memiliki pola yang dapat digunakan kembali dan dapat dimasukkan ke dalam proyek Java apa pun yang secara otomatis menghasilkan deck PowerPoint.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan Aspose.Slides untuk Java
- Membuat dan mengonfigurasi diagram donat dalam presentasi
- Menyesuaikan estetika diagram seperti ukuran lubang
- Menyimpan presentasi dengan diagram baru Anda

Mari kita mulai dengan menyiapkan lingkungan kita!

## Jawaban Cepat
- **Perpustakaan mana yang membuat doughnut chart java?** Aspose.Slides for Java.  
- **Berapa banyak baris kode yang dibutuhkan untuk diagram donat dasar?** Sekitar 8–10 baris setelah presentasi diinstansiasi.  
- **Apakah saya dapat mengubah ukuran lubang?** Ya, metode `setHoleSize(double)` menerima nilai dari 0 % hingga 100 %.  
- **Format output apa yang didukung?** PPTX, PDF, XPS, PNG, JPEG dan beberapa lainnya (lebih dari 50 total).  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk penggunaan tak terbatas; versi percobaan gratis dapat digunakan untuk evaluasi.

## Apa itu Aspose.Slides untuk Java?
**Aspose.Slides for Java** adalah API yang dikelola sepenuhnya yang memungkinkan pengembang untuk membuat, memodifikasi, mengonversi, dan merender file PowerPoint tanpa Microsoft Office. API ini mendukung lebih dari 50 format file dan dapat menangani presentasi dengan ribuan slide sambil menjaga penggunaan memori tetap rendah.

## Mengapa menggunakan diagram donat dalam presentasi?
Diagram donat menampilkan hubungan bagian‑ke‑keseluruhan sambil membebaskan ruang di tengah untuk label atau gambar. Aspose.Slides dapat merender diagram donat hingga **500 slide per menit** pada server 2.5 GHz standar, dan memproses **presentasi ratusan halaman** tanpa memuat seluruh file ke memori, menjadikannya ideal untuk solusi pelaporan berskala besar.

## Prasyarat
Sebelum memulai, pastikan Anda telah memenuhi prasyarat berikut:

### Perpustakaan dan Versi yang Diperlukan
Untuk bekerja dengan Aspose.Slides untuk Java, sertakan dalam proyek Anda melalui Maven atau Gradle, atau unduh secara langsung.

#### Persyaratan Penyiapan Lingkungan
- JDK (Java Development Kit) yang berfungsi, sebaiknya versi 8 atau lebih tinggi.  
- IDE (Integrated Development Environment) seperti IntelliJ IDEA atau Eclipse.

### Prasyarat Pengetahuan
Familiaritas dengan Java dan konsep pemrograman dasar sangat membantu. Pengetahuan dasar tentang Maven atau Gradle akan mempermudah proses penyiapan.

## Menyiapkan Aspose.Slides untuk Java
Mengintegrasikan Aspose.Slides ke dalam proyek Anda dapat dilakukan dengan beberapa cara:

**Maven:**  
Tambahkan dependensi ini ke file `pom.xml` Anda:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Sertakan ini dalam file `build.gradle` Anda:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
Sebagai alternatif, unduh versi terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Perolehan Lisensi
- **Free Trial:** Mulailah dengan mengunduh versi percobaan untuk menjelajahi fitur Aspose.Slides.  
- **Temporary License:** Dapatkan lisensi sementara untuk fungsionalitas tambahan tanpa batasan.  
- **Purchase:** Untuk penggunaan berkelanjutan, pembelian lisensi diperlukan.

Setelah Anda menyiapkan perpustakaan dan lingkungan siap, mari lanjut ke implementasi diagram donat kami.

## Cara membuat diagram donat di Java?
Muat objek `Presentation` baru, tambahkan diagram donat ke slide, atur ukuran lubang, dan simpan file – semuanya dalam beberapa panggilan API yang sederhana. Pendekatan ini memberi Anda kontrol penuh atas data diagram, tampilan, dan format ekspor, serta berfungsi tanpa memerlukan Microsoft PowerPoint terpasang di server.

### Inisialisasi Objek Presentation
Kelas `Presentation` adalah objek tingkat‑atas Aspose.Slides yang mewakili file PowerPoint dalam memori.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Langkah ini membuat presentasi kosong di mana Anda dapat menambahkan slide, shape, dan diagram.

### Menambahkan Diagram Donat ke Slide
`ISlide` adalah antarmuka untuk satu slide; Anda dapat mengambil slide pertama atau menambahkan yang baru.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
Metode `addChart` membuat diagram donat; parameter menentukan posisi (X, Y) dan ukuran (lebar, tinggi) pada slide.

### Mengonfigurasi Ukuran Lubang Donat
`Chart` menyediakan `setHoleSize(double)` untuk mengontrol radius dalam sebagai persentase radius diagram.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Mengatur ukuran lubang menjadi 90 % membuat diagram tampak hampir seperti lingkaran penuh, yang berguna ketika Anda ingin menekankan segmen luar.

### Menyimpan Presentasi
`presentation.save(String, SaveFormat)` menulis file ke disk dalam format yang dipilih.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
Contoh ini menyimpan hasil sebagai `DoughnutHoleSize_out.pptx`, tetapi Anda juga dapat memilih PDF, PNG, atau format lain dari lebih dari 50 yang didukung.

### Membersihkan Sumber Daya
Memanggil `presentation.dispose()` melepaskan sumber daya native dan mencegah kebocoran memori, terutama penting dalam aplikasi server yang berjalan lama.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Aplikasi Praktis
Diagram donat sangat fleksibel. Berikut beberapa skenario di mana mereka bersinar:
1. **Budget Allocation:** Menampilkan bagaimana anggaran didistribusikan di antara departemen.  
2. **Survey Results:** Memvisualisasikan respons terhadap pertanyaan dengan jawaban pilihan ganda.  
3. **Website Traffic Sources:** Menunjukkan persentase lalu lintas yang berasal dari saluran berbeda (organik, berbayar, rujukan, dll.).

## Pertimbangan Kinerja
Saat bekerja dengan Aspose.Slides, pertimbangkan tip berikut untuk kinerja optimal:
- Buang objek `Presentation` segera setelah selesai untuk membebaskan memori native.  
- Gunakan stream (`FileInputStream`, `ByteArrayOutputStream`) untuk kumpulan data besar agar tidak memuat seluruh file ke RAM.  
- Gunakan kembali objek diagram saat menghasilkan banyak slide dalam loop untuk mengurangi overhead pembuatan objek.

## Masalah Umum dan Solusi
- **Error while saving:** Pastikan direktori output ada dan aplikasi memiliki izin menulis.  
- **Missing chart data:** Pastikan Anda mengisi koleksi `ChartData` diagram sebelum memanggil `setHoleSize`.  
- **Memory spikes:** Untuk presentasi dengan ribuan slide, aktifkan `Presentation.setSlideSize` ke ukuran lebih kecil dan buang slide menengah segera.

## Pertanyaan yang Sering Diajukan

**Q: Can I adjust the colors of my doughnut chart segments?**  
A: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` and then specify the desired RGB color.

**Q: How do I add data labels to my chart?**  
A: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` to display the value inside each segment.

**Q: Is it possible to save charts in formats other than PPTX?**  
A: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many other formats—over 50 in total.

**Q: What should I do if I encounter an exception while loading a large presentation?**  
A: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)` to stream the file and reduce memory consumption.

**Q: Can I automate chart updates with live data sources?**  
A: Yes. Retrieve data from a database or REST API, update the `ChartData` collection, and call `chart.refresh()` before saving the presentation.

## Sumber Daya
- **Documentation:** Jelajahi referensi API detail di [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Download:** Dapatkan versi perpustakaan terbaru dari [Aspose.Slides releases](https://releases.aspose.com/slides/java/).  
- **Purchase:** Untuk akses penuh, beli lisensi di [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Free Trial:** Coba Aspose.Slides dengan versi percobaan gratis yang tersedia di halaman unduhan mereka.  
- **Temporary License:** Dapatkan lisensi sementara untuk pengujian lanjutan tanpa batasan.  
- **Support:** Punya pertanyaan? Kunjungi [Aspose Forum](https://forum.aspose.com/c/slides/11) untuk bantuan.

---

**Terakhir Diperbarui:** 2026-07-27  
**Diuji Dengan:** Aspose.Slides for Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menambahkan Diagram ke PowerPoint Menggunakan Aspose.Slides untuk Java: Panduan Langkah‑per‑Langkah](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Cara Membuat Diagram di Java dengan Aspose.Slides: Panduan Komprehensif](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}