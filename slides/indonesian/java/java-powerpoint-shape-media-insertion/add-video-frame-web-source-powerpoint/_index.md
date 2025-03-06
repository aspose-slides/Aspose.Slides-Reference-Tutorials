---
title: Tambahkan Bingkai Video dari Sumber Web di PowerPoint
linktitle: Tambahkan Bingkai Video dari Sumber Web di PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menyempurnakan presentasi PowerPoint Anda dengan menambahkan bingkai video dari sumber web menggunakan Aspose.Slides untuk Java.
weight: 18
url: /id/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menambahkan bingkai video dari sumber web, seperti YouTube, ke presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Dengan mengikuti petunjuk langkah demi langkah ini, Anda akan dapat menyempurnakan presentasi Anda dengan memasukkan elemen multimedia yang menarik.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang pemrograman Java.
- JDK (Java Development Kit) diinstal pada sistem Anda.
-  Aspose.Slides untuk perpustakaan Java diunduh dan ditambahkan ke proyek Java Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).
- Koneksi internet aktif untuk mengakses sumber web (misalnya YouTube).

## Paket Impor
Pertama, impor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## Langkah 1: Buat Objek Presentasi PowerPoint
Inisialisasi objek Presentasi, yang mewakili presentasi PowerPoint:
```java
Presentation pres = new Presentation();
```
## Langkah 2: Tambahkan Bingkai Video
Sekarang, mari tambahkan bingkai video ke presentasi. Bingkai ini akan berisi video dari sumber web. Kami akan menggunakan metode addVideoFrame:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
Ganti "VIDEO_ID" dengan ID video YouTube yang ingin Anda sematkan.
## Langkah 3: Atur Mode Putar Video
Atur mode putar untuk bingkai video. Dalam contoh ini, kami akan menyetelnya ke Otomatis:
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## Langkah 4: Muat Gambar Kecil
Untuk meningkatkan daya tarik visual, kami akan memuat thumbnail video. Langkah ini melibatkan pengambilan gambar mini dari sumber web:
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## Langkah 5: Simpan Presentasi
Terakhir, simpan presentasi yang dimodifikasi:
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
Ganti "YOUR_DIRECTORY" dengan direktori tempat Anda ingin menyimpan presentasi.

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menambahkan bingkai video dari sumber web di PowerPoint menggunakan Aspose.Slides untuk Java. Memasukkan elemen multimedia seperti video dapat meningkatkan dampak dan keterlibatan presentasi Anda secara signifikan.
## FAQ
### Bisakah saya menambahkan video dari sumber selain YouTube?
Ya, Anda dapat menambahkan video dari berbagai sumber web asalkan menyediakan tautan yang dapat disematkan.
### Apakah saya memerlukan koneksi internet untuk memutar video yang disematkan?
Ya, koneksi internet aktif diperlukan untuk melakukan streaming video dari sumber web.
### Bisakah saya menyesuaikan tampilan bingkai video?
Sangat! Aspose.Slides menyediakan opsi ekstensif untuk menyesuaikan tampilan dan perilaku bingkai video.
### Apakah Aspose.Slides kompatibel dengan semua versi PowerPoint?
Aspose.Slides mendukung berbagai versi PowerPoint, memastikan kompatibilitas di berbagai platform.
### Di mana saya dapat menemukan lebih banyak sumber daya dan dukungan untuk Aspose.Slides?
 Anda dapat mengunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11) untuk bantuan, dokumentasi, dan dukungan komunitas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
