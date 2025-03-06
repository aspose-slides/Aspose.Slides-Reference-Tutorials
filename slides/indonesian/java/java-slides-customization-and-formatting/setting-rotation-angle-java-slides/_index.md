---
title: Mengatur Sudut Rotasi di Slide Java
linktitle: Mengatur Sudut Rotasi di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Optimalkan slide Java Anda dengan Aspose.Slides untuk Java. Pelajari cara mengatur sudut rotasi untuk elemen teks. Panduan langkah demi langkah dengan kode sumber.
weight: 17
url: /id/java/customization-and-formatting/setting-rotation-angle-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Pengantar Pengaturan Sudut Rotasi di Slide Java

Dalam tutorial ini, kita akan mempelajari cara mengatur sudut rotasi untuk teks dalam judul sumbu bagan menggunakan pustaka Aspose.Slides untuk Java. Dengan menyesuaikan sudut rotasi, Anda dapat menyesuaikan tampilan judul sumbu bagan agar lebih sesuai dengan kebutuhan presentasi Anda.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda. Anda dapat mengunduh perpustakaan dari situs web Aspose dan mengikuti petunjuk instalasi yang disediakan dalam dokumentasinya.

## Langkah 1: Buat Presentasi

Pertama, Anda perlu membuat presentasi baru atau memuat presentasi yang sudah ada. Dalam contoh ini, kita akan membuat presentasi baru:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Bagan ke Slide

Selanjutnya, kita akan menambahkan grafik ke slide. Dalam contoh ini, kami menambahkan bagan kolom berkerumun:

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## Langkah 3: Tetapkan Sudut Rotasi untuk Judul Sumbu

Untuk mengatur sudut rotasi judul sumbu, Anda perlu mengakses judul sumbu vertikal bagan dan menyesuaikan sudut rotasinya. Inilah cara Anda melakukannya:

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

Dalam cuplikan kode ini, kami mengatur sudut rotasi menjadi 90 derajat, yang akan memutar teks secara vertikal. Anda dapat menyesuaikan sudut dengan nilai yang Anda inginkan.

## Langkah 4: Simpan Presentasi

Terakhir, simpan presentasi ke file PowerPoint:

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Kode Sumber Lengkap Untuk Mengatur Sudut Rotasi di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
	pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengatur sudut rotasi untuk teks dalam judul sumbu bagan menggunakan Aspose.Slides untuk Java. Fitur ini memungkinkan Anda menyesuaikan tampilan bagan untuk membuat presentasi yang menarik secara visual. Bereksperimenlah dengan sudut rotasi yang berbeda untuk mendapatkan tampilan bagan Anda yang diinginkan.

## FAQ

### Bagaimana cara mengubah sudut rotasi untuk elemen teks lain dalam slide?

Anda dapat mengubah sudut rotasi untuk elemen teks lainnya, seperti bentuk atau kotak teks, menggunakan pendekatan serupa. Akses format teks elemen dan atur sudut rotasi sesuai kebutuhan.

### Bisakah saya juga memutar teks dalam judul sumbu horizontal?

Ya, Anda dapat memutar teks pada judul sumbu horizontal dengan menyesuaikan sudut rotasi. Cukup atur sudut rotasi ke nilai yang Anda inginkan, misalnya 90 derajat untuk teks vertikal atau 0 derajat untuk teks horizontal.

### Opsi pemformatan apa lagi yang tersedia untuk judul bagan?

Aspose.Slides untuk Java menyediakan berbagai opsi pemformatan untuk judul bagan, termasuk gaya font, warna, dan perataan. Anda dapat menjelajahi dokumentasi untuk detail selengkapnya tentang menyesuaikan judul bagan.

### Apakah mungkin untuk menganimasikan rotasi teks dalam judul sumbu bagan?

Ya, Anda dapat menambahkan efek animasi ke elemen teks, termasuk judul sumbu bagan, menggunakan Aspose.Slides untuk Java. Lihat dokumentasi untuk informasi tentang menambahkan animasi ke presentasi Anda.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
