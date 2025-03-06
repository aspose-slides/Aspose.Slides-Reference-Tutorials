---
title: Mengatur Posisi Sumbu di Slide Java
linktitle: Mengatur Posisi Sumbu di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Sempurnakan Grafik Anda dengan Aspose.Slides untuk Java. Pelajari cara mengatur sumbu posisi di slide Java, membuat presentasi yang menakjubkan, dan menyesuaikan tata letak bagan dengan mudah.
weight: 16
url: /id/java/customization-and-formatting/setting-position-axis-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Pengantar Pengaturan Posisi Sumbu di Aspose.Slide untuk Java

Dalam tutorial ini, kita akan mempelajari cara mengatur sumbu posisi pada grafik menggunakan Aspose.Slides for Java. Memposisikan sumbu dapat berguna saat Anda ingin menyesuaikan tampilan dan tata letak bagan Anda. Kami akan membuat bagan kolom berkerumun dan menyesuaikan posisi sumbu horizontal antar kategori.

## Prasyarat

 Sebelum kita mulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda. Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Membuat Presentasi

Pertama, mari buat presentasi baru untuk dikerjakan:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 Pastikan untuk mengganti`"Your Document Directory"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Menambahkan Bagan

Selanjutnya, kita akan menambahkan bagan kolom berkerumun ke slide. Kami menentukan jenis bagan, posisi (koordinat x, y), dan dimensi (lebar dan tinggi) bagan:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Di sini, kami telah menambahkan bagan kolom berkerumun pada posisi (50, 50) dengan lebar 450 dan tinggi 300. Anda dapat menyesuaikan nilai ini sesuai kebutuhan.

## Langkah 3: Mengatur Posisi Sumbu

Untuk mengatur sumbu posisi antar kategori dapat menggunakan kode berikut:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Kode ini mengatur sumbu horizontal untuk ditampilkan antar kategori, yang dapat berguna untuk tata letak bagan tertentu.

## Langkah 4: Menyimpan Presentasi

Terakhir, mari simpan presentasi dengan bagan:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 Mengganti`"AsposeClusteredColumnChart.pptx"` dengan nama file yang Anda inginkan.

Itu dia! Anda telah berhasil membuat bagan kolom berkerumun dan mengatur sumbu posisi antar kategori menggunakan Aspose.Slides untuk Java.

## Kode Sumber Lengkap
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi cara mengatur sumbu posisi dalam bagan menggunakan Aspose.Slides untuk Java. Dengan mengikuti langkah-langkah yang dijelaskan dalam panduan ini, Anda telah mempelajari cara membuat bagan kolom berkerumun dan menyesuaikan tampilannya dengan memposisikan sumbu horizontal di antara kategori. Aspose.Slides untuk Java menyediakan fitur canggih untuk bekerja dengan bagan dan presentasi, menjadikannya alat yang berharga bagi pengembang Java.

## FAQ

### Bagaimana cara menyesuaikan grafik lebih lanjut?

Anda dapat menyesuaikan berbagai aspek bagan, termasuk seri data, judul bagan, legenda, dan banyak lagi. Mengacu kepada[Aspose.Slides untuk dokumentasi Java](https://reference.aspose.com/slides/java/) untuk petunjuk rinci dan contoh.

### Bisakah saya mengubah jenis grafik?

 Ya, Anda dapat mengubah jenis bagan dengan memodifikasi`ChartType` parameter saat menambahkan grafik. Aspose.Slides untuk Java mendukung berbagai jenis bagan seperti diagram batang, diagram garis, dan banyak lagi.

### Di mana saya dapat menemukan lebih banyak contoh dan dokumentasi?

 Anda dapat menemukan dokumentasi komprehensif dan contoh lainnya di[Aspose.Slides untuk dokumentasi Java](https://reference.aspose.com/slides/java/) halaman.

Ingatlah untuk membuang objek presentasi setelah Anda selesai menggunakannya untuk melepaskan sumber daya sistem:

```java
if (pres != null) pres.dispose();
```

Itu saja untuk tutorial ini. Anda telah mempelajari cara mengatur sumbu posisi dalam bagan menggunakan Aspose.Slides untuk Java.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
