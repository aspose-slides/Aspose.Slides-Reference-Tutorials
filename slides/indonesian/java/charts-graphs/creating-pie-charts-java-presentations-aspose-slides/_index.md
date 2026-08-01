---
date: '2026-08-01'
description: Pelajari cara menggunakan lisensi Aspose Slides untuk membuat dan menyesuaikan
  diagram lingkaran dalam presentasi Java. Ikuti langkah demi langkah untuk mengonfigurasi
  data diagram lingkaran dan menambahkan slide diagram secara efisien.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Pelajari cara menggunakan lisensi Aspose Slides untuk membuat dan
  menyesuaikan diagram lingkaran dalam presentasi Java. Ikuti langkah demi langkah
  untuk mengonfigurasi data diagram lingkaran dan menambahkan slide diagram secara
  efisien.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Buat Diagram Lingkaran di Java dengan Lisensi Aspose Slides
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Buat Diagram Lingkaran di Java dengan Lisensi Aspose Slides
url: /id/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Diagram Pai dalam Presentasi Java Menggunakan Aspose.Slides

## Pendahuluan

Jika Anda perlu menghasilkan presentasi yang tampak profesional, **lisensi Aspose Slides** memberi Anda kemampuan untuk membuat dan menata diagram secara programatis. Dalam panduan ini Anda akan belajar cara membuat diagram pai, mengonfigurasi datanya, dan menyematkannya ke dalam dek slide Java—semua tanpa bergantung pada Microsoft PowerPoint. Kami akan membahas penyiapan, alur kode, dan tips praktik terbaik sehingga Anda dapat menyajikan laporan visual yang halus dalam hitungan menit.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan Aspose.Slides untuk Java dengan lisensi yang valid
- Langkah‑langkah membuat dan menyesuaikan diagram pai
- Cara mengonfigurasi data diagram pai dan menambahkan slide diagram
- Kesalahan umum dan trik kinerja

Mari mulai dengan memastikan lingkungan Anda siap.

## Jawaban Cepat
- **Apa yang diaktifkan oleh lisensi Aspose Slides?** Pembuatan diagram lengkap, ekspor ke PDF/HTML, dan penghapusan watermark.
- **Versi Java mana yang diperlukan?** JDK 16 atau yang lebih baru.
- **Apakah saya memerlukan Maven atau Gradle?** Kedua‑nya dapat digunakan; perpustakaan tersedia melalui keduanya.
- **Berapa banyak titik data yang dapat ditampung diagram pai?** Hingga 10 000 titik tanpa masalah memori.
- **Bisakah saya mengekspor slide sebagai gambar?** Ya – PNG, JPEG, SVG, dan lainnya didukung.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:
- **Perpustakaan yang Diperlukan:** Aspose.Slides untuk Java (versi 25.4 atau lebih baru) – versi ini mendukung format file terbaru dan optimasi kinerja.
- **Penyiapan Lingkungan:** JDK 16+ terpasang dan dikonfigurasi di IDE atau sistem build Anda.
- **Pengetahuan Dasar:** Familiaritas dengan Java, Maven atau Gradle, serta konsep pemrograman berorientasi objek.

## Menyiapkan Aspose.Slides untuk Java

Untuk menggunakan Aspose.Slides untuk Java, sertakan dalam proyek Anda. Berikut cara menambahkan dependensi dengan alat build yang paling umum:

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

**Unduhan Langsung:** Anda juga dapat mengunduh JAR terbaru dari [Rilis Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/).

### Akuisisi Lisensi

