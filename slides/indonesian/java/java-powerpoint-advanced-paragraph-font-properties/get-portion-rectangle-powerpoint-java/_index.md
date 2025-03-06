---
title: Dapatkan Porsi Persegi Panjang di PowerPoint dengan Java
linktitle: Dapatkan Porsi Persegi Panjang di PowerPoint dengan Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mendapatkan bagian persegi panjang di PowerPoint menggunakan Aspose.Slides untuk Java dengan tutorial langkah demi langkah yang mendetail ini. Sempurna untuk pengembang Java.
weight: 12
url: /id/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Membuat presentasi dinamis di Java sangatlah mudah dengan Aspose.Slides untuk Java. Dalam tutorial ini, kita akan mendalami seluk beluk cara mendapatkan bagian persegi panjang di PowerPoint menggunakan Aspose.Slides. Kami akan membahas semuanya mulai dari menyiapkan lingkungan Anda hingga menguraikan kode langkah demi langkah. Jadi, mari kita mulai!
## Prasyarat
Sebelum kita beralih ke kode, pastikan Anda memiliki semua yang perlu Anda ikuti dengan lancar:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK 8 atau lebih tinggi di mesin Anda.
2.  Aspose.Slides untuk Java: Unduh versi terbaru dari[Di Sini](https://releases.aspose.com/slides/java/).
3. Lingkungan Pengembangan Terpadu (IDE): Eclipse, IntelliJ IDEA, atau IDE Java lainnya pilihan Anda.
4. Pengetahuan Dasar Java: Pemahaman tentang pemrograman Java sangat penting.
## Paket Impor
Hal pertama yang pertama, mari impor paket yang diperlukan. Ini akan mencakup Aspose.Slides dan beberapa lainnya untuk menangani tugas kita secara efisien.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Langkah 1: Menyiapkan Presentasi
Langkah pertama adalah membuat presentasi baru. Ini akan menjadi kanvas kami untuk dikerjakan.
```java
Presentation pres = new Presentation();
```
## Langkah 2: Membuat Tabel
Sekarang, mari tambahkan tabel ke slide pertama presentasi kita. Tabel ini akan berisi sel tempat kita akan menambahkan teks.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Langkah 3: Menambahkan Paragraf ke Sel
Selanjutnya, kita akan membuat paragraf dan menambahkannya ke sel tertentu di tabel. Ini melibatkan pembersihan teks yang ada dan kemudian menambahkan paragraf baru.
```java
// Buat paragraf
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Tambahkan teks ke dalam sel tabel
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Langkah 4: Menambahkan Bingkai Teks ke BentukOtomatis
Untuk membuat presentasi kita lebih dinamis, kita akan menambahkan bingkai teks ke BentukOtomatis dan mengatur perataannya.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Langkah 5: Menghitung Koordinat
Kita perlu mendapatkan koordinat pojok kiri atas sel tabel. Ini akan membantu kita menempatkan bentuk secara akurat.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Langkah 6: Menambahkan Bingkai ke Paragraf dan Bagian
 Menggunakan`IParagraph.getRect()` Dan`IPortion.getRect()`metode, kita dapat menambahkan bingkai ke paragraf dan bagian kita. Ini melibatkan pengulangan paragraf dan bagian, membuat bentuk di sekelilingnya, dan menyesuaikan tampilannya.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Langkah 7: Menambahkan Bingkai ke Paragraf BentukOtomatis
Demikian pula, kami akan menambahkan bingkai ke paragraf di BentukOtomatis kami, meningkatkan daya tarik visual presentasi.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Langkah 8: Menyimpan Presentasi
Terakhir, kita akan menyimpan presentasi kita ke jalur tertentu.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Langkah 9: Membersihkan
Merupakan praktik yang baik untuk membuang objek presentasi untuk mengosongkan sumber daya.
```java
if (pres != null) pres.dispose();
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mendapatkan bagian persegi panjang di PowerPoint menggunakan Aspose.Slides untuk Java. Pustaka yang kuat ini membuka banyak kemungkinan untuk membuat presentasi yang dinamis dan menarik secara visual secara terprogram. Selami lebih dalam Aspose.Slides dan jelajahi lebih banyak fitur untuk menyempurnakan presentasi Anda lebih jauh.
## FAQ
### Apa itu Aspose.Slide untuk Java?
Aspose.Slides untuk Java adalah perpustakaan canggih yang memungkinkan pengembang membuat, memodifikasi, dan memanipulasi presentasi PowerPoint secara terprogram.
### Bisakah saya menggunakan Aspose.Slides untuk Java dalam proyek komersial?
 Ya, Aspose.Slides untuk Java dapat digunakan dalam proyek komersial. Anda dapat membeli lisensi dari[Di Sini](https://purchase.aspose.com/buy).
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides untuk Java?
 Ya, Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi Aspose.Slides untuk Java?
 Dokumentasi tersedia[Di Sini](https://reference.aspose.com/slides/java/).
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk Java?
 Anda bisa mendapatkan dukungan dari forum Aspose[Di Sini](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
