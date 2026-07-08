---
date: '2026-07-08'
description: Pelajari cara menambahkan diagram lingkaran pada presentasi PowerPoint
  menggunakan Aspose.Slides for Java. Ikuti panduan langkah demi langkah ini untuk
  membuat dan menyesuaikan diagram lingkaran profesional.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Tambahkan diagram lingkaran PowerPoint menggunakan Aspose.Slides for
  Java. Tutorial ini menunjukkan cara menghasilkan dan menyesuaikan diagram lingkaran
  secara programatik, sempurna untuk laporan otomatis.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Tambahkan Diagram Lingkaran PowerPoint dengan Aspose.Slides for Java – Panduan
  Cepat
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Cara menambahkan diagram lingkaran PowerPoint dengan Aspose.Slides for Java
url: /id/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tambahkan Diagram Lingkaran PowerPoint dengan Aspose.Slides untuk Java

## Pendahuluan

Jika Anda perlu **menambahkan diagram lingkaran PowerPoint** tanpa membuka PowerPoint secara manual, Anda berada di tempat yang tepat. Dalam panduan ini kami akan menjelaskan cara menyiapkan Aspose.Slides untuk Java, membuat diagram lingkaran, dan menyesuaikan setiap irisan—sempurna untuk pelaporan otomatis, dasbor, atau presentasi yang dipersonalisasi. Pada akhirnya Anda akan memiliki potongan kode Java yang dapat digunakan kembali yang menghasilkan file PowerPoint diagram lingkaran yang halus dalam hitungan detik.

### Jawaban Cepat
- **Library apa yang membuat diagram?** Aspose.Slides untuk Java (rilisan terbaru).  
- **Bisakah saya menjalankannya tanpa tampilan?** Ya—tidak memerlukan instalasi Office.  
- **Versi Java mana yang optimal?** JDK 16+ untuk kinerja terbaik dan perbaikan GC.  
- **Bagaimana cara meledakkan sebuah irisan?** Panggil `setExplosion` pada `IDataPoint` dan tetapkan offset piksel.  
- **Apakah saya memerlukan lisensi untuk produksi?** Versi percobaan dapat digunakan untuk pengembangan; lisensi permanen menghilangkan semua batas evaluasi.

## Mengapa menambahkan diagram lingkaran PowerPoint menggunakan Aspose.Slides untuk Java?

Anda dapat menghasilkan laporan visual terkini langsung dari layanan back‑end Anda, menghilangkan kesalahan salin‑tempel manual dan menjamin gaya yang konsisten dengan merek. Aspose.Slides mendukung **lebih dari 70 tipe diagram** dan dapat memproses presentasi dengan **lebih dari 10.000 slide** tanpa memuat seluruh file ke dalam memori, menjadikannya ideal untuk otomatisasi skala besar.

## Prasyarat

- **Aspose.Slides untuk Java** – tutorial ini merujuk pada versi 25.4 (yang terbaru pada saat penulisan).  
- **Java Development Kit** – JDK 16 atau yang lebih baru disarankan.  
- **Maven** atau **Gradle** untuk penanganan dependensi.  

## Menyiapkan Aspose.Slides untuk Java

### Maven
Tambahkan dependensi ini ke file `pom.xml` Anda:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Sertakan yang berikut dalam file `build.gradle` Anda:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Sebagai alternatif, unduh versi terbaru langsung dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Lisensi
Untuk menggunakan Aspose.Slides tanpa batasan:

