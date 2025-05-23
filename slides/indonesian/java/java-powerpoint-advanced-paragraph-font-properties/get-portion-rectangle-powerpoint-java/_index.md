---
"description": "Pelajari cara membuat persegi panjang di PowerPoint menggunakan Aspose.Slides untuk Java dengan tutorial terperinci dan langkah demi langkah ini. Sempurna untuk pengembang Java."
"linktitle": "Dapatkan Porsi Persegi Panjang di PowerPoint dengan Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Dapatkan Porsi Persegi Panjang di PowerPoint dengan Java"
"url": "/id/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dapatkan Porsi Persegi Panjang di PowerPoint dengan Java

## Perkenalan
Membuat presentasi dinamis di Java sangat mudah dengan Aspose.Slides untuk Java. Dalam tutorial ini, kita akan menyelami seluk-beluk membuat persegi panjang di PowerPoint menggunakan Aspose.Slides. Kita akan membahas semuanya mulai dari menyiapkan lingkungan hingga menguraikan kode langkah demi langkah. Jadi, mari kita mulai!
## Prasyarat
Sebelum kita masuk ke kode, mari pastikan Anda memiliki semua yang dibutuhkan untuk mengikutinya dengan lancar:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK 8 atau lebih tinggi di komputer Anda.
2. Aspose.Slides untuk Java: Unduh versi terbaru dari [Di Sini](https://releases.aspose.com/slides/java/).
3. Lingkungan Pengembangan Terpadu (IDE): Eclipse, IntelliJ IDEA, atau IDE Java lainnya pilihan Anda.
4. Pengetahuan Dasar Java: Pemahaman tentang pemrograman Java sangatlah penting.
## Paket Impor
Pertama-tama, mari impor paket-paket yang diperlukan. Paket ini akan mencakup Aspose.Slides dan beberapa paket lainnya untuk menangani tugas kita secara efisien.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Langkah 1: Menyiapkan Presentasi
Langkah pertama adalah membuat presentasi baru. Ini akan menjadi kanvas untuk kita kerjakan.
```java
Presentation pres = new Presentation();
```
## Langkah 2: Membuat Tabel
Sekarang, mari tambahkan tabel ke slide pertama presentasi kita. Tabel ini akan berisi sel-sel tempat kita akan menambahkan teks.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Langkah 3: Menambahkan Paragraf ke Sel
Selanjutnya, kita akan membuat paragraf dan menambahkannya ke sel tertentu dalam tabel. Ini melibatkan penghapusan teks yang ada dan kemudian menambahkan paragraf baru.
```java
// Membuat paragraf
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
Kita perlu mendapatkan koordinat sudut kiri atas sel tabel. Ini akan membantu kita menempatkan bentuk-bentuk tersebut secara akurat.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Langkah 6: Menambahkan Bingkai ke Paragraf dan Bagian
Menggunakan `IParagraph.getRect()` Dan `IPortion.getRect()` metode, kita dapat menambahkan bingkai ke paragraf dan bagian. Ini melibatkan pengulangan melalui paragraf dan bagian, membuat bentuk di sekitarnya, dan menyesuaikan tampilannya.
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
Demikian pula, kita akan menambahkan bingkai ke paragraf di AutoShape kita, untuk meningkatkan daya tarik visual presentasi.
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
Terakhir, kita akan menyimpan presentasi kita ke jalur yang ditentukan.
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
Selamat! Anda telah berhasil mempelajari cara mendapatkan bagian persegi panjang di PowerPoint menggunakan Aspose.Slides untuk Java. Pustaka canggih ini membuka banyak kemungkinan untuk membuat presentasi yang dinamis dan menarik secara visual secara terprogram. Pelajari lebih dalam Aspose.Slides dan jelajahi lebih banyak fitur untuk menyempurnakan presentasi Anda lebih jauh.
## Pertanyaan yang Sering Diajukan
### Apa itu Aspose.Slides untuk Java?
Aspose.Slides untuk Java adalah pustaka hebat yang memungkinkan pengembang untuk membuat, memodifikasi, dan memanipulasi presentasi PowerPoint secara terprogram.
### Dapatkah saya menggunakan Aspose.Slides untuk Java dalam proyek komersial?
Ya, Aspose.Slides untuk Java dapat digunakan dalam proyek komersial. Anda dapat membeli lisensi dari [Di Sini](https://purchase.aspose.com/buy).
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides untuk Java?
Ya, Anda dapat mengunduh uji coba gratis dari [Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi untuk Aspose.Slides untuk Java?
Dokumentasinya tersedia [Di Sini](https://reference.aspose.com/slides/java/).
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk Java?
Anda bisa mendapatkan dukungan dari forum Aspose [Di Sini](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}