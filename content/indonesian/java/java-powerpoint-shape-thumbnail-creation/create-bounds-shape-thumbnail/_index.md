---
title: Buat Thumbnail Bentuk Batas
linktitle: Buat Thumbnail Bentuk Batas
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat gambar mini bentuk dengan batas menggunakan Aspose.Slides untuk Java. Tutorial langkah demi langkah ini memandu Anda melalui prosesnya.
type: docs
weight: 10
url: /id/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---
## Perkenalan
Aspose.Slides untuk Java adalah perpustakaan canggih yang memungkinkan pengembang Java membuat, memanipulasi, dan mengonversi presentasi PowerPoint secara terprogram. Dalam tutorial ini, kita akan mempelajari cara membuat gambar mini suatu bentuk dengan batas menggunakan Aspose.Slides untuk Java.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK) diinstal pada sistem Anda.
2.  Aspose.Slides untuk perpustakaan Java diunduh dan ditambahkan ke proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).

## Paket Impor
Pastikan Anda mengimpor paket yang diperlukan dalam kode Java Anda:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Langkah 1: Siapkan Proyek Anda
Buat proyek Java baru di IDE pilihan Anda dan tambahkan pustaka Aspose.Slides for Java ke dependensi proyek Anda.
## Langkah 2: Buat Instansiasi Objek Presentasi
 Buat contoh a`Presentation` objek dengan memberikan jalur ke file presentasi PowerPoint Anda.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Langkah 3: Buat Thumbnail Bentuk Batas
Sekarang, mari kita membuat gambar mini suatu bentuk dengan batas dari presentasi.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara membuat gambar mini suatu bentuk dengan batas menggunakan Aspose.Slides untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah membuat thumbnail bentuk dalam presentasi PowerPoint Anda secara terprogram.
## FAQ
### Bisakah saya membuat thumbnail untuk bentuk tertentu dalam slide?
Ya, Anda dapat mengakses bentuk individual dalam slide dan membuat thumbnail untuk bentuk tersebut menggunakan Aspose.Slides untuk Java.
### Apakah Aspose.Slides for Java kompatibel dengan semua versi file PowerPoint?
Aspose.Slides untuk Java mendukung berbagai format file PowerPoint, termasuk PPT, PPTX, PPS, PPSX, dan banyak lagi.
### Bisakah saya menyesuaikan tampilan gambar mini yang dihasilkan?
Ya, Anda dapat menyesuaikan properti gambar mini, seperti ukuran dan kualitas, sesuai kebutuhan Anda.
### Apakah Aspose.Slides untuk Java mendukung fitur lain selain pembuatan thumbnail?
Ya, Aspose.Slides untuk Java menyediakan fungsionalitas ekstensif untuk bekerja dengan presentasi PowerPoint, termasuk manipulasi slide, ekstraksi teks, dan pembuatan bagan.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides untuk Java?
 Ya, Anda dapat mengunduh versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).