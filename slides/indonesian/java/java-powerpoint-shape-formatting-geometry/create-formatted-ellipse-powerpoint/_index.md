---
title: Buat Ellipse Terformat di PowerPoint
linktitle: Buat Ellipse Terformat di PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat elips yang diformat di PowerPoint menggunakan Aspose.Slides untuk Java dengan panduan langkah demi langkah terperinci kami.
weight: 17
url: /id/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Selamat datang di tutorial komprehensif tentang membuat elips yang diformat di PowerPoint menggunakan Aspose.Slides untuk Java. Aspose.Slides adalah perpustakaan canggih yang memungkinkan pengembang memanipulasi file PowerPoint secara terprogram. Baik Anda mengotomatiskan pembuatan slide atau menyempurnakan presentasi dengan bentuk khusus, panduan ini akan memandu Anda melalui setiap langkah, memastikan Anda dapat menambahkan elips yang diformat sempurna ke slide Anda dengan mudah. Mari selami dan lihat bagaimana kita bisa mencapainya!
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda menginstal JDK 1.6 atau lebih tinggi.
2.  Aspose.Slides untuk Java: Unduh versi terbaru dari[Aspose.Slide untuk Java](https://releases.aspose.com/slides/java/).
3. Lingkungan Pengembangan Terpadu (IDE): Gunakan IDE seperti IntelliJ IDEA atau Eclipse.
4. Pengetahuan Dasar Java: Diperlukan keakraban dengan pemrograman Java.
## Paket Impor
Untuk mulai menggunakan Aspose.Slides, Anda perlu mengimpor paket yang diperlukan. Inilah cara Anda melakukannya:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Langkah 1: Siapkan Direktori Proyek Anda
Pertama, Anda memerlukan direktori untuk menyimpan file PowerPoint Anda.
### Buat Direktori
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 Pastikan Anda menggantinya`"Your Document Directory"` dengan jalur sebenarnya tempat Anda ingin menyimpan file Anda.
## Langkah 2: Inisialisasi Presentasi
Sekarang, buat instance kelas Presentasi, yang mewakili file PowerPoint.
```java
// Kelas Presentasi Instantiate yang mewakili PPTX
Presentation pres = new Presentation();
```
## Langkah 3: Dapatkan Slide Pertama
Selanjutnya, dapatkan slide pertama dari presentasi di mana Anda akan menambahkan elips.
```java
// Dapatkan slide pertama
ISlide sld = pres.getSlides().get_Item(0);
```
## Langkah 4: Tambahkan Bentuk Ellipse
Tambahkan bentuk otomatis tipe elips ke slide.
```java
// Tambahkan bentuk otomatis tipe elips
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 Di Sini,`50, 150, 150, 50` adalah koordinat dan ukuran elips (posisi x, posisi y, lebar, tinggi).
## Langkah 5: Terapkan Pemformatan ke Ellipse
Sekarang, terapkan beberapa pemformatan pada elips. Kami akan menetapkan warna isian solid dan warna garis.
### Atur Warna Isi
```java
// Terapkan beberapa pemformatan ke bentuk elips
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Atur Warna dan Lebar Garis
```java
// Terapkan beberapa pemformatan ke baris Ellipse
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Langkah 6: Simpan Presentasi
Terakhir, simpan presentasi ke direktori yang Anda tentukan.
```java
// Tulis file PPTX ke disk
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Langkah 7: Buang Objek Presentasi
Buang objek presentasi untuk mengosongkan sumber daya.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Kesimpulan
Selamat! Anda telah berhasil membuat elips yang diformat dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Tutorial ini memandu Anda dalam menyiapkan proyek, menambahkan elips, menerapkan pemformatan, dan menyimpan presentasi Anda. Dengan keterampilan ini, kini Anda dapat menyempurnakan slide PowerPoint Anda secara terprogram, menjadikan presentasi Anda lebih dinamis dan menarik secara visual.
## FAQ
### Apa itu Aspose.Slide untuk Java?
Aspose.Slides untuk Java adalah perpustakaan canggih yang memungkinkan pengembang membuat, memodifikasi, dan mengelola presentasi PowerPoint secara terprogram.
### Bisakah saya menggunakan Aspose.Slides untuk Java dengan IDE apa pun?
Ya, Anda dapat menggunakan Aspose.Slides untuk Java dengan IDE Java apa pun seperti IntelliJ IDEA, Eclipse, atau NetBeans.
### Apakah saya memerlukan lisensi untuk Aspose.Slides?
Ya, Aspose.Slides adalah produk komersial, dan Anda memerlukan lisensi untuk fungsionalitas penuh. Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Slides untuk Java?
 Anda dapat menemukan dokumentasi terperinci di Aspose.Slides untuk Java[halaman dokumentasi](https://reference.aspose.com/slides/java/).
### Apakah ada dukungan yang tersedia untuk Aspose.Slides?
 Ya, Aspose menawarkan dukungan melalui mereka[forum](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
