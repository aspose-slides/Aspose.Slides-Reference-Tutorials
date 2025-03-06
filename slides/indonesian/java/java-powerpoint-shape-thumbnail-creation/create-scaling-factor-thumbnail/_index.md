---
title: Buat Thumbnail Faktor Penskalaan
linktitle: Buat Thumbnail Faktor Penskalaan
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat gambar mini faktor penskalaan di Java menggunakan Aspose.Slides untuk Java. Panduan yang mudah diikuti dengan petunjuk langkah demi langkah.
weight: 12
url: /id/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan thumbnail faktor penskalaan menggunakan Aspose.Slides untuk Java. Ikuti petunjuk langkah demi langkah ini untuk mencapai hasil yang Anda inginkan.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada sistem Anda.
- Aspose.Slides untuk perpustakaan Java diunduh dan disiapkan di proyek Java Anda.
- Pemahaman dasar bahasa pemrograman Java.

## Paket Impor
Pertama, impor paket yang diperlukan untuk bekerja dengan Aspose.Slides dalam kode Java Anda. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah:
## Langkah 1: Atur Direktori Dokumen
Tentukan jalur ke direktori dokumen Anda tempat file presentasi PowerPoint berada.
```java
String dataDir = "Your Document Directory";
```
 Mengganti`"Your Document Directory"` dengan jalur ke direktori dokumen Anda yang sebenarnya.
## Langkah 2: Buat Instansiasi Objek Presentasi
Buat instance kelas Presentasi untuk mewakili file presentasi PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Pastikan untuk mengganti`"HelloWorld.pptx"` dengan nama file presentasi PowerPoint Anda.
## Langkah 3: Buat Gambar Skala Penuh
Hasilkan gambar skala penuh dari slide yang diinginkan dari presentasi.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Kode ini mengambil thumbnail dari bentuk pertama pada slide pertama presentasi.
## Langkah 4: Simpan Gambar
Simpan gambar yang dihasilkan ke disk dalam format PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Pastikan untuk mengganti`"Scaling Factor Thumbnail_out.png"` dengan nama file keluaran yang diinginkan.

## Kesimpulan
Kesimpulannya, Anda telah berhasil membuat thumbnail faktor penskalaan menggunakan Aspose.Slides for Java. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah mengintegrasikan fungsi ini ke dalam aplikasi Java Anda.
## FAQ
### Bisakah saya menggunakan Aspose.Slides untuk Java dengan IDE Java apa pun?
Ya, Aspose.Slides untuk Java dapat digunakan dengan Java Integrated Development Environment (IDE) apa pun seperti Eclipse, IntelliJ IDEA, atau NetBeans.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides untuk Java?
 Ya, Anda dapat memanfaatkan uji coba gratis Aspose.Slides untuk Java dengan mengunjungi[situs web](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan untuk Aspose.Slides untuk Java?
 Anda dapat menemukan dukungan untuk Aspose.Slides untuk Java di[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11).
### Bagaimana saya bisa membeli Aspose.Slides untuk Java?
 Anda dapat membeli Aspose.Slides untuk Java dari[halaman pembelian](https://purchase.aspose.com/buy).
### Apakah saya memerlukan lisensi sementara untuk menggunakan Aspose.Slides untuk Java?
 Ya, Anda bisa mendapatkan lisensi sementara dari[halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
