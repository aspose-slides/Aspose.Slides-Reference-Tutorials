---
date: '2026-08-06'
description: Pelajari cara mengubah warna font legenda dan memodifikasi teks legenda
  diagram menggunakan Aspose.Slides for Java. Ikuti petunjuk langkah demi langkah
  untuk menyesuaikan legenda diagram dengan cepat.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Pelajari cara mengubah warna font legenda dan memodifikasi teks legenda
  diagram dengan Aspose.Slides for Java. Panduan ini menunjukkan langkah-langkah tepat
  dan praktik terbaik.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Cara mengubah warna font legenda di Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Cara mengubah warna font legenda di Aspose.Slides for Java
url: /id/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara mengubah warna font legenda di Aspose.Slides untuk Java

## Pendahuluan
Jika Anda perlu **mengubah warna font legenda** dalam sebuah diagram, Aspose.Slides untuk Java memberi Anda kontrol penuh atas setiap entri legenda. Tutorial ini memandu Anda melalui penyesuaian gaya teks legenda, menerapkan font tebal atau miring, dan mengatur warna solid sehingga diagram Anda terlihat persis seperti yang Anda inginkan. Pada akhir panduan ini Anda akan dapat memodifikasi teks legenda diagram dengan percaya diri dan mengintegrasikan perubahan ke dalam presentasi yang ada.

**Apa yang akan Anda pelajari**
- Cara **mengubah warna font legenda** secara programatis.
- Cara **memodifikasi teks legenda diagram** seperti tebal, miring, dan ukuran.
- Tips untuk menerapkan perubahan pada beberapa diagram dalam satu presentasi.
- Cara mengintegrasikan langkah-langkah ini ke dalam alur kerja otomatisasi yang lebih besar.

## Jawaban Cepat
- **Apakah saya dapat mengubah warna satu entri legenda?** Ya – akses entri melalui indeksnya dan atur format isian menjadi warna solid.  
- **Apakah saya memerlukan lisensi untuk menggunakan API ini?** Lisensi sementara atau berbayar diperlukan untuk produksi; percobaan gratis dapat digunakan untuk evaluasi.  
- **Versi Java mana yang didukung?** Aspose.Slides untuk Java 25.4+ bekerja dengan JDK 16 dan yang lebih baru.  
- **Apakah perubahan akan memengaruhi elemen diagram lain?** Tidak, pemformatan legenda terisolasi dari gaya seri data.  
- **Apakah pemrosesan batch memungkinkan?** Tentu – lakukan loop melalui slide dan diagram untuk menerapkan pengaturan legenda yang sama di seluruh dek.

## Apa itu mengubah warna font legenda?
`change legend font color` mengacu pada operasi programatis untuk mengatur warna teks entri legenda diagram menggunakan API Aspose.Slides. Operasi ini memperbarui tampilan visual legenda tanpa mengubah data yang mendasarinya.

## Mengapa menyesuaikan legenda diagram?
Aspose.Slides mendukung **lebih dari 50 format input dan output** dan dapat menangani presentasi dengan **lebih dari 500 slide** sambil menjaga penggunaan memori di bawah 200 MB. Menyesuaikan legenda meningkatkan keterbacaan, memperkuat warna merek, dan memastikan poin data penting menonjol—terutama dalam dek bisnis atau edukasi di mana kejelasan visual memengaruhi pengambilan keputusan.

## Prasyarat
- Perpustakaan **Aspose.Slides untuk Java** (Versi 25.4 atau lebih baru).  
- Java Development Kit (JDK) 16 atau lebih tinggi.  
- IDE seperti IntelliJ IDEA, Eclipse, atau NetBeans.  
- Maven atau Gradle untuk manajemen dependensi.  
- Pengetahuan dasar pemrograman Java.

## Menyiapkan Aspose.Slides untuk Java
Untuk mulai menyesuaikan legenda diagram Anda, tambahkan perpustakaan ke proyek Anda menggunakan salah satu metode di bawah ini.

