---
title: Tetapkan Opsi Kustom Legenda di Slide Java
linktitle: Tetapkan Opsi Kustom Legenda di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengatur opsi legenda khusus di Java Slides menggunakan Aspose.Slides for Java. Sesuaikan posisi dan ukuran legenda di bagan PowerPoint Anda.
weight: 14
url: /id/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Pengantar Mengatur Opsi Kustom Legenda di Slide Java

Dalam tutorial ini, kami akan mendemonstrasikan cara mengkustomisasi properti legenda bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Anda dapat memodifikasi posisi legenda, ukuran, dan atribut lainnya sesuai kebutuhan presentasi Anda.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Aspose.Slides untuk Java API diinstal.
- Lingkungan pengembangan Java disiapkan.

## Langkah 1: Impor kelas yang diperlukan:

```java
// Impor Aspose.Slides untuk kelas Java
import com.aspose.slides.*;
```

## Langkah 2: Tentukan jalur ke direktori dokumen Anda:

```java
String dataDir = "Your Document Directory";
```

##  Langkah 3: Buat sebuah instance dari`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Langkah 4: Tambahkan slide ke presentasi:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Langkah 5: Tambahkan bagan kolom berkerumun ke slide:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Langkah 6. Tetapkan Properti Legenda:

- Tetapkan posisi X pada legenda (relatif terhadap lebar grafik):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Tetapkan posisi Y pada legenda (relatif terhadap tinggi grafik):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Mengatur lebar legenda (relatif terhadap lebar grafik):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Tetapkan tinggi legenda (relatif terhadap tinggi grafik):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Langkah 7: Simpan presentasi ke disk:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Itu dia! Anda telah berhasil mengkustomisasi properti legenda bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java.

## Kode Sumber Lengkap Untuk Opsi Kustom Set Legenda di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
try
{
	// Dapatkan referensi slide
	ISlide slide = presentation.getSlides().get_Item(0);
	// Tambahkan bagan kolom berkerumun pada slide
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Tetapkan Properti Legenda
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Tulis presentasi ke disk
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mengkustomisasi properti legenda bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Anda dapat memodifikasi posisi legenda, ukuran, dan atribut lainnya untuk membuat presentasi yang menarik secara visual dan informatif.

## FAQ

## Bagaimana cara mengubah posisi legenda?

 Untuk mengubah posisi legenda, gunakan`setX` Dan`setY` metode objek legenda. Nilainya ditentukan secara relatif terhadap lebar dan tinggi bagan.

## Bagaimana cara menyesuaikan ukuran legenda?

 Anda dapat menyesuaikan ukuran legenda dengan menggunakan`setWidth` Dan`setHeight` metode objek legenda. Nilai-nilai ini juga relatif terhadap lebar dan tinggi bagan.

## Bisakah saya menyesuaikan atribut legenda lainnya?

Ya, Anda dapat menyesuaikan berbagai atribut legenda, seperti gaya font, batas, warna latar belakang, dan lainnya. Jelajahi dokumentasi Aspose.Slides untuk informasi mendetail tentang penyesuaian legenda lebih lanjut.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