- Mulailah dengan **versi percobaan gratis** untuk mengevaluasi API.  
- Minta **lisensi sementara** untuk pengujian lanjutan di halaman [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Beli langganan penuh melalui [Purchase page](https://purchase.aspose.com/buy).

## Cara menambahkan diagram lingkaran PowerPoint menggunakan Aspose.Slides untuk Java

Muat presentasi baru, sisipkan diagram lingkaran, dan simpan file—semua dalam tiga langkah singkat. Pola ini bekerja untuk set data berukuran apa pun dan dapat dibungkus dalam loop untuk menghasilkan puluhan slide secara otomatis. Pendekatan ini ringan, hanya memerlukan beberapa baris kode dan tidak memerlukan sumber daya eksternal, sehingga cocok untuk utilitas kecil maupun pekerjaan batch besar.

### Langkah 1: Inisialisasi Presentasi
Kelas `Presentation` mewakili satu file PowerPoint dalam memori. Membuat sebuah instance memberi Anda dek slide kosong yang segar untuk dikerjakan.
```java
Presentation pres = new Presentation();
```

### Langkah 2: Tambahkan Diagram Lingkaran
Sisipkan diagram lingkaran pada slide pertama. Koordinat (50, 50) dan ukuran (600 × 400) cocok dengan tata letak standar 16:9 dan memberi ruang untuk judul.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Langkah 3: Simpan Presentasi
Tulis presentasi ke disk. Ganti `YOUR_OUTPUT_DIRECTORY` dengan folder tempat Anda ingin menyimpan file.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Langkah 4: Bersihkan Sumber Daya
Hapus objek `Presentation` untuk membebaskan sumber daya native dan menghindari kebocoran memori.
```java
if (pres != null) pres.dispose();
```

## Cara menyesuaikan ledakan dan warna data point?

Muat diagram, temukan data point target, lalu terapkan offset ledakan dan warna isi solid. Ini membuat irisan menonjol untuk penekanan. Penyesuaian ini membantu menarik perhatian audiens ke nilai kritis dan meningkatkan keterbacaan keseluruhan diagram.

### Langkah 1: Muat Presentasi yang Ada (atau gunakan kembali yang baru saja Anda buat)
Objek `Presentation` memuat file PowerPoint yang ada ke dalam memori, memungkinkan Anda memodifikasi isinya.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Langkah 2: Akses Diagram dan Data Point Target
Antarmuka `IDataPoint` mewakili sebuah data point (irisan) individu dalam seri diagram.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Langkah 3: Terapkan Ledakan dan Warna
`setExplosion(int)` menetapkan jarak, dalam piksel, yang membuat sebuah irisan teroffset dari pusat diagram. Pisahkan irisan secara visual dengan `setExplosion(20)` dan ubah isinya menjadi biru menggunakan `setFillType(FillType.Solid)` serta `setSolidFillColor(Color.BLUE)`.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Langkah 4: Simpan dan Hapus
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Aplikasi Praktis
- **Laporan Penjualan:** Sorot produk terlaris dengan irisan yang meledak.  
- **Analisis Anggaran:** Tetapkan warna berbeda untuk departemen demi perbandingan visual cepat.  
- **Slide Pendidikan:** Pecah konsep kompleks menjadi segmen diagram yang mudah dipahami.  

## Pertimbangan Kinerja
- **Hapus objek** segera untuk menghindari kebocoran memori, terutama saat menghasilkan banyak slide dalam loop.  
- **Pantau penggunaan heap** untuk presentasi besar; gunakan overload `Save` yang menerima `OutputStream` untuk men-stream data dan menjaga jejak memori tetap rendah.  
- Tetap gunakan **JDK 16+** untuk memanfaatkan perbaikan garbage‑collection terbaru, yang dapat mengurangi waktu pemrosesan hingga 30 % untuk dek 1.000 slide.

## Kesimpulan
Anda kini memiliki alur kerja lengkap yang siap produksi untuk **menambahkan diagram lingkaran PowerPoint** menggunakan Aspose.Slides untuk Java. Bereksperimenlah dengan jarak ledakan, warna, dan set data yang berbeda untuk menyesuaikan dengan merek Anda. Saat sudah siap, jelajahi tipe diagram lain—batang, garis, atau sebar—untuk membangun dasbor analitik lengkap di dalam PowerPoint.

## Pertanyaan yang Sering Diajukan

**Q: Apa keuntungan terbesar menggunakan Aspose.Slides untuk Java?**  
**A:** Memungkinkan Anda membuat, mengedit, dan merender file PowerPoint secara programatis tanpa perlu menginstal Microsoft Office, mendukung lebih dari 70 tipe diagram dan lebih dari 100 + format file.

**Q: Bisakah saya menghasilkan file PowerPoint dari awal?**  
**A:** Ya, buat objek `Presentation`, tambahkan slide, diagram, atau bentuk, lalu panggil `save`—semua dalam kode Java murni.

**Q: Bagaimana cara meledakkan irisan pie tertentu?**  
**A:** Dapatkan `IDataPoint` untuk irisan tersebut dan panggil `setExplosion(pixelOffset)`. Offset menentukan seberapa jauh irisan bergerak ke luar.

**Q: Apakah ada batasan jumlah slide yang dapat saya buat?**  
**A:** Aspose.Slides dapat menangani presentasi dengan hingga **10.000 slide** dalam satu file, asalkan Anda men-stream output untuk menghindari memuat semuanya ke memori.

**Q: Di mana saya dapat menemukan contoh kustomisasi diagram lanjutan?**  
**A:** Lihat dokumentasi resmi [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) untuk referensi API terperinci dan contoh proyek.

## Sumber Daya
- **Dokumentasi:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Unduh Perpustakaan:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Beli Lisensi:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Versi Percobaan Gratis:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Lisensi Sementara:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Forum Dukungan:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Terakhir Diperbarui:** 2026-07-08  
**Diuji Dengan:** Aspose.Slides untuk Java 25.4 (klasifier JDK 16)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Menambahkan Diagram ke PowerPoint Menggunakan Aspose.Slides untuk Java: Panduan Langkah‑ demi‑Langkah](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animasi Diagram PowerPoint Menggunakan Aspose.Slides untuk Java – Panduan Langkah‑ demi‑Langkah](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Buat dan Validasi Tata Letak Diagram di PowerPoint Menggunakan Aspose.Slides untuk Java | Panduan SEO‑Optimized](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}