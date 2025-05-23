---
"description": "Pelajari cara menerapkan efek rotasi 3D pada bentuk di PowerPoint menggunakan Aspose.Slides untuk Java dengan tutorial langkah demi langkah yang komprehensif ini."
"linktitle": "Menerapkan Efek Rotasi 3D pada Bentuk di PowerPoint"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Menerapkan Efek Rotasi 3D pada Bentuk di PowerPoint"
"url": "/id/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menerapkan Efek Rotasi 3D pada Bentuk di PowerPoint

## Perkenalan
Apakah Anda siap untuk membawa presentasi PowerPoint Anda ke tingkat berikutnya? Menambahkan efek rotasi 3D dapat membuat slide Anda lebih dinamis dan menarik. Apakah Anda seorang pengembang berpengalaman atau baru memulai, tutorial langkah demi langkah ini akan menunjukkan kepada Anda cara menerapkan efek rotasi 3D ke bentuk di PowerPoint menggunakan Aspose.Slides untuk Java. Mari kita mulai!
## Prasyarat
Sebelum kita memulai, pastikan Anda telah menyiapkan hal-hal berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduhnya dari [Situs web Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides untuk Java: Unduh versi terbaru Aspose.Slides untuk Java dari [tautan unduhan](https://releases.aspose.com/slides/java/).
3. Lingkungan Pengembangan Terpadu (IDE): Gunakan IDE seperti IntelliJ IDEA atau Eclipse untuk pengkodean.
4. Lisensi yang valid: Jika Anda tidak memiliki lisensi, Anda bisa mendapatkannya [lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk mencoba fitur-fiturnya.
## Paket Impor
Pertama, mari impor paket yang diperlukan ke dalam proyek Java Anda. Impor ini akan membantu Anda menangani presentasi dan bentuk dengan Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Langkah 1: Siapkan Proyek Anda
Sebelum mulai menggunakan kode, siapkan lingkungan proyek Anda. Pastikan Anda telah menambahkan Aspose.Slides for Java ke dependensi proyek Anda.
Tambahkan Aspose.Slides ke Proyek Anda:
1. Unduh file JAR Aspose.Slides dari [halaman unduhan](https://releases.aspose.com/slides/java/).
2. Tambahkan file JAR ini ke jalur pembuatan proyek Anda.
## Langkah 2: Buat Presentasi PowerPoint Baru
Pada langkah ini, kita akan membuat presentasi PowerPoint baru.
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation pres = new Presentation();
```
Potongan kode ini menginisialisasi objek presentasi baru tempat kita akan menambahkan bentuk.
## Langkah 3: Tambahkan Bentuk Persegi Panjang
Berikutnya, mari tambahkan bentuk persegi panjang ke slide pertama.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Kode ini menambahkan bentuk persegi panjang pada posisi dan ukuran yang ditentukan pada slide pertama.
## Langkah 4: Terapkan Rotasi 3D ke Persegi Panjang
Sekarang, mari terapkan efek rotasi 3D pada bentuk persegi panjang.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Di sini, kita atur kedalaman, sudut rotasi kamera, jenis kamera, dan jenis pencahayaan untuk memberikan tampilan 3D pada persegi panjang kita.
## Langkah 5: Tambahkan Bentuk Garis
Mari tambahkan bentuk lain, kali ini garis, ke slide.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Kode ini menempatkan bentuk garis pada slide.
## Langkah 6: Terapkan Rotasi 3D ke Garis
Terakhir, kita akan menerapkan efek rotasi 3D pada bentuk garis.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Mirip dengan persegi panjang, kami mengatur properti 3D untuk bentuk garis.
## Langkah 7: Simpan Presentasi
Setelah menambahkan dan mengonfigurasi bentuk Anda, simpan presentasi.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Kode ini menyimpan presentasi Anda dengan nama file yang ditentukan dalam format yang diinginkan.
## Kesimpulan
Selamat! Anda telah berhasil menerapkan efek rotasi 3D ke bentuk dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat membuat presentasi yang menarik secara visual dan dinamis. Untuk penyesuaian lebih lanjut dan fitur yang lebih canggih, lihat [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/java/).
## Pertanyaan yang Sering Diajukan
### Apa itu Aspose.Slides untuk Java?
Aspose.Slides untuk Java adalah API yang hebat untuk membuat, memodifikasi, dan memanipulasi presentasi PowerPoint secara terprogram.
### Dapatkah saya mencoba Aspose.Slides untuk Java secara gratis?
Ya, Anda bisa mendapatkannya [uji coba gratis](https://releases.aspose.com/) atau sebuah [lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk menguji fitur-fiturnya.
### Jenis bentuk apa yang dapat saya tambahkan efek 3D di Aspose.Slides?
Anda dapat menambahkan efek 3D ke berbagai bentuk seperti persegi panjang, garis, elips, dan bentuk khusus.
### Bagaimana cara mendapatkan dukungan untuk Aspose.Slides untuk Java?
Anda dapat mengunjungi [forum dukungan](https://forum.aspose.com/c/slides/11) untuk bantuan dan mendiskusikan masalah apa pun.
### Dapatkah saya menggunakan Aspose.Slides untuk Java dalam proyek komersial?
Ya, tetapi Anda perlu membeli lisensi. Anda dapat membelinya dari [halaman pembelian](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}