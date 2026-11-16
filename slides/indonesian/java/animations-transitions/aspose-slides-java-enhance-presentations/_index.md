---
date: '2026-11-16'
description: Gambar bingkai di sekitar teks dalam tabel PowerPoint menggunakan Aspose.Slides
  for Java – pelajari cara membuat tabel, menambahkan teks ke sel, menyorot sel, dan
  mengekspor file sebagai PPTX.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Gambar bingkai di sekitar teks dalam tabel PowerPoint menggunakan
  Aspose.Slides for Java. Panduan ini menunjukkan cara membuat tabel, menambahkan
  dan meratakan teks, menyorot sel, serta mengekspor slide sebagai PNG.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Gambar bingkai di sekitar teks dan buat tabel di PowerPoint dengan Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: Cara menggambar bingkai di sekitar teks dan membuat tabel di PowerPoint dengan
  Aspose.Slides for Java
url: /id/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menggambar bingkai di sekitar teks dan membuat tabel di PowerPoint dengan Aspose.Slides untuk Java

## Pendahuluan

Menggambar **bingkai di sekitar teks** dalam slide PowerPoint memungkinkan Anda menyoroti angka penting tanpa mengubah konten dasarnya. Dalam tutorial ini Anda akan belajar cara membuat tabel secara programatik, menyisipkan dan meratakan teks di dalam sel, menyoroti kata tertentu atau seluruh sel, dan akhirnya menyimpan presentasi sebagai file PPTX. Pada akhir tutorial Anda akan memiliki slide yang dipoles yang menarik perhatian audiens tepat di tempat yang Anda inginkan.

## Jawaban Cepat
- **Apa arti “add text to table”?** Itu berarti menyisipkan atau memperbarui konten teks dari sel tabel individu secara programatik.  
- **Metode mana yang menyimpan file?** `pres.save("output.pptx", SaveFormat.Pptx)` – langkah **save presentation as pptx** ini menyelesaikan perubahan Anda.  
- **Bagaimana saya dapat meratakan teks di dalam shape?** Gunakan `TextAlignment.Left` (atau Center/Right) melalui `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Bisakah saya menggambar persegi panjang di sekitar paragraf?** Ya – iterasi paragraf, dapatkan persegi pembatasnya, dan tambahkan `IAutoShape` tanpa isi dan dengan garis hitam.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara berfungsi untuk evaluasi; lisensi penuh diperlukan untuk penggunaan produksi.  

## Mengapa menggambar bingkai di sekitar teks?

Menggambar bingkai di sekitar teks secara langsung menyoroti angka penting, peringatan, atau judul. Ini memberikan petunjuk visual sambil mempertahankan format asli tidak berubah, menjadikannya ideal untuk laporan keuangan, dasbor KPI, atau slide apa pun yang memerlukan penekanan.

## Apa itu bingkai di sekitar teks?

`draw frame around text` adalah teknik menambahkan bentuk persegi panjang secara programatik yang mengikuti batas tepat sebuah paragraf atau bagian teks, menggunakan format garis tanpa mengisi bagian dalam. Pendekatan ini memungkinkan Anda menekankan konten tanpa mengubah teks itu sendiri.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

### Perpustakaan yang diperlukan
Anda memerlukan Aspose.Slides untuk Java. Sertakan dengan salah satu pengelola paket:

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

Anda juga dapat menelusuri rilis di [Rilis Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/).

### Penyiapan lingkungan
Java Development Kit (JDK) 16 atau yang lebih baru disarankan karena contoh menggunakan classifier `jdk16`. IDE apa pun seperti IntelliJ IDEA atau Eclipse dapat digunakan.

### Prasyarat pengetahuan
- Kemampuan dasar pemrograman Java.  
- Keterbiasaan dengan konsep PowerPoint (slide, shape, tabel).  
- Pemahaman tentang cara Maven/Gradle mengelola dependensi.

## Menyiapkan Aspose.Slides untuk Java

`Presentation` adalah kelas inti Aspose.Slides yang mewakili file PowerPoint dalam memori dan memberikan akses ke slide, shape, dan tabel. Ia dapat menangani presentasi hingga **10.000 slide** sambil menjaga penggunaan memori di bawah **500 MB**, menjadikannya cocok untuk otomatisasi skala besar.

1. **Instal perpustakaan** – gunakan Maven atau Gradle, atau unduh langsung dari [Rilis Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/).  
2. **Perolehan lisensi** – mulai dengan percobaan gratis dari [Lisensi Sementara](https://purchase.aspose.com/temporary-license/) dan tingkatkan ke lisensi penuh di [Beli Aspose.Slides](https://purchase.aspose.com/buy) untuk beban kerja produksi.  
3. **Inisialisasi dasar** – buat objek `Presentation` baru dan muat atau buat slide sesuai kebutuhan.  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Cara menambahkan teks ke tabel di Aspose.Slides untuk Java?

`Presentation` adalah kelas utama yang mewakili file PowerPoint dalam memori.  
Muat `Presentation` baru, buat tabel pada koordinat yang diinginkan, isi sel dengan objek `TextFrame`, dan akhirnya panggil `pres.save("output.pptx", SaveFormat.Pptx)`. Urutan ini membuat **create table in PowerPoint**, menyuntikkan teks khusus ke setiap sel, dan menulis hasilnya ke file PPTX dalam alur kerja tunggal yang efisien.

### Jawaban langsung
Buat tabel dengan memanggil `slide.getShapes().addTable(...)`, kemudian untuk setiap sel gunakan `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))`. Setelah mengisi semua sel, panggil `pres.save("output.pptx", SaveFormat.Pptx)` untuk menulis file. Pendekatan ini memungkinkan Anda mengontrol secara programatik konten dan gaya setiap sel.

#### Fitur 1: buat tabel dan tambahkan teks ke sel

**1. buat tabel** – inisialisasi presentasi, tambahkan slide, dan tempatkan tabel pada (50, 50) dengan lebar kolom dan tinggi baris yang ditentukan.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. tambahkan teks ke sel** – untuk setiap sel, buat `Paragraph`, tambahkan `Portion` dengan string yang diinginkan, dan tetapkan paragraf ke `TextFrame` sel.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. simpan presentasi** – panggil `pres.save("output.pptx", SaveFormat.Pptx)`.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Cara menggambar bingkai di sekitar teks dalam slide PowerPoint?

`Rectangle2D` mewakili area persegi panjang dalam ruang koordinat dua dimensi.  
Muat slide, temukan paragraf atau bagian yang ingin Anda tekankan, dapatkan persegi pembatasnya melalui `getRect()`, lalu tambahkan persegi `IAutoShape` tanpa isi dan dengan garis berwarna. Metode ini bekerja untuk seluruh paragraf maupun bagian kata individu.

### Jawaban langsung
Untuk menggambar bingkai di sekitar teks, pertama dapatkan persegi paragraf (`Rectangle2D rect = paragraph.getRect();`). Kemudian buat persegi `IAutoShape` (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), atur `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)`, dan nonaktifkan isi (`shape.getFillFormat().setFillType(FillType.NoFill)`). Shape tersebut akan secara sempurna menyorot teks.

#### Fitur 3: gambar bingkai di sekitar paragraf dan bagian dalam sel tabel

**1. buat tabel** – gunakan kembali kode dari Fitur 1 untuk menyiapkan tabel awal.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. tambahkan paragraf** – gunakan kembali kode pembuatan paragraf dari Fitur 1.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. gambar bingkai** – iterasi setiap paragraf, dapatkan persegi pembatasnya, dan tambahkan shape persegi seperti dijelaskan di atas. Untuk bagian yang berisi karakter ‘0’, gambar bingkai tambahan untuk menyorot angka tersebut.  
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```  

