---
title: Terapkan Outer Shadow di PowerPoint dengan Java
linktitle: Terapkan Outer Shadow di PowerPoint dengan Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menerapkan efek bayangan luar di PowerPoint menggunakan Java dengan Aspose.Slides. Sempurnakan presentasi Anda dengan kedalaman dan daya tarik visual.
weight: 13
url: /id/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Perkenalan
Membuat presentasi PowerPoint yang menarik secara visual sering kali melibatkan penambahan berbagai efek pada bentuk dan teks. Salah satu efek tersebut adalah bayangan luar, yang dapat membuat elemen menonjol dan menambah kedalaman pada slide Anda. Dalam tutorial ini, Anda akan mempelajari cara menerapkan efek bayangan luar pada bentuk di PowerPoint menggunakan Java dengan Aspose.Slides.
## Prasyarat

Sebelum memulai tutorial ini, pastikan Anda memiliki prasyarat berikut:

1. Java Development Kit (JDK): Pastikan Anda telah menginstal Java di sistem Anda. Anda dapat mengunduh dan menginstal JDK versi terbaru dari situs web Oracle.

2.  Aspose.Slides for Java: Unduh dan instal Aspose.Slides for Java dari[Unduh Halaman](https://releases.aspose.com/slides/java/).

3. Lingkungan Pengembangan Terpadu (IDE): Pilih IDE Java pilihan Anda seperti Eclipse, IntelliJ IDEA, atau NetBeans untuk coding dan menjalankan aplikasi Java.

4. Pengetahuan Dasar Java: Keakraban dengan dasar-dasar bahasa pemrograman Java dan konsep berorientasi objek akan bermanfaat untuk memahami contoh kode.

## Paket Impor

Pertama, impor paket yang diperlukan untuk bekerja dengan Aspose.Slides dan fungsi terkait di proyek Java Anda:

```java
import com.aspose.slides.*;
```

Sekarang mari kita pecahkan kode contoh menjadi beberapa langkah untuk menerapkan efek bayangan luar pada bentuk di PowerPoint menggunakan Java dengan Aspose.Slides:

## Langkah 1: Siapkan lingkungan proyek Anda

Buat proyek Java baru di IDE pilihan Anda dan tambahkan pustaka Aspose.Slides untuk Java ke jalur pembangunan proyek Anda.

## Langkah 2: Inisialisasi objek Presentasi

 Buat sebuah instance dari`Presentation` kelas, yang mewakili file presentasi PowerPoint.

```java
Presentation presentation = new Presentation();
```

## Langkah 3: Tambahkan slide dan bentuk

Dapatkan referensi ke slide tempat Anda ingin menambahkan bentuk, lalu tambahkan BentukOtomatis (misal, persegi panjang) ke slide.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Langkah 4: Sesuaikan bentuknya

Atur tipe isian bentuk ke 'NoFill' dan tambahkan teks ke bentuk.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Langkah 5: Sesuaikan teks

Akses properti teks bentuk dan sesuaikan ukuran font.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Langkah 6: Aktifkan efek Outer Shadow

Aktifkan efek bayangan luar untuk bagian teks.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Langkah 7: Tetapkan parameter bayangan

Tentukan parameter efek bayangan luar, seperti radius buram, arah, jarak, dan warna bayangan.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Langkah 8: Simpan presentasi

Simpan presentasi yang dimodifikasi dengan efek bayangan luar yang diterapkan pada bentuk.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Selamat! Anda telah berhasil menerapkan efek bayangan luar ke bentuk di PowerPoint menggunakan Java dengan Aspose.Slides. Bereksperimenlah dengan berbagai parameter untuk mencapai efek visual yang diinginkan dalam presentasi Anda.

## FAQ

### Bisakah saya menerapkan efek bayangan luar pada bentuk lain selain persegi panjang?
Ya, Anda bisa menerapkan efek bayangan luar ke berbagai bentuk yang didukung oleh Aspose.Slide, seperti lingkaran, segitiga, dan bentuk khusus.

### Apakah mungkin untuk menyesuaikan warna dan intensitas bayangan?
Sangat! Anda memiliki kendali penuh atas parameter bayangan, termasuk warna, radius buram, arah, dan jarak.

### Bisakah saya menerapkan beberapa efek pada bentuk yang sama?
Ya, Anda dapat menggabungkan beberapa efek seperti bayangan luar, bayangan dalam, cahaya, dan refleksi untuk meningkatkan daya tarik visual bentuk dan teks dalam presentasi Anda.

### Apakah Aspose.Slides mendukung penerapan efek pada elemen teks?
Ya, Anda dapat menerapkan efek tidak hanya pada bentuk tetapi juga pada bagian teks individual dalam bentuk, memberi Anda fleksibilitas luas dalam mendesain slide Anda.

### Di mana saya dapat menemukan lebih banyak sumber daya dan dukungan untuk Aspose.Slides?
 Anda dapat merujuk ke[dokumentasi](https://reference.aspose.com/slides/java/) untuk referensi API terperinci dan jelajahi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11) untuk dukungan dan diskusi komunitas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
