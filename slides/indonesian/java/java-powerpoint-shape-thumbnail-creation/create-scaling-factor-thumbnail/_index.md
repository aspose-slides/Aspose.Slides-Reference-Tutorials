---
"description": "Pelajari cara membuat thumbnail faktor skala di Java menggunakan Aspose.Slides untuk Java. Panduan yang mudah diikuti dengan petunjuk langkah demi langkah."
"linktitle": "Buat Gambar Mini Faktor Skala"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Buat Gambar Mini Faktor Skala"
"url": "/id/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Buat Gambar Mini Faktor Skala

## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan thumbnail faktor skala menggunakan Aspose.Slides untuk Java. Ikuti petunjuk langkah demi langkah ini untuk mencapai hasil yang Anda inginkan.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) terinstal di sistem Anda.
- Aspose.Slides untuk pustaka Java diunduh dan disiapkan dalam proyek Java Anda.
- Pemahaman dasar tentang bahasa pemrograman Java.

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

Sekarang, mari kita uraikan contoh yang diberikan menjadi beberapa langkah:
## Langkah 1: Mengatur Direktori Dokumen
Tentukan jalur ke direktori dokumen tempat file presentasi PowerPoint berada.
```java
String dataDir = "Your Document Directory";
```
Mengganti `"Your Document Directory"` dengan jalur ke direktori dokumen Anda sebenarnya.
## Langkah 2: Membuat Instansiasi Objek Presentasi
Buat contoh kelas Presentasi untuk merepresentasikan berkas presentasi PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
Pastikan untuk mengganti `"HelloWorld.pptx"` dengan nama berkas presentasi PowerPoint Anda.
## Langkah 3: Buat Gambar Skala Penuh
Hasilkan gambar skala penuh dari slide yang diinginkan dari presentasi.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Kode ini mengambil gambar mini bentuk pertama pada slide pertama presentasi.
## Langkah 4: Simpan Gambar
Simpan gambar yang dihasilkan ke disk dalam format PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
Pastikan untuk mengganti `"Scaling Factor Thumbnail_out.png"` dengan nama file keluaran yang diinginkan.

## Kesimpulan
Sebagai kesimpulan, Anda telah berhasil membuat thumbnail faktor skala menggunakan Aspose.Slides untuk Java. Dengan mengikuti langkah-langkah yang diberikan, Anda dapat dengan mudah mengintegrasikan fungsionalitas ini ke dalam aplikasi Java Anda.
## Pertanyaan yang Sering Diajukan
### Dapatkah saya menggunakan Aspose.Slides untuk Java dengan IDE Java apa pun?
Ya, Aspose.Slides untuk Java dapat digunakan dengan Java Integrated Development Environment (IDE) apa pun seperti Eclipse, IntelliJ IDEA, atau NetBeans.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides untuk Java?
Ya, Anda dapat memanfaatkan uji coba gratis Aspose.Slides untuk Java dengan mengunjungi [situs web](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan untuk Aspose.Slides untuk Java?
Anda dapat menemukan dukungan untuk Aspose.Slides untuk Java di [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Bagaimana saya dapat membeli Aspose.Slides untuk Java?
Anda dapat membeli Aspose.Slides untuk Java dari [halaman pembelian](https://purchase.aspose.com/buy).
### Apakah saya memerlukan lisensi sementara untuk menggunakan Aspose.Slides untuk Java?
Ya, Anda dapat memperoleh lisensi sementara dari [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}