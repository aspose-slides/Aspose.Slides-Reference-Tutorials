---
date: '2025-12-10'
description: Pelajari cara menambahkan teks ke tabel dan menggambar bingkai di sekitar
  teks di PowerPoint menggunakan Aspose.Slides untuk Java. Panduan ini mencakup pembuatan
  tabel, pengaturan perataan teks, dan membingkai konten.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides untuk Java – menambahkan teks ke tabel & manipulasi bingkai
url: /id/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Menguasai Manipulasi Tabel dan Bingkai dalam Presentasi dengan Aspose.Slides untuk Java

## Pendahuluan

Menyajikan data secara efektif dapat menjadi tantangan di PowerPoint. Baik Anda seorang pengembang perangkat lunak maupun desainer presentasi, **add text to table** sel dan menggambar bingkai di sekitar paragraf penting untuk membuat slide Anda menonjol. Dalam tutorial ini Anda akan melihat secara tepat cara menambahkan teks ke tabel, menyelaraskannya, dan menggambar bingkai di sekitar teks — semua dengan Aspose.Slides untuk Java. Pada akhir tutorial, Anda akan dapat membuat deck yang halus yang menyoroti informasi yang tepat pada waktu yang tepat.

Siap mengubah presentasi Anda? Mari kita mulai!

## Jawaban Cepat
- **Apa arti “add text to table”?** Itu berarti menyisipkan atau memperbarui konten teks dari sel tabel individu secara programatis.  
- **Metode mana yang menyimpan file?** `pres.save("output.pptx", SaveFormat.Pptx)` – langkah **save presentation as pptx** ini menyelesaikan perubahan Anda.  
- **Bagaimana saya dapat menyelaraskan teks di dalam shape?** Gunakan `TextAlignment.Left` (atau Center/Right) melalui `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Bisakah saya menggambar persegi panjang di sekitar paragraf?** Ya – iterasi melalui paragraf, dapatkan persegi pembatasnya, dan tambahkan `IAutoShape` tanpa isi dan dengan garis hitam.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara berfungsi untuk evaluasi; lisensi penuh diperlukan untuk penggunaan produksi.

## Prasyarat

Sebelum menyelami kode, pastikan Anda memiliki hal berikut:

### Perpustakaan yang Diperlukan
Anda memerlukan Aspose.Slides untuk Java. Berikut cara menyertakannya menggunakan Maven atau Gradle:

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
Pastikan Anda memiliki Java Development Kit (JDK) terinstal, sebaiknya JDK 16 atau lebih baru, karena contoh ini menggunakan classifier `jdk16`.

### Prasyarat Pengetahuan
- Pemahaman dasar tentang pemrograman Java.  
- Keterbiasaan dengan perangkat lunak presentasi seperti PowerPoint.  
- Pengalaman menggunakan Integrated Development Environment (IDE) seperti IntelliJ IDEA atau Eclipse.

## Menyiapkan Aspose.Slides untuk Java

Untuk mulai menggunakan Aspose.Slides, ikuti langkah-langkah berikut:

1. **Instal Perpustakaan**: Gunakan Maven atau Gradle untuk mengelola dependensi, atau unduh langsung dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **Perolehan Lisensi**:
   - Mulailah dengan percobaan gratis dengan mengunduh lisensi sementara dari [Temporary License](https://purchase.aspose.com/temporary-license/).
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

## Mengapa menambahkan teks ke tabel dan menggambar bingkai?

Menambahkan teks ke tabel memungkinkan Anda menyajikan data terstruktur dengan jelas, sementara menggambar bingkai di sekitar paragraf atau bagian tertentu (misalnya, yang berisi karakter **'0'**) menarik perhatian audiens ke nilai penting. Kombinasi ini sempurna untuk laporan keuangan, dasbor, atau slide apa pun yang memerlukan penekanan pada angka kunci tanpa kekacauan.

## Cara menambahkan teks ke tabel dalam Aspose.Slides untuk Java

### Fitur 1: Buat Tabel dan Tambahkan Teks ke Sel

#### Gambaran Umum
Fitur ini menunjukkan cara **how to create table**, kemudian **add text to table** sel dan selanjutnya **save presentation as pptx**.

#### Langkah-langkah

**1. Buat Tabel**  
Pertama, inisialisasi presentasi Anda dan tambahkan tabel pada posisi (50, 50) dengan lebar kolom dan tinggi baris yang ditentukan.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Tambahkan Teks ke Sel**  
Buat paragraf dengan bagian teks dan tambahkan ke sel tertentu.
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

**3. Simpan Presentasi**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Fitur 2: Tambahkan TextFrame ke AutoShape dan Atur Penjajaran

#### Gambaran Umum
Pelajari cara menambahkan bingkai teks dengan penjajaran tertentu ke auto shape—contoh dari **set text alignment java**.

#### Langkah-langkah

**1. Tambahkan AutoShape**  
Tambahkan persegi panjang sebagai AutoShape pada posisi (400, 100) dengan dimensi yang ditentukan.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Atur Penjajaran Teks**  
Setel teks menjadi “Text in shape” dan sejajarkan ke kiri.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Simpan Presentasi**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Fitur 3: Gambar Bingkai di sekitar Paragraf dan Bagian dalam Sel Tabel

#### Gambaran Umum
Fitur ini berfokus pada **draw frames around text** dan bahkan **draw rectangle around paragraph** untuk bagian yang berisi karakter ‘0’.

#### Langkah-langkah

**1. Buat Tabel**  
Gunakan kembali kode dari “Create Table and Add Text to Cells” untuk pengaturan awal.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Tambahkan Paragraf**  
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

**3. Gambar Bingkai**  
Iterasi melalui paragraf dan bagian untuk menggambar bingkai di sekitarnya.
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

**4. Simpan Presentasi**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Kesimpulan
Dengan mengikuti panduan ini, Anda dapat **add text to table**, menyelaraskan teks di dalam shape, dan **draw frames around text** untuk menekankan informasi penting. Menguasai teknik ini memungkinkan Anda membuat presentasi yang sangat halus dan berbasis data dengan Aspose.Slides untuk Java. Untuk eksplorasi lebih lanjut, coba gabungkan fitur-fitur ini dengan diagram, animasi, atau men ke PDF.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan API ini dengan versi JDK yang lebih lama?**  
A: Perpustakaan mendukung JDK 8 ke atas, tetapi classifier `jdk16` memberikan kinerja terbaik pada runtime yang lebih baru.

**Q: Bagaimana cara mengubah warna bingkai?**  
A: Modifikasi warna isi format garis, misalnya `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Apakah memungkinkan mengekspor slide akhir sebagai gambar?**  
A: Ya—gunakan `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` dan kemudian simpan array byte.

**Q: Bagaimana jika saya perlu menyorot hanya kata “Total” di dalam sel?**  
A: Iterasi melalui `cell.getTextFrame().getParagraphs()`, temukan bagian yang berisi “Total”, dan gambar persegi panjang di sekitar kotak pembatas bagian tersebut.

**Q: Apakah Aspose.Slides menangani presentasi besar secara efisien?**  
A: API mengalirkan data dan melepaskan sumber daya ketika `pres.dispose()` dipanggil, yang membantu manajemen memori untuk file besar.

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}