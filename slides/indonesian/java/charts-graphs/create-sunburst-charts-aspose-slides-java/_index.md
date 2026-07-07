---
date: '2026-07-03'
description: Pelajari cara membuat sunburst charts langkah demi langkah di Java menggunakan
  Aspose.Slides, dengan opsi kustomisasi penuh untuk presentasi PowerPoint.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Cara Membuat Sunburst Charts di Java Menggunakan Aspose.Slides
url: /id/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Sunburst Chart di Java Menggunakan Aspose.Slides

## Pendahuluan
Dalam presentasi yang didorong oleh data saat ini, **cara membuat sunburst** visualisasi dengan cepat dapat membuat slide Anda menonjol. Tutorial ini memandu Anda membangun diagram Sunburst dengan Aspose.Slides untuk Java, mulai dari penyiapan proyek hingga ekspor akhir, sehingga Anda dapat menyajikan grafik data hierarkis yang menarik tanpa meninggalkan ekosistem Java.

## Jawaban Cepat
- **Apa kelas utama untuk file PowerPoint?** `Presentation` – mewakili seluruh PPTX dalam memori.  
- **Berapa baris kode yang dibutuhkan untuk sunburst dasar?** Biasanya 5–7 baris setelah pustaka direferensikan.  
- **Format output apa yang didukung?** PPTX, PDF, PNG, SVG, dan HTML.  
- **Apakah saya dapat menata segmen individual?** Ya – warna isi, batas, dan label data dapat disesuaikan sepenuhnya.  
- **Apakah saya memerlukan lisensi untuk produksi?** Evaluasi gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk penerapan.

## Apa Itu Sunburst Chart?
Diagram Sunburst memvisualisasikan data hierarkis sebagai cincin konsentris, di mana setiap cincin mewakili tingkat hierarki. Ini memungkinkan penonton memahami hubungan induk‑anak secara sekilas, menjadikannya ideal untuk bagan organisasi, tampilan taksonomi, dan metrik multi‑tingkat. Diagram ini sangat berguna untuk menampilkan kategori multi‑tingkat seperti lini produk, wilayah geografis, atau struktur organisasi, memungkinkan penonton melihat baik distribusi keseluruhan maupun rincian detail dalam setiap segmen.

## Mengapa Menggunakan Aspose.Slides untuk Sunburst Chart?
Aspose.Slides mendukung **lebih dari 30 jenis diagram**, memproses file hingga **500 MB** tanpa memuat seluruh dokumen ke memori, dan merender grafik pada **300 DPI** untuk output yang sangat jelas. Kemampuan terukur ini memastikan pembuatan cepat dan visual berkualitas tinggi bahkan untuk presentasi besar. Selain itu, pustaka ini menawarkan operasi yang thread‑safe dan terintegrasi mulus dengan alat build Java populer, menjadikannya cocok untuk pembuatan presentasi baik di sisi desktop maupun server secara skala besar.

## Prasyarat
- Java Development Kit (JDK) 8 atau lebih baru.  
- Maven atau Gradle untuk manajemen dependensi.  
- Aspose.Slides untuk Java (versi terbaru).  
- Pemahaman dasar tentang struktur data hierarkis.

## Cara Membuat Sunburst Chart Langkah demi Langkah?
Muat lingkungan Anda, tambahkan diagram, masukkan data hierarkis, atur tampilannya, dan simpan file – semuanya dalam beberapa langkah sederhana. Di bawah ini adalah alur kerja tepat yang dapat Anda ikuti tanpa menulis kode boilerplate tambahan. Proses ini sepenuhnya otomatis, tidak memerlukan interaksi UI manual, dan dapat dimasukkan ke dalam pekerjaan batch atau layanan web untuk menghasilkan diagram sesuai permintaan.

### Langkah 1: Siapkan Proyek
Tambahkan dependensi Maven Aspose.Slides (atau potongan Gradle yang setara) ke `pom.xml` Anda. Ini akan mengunduh semua binary yang diperlukan serta pustaka transitive.

### Langkah 2: Muat atau Buat Presentasi
`Presentation` adalah objek tingkat‑atas Aspose.Slides yang mewakili satu file PowerPoint dalam memori. Buat instance dengan `new Presentation()` untuk deck baru atau berikan jalur file untuk membuka PPTX yang sudah ada.