### Maven
Tambahkan dependensi berikut ke file `pom.xml` Anda:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Sertakan baris ini dalam file `build.gradle` Anda:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduhan Langsung
Anda juga dapat memperoleh JAR terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Langkah Pengadaan Lisensi
- **Free trial:** Mulai dengan percobaan gratis untuk menjelajahi fitur Aspose.Slides.  
- **Temporary license:** Ajukan lisensi sementara untuk evaluasi yang lebih lama.  
- **Purchase:** Untuk akses penuh, pertimbangkan membeli lisensi dari [Aspose Purchase](https://purchase.aspose.com/buy).

#### Inisialisasi dan Pengaturan Dasar
Setelah menambahkan perpustakaan ke proyek Anda:
1. Inisialisasi Aspose.Slides dalam aplikasi Java Anda.  
2. Muat presentasi yang ada atau buat yang baru.

## Cara mengubah warna font legenda?
Untuk mengubah warna font legenda, muat presentasi, ambil objek diagram, dapatkan legendanya, lalu modifikasi format teks setiap entri legenda dengan mengatur tipe isian menjadi solid dan menentukan warna yang diinginkan. Operasi tunggal ini memperbarui warna teks legenda secara instan tanpa perlu menggambar ulang seluruh slide. Contoh: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Pendekatan ini bekerja untuk semua tipe diagram dan tidak memerlukan render ulang seluruh slide.

### Mengakses dan memodifikasi properti teks legenda

#### Definisi anchor
Antarmuka `IChart` mewakili objek diagram pada sebuah slide, dan metode `getLegend()`‑nya mengembalikan objek `ILegend` yang berisi koleksi item `ILegendEntry`.

#### Menambahkan diagram ke presentasi Anda
1. **Muat presentasi:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Tambahkan diagram kolom berkelompok:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Menyesuaikan properti font
3. **Akses format teks entri legenda:**  
   Di sini, `legendEntry` adalah objek `ILegendEntry` yang mewakili satu entri dalam legenda diagram.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Atur gaya tebal dan miring dengan tinggi tertentu:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **Ubah tipe isian menjadi warna solid untuk visibilitas yang lebih baik:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### Menyimpan presentasi
6. **Simpan perubahan Anda:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Kesalahan umum dan pemecahan masalah
- Pastikan indeks entri legenda cocok dengan urutan seri dalam diagram Anda.  
- Pastikan Anda menggunakan versi perpustakaan yang mendukung `setSolidFillColor` (tersedia sejak versi 20.9).  

## Aplikasi Praktis
1. **Presentasi bisnis:** Sesuaikan warna legenda dengan merek perusahaan untuk tampilan yang rapi.  
2. **Materi edukasi:** Sorot seri data utama dengan menggunakan warna legenda yang kontras.  
3. **Dek pemasaran:** Tekankan metrik kinerja dengan legenda tebal dan berwarna untuk menarik perhatian pemangku kepentingan.  

Anda juga dapat mengotomatisasi pembaruan legenda dengan mengambil nilai warna dari basis data atau file konfigurasi.

## Pertimbangan Kinerja
Saat memproses dek besar, perhatikan tips berikut:

- **Manajemen memori yang efisien:** Panggil `presentation.dispose()` setelah menyimpan untuk melepaskan sumber daya native.  
- **Muat hanya slide yang diperlukan:** Gunakan `Presentation.load(String path, LoadOptions options)` dengan `LoadOptions.setLoadOnlySlideIds()` jika Anda membutuhkan subset.  
- **Pemrosesan batch:** Kelompokkan pembaruan legenda per slide untuk mengurangi jumlah panggilan API dan meningkatkan throughput.

## Kesimpulan
Anda kini tahu cara **mengubah warna font legenda** dan **memodifikasi teks legenda diagram** menggunakan Aspose.Slides untuk Java. Kustomisasi ini meningkatkan kejelasan visual dan membantu Anda menyampaikan data lebih efektif. Bereksperimenlah dengan berbagai font, ukuran, dan warna untuk menyesuaikan panduan gaya presentasi Anda, dan jelajahi fitur styling diagram lainnya untuk membuat dek yang benar‑benar profesional.

**Langkah Selanjutnya**
- Coba terapkan gaya legenda yang sama pada diagram pai dan garis.  
- Gabungkan penyesuaian legenda dengan pemformatan label data untuk diagram yang sepenuhnya bermerk.  

Siap meningkatkan presentasi Anda? Terapkan langkah-langkah di atas dan lihat perbedaannya secara instan!

## Bagian FAQ
1. **Bagaimana cara mengubah warna teks entri legenda?**  
   Gunakan `getFillFormat().setFillType(FillType.Solid)` lalu `setSolidFillColor(Color.YOUR_COLOR)` pada format teks entri legenda.

2. **Bisakah saya menerapkan perubahan ini ke semua legenda dalam sebuah presentasi?**  
   Ya – iterasi melalui setiap slide, temukan setiap diagram, dan perbarui entri legendanya dalam sebuah loop.

3. **Apakah memungkinkan menyesuaikan ukuran font secara dinamis berdasarkan panjang teks?**  
   Anda dapat menghitung ukuran yang diperlukan dengan `TextFrame.getTextFrameFormat().getFontHeight()` dan mengaturnya melalui `setFontHeight(double)`.

4. **Bagaimana jika saya menemukan masalah dengan pengindeksan entri legenda?**  
   Periksa kembali bahwa indeks yang Anda gunakan cocok dengan urutan seri; ingat bahwa indeks dimulai dari nol.

5. **Di mana saya dapat menemukan contoh Aspose.Slides lainnya?**  
   Jelajahi [Aspose Documentation](https://reference.aspose.com/slides/java/) untuk panduan lengkap dan referensi API.

**Pertanyaan & Jawaban Tambahan**

**Q: Apakah mengubah warna font legenda memengaruhi file PDF yang diekspor?**  
A: Tidak, perubahan warna dipertahankan dalam semua format ekspor yang didukung oleh Aspose.Slides, termasuk PDF dan PPTX.

**Q: Bisakah saya menggunakan gradien alih-alih warna solid?**  
A: Ya – atur `FillType.Gradient` dan konfigurasikan titik gradien melalui `getGradientStyle()`.

**Q: Berapa banyak entri legenda yang dapat dimiliki sebuah diagram?**  
A: Sebuah diagram dapat memiliki hingga 256 entri legenda, terbatas hanya oleh jumlah seri data yang Anda tambahkan.

## Sumber Daya
- **Documentation:** Panduan komprehensif menggunakan fitur Aspose.Slides ([Link](https://reference.aspose.com/slides/java/)).  
- **Download:** Akses versi terbaru Aspose.Slides untuk Java ([Link](https://releases.aspose.com/slides/java/)).  
- **Purchase:** Beli lisensi untuk membuka semua kemampuan ([Link](https://purchase.aspose.com/buy)).  
- **Free trial & temporary license:** Mulai dengan percobaan gratis dan ajukan lisensi sementara ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Support:** Dapatkan bantuan dari komunitas di forum dukungan Aspose ([Link](https://forum.aspose.com/c/slides/11)).

---

**Last Updated:** 2026-08-06  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## Tutorial Terkait

- [Meningkatkan Diagram PowerPoint: Kustomisasi Font & Sumbu dengan Aspose.Slides untuk Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides untuk Java: Panduan Kerangka Teks Dinamis & Kustomisasi Font](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Animasi Diagram PowerPoint Menggunakan Aspose.Slides untuk Java – Panduan Langkah demi Langkah](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}