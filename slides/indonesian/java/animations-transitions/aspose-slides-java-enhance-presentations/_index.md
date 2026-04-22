---
date: '2026-02-09'
description: Pelajari cara menggambar bingkai di sekitar teks dan menambahkan teks
  ke sel tabel di PowerPoint menggunakan Aspose.Slides for Java. Tutorial ini mencakup
  pembuatan tabel, pengaturan perataan teks, dan menyimpan presentasi sebagai pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Cara Menggambar Bingkai dan Menambahkan Teks ke Tabel dengan Aspose.Slides
  untuk Java
url: /id/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menggambar Bingkai dan Menambahkan Teks ke Tabel dalam Presentasi dengan Aspose.Slides untuk Java

## Pendahuluan

Menyajikan data secara jelas di PowerPoint dapat menjadi tantangan nyata, terutama ketika Anda perlu **add text to table** pada sel dan menyoroti nilai penting dengan petunjuk visual. Dalam panduan ini Anda akan belajar **how to draw frames** di sekitar paragraf tertentu, mengatur penyelarasan teks di dalam shape, dan akhirnya **save presentation as pptx**—semua menggunakan Aspose.Slides untuk Java. Pada akhir tutorial Anda akan memiliki deck slide yang dipoles dan menarik perhatian audiens tepat di tempat yang Anda inginkan.

Siap membuat slide Anda menonjol? Mari kita jalani prosesnya langkah demi langkah.

## Jawaban Cepat
- **Apa arti “add text to table”?** Itu berarti menyisipkan atau memperbarui konten teks dari sel tabel individu secara programatis.  
- **Metode mana yang menyimpan file?** `pres.save("output.pptx", SaveFormat.Pptx)` – langkah **save presentation as pptx** ini menyelesaikan perubahan Anda.  
- **Bagaimana cara menyelaraskan teks di dalam shape?** Gunakan `TextAlignment.Left` (atau Center/Right) melalui `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Bisakah saya menggambar persegi panjang di sekitar paragraf?** Ya – iterasi paragraf, dapatkan persegi pembatasnya, dan tambahkan `IAutoShape` tanpa isi dan garis hitam.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara berfungsi untuk evaluasi; lisensi penuh diperlukan untuk penggunaan produksi.  

## Mengapa menggambar bingkai di sekitar teks?

Menggambar bingkai (atau persegi panjang) di sekitar paragraf atau bagian tertentu (misalnya, teks apa pun yang mengandung karakter **'0'**) langsung menarik perhatian. Teknik ini ideal untuk:

- Menyoroti angka keuangan utama dalam tabel.  
- Menekankan peringatan atau catatan penting dalam slide.  
- Membuat pemisah visual tanpa menambahkan shape tambahan secara manual.

## Prasyarat

Sebelum menyelam ke kode, pastikan Anda memiliki hal berikut:

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

### Penyiapan Lingkungan
Pastikan Anda memiliki Java Development Kit (JDK) terpasang, sebaiknya JDK 16 atau lebih baru, karena contoh ini menggunakan classifier `jdk16`.

### Prasyarat Pengetahuan
- Pemahaman dasar tentang pemrograman Java.  
- Keterbiasaan dengan perangkat lunak presentasi seperti PowerPoint.  
- Pengalaman menggunakan Integrated Development Environment (IDE) seperti IntelliJ IDEA atau Eclipse.

## Menyiapkan Aspose.Slides untuk Java

Untuk mulai menggunakan Aspose.Slides, ikuti langkah-langkah berikut:

1. **Install the Library**: Gunakan Maven atau Gradle untuk mengelola dependensi, atau unduh langsung dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Mulai dengan trial gratis dengan mengunduh lisensi sementara dari [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Untuk akses penuh, pertimbangkan membeli lisensi di [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:
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

## Cara Menambahkan Teks ke Tabel dalam Aspose.Slides untuk Java

### Fitur 1: Membuat Tabel dan Menambahkan Teks ke Sel

#### Gambaran Umum
Fitur ini menunjukkan cara **create table**, kemudian **add text to table** pada sel dan selanjutnya **save presentation as pptx**.

#### Langkah-langkah

**1. Create a Table**  
Pertama, inisialisasi presentasi Anda dan tambahkan tabel pada posisi (50, 50) dengan lebar kolom dan tinggi baris yang ditentukan.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
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

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Fitur 2: Menambahkan TextFrame ke AutoShape dan Mengatur Penyelarasan

#### Gambaran Umum
Pelajari cara menambahkan text frame dengan penyelarasan khusus ke auto shape—contoh **set text alignment java**.

#### Langkah-langkah

**1. Add an AutoShape**  
Tambahkan persegi panjang sebagai AutoShape pada posisi (400, 100) dengan dimensi yang ditentukan.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
Set teks menjadi “Text in shape” dan sejajarkan ke kiri.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Fitur 3: Menggambar Bingkai di sekitar Paragraf dan Bagian dalam Sel Tabel

#### Gambaran Umum
Fitur ini berfokus pada **draw frames around text** dan bahkan **draw rectangle around paragraph** untuk bagian yang mengandung karakter ‘0’.

#### Langkah-langkah

**1. Create a Table**  
Gunakan kembali kode dari “Create Table and Add Text to Cells” untuk penyiapan awal.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
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

**3. Draw Frames**  
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

**4. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Kesalahan Umum & Tips

- **Null checks** – Selalu bungkus penggunaan `Presentation` Anda dalam blok try‑finally untuk memastikan `pres.dispose()` dijalankan dan membebaskan sumber daya native.  
- **Bounding rectangle accuracy** – Persegi yang dikembalikan oleh `para.getRect()` mencerminkan tata letak saat ini; jika Anda mengubah ukuran font atau margin, hitung ulang persegi sebelum menggambar bingkai.  
- **Performance** – Saat bekerja dengan tabel sangat besar, pertimbangkan batch penambahan shape atau gunakan kembali satu instance `IAutoShape` dengan geometri yang diperbarui untuk mengurangi beban memori.

## Pertanyaan yang Sering Diajukan

**Q: Can I use these APIs with older JDK versions?**  
A: Perpustakaan ini mendukung JDK 8 ke atas, tetapi classifier `jdk16` memberikan kinerja terbaik pada runtime yang lebih baru.

**Q: How do I change the frame color?**  
A: Modifikasi warna isi format garis, misalnya `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: Ya—gunakan `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` lalu simpan array byte-nya.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: Iterasi melalui `cell.getTextFrame().getParagraphs()`, temukan bagian yang berisi “Total”, dan gambar persegi di sekitar kotak pembatas bagian tersebut.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: API ini melakukan streaming data dan melepaskan sumber daya saat `pres.dispose()` dipanggil, yang membantu manajemen memori untuk file besar.

---

**Terakhir Diperbarui:** 2026-02-09  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (jdk16)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
