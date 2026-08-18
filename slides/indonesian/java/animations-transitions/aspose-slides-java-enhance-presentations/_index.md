---
date: '2026-06-23'
description: Pelajari cara membuat table di PowerPoint, menambahkan text ke table
  cells, menggambar frames di sekitar text, dan menyimpan presentation sebagai pptx
  menggunakan Aspose.Slides for Java.
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
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
title: Cara membuat table di PowerPoint dan menggambar frames dengan Aspose.Slides
  for Java
url: /id/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara membuat tabel di PowerPoint dan menggambar bingkai dengan Aspose.Slides for Java

## Pendahuluan

Membuat **create table in PowerPoint** secara programatik dapat menghemat Anda berjam‑jam pemformatan manual, terutama ketika Anda perlu menyoroti angka kunci atau menambahkan catatan penjelas. Dalam tutorial ini Anda akan mempelajari cara menambahkan teks ke sel tabel, menggambar bingkai di sekitar paragraf tertentu, mengatur perataan teks secara tepat, dan akhirnya **save presentation as pptx** – semuanya dengan API Aspose.Slides for Java yang kuat. Pada akhir tutorial Anda akan memiliki slide yang tampak rapi, mudah dibaca, dan langsung menarik perhatian audiens ke data terpenting.

## Jawaban Cepat
- **Apa arti “add text to table”?** Itu berarti menyisipkan atau memperbarui konten teks pada sel tabel individu secara programatik.  
- **Metode mana yang menyimpan file?** `pres.save("output.pptx", SaveFormat.Pptx)` – langkah **save presentation as pptx** ini menyelesaikan perubahan Anda.  
- **Bagaimana cara menyejajarkan teks di dalam bentuk?** Gunakan `TextAlignment.Left` (atau Center/Right) melalui `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Bisakah saya menggambar persegi panjang di sekitar paragraf?** Ya – iterasi paragraf, dapatkan persegi pembatasnya, dan tambahkan `IAutoShape` tanpa isi dan garis hitam.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk penggunaan produksi.  

## Mengapa menggambar bingkai di sekitar teks?

Menggambar bingkai (atau persegi panjang) di sekitar paragraf atau bagian tertentu—misalnya teks yang mengandung karakter **'0'**—langsung menarik perhatian audiens ke konten tersebut. Ini memberikan isyarat visual yang jelas tanpa mengubah teks yang mendasarinya, menjadikannya ideal untuk menyoroti angka penting, peringatan, atau memisahkan bagian dalam slide.

## Prasyarat

Sebelum menyelami kode, pastikan Anda memiliki hal berikut:

### Pustaka yang Diperlukan
Anda akan membutuhkan Aspose.Slides for Java. Berikut cara menyertakannya menggunakan Maven atau Gradle:

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

### Pengaturan Lingkungan
Pastikan Anda memiliki Java Development Kit (JDK) terpasang, sebaiknya JDK 16 atau yang lebih baru, karena contoh ini menggunakan classifier `jdk16`.

### Prasyarat Pengetahuan
- Pemahaman dasar tentang pemrograman Java.  
- Familiaritas dengan perangkat lunak presentasi seperti PowerPoint.  
- Pengalaman menggunakan Integrated Development Environment (IDE) seperti IntelliJ IDEA atau Eclipse.

## Menyiapkan Aspose.Slides for Java

`Presentation` adalah kelas inti Aspose.Slides yang mewakili file PowerPoint dalam memori dan memberikan akses ke slide, bentuk, serta tabel. Untuk mulai menggunakan Aspose.Slides, ikuti langkah‑langkah berikut:

1. **Install the Library**: Gunakan Maven atau Gradle untuk mengelola dependensi, atau unduh langsung dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Mulai dengan percobaan gratis dengan mengunduh lisensi sementara dari [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Untuk akses penuh, pertimbangkan membeli lisensi di [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Inisialisasi Dasar**:  
   Inisialisasi lingkungan presentasi Anda dengan potongan kode berikut:  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Cara Menambahkan Teks ke Tabel di Aspose.Slides for Java?

Muat `Presentation` baru, buat tabel pada koordinat yang diinginkan, isi sel dengan objek `TextFrame`, dan akhirnya panggil `pres.save("output.pptx", SaveFormat.Pptx)`. Urutan ini menciptakan **create table in PowerPoint**, menyuntikkan teks khusus ke setiap sel, dan menulis hasilnya ke file PPTX dalam alur kerja yang tunggal dan efisien.

### Fitur 1: Membuat Tabel dan Menambahkan Teks ke Sel

#### Ikhtisar
Fitur ini menunjukkan cara **create table**, kemudian **add text to table** pada sel dan selanjutnya **save presentation as pptx**.

#### Langkah‑langkah

**1. Membuat Tabel**  
Pertama, inisialisasi presentasi Anda dan tambahkan tabel pada posisi (50, 50) dengan lebar kolom dan tinggi baris yang ditentukan.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Menambahkan Teks ke Sel**  
Buat paragraf dengan bagian‑bagian teks dan tambahkan ke sel tertentu.  
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

**3. Menyimpan Presentasi**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Fitur 2: Menambahkan TextFrame ke AutoShape dan Mengatur Perataan

#### Ikhtisar
Pelajari cara menambahkan bingkai teks dengan perataan khusus ke sebuah auto shape—contoh **set text alignment java**.

#### Langkah‑langkah

AutoShape adalah bentuk yang dapat menampung teks dan grafik.

**1. Menambahkan AutoShape**  
Tambahkan persegi panjang sebagai AutoShape pada posisi (400, 100) dengan dimensi yang ditentukan.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

Enum `TextAlignment` mendefinisikan opsi perataan horizontal untuk teks dalam sebuah bentuk.

**2. Mengatur Perataan Teks**  
Setel teks menjadi “Text in shape” dan sejajarkan ke kiri.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. Menyimpan Presentasi**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Fitur 3: Menggambar Bingkai di sekitar Paragraf dan Bagian dalam Sel Tabel

#### Ikhtisar
Fitur ini berfokus pada **draw frames around text** dan bahkan **draw rectangle around paragraph** untuk bagian yang mengandung karakter ‘0’.

#### Langkah‑langkah

`IAutoShape` mewakili objek bentuk yang dapat digambar pada slide, seperti persegi panjang yang digunakan sebagai bingkai.

**1. Membuat Tabel**  
Gunakan kembali kode dari “Create Table and Add Text to Cells” untuk penyiapan awal.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Menambahkan Paragraf**  
Gunakan kembali kode pembuatan paragraf dari fitur sebelumnya.  
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

**3. Menggambar Bingkai**  
Iterasi paragraf dan bagian untuk menggambar bingkai di sekitarnya.  
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

**4. Menyimpan Presentasi**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Kesulitan Umum & Tips

- **Null checks** – Selalu bungkus penggunaan `Presentation` Anda dalam blok try‑finally untuk memastikan `pres.dispose()` dijalankan dan sumber daya native dibebaskan.  
- **Akurasi persegi pembatas** – Persegi yang dikembalikan oleh `para.getRect()` mencerminkan tata letak saat ini; jika Anda mengubah ukuran font atau margin, hitung ulang persegi sebelum menggambar bingkai.  
- **Kinerja** – Saat bekerja dengan tabel yang sangat besar, pertimbangkan untuk mengelompokkan penambahan bentuk atau menggunakan satu instance `IAutoShape` yang diperbarui geometri‑nya untuk mengurangi beban memori.  

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan API ini dengan versi JDK yang lebih lama?**  
A: Perpustakaan mendukung JDK 8 ke atas, namun classifier `jdk16` memberikan kinerja terbaik pada runtime yang lebih baru.

**Q: Bagaimana cara mengubah warna bingkai?**  
A: Modifikasi warna isi format garis, misalnya `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Apakah memungkinkan mengekspor slide akhir sebagai gambar?**  
A: Ya—gunakan `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` lalu simpan array byte‑nya.

**Q: Bagaimana jika saya hanya perlu menyoroti kata “Total” di dalam sel?**  
A: Iterasi melalui `cell.getTextFrame().getParagraphs()`, temukan bagian yang berisi “Total”, dan gambar persegi panjang di sekitar kotak pembatas bagian tersebut.

**Q: Apakah Aspose.Slides menangani presentasi besar secara efisien?**  
A: API ini melakukan streaming data dan melepaskan sumber daya ketika `pres.dispose()` dipanggil, yang membantu manajemen memori untuk file berukuran besar.

---

**Terakhir Diperbarui:** 2026-06-23  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (jdk16)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Aspose.Slides for Java: Menguasai Manipulasi Tabel & Teks PPTX dalam Presentasi PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Cara Membuat Bingkai Teks Dinamis di PowerPoint Menggunakan Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Menambahkan Kolom dalam Bingkai Teks menggunakan Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}