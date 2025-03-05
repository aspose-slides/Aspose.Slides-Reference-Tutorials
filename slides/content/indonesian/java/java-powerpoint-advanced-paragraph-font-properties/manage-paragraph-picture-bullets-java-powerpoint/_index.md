---
title: Kelola Poin Gambar Paragraf di Java PowerPoint
linktitle: Kelola Poin Gambar Paragraf di Java PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menambahkan poin gambar kustom ke slide PowerPoint menggunakan Aspose.Slides untuk Java. Ikuti panduan terperinci langkah demi langkah ini untuk integrasi yang lancar.
type: docs
weight: 11
url: /id/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---
## Perkenalan
Membuat presentasi yang menarik dan menarik secara visual adalah keterampilan penting dalam dunia bisnis modern. Pengembang Java dapat memanfaatkan Aspose.Slides untuk menyempurnakan presentasi mereka dengan poin gambar yang disesuaikan dalam slide PowerPoint. Tutorial ini akan memandu Anda melalui proses langkah demi langkah, memastikan Anda dapat dengan percaya diri menambahkan poin gambar ke presentasi Anda.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Kit Pengembangan Java (JDK) diinstal
- Lingkungan Pengembangan Terintegrasi (IDE) seperti Eclipse atau IntelliJ IDEA
- Aspose.Slide untuk perpustakaan Java
- Pengetahuan dasar tentang pemrograman Java
- File gambar untuk gambar peluru
 Untuk mengunduh perpustakaan Aspose.Slides untuk Java, kunjungi[Unduh Halaman](https://releases.aspose.com/slides/java/) . Untuk dokumentasi, periksa[dokumentasi](https://reference.aspose.com/slides/java/).
## Paket Impor
Pertama, pastikan Anda telah mengimpor paket yang diperlukan untuk proyek Anda. Tambahkan impor berikut di awal file Java Anda:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Mari kita bagi prosesnya menjadi langkah-langkah yang dapat dikelola.
## Langkah 1: Siapkan Direktori Proyek Anda
Buat direktori baru untuk proyek Anda. Direktori ini akan berisi file Java Anda, perpustakaan Aspose.Slides, dan file gambar untuk poin.
```java
String dataDir = "Your Document Directory";
```
## Langkah 2: Inisialisasi Presentasi
 Inisialisasi instance baru dari`Presentation` kelas. Objek ini mewakili presentasi PowerPoint Anda.
```java
Presentation presentation = new Presentation();
```
## Langkah 3: Akses Slide Pertama
Akses slide pertama presentasi. Slide memiliki indeks nol, jadi slide pertama berada pada indeks 0.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Langkah 4: Muat Gambar Bullet
Muat gambar yang ingin Anda gunakan untuk poin. Gambar ini harus ditempatkan di direktori proyek Anda.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Langkah 5: Tambahkan BentukOtomatis ke Slide
Tambahkan BentukOtomatis ke slide. Bentuknya akan berisi teks dengan poin-poin khusus.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Langkah 6: Akses Bingkai Teks
Akses bingkai teks BentukOtomatis untuk memanipulasi paragrafnya.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Langkah 7: Hapus Paragraf Default
Hapus paragraf default yang secara otomatis ditambahkan ke bingkai teks.
```java
textFrame.getParagraphs().removeAt(0);
```
## Langkah 8: Buat Paragraf Baru
Buat paragraf baru dan atur teksnya. Paragraf ini akan berisi poin gambar khusus.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Langkah 9: Atur Gaya dan Gambar Poin
Atur gaya poin untuk menggunakan gambar khusus yang dimuat sebelumnya.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Langkah 10: Sesuaikan Ketinggian Peluru
Atur ketinggian peluru untuk memastikannya terlihat bagus dalam presentasi.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Langkah 11: Tambahkan Paragraf ke Bingkai Teks
Tambahkan paragraf yang baru dibuat ke bingkai teks BentukOtomatis.
```java
textFrame.getParagraphs().add(paragraph);
```
## Langkah 12: Simpan Presentasi
Terakhir, simpan presentasi sebagai file PPTX dan PPT.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Kesimpulan
 Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menambahkan poin gambar kustom ke presentasi PowerPoint Anda menggunakan Aspose.Slides untuk Java. Perpustakaan canggih ini menawarkan beragam fitur untuk membantu Anda membuat presentasi yang profesional dan menarik secara visual. Jangan lupa untuk menjelajahinya[dokumentasi](https://reference.aspose.com/slides/java/)untuk fitur lanjutan dan opsi penyesuaian lainnya.
## FAQ
### Apa itu Aspose.Slide untuk Java?
Aspose.Slides untuk Java adalah perpustakaan canggih yang memungkinkan pengembang Java membuat, memodifikasi, dan memanipulasi presentasi PowerPoint secara terprogram.
### Bisakah saya menggunakan gambar apa pun untuk poin gambar?
Ya, Anda dapat menggunakan gambar apa pun untuk poin gambar asalkan dapat diakses dari direktori proyek Anda.
### Apakah saya memerlukan lisensi untuk menggunakan Aspose.Slides untuk Java?
 Aspose.Slides untuk Java memerlukan lisensi untuk fungsionalitas penuh. Anda dapat memperoleh lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/) atau membeli lisensi penuh[Di Sini](https://purchase.aspose.com/buy).
### Bisakah saya menambahkan beberapa paragraf dengan gaya poin berbeda dalam satu BentukOtomatis?
Ya, Anda dapat menambahkan beberapa paragraf dengan gaya poin berbeda ke satu BentukOtomatis dengan membuat dan mengonfigurasi setiap paragraf satu per satu.
### Di mana saya dapat menemukan lebih banyak contoh dan dukungan?
 Anda dapat menemukan lebih banyak contoh di[dokumentasi](https://reference.aspose.com/slides/java/) dan dapatkan dukungan dari komunitas Aspose di[forum](https://forum.aspose.com/c/slides/11).