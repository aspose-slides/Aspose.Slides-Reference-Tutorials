---
title: Atur Warna Isi Seri Otomatis di Slide Java
linktitle: Atur Warna Isi Seri Otomatis di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengatur warna isian rangkaian otomatis di Java Slides menggunakan Aspose.Slides for Java. Panduan langkah demi langkah dengan contoh kode untuk presentasi dinamis.
weight: 14
url: /id/java/data-manipulation/set-automatic-series-fill-color-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengantar Mengatur Warna Isi Seri Otomatis di Slide Java

Dalam tutorial ini, kita akan mempelajari cara mengatur warna isian rangkaian otomatis di Java Slides menggunakan Aspose.Slides for Java API. Aspose.Slides untuk Java adalah perpustakaan canggih yang memungkinkan Anda membuat, memanipulasi, dan mengelola presentasi PowerPoint secara terprogram. Di akhir panduan ini, Anda akan dapat membuat bagan dan mengatur warna isian rangkaian otomatis dengan mudah.

## Prasyarat

Sebelum kita mendalami kodenya, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Slides untuk perpustakaan Java ditambahkan ke proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).

Sekarang kita sudah memiliki garis besarnya, mari kita mulai dengan panduan langkah demi langkah.

## Langkah 1: Pengenalan Aspose.Slides untuk Java

Aspose.Slides for Java adalah Java API yang memungkinkan pengembang bekerja dengan presentasi PowerPoint. Ini menyediakan berbagai fitur, termasuk membuat, mengedit, dan memanipulasi slide, bagan, bentuk, dan banyak lagi.

## Langkah 2: Menyiapkan Proyek Java Anda

Sebelum kita memulai pengkodean, pastikan Anda telah menyiapkan proyek Java di Lingkungan Pengembangan Terpadu (IDE) pilihan Anda. Pastikan untuk menambahkan perpustakaan Aspose.Slides untuk Java ke proyek Anda.

## Langkah 3: Membuat Presentasi PowerPoint

Untuk memulai, buat presentasi PowerPoint baru menggunakan cuplikan kode berikut:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

 Mengganti`"Your Document Directory"` dengan jalur tempat Anda ingin menyimpan presentasi.

## Langkah 4: Menambahkan Bagan ke Presentasi

Selanjutnya, mari tambahkan bagan kolom berkerumun ke presentasi. Kami akan menggunakan kode berikut untuk mencapai hal ini:

```java
// Membuat bagan kolom berkerumun
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

Kode ini membuat bagan kolom berkerumun pada slide pertama presentasi.

## Langkah 5: Mengatur Warna Isi Seri Otomatis

Sekarang sampai pada bagian kuncinya—mengatur warna isian rangkaian otomatis. Kami akan mengulangi rangkaian bagan dan mengatur format pengisiannya ke otomatis:

```java
// Mengatur format pengisian seri ke otomatis
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

Kode ini memastikan bahwa warna isian rangkaian diatur ke otomatis.

## Langkah 6: Menyimpan Presentasi

Untuk menyimpan presentasi, gunakan kode berikut:

```java
// Tulis file presentasi ke disk
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

 Mengganti`"AutoFillSeries_out.pptx"` dengan nama file yang diinginkan.

## Kode Sumber Lengkap Untuk Mengatur Warna Isi Seri Otomatis di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// Membuat bagan kolom berkerumun
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// Mengatur format pengisian seri ke otomatis
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
	}
	// Tulis file presentasi ke disk
	presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Selamat! Anda telah berhasil mengatur warna isian rangkaian otomatis di Slide Java menggunakan Aspose.Slides untuk Java. Anda sekarang dapat menggunakan pengetahuan ini untuk membuat presentasi PowerPoint yang dinamis dan menarik secara visual di aplikasi Java Anda.

## FAQ

### Bagaimana cara mengubah tipe bagan ke gaya lain?

 Anda dapat mengubah jenis grafik dengan menggantinya`ChartType.ClusteredColumn` dengan tipe grafik yang diinginkan, seperti`ChartType.Line` atau`ChartType.Pie`.

### Bisakah saya menyesuaikan tampilan grafik lebih lanjut?

Ya, Anda dapat menyesuaikan tampilan bagan dengan memodifikasi berbagai properti bagan, seperti warna, font, dan label.

### Apakah Aspose.Slides untuk Java cocok untuk penggunaan komersial?

Ya, Aspose.Slides for Java dapat digunakan untuk proyek pribadi dan komersial. Anda dapat merujuk pada persyaratan lisensi mereka untuk lebih jelasnya.

### Apakah ada fitur lain yang disediakan oleh Aspose.Slides untuk Java?

Ya, Aspose.Slides for Java menawarkan berbagai fitur, termasuk manipulasi slide, pemformatan teks, dan dukungan animasi.

### Di mana saya dapat menemukan lebih banyak sumber daya dan dokumentasi?

 Anda dapat mengakses dokumentasi komprehensif untuk Aspose.Slides untuk Java di[Di Sini](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
