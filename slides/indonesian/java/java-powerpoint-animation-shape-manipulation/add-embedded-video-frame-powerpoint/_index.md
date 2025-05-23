---
"description": "Pelajari cara menyematkan bingkai video di PowerPoint menggunakan Aspose.Slides untuk Java dengan tutorial langkah demi langkah ini. Sempurnakan presentasi Anda dengan mudah."
"linktitle": "Tambahkan Bingkai Video Tertanam di PowerPoint"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Tambahkan Bingkai Video Tertanam di PowerPoint"
"url": "/id/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Bingkai Video Tertanam di PowerPoint

## Perkenalan
Menambahkan video ke presentasi PowerPoint Anda dapat membuatnya lebih menarik dan informatif. Dengan menggunakan Aspose.Slides for Java, Anda dapat dengan mudah menyematkan video langsung ke slide Anda. Dalam tutorial ini, kami akan memandu Anda melalui proses ini langkah demi langkah, memastikan Anda memahami setiap bagian kode dan cara kerjanya. Baik Anda seorang pengembang berpengalaman atau baru memulai, panduan ini akan membantu Anda menyempurnakan presentasi Anda dengan video yang disematkan.
## Prasyarat
Sebelum menyelami kode, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di komputer Anda.
2. Aspose.Slides untuk Java: Unduh dan instal pustaka Aspose.Slides untuk Java.
3. Lingkungan Pengembangan Terpadu (IDE): Gunakan IDE seperti IntelliJ IDEA atau Eclipse untuk pengalaman pengembangan yang lebih baik.
4. Berkas Video: Miliki berkas video yang ingin Anda sematkan dalam presentasi PowerPoint Anda.
## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan untuk bekerja dengan Aspose.Slides. Impor ini akan membantu Anda mengelola slide, video, dan berkas presentasi.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Langkah 1: Siapkan Lingkungan Anda
Sebelum Anda mulai membuat kode, pastikan lingkungan Anda telah diatur dengan benar. Ini melibatkan pembuatan direktori yang diperlukan dan persiapan berkas video.
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Buat direktori jika belum ada.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Langkah 2: Buat Kelas Presentasi
Buat contoh dari `Presentation` kelas. Kelas ini mewakili berkas PowerPoint Anda.
```java
// Membuat instance kelas Presentasi yang mewakili PPTX
Presentation pres = new Presentation();
```
## Langkah 3: Dapatkan Slide Pertama
Akses slide pertama dalam presentasi tempat Anda akan menyematkan video.
```java
// Dapatkan slide pertama
ISlide sld = pres.getSlides().get_Item(0);
```
## Langkah 4: Tambahkan Video ke Presentasi
Sisipkan berkas video ke dalam presentasi. Pastikan jalur video ditentukan dengan benar.
```java
// Sematkan video di dalam presentasi
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Langkah 5: Tambahkan Bingkai Video ke Slide
Buat bingkai video pada slide dan atur dimensi dan posisinya.
```java
// Tambahkan Bingkai Video
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Langkah 6: Konfigurasikan Properti Bingkai Video
Atur video ke bingkai video dan konfigurasikan pengaturan pemutarannya seperti mode pemutaran dan volume.
```java
// Atur video ke Bingkai Video
vf.setEmbeddedVideo(vid);
// Mengatur Mode Putar dan Volume Video
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Langkah 7: Simpan Presentasi
Simpan presentasi dengan video tertanam ke direktori yang Anda tentukan.
```java
// Tulis file PPTX ke disk
pres.save(resultPath, SaveFormat.Pptx);
```
## Langkah 8: Bersihkan Sumber Daya
Terakhir, buang objek presentasi untuk mengosongkan sumber daya.
```java
// Buang objek presentasi
if (pres != null) pres.dispose();
```
## Kesimpulan
Menyematkan video dalam presentasi PowerPoint Anda menggunakan Aspose.Slides for Java merupakan proses yang mudah. Dengan mengikuti langkah-langkah yang diuraikan dalam panduan ini, Anda dapat menyempurnakan presentasi Anda dengan konten video yang menarik. Ingat, latihan akan menghasilkan kesempurnaan, jadi cobalah menyematkan video yang berbeda dan sesuaikan propertinya untuk melihat mana yang paling sesuai dengan kebutuhan Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menyematkan beberapa video dalam satu slide?
Ya, Anda dapat menyematkan beberapa video dalam satu slide dengan menambahkan beberapa bingkai video.
### Bagaimana cara mengontrol pemutaran video?
Anda dapat mengontrol pemutaran menggunakan `setPlayMode` Dan `setVolume` metode dari `IVideoFrame` kelas.
### Format video apa yang didukung oleh Aspose.Slides?
Aspose.Slides mendukung berbagai format video termasuk MP4, AVI, dan WMV.
### Apakah saya memerlukan lisensi untuk menggunakan Aspose.Slides?
Ya, Anda memerlukan lisensi yang valid untuk menggunakan Aspose.Slides. Anda dapat memperoleh lisensi sementara untuk evaluasi.
### Bisakah saya menyesuaikan ukuran dan posisi bingkai video?
Ya, Anda dapat menyesuaikan ukuran dan posisi dengan mengatur parameter yang sesuai saat menambahkan bingkai video.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}