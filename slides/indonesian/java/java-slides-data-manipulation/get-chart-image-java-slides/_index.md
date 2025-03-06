---
title: Dapatkan Gambar Bagan di Slide Java
linktitle: Dapatkan Gambar Bagan di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mendapatkan gambar bagan di Java Slides menggunakan Aspose.Slides for Java. Panduan langkah demi langkah ini memberikan kode sumber dan tips untuk integrasi yang lancar.
weight: 19
url: /id/java/data-manipulation/get-chart-image-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Pengantar Mendapatkan Gambar Bagan di Slide Java

Aspose.Slides untuk Java adalah perpustakaan canggih yang memungkinkan Anda bekerja dengan presentasi PowerPoint secara terprogram. Dengan perpustakaan ini, Anda dapat membuat, memanipulasi, dan mengekstrak berbagai elemen dari presentasi, termasuk bagan. Salah satu persyaratan umum adalah mendapatkan gambar bagan dari slide, dan kami akan mendemonstrasikan cara melakukannya dalam panduan ini.

## Prasyarat

Sebelum kita mendalami kodenya, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Slides untuk perpustakaan Java diunduh dan dikonfigurasi di proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Siapkan Proyek Anda

Mulailah dengan membuat proyek Java di Lingkungan Pengembangan Terpadu (IDE) pilihan Anda. Pastikan Anda telah menambahkan pustaka Aspose.Slides for Java ke dependensi proyek Anda.

## Langkah 2: Inisialisasi Presentasi

Untuk memulai, Anda perlu menginisialisasi presentasi PowerPoint. Dalam contoh ini, kami berasumsi Anda memiliki file PowerPoint bernama "test.pptx" di direktori dokumen Anda.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Langkah 3: Tambahkan Bagan dan Dapatkan Gambarnya

Selanjutnya, Anda dapat menambahkan bagan ke slide dan mendapatkan gambarnya. Dalam contoh ini, kami akan menambahkan bagan kolom berkerumun.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

Dalam cuplikan kode ini, kita membuat bagan kolom berkerumun pada slide pertama presentasi dan kemudian mendapatkan gambar mininya. Gambar disimpan sebagai "image.png" di direktori yang ditentukan.

## Kode Sumber Lengkap Untuk Mendapatkan Gambar Bagan di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Mendapatkan gambar bagan dari Java Slides menggunakan Aspose.Slides for Java adalah proses yang mudah. Dengan kode yang disediakan, Anda dapat dengan mudah mengintegrasikan fungsi ini ke dalam aplikasi Java Anda, memungkinkan Anda bekerja dengan presentasi PowerPoint secara efektif.

## FAQ

### Bagaimana cara menginstal Aspose.Slides untuk Java?

 Menginstal Aspose.Slides untuk Java itu sederhana. Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/slides/java/) dan ikuti petunjuk instalasi yang disediakan dalam dokumentasi.

### Bisakah saya menyesuaikan bagan sebelum mendapatkan gambarnya?

Ya, Anda dapat menyesuaikan tampilan bagan, data, dan properti lainnya sebelum mendapatkan gambarnya. Aspose.Slides untuk Java menyediakan opsi luas untuk penyesuaian bagan.

### Fitur lain apa yang ditawarkan Aspose.Slides untuk Java?

Aspose.Slides untuk Java menawarkan berbagai fitur untuk bekerja dengan presentasi PowerPoint, termasuk pembuatan slide, manipulasi teks, pengeditan bentuk, dan banyak lagi. Anda dapat menjelajahi dokumentasi untuk informasi rinci.

### Apakah Aspose.Slides untuk Java cocok untuk penggunaan komersial?

Ya, Aspose.Slides untuk Java dapat digunakan untuk tujuan komersial. Ini memberikan opsi lisensi yang diperuntukkan bagi pengembang individu dan perusahaan.

### Bisakah saya menyimpan gambar grafik dalam format lain?

 Tentu! Anda dapat menyimpan gambar grafik dalam berbagai format, seperti JPEG atau GIF, dengan menentukan ekstensi file yang sesuai di`ImageIO.write` metode.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
