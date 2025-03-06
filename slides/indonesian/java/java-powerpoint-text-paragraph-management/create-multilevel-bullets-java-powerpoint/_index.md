---
title: Buat Poin Bertingkat di Java PowerPoint
linktitle: Buat Poin Bertingkat di Java PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat poin bertingkat di PowerPoint menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan contoh kode dan FAQ.
weight: 14
url: /id/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara membuat poin bertingkat dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Menambahkan poin-poin adalah persyaratan umum untuk membuat konten yang terorganisir dan menarik secara visual dalam presentasi. Kami akan menjalani prosesnya langkah demi langkah, memastikan bahwa pada akhir panduan ini, Anda akan diperlengkapi untuk menyempurnakan presentasi Anda dengan poin-poin terstruktur di berbagai tingkatan.
## Prasyarat
Sebelum kita mulai, pastikan Anda telah menyiapkan yang berikut:
- Lingkungan Pengembangan Java: Pastikan Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Slides for Java Library: Unduh dan instal Aspose.Slides for Java dari[Di Sini](https://releases.aspose.com/slides/java/).
- IDE: Gunakan Java Integrated Development Environment (IDE) pilihan Anda seperti IntelliJ IDEA, Eclipse, atau lainnya.
- Pengetahuan Dasar: Keakraban dengan pemrograman Java dan konsep dasar PowerPoint akan sangat membantu.

## Paket Impor
Sebelum masuk ke tutorial, mari impor paket yang diperlukan dari Aspose.Slides untuk Java yang akan kita gunakan sepanjang tutorial.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Langkah 1: Siapkan Proyek Anda
Pertama, buat proyek Java baru di IDE Anda dan tambahkan Aspose.Slides for Java ke dependensi proyek Anda. Pastikan file JAR Aspose.Slides yang diperlukan disertakan dalam jalur pembangunan proyek Anda.
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
```
## Langkah 2: Inisialisasi Objek Presentasi
Mulailah dengan membuat contoh presentasi baru. Ini akan berfungsi sebagai dokumen PowerPoint tempat Anda akan menambahkan slide dan konten.
```java
Presentation pres = new Presentation();
```
## Langkah 3: Akses Slide
Selanjutnya, akses slide tempat Anda ingin menambahkan poin bertingkat. Untuk contoh ini, kita akan bekerja dengan slide pertama (`Slide(0)`).
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Langkah 4: Tambahkan BentukOtomatis dengan Bingkai Teks
Tambahkan BentukOtomatis ke slide tempat Anda akan menempatkan teks dengan poin bertingkat.
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Langkah 5: Akses Bingkai Teks
Akses bingkai teks dalam BentukOtomatis tempat Anda akan menambahkan paragraf dengan poin-poin.
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); //Hapus paragraf default
```
## Langkah 6: Tambahkan Paragraf dengan Poin
Tambahkan paragraf dengan tingkat poin yang berbeda. Berikut cara menambahkan poin bertingkat:
```java
// Tingkat pertama
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
// Tingkat kedua
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
// Tingkat Ketiga
IParagraph para3 = new Paragraph();
para3.setText("Third Level");
para3.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para3.getParagraphFormat().getBullet().setChar((char) 8226);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para3.getParagraphFormat().setDepth((short) 2);
text.getParagraphs().add(para3);
// Tingkat Keempat
IParagraph para4 = new Paragraph();
para4.setText("Fourth Level");
para4.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para4.getParagraphFormat().getBullet().setChar('-');
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para4.getParagraphFormat().setDepth((short) 3);
text.getParagraphs().add(para4);
```
## Langkah 7: Simpan Presentasi
Terakhir, simpan presentasi sebagai file PPTX di direktori yang Anda inginkan.
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## Kesimpulan
Dalam tutorial ini, kita telah membahas cara membuat poin bertingkat dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat secara efektif menyusun konten Anda dengan poin-poin yang terorganisir di berbagai tingkat, sehingga meningkatkan kejelasan dan daya tarik visual presentasi Anda.
## FAQ
### Bisakah saya menyesuaikan simbol poin lebih lanjut?
Ya, Anda dapat menyesuaikan simbol poin dengan menyesuaikan karakter Unicode atau menggunakan bentuk yang berbeda.
### Apakah Aspose.Slides mendukung jenis poin lainnya?
Ya, Aspose.Slides mendukung berbagai jenis poin termasuk simbol, angka, dan gambar khusus.
### Apakah Aspose.Slides kompatibel dengan semua versi PowerPoint?
Aspose.Slides menghasilkan presentasi yang kompatibel dengan Microsoft PowerPoint 2007 dan versi yang lebih tinggi.
### Bisakah saya mengotomatiskan pembuatan slide menggunakan Aspose.Slides?
Ya, Aspose.Slides menyediakan API untuk mengotomatiskan pembuatan, modifikasi, dan manipulasi presentasi PowerPoint.
### Di mana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk Java?
 Anda bisa mendapatkan dukungan dari komunitas dan pakar Aspose.Slides di[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