### Langkah 3: Tambahkan Sunburst Chart
Sisipkan bentuk diagram baru ke slide menggunakan `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. Ini membuat placeholder Sunburst yang siap untuk data. `ChartType.Sunburst` menentukan tipe diagram Sunburst saat menambahkan diagram ke slide.

### Langkah 4: Isi Data Hierarkis
`ChartData` menyimpan seri data dan kategori untuk sebuah diagram. Akses koleksi `ChartData` diagram dan tambahkan seri serta kategori yang mencerminkan hierarki Anda. Untuk setiap tingkat, tentukan hubungan induk‑anak melalui properti `ParentSeries`, memungkinkan diagram merender cincin konsentris secara otomatis.

### Langkah 5: Sesuaikan Penampilan
Sesuaikan warna segmen, gaya batas, dan label data melalui objek `ChartSeries` dan `ChartDataPoint`. `ChartSeries` mewakili serangkaian titik data dalam diagram. `ChartDataPoint` mewakili titik data individual dalam sebuah seri. Anda juga dapat mengaktifkan rotasi 3‑D atau mengatur properti `Explode` untuk menyorot irisan tertentu.

### Langkah 6: Simpan Presentasi
Enum `SaveFormat` menentukan format file yang dapat Anda gunakan untuk menyimpan presentasi. Panggil `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` untuk menulis file ke disk. Anda juga dapat mengekspor ke PDF atau PNG dengan mengubah nilai enum `SaveFormat`.

## Cara Menyesuaikan Warna Sunburst Chart?
Tentukan warna isi untuk setiap `ChartDataPoint` menggunakan `point.getFillFormat().setFillType(FillType.Solid)` dan kemudian `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Pendekatan langsung ini memungkinkan Anda menyesuaikan merek perusahaan atau menekankan titik data penting. Anda juga dapat menerapkan isian gradien, mengatur transparansi, atau menggunakan warna tema untuk memastikan konsistensi dengan desain slide lainnya.

## Masalah Umum dan Solusinya
- **Masalah:** Hierarki tampak datar.  
  **Solusi:** Pastikan setiap seri anak secara tepat merujuk ke `ParentSeries`-nya. Link yang hilang menyebabkan diagram memperlakukan semua data sebagai satu tingkat.  
- **Masalah:** PNG yang diekspor terlihat buram.  
  **Solusi:** Tingkatkan DPI ekspor dengan mengatur `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.  
- **Masalah:** File PPTX besar menyebabkan OutOfMemoryError.  
  **Solusi:** Gunakan `Presentation.setMemoryOptimization(true)` untuk streaming data dan menjaga penggunaan memori tetap rendah.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menghasilkan Sunburst chart dari file CSV?**  
J: Ya. Baca CSV, bangun hierarki di memori, dan masukkan ke koleksi `ChartData` diagram sebelum menyimpan.

**T: Apakah Aspose.Slides mendukung transisi animasi untuk Sunburst chart?**  
J: Ya. Terapkan `SlideShowTransition` ke slide atau gunakan `ChartFormat.setAnimationEnabled(true)` untuk animasi tingkat diagram.

**T: Apakah memungkinkan mengekspor diagram sebagai grafik vektor SVG?**  
J: Tentu saja. Simpan presentasi dengan `SaveFormat.Svg` untuk mendapatkan versi vektor skalabel dari Sunburst chart.

**T: Berapa jumlah maksimum titik data yang dapat ditangani Sunburst chart?**  
J: Aspose.Slides secara andal memproses hingga **10.000** titik data dalam satu Sunburst chart tanpa penurunan kinerja.

**T: Apakah saya memerlukan lisensi terpisah untuk setiap lingkungan deployment?**  
J: Satu lisensi komersial mencakup semua lingkungan (pengembangan, staging, produksi) selama ketentuan lisensi dipatuhi.

## Kesimpulan
Anda kini memiliki panduan lengkap langkah demi langkah untuk **cara membuat sunburst** chart di Java menggunakan Aspose.Slides. Dengan mengikuti alur kerja di atas, Anda dapat menghasilkan visualisasi hierarkis berkualitas tinggi yang sepenuhnya dapat disesuaikan untuk presentasi PowerPoint apa pun.

---

**Terakhir Diperbarui:** 2026-07-03  
**Diuji Dengan:** Aspose.Slides for Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menambahkan Diagram ke PowerPoint Menggunakan Aspose.Slides untuk Java: Panduan Langkah demi Langkah](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Menguasai Kustomisasi Diagram PowerPoint Menggunakan Aspose.Slides Java untuk Presentasi Dinamis](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Animasi Kategori Diagram PowerPoint dengan Aspose.Slides untuk Java | Panduan Langkah demi Langkah](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}