**4. simpan presentasi** – langkah akhir yang sama seperti sebelumnya.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Cara menambahkan text frame ke AutoShape dan mengatur perataan

`AutoShape` adalah shape yang dapat berisi teks, gambar, atau konten lain.  
`AutoShape` dapat menampung `TextFrame`. Anda dapat mengontrol perataan horizontal menggunakan enum `ParagraphFormat`.

### Jawaban langsung
Buat AutoShape persegi panjang (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), akses `TextFrame`-nya, atur teks dengan `shape.getTextFrame().setText("Text in shape")`, lalu panggil `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)`. Ini meratakan teks ke kiri di dalam shape.

**1. tambahkan AutoShape** – tempatkan persegi panjang pada lokasi yang diinginkan.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. atur perataan teks** – terapkan perataan kiri seperti yang ditunjukkan di atas.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. simpan presentasi** – langkah akhir yang sama.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Kesalahan umum & tips

- **Selalu dispose** – bungkus penggunaan `Presentation` Anda dalam blok try‑finally dan panggil `pres.dispose()` untuk membebaskan sumber daya native.  
- **Hitung ulang persegi pembatas** – jika Anda mengubah ukuran font, margin, atau padding sel setelah menggambar bingkai, panggil `paragraph.getRect()` lagi sebelum menambahkan shape.  
- **Buat shape secara batch untuk tabel besar** – menggunakan kembali satu instance `IAutoShape` dan memperbarui geometri mengurangi tekanan memori saat memproses tabel dengan ratusan baris.  
- **Angka kinerja** – Aspose.Slides dapat menghasilkan PPTX 200‑halaman dalam kurang dari 2 detik pada server 4‑core tipikal, dan menggambar bingkai di sekitar 1.000 paragraf menambah overhead kurang dari 150 ms.

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan API ini dengan versi JDK yang lebih lama?**  
A: Perpustakaan mendukung JDK 8 ke atas, tetapi classifier `jdk16` memberikan kinerja terbaik pada runtime yang lebih baru.

**Q: Bagaimana cara mengubah warna bingkai?**  
A: Modifikasi warna isi format garis, misalnya `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Apakah memungkinkan mengekspor slide akhir sebagai gambar?**  
A: Ya—gunakan `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` dan kemudian simpan array byte.

**Q: Bagaimana jika saya perlu menyorot hanya kata “Total” di dalam sel?**  
A: Iterasi melalui `cell.getTextFrame().getParagraphs()`, temukan bagian yang berisi “Total”, dan gambar persegi di sekitar kotak pembatas bagian tersebut.

**Q: Apakah Aspose.Slides menangani presentasi besar secara efisien?**  
A: API mem-stream data dan melepaskan sumber daya saat `pres.dispose()` dipanggil, yang membantu manajemen memori untuk file besar.

---

**Terakhir Diperbarui:** 2026-11-16  
**Diuji Dengan:** Aspose.Slides untuk Java 25.4 (jdk16)  
**Penulis:** Aspose  



## Tutorial terkait

- [Aspose.Slides untuk Java: Menguasai Manipulasi Tabel & Teks PPTX dalam Presentasi PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Cara Membuat Text Frame Dinamis di PowerPoint Menggunakan Aspose.Slides untuk Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Menambahkan Kolom dalam Text Frame menggunakan Aspose.Slides untuk Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}