Aspose menawarkan percobaan gratis yang membuka semua fitur, tetapi **lisensi Aspose Slides yang valid** diperlukan untuk penggunaan produksi guna menghapus watermark evaluasi dan memperoleh manfaat kinerja. Opsi pembelian tercantum di [halaman pembelian](https://purchase.aspose.com/buy). Setelah memperoleh file lisensi, muat sekali saat aplikasi dimulai:

`License` memuat dan menerapkan lisensi Aspose.Slides Anda.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## Panduan Implementasi

### Membuat dan Menambahkan Diagram Pai ke Presentasi

#### Gambaran Umum
Bagian ini menjelaskan cara membuat diagram pai, mengonfigurasi seri datanya, dan menyematkan diagram ke dalam slide. Anda akan melihat alur lengkap mulai dari inisialisasi objek presentasi hingga menyimpan file akhir.

#### Langkah 1: Inisialisasi Presentation  
`Presentation` adalah objek tingkat‑atas Aspose.Slides yang mewakili file PowerPoint dalam memori. Membuat instance memberikan Anda dek slide kosong yang siap dimodifikasi.

```java
demo.Presentation pres = new demo.Presentation();
```  
Baris ini membuat presentasi baru di mana semua perubahan selanjutnya akan diterapkan.

#### Langkah 2: Tambahkan Diagram Pai ke Slide  
`Chart` adalah kelas yang mengenkapsulasi objek diagram, termasuk diagram pai. Menambahkan diagram ke slide cukup dengan satu pemanggilan metode yang menentukan posisi dan ukuran.

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` dan `yPosition` menentukan sudut kiri‑atas diagram.  
- `width` dan `height` mendefinisikan jejak visual diagram pada slide.

#### Langkah 3: Konfigurasikan Data Diagram Pai  
`ChartData` menyimpan seri data untuk sebuah diagram.  
**Bagaimana cara mengonfigurasi data diagram pai?**  
Berikan jawaban singkat terlebih dahulu: Gunakan koleksi `ChartData` untuk menambahkan seri, lalu isi objek `ChartDataPoint` dengan nilai numerik dan nama kategori. Pendekatan ini memungkinkan Anda menampilkan hingga 10 000 irisan sambil mempertahankan format label. Setelah data diatur, Anda dapat menyesuaikan warna, legenda, dan label data agar sesuai dengan panduan gaya perusahaan.

Berikut kode yang menambahkan dua kategori dan menampilkan labelnya:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
Potongan kode ini membuat seri data, menyisipkan dua titik, dan mengaktifkan label kategori pada diagram.

#### Langkah 4: Simpan Presentasi  
Akhirnya, persistenkan presentasi ke format file pilihan Anda (PPTX, PDF, atau PNG). Metode `save` menghormati lisensi aktif, memastikan tidak ada watermark percobaan yang muncul.

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### Masalah Umum dan Solusinya
- **Kesalahan Lisensi Hilang:** Pastikan jalur file lisensi benar dan objek `License` diinstansiasi sebelum pemanggilan Aspose.Slides apa pun.
- **Diagram Kosong:** Verifikasi bahwa seri `ChartData` berisi setidaknya satu `ChartDataPoint`. Seri kosong menghasilkan area diagram yang kosong.
- **Keterlambatan Kinerja dengan Set Data Besar:** Gunakan `presentation.getSlides().removeAt(index)` untuk membuang slide yang tidak terpakai dan panggil `System.gc()` setelah pemrosesan berat.

## Aplikasi Praktis
1. **Laporan Bisnis:** Visualisasikan pangsa pasar atau distribusi pendapatan antar wilayah dengan satu diagram pai.
2. **Presentasi Akademik:** Tampilkan hasil survei atau hasil percobaan dalam format yang jelas dan mudah dicerna.
3. **Dashboard Proyek:** Representasikan persentase penyelesaian tugas atau alokasi sumber daya secara instan pada slide.

Anda juga dapat menggabungkan Aspose.Slides dengan JDBC untuk menarik data langsung dari basis data, menghasilkan diagram yang selalu terbaru untuk briefing eksekutif mingguan.

## Pertimbangan Kinerja
Saat menangani presentasi yang berisi banyak gambar resolusi tinggi atau set data besar:
- Lepaskan objek segera menggunakan `try‑with‑resources` atau pemanggilan eksplisit `dispose()`.
- Aktifkan pemuatan malas (lazy loading) sumber daya slide untuk menjaga penggunaan memori tetap rendah.
- Untuk pemrosesan batch, gunakan kembali satu instance `Presentation` bila memungkinkan untuk mengurangi beban JVM.

## Kesimpulan
Anda kini memiliki alur kerja lengkap dan siap produksi untuk membuat diagram pai di Java menggunakan **lisensi Aspose Slides**. Bereksperimenlah dengan tipe diagram lain—batang, garis, atau donat—untuk memperkaya slide Anda lebih lanjut. Selanjutnya, jelajahi kemampuan ekspor API untuk menghasilkan laporan PDF atau gambar PNG secara otomatis.

## Pertanyaan yang Sering Diajukan

**T: Bagaimana cara menambahkan beberapa diagram ke satu slide?**  
J: Panggil `slide.getShapes().addChart()` untuk setiap diagram, dengan memberikan koordinat dan dimensi unik untuk masing‑masing instance.

**T: Apa saja alternatif untuk Aspose.Slides untuk Java?**  
J: Apache POI dan JFreeChart adalah alternatif umum, tetapi keduanya tidak memiliki opsi ekspor lengkap dan model lisensi seperti Aspose.

**T: Bisakah saya mengonversi presentasi saya ke format lain menggunakan Aspose.Slides?**  
J: Ya—ekspor ke PDF, XPS, HTML, PNG, JPEG, SVG, dan lainnya dengan satu panggilan `save`.

**T: Bagaimana cara menangani lisensi untuk tim pengembangan besar?**  
J: Beli lisensi enterprise yang mencakup banyak pengembang dan server; hubungi penjualan Aspose untuk diskon volume.

**T: Bagaimana jika data diagram saya sering berubah?**  
J: Integrasikan Aspose.Slides dengan sumber data (misalnya kueri SQL) dan bangun ulang diagram pada waktu runtime; API mendukung binding data dinamis.

## Sumber Daya
- **Dokumentasi:** [Referensi Aspose.Slides Java](https://reference.aspose.com/slides/java/)
- **Unduhan:** [Rilis Terbaru](https://releases.aspose.com/slides/java/)
- **Pembelian:** [Beli Lisensi](https://purchase.aspose.com/buy)
- **Percobaan Gratis:** [Coba Aspose.Slides Gratis](https://releases.aspose.com/slides/java/)
- **Lisensi Sementara:** [Dapatkan Lisensi Sementara](https://purchase.aspose.com/temporary-license/)
- **Dukungan:** [Forum Aspose](https://forum.aspose.com/c/slides/11)

---

**Terakhir Diperbarui:** 2026-08-01  
**Diuji Dengan:** Aspose.Slides for Java 25.4  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menambahkan dan Mengonfigurasi Diagram dalam Presentasi Menggunakan Aspose.Slides untuk Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Buat dan Sesuaikan Diagram dalam Presentasi Java Menggunakan Aspose.Slides](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [Cara Membuat dan Mengonfigurasi Presentasi dengan Aspose.Slides Java: Panduan Langkah‑per‑Langkah](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}