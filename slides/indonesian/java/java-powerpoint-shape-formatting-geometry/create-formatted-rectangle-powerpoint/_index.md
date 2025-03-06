---
title: Buat Persegi Panjang Berformat di PowerPoint
linktitle: Buat Persegi Panjang Berformat di PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat dan memformat persegi panjang di PowerPoint menggunakan Aspose.Slides untuk Java dengan panduan langkah demi langkah ini.
weight: 18
url: /id/java/java-powerpoint-shape-formatting-geometry/create-formatted-rectangle-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan persegi panjang berformat dalam slide PowerPoint menggunakan Aspose.Slides untuk Java. Kami akan menguraikan setiap langkah, memastikan Anda dapat mengikuti dan menerapkannya dalam proyek Anda sendiri.
## Prasyarat
Sebelum kita mendalami kodenya, mari kita bahas prasyaratnya. Anda memerlukan yang berikut ini:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2. Aspose.Slides for Java Library: Unduh dan sertakan perpustakaan Aspose.Slides for Java dalam proyek Anda.
3. Lingkungan Pengembangan Terintegrasi (IDE): IDE seperti IntelliJ IDEA atau Eclipse akan membuat pengalaman pengkodean Anda lebih lancar.
4. Pengetahuan Dasar Java: Keakraban dengan pemrograman Java akan membantu Anda mengikuti tutorial ini.
## Paket Impor
Untuk memulai, Anda perlu mengimpor paket yang diperlukan dari perpustakaan Aspose.Slides. Inilah cara Anda melakukannya:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
Impor ini sangat penting karena membawa kelas yang diperlukan untuk membuat dan memformat bentuk dalam presentasi PowerPoint Anda.
## Langkah 1: Menyiapkan Direktori Proyek
Pertama, Anda perlu membuat direktori untuk proyek Anda. Direktori ini akan menyimpan file PowerPoint Anda.
```java
String dataDir = "Your Document Directory";
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
Kode ini memeriksa apakah direktori tersebut ada dan membuatnya jika tidak ada. Merupakan praktik yang baik untuk menjaga file proyek Anda tetap teratur.
## Langkah 2: Buat Instansiasi Kelas Presentasi
 Selanjutnya, Anda akan membuat instance`Presentation` kelas, yang mewakili file PowerPoint Anda.
```java
Presentation pres = new Presentation();
```
Baris kode ini membuat presentasi baru dan kosong yang dapat Anda tambahkan kontennya.
## Langkah 3: Tambahkan Slide ke Presentasi
Sekarang, mari tambahkan slide ke presentasi Anda. Secara default, presentasi baru berisi satu slide, jadi kami akan mengerjakannya.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
Cuplikan kode ini mengambil slide pertama dari presentasi.
## Langkah 4: Tambahkan Bentuk Persegi Panjang
Sekarang kita akan menambahkan persegi panjang ke slide.
```java
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Di sini, kami menambahkan persegi panjang dengan dimensi tertentu (lebar, tinggi) dan posisi (x, y) ke slide.
## Langkah 5: Format Persegi Panjang
Mari terapkan beberapa pemformatan untuk membuat persegi panjang menarik secara visual.
```java
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
Kode ini mengatur tipe isian menjadi padat dan warna isian menjadi coklat.
## Format Perbatasan Persegi Panjang
Selanjutnya, kita akan memformat batas persegi panjang.
```java
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
Kode ini mengatur warna batas menjadi hitam dan lebar batas menjadi 5.
## Langkah 6: Simpan Presentasi
Terakhir, simpan presentasi ke direktori proyek Anda.
```java
pres.save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
Baris kode ini menyimpan presentasi sebagai file PPTX di direktori yang Anda tentukan.
## Langkah 7: Bersihkan Sumber Daya
 Merupakan praktik yang baik untuk membuangnya`Presentation` keberatan untuk mengosongkan sumber daya.
```java
if (pres != null) pres.dispose();
```
Hal ini memastikan bahwa semua sumber daya dilepaskan dengan benar.
## Kesimpulan
Membuat dan memformat bentuk dalam presentasi PowerPoint menggunakan Aspose.Slides for Java adalah proses yang mudah. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat mengotomatiskan pembuatan slide yang menarik secara visual dengan mudah. Baik Anda mengembangkan aplikasi untuk pelaporan bisnis, konten pendidikan, atau presentasi dinamis, Aspose.Slides untuk Java menawarkan alat yang Anda butuhkan untuk berhasil.
## FAQ
### Apa itu Aspose.Slide untuk Java?
Aspose.Slides untuk Java adalah pustaka yang memungkinkan pengembang membuat, memodifikasi, dan mengonversi presentasi PowerPoint secara terprogram.
### Bisakah saya menggunakan Aspose.Slides untuk Java dengan IDE apa pun?
Ya, Anda dapat menggunakan Aspose.Slides untuk Java dengan IDE apa pun yang kompatibel dengan Java seperti IntelliJ IDEA, Eclipse, atau NetBeans.
### Bagaimana saya bisa mendapatkan uji coba gratis Aspose.Slides untuk Java?
 Anda dapat mengunduh uji coba gratis Aspose.Slides untuk Java dari[Di Sini](https://releases.aspose.com/).
###  Apakah perlu membuangnya`Presentation` object?
 Ya, membuangnya`Presentation` objek membantu mengosongkan sumber daya dan menghindari kebocoran memori.
### Di mana saya dapat menemukan dokumentasi Aspose.Slides untuk Java?
 Dokumentasi tersedia[Di Sini](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
