---
title: Atur Buku Kerja Eksternal Dengan Perbarui Data Bagan di Slide Java
linktitle: Atur Buku Kerja Eksternal Dengan Perbarui Data Bagan di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengatur buku kerja eksternal dan memperbarui data bagan di Java Slides menggunakan Aspose.Slides untuk Java. Tingkatkan keterampilan otomatisasi PowerPoint Anda.
weight: 20
url: /id/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Pengantar Mengatur Buku Kerja Eksternal Dengan Memperbarui Data Bagan di Slide Java

Dalam panduan komprehensif ini, kami akan memandu Anda melalui proses pengaturan buku kerja eksternal dengan data bagan yang diperbarui di Java Slides menggunakan Aspose.Slides for Java API. Pustaka canggih ini memungkinkan Anda memanipulasi presentasi PowerPoint secara terprogram, sehingga memudahkan untuk mengotomatisasi tugas seperti memperbarui data bagan dari sumber eksternal. Di akhir tutorial ini, Anda akan memiliki pemahaman yang jelas tentang cara menyelesaikan tugas ini dengan petunjuk langkah demi langkah dan kode Java yang menyertainya.

## Prasyarat

Sebelum kita mendalami penerapannya, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Slides for Java: Anda harus menginstal pustaka Aspose.Slides for Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).

2. Lingkungan Pengembangan Java: Pastikan Anda telah menyiapkan lingkungan pengembangan Java di sistem Anda.

## Langkah 1: Buat Presentasi Baru

Untuk memulai, mari buat presentasi PowerPoint baru menggunakan Aspose.Slides for Java. Berikut kode Java untuk melakukan itu:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Bagan

Sekarang, mari tambahkan bagan ke presentasi kita. Kami akan membuat diagram lingkaran dalam contoh ini:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Langkah 3: Atur Buku Kerja Eksternal

Di sinilah kita menetapkan buku kerja eksternal sebagai sumber data untuk bagan kita. Anda perlu memberikan URL ke buku kerja eksternal, meskipun saat ini belum ada:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://jalur/tidak/ada", salah);
```

## Langkah 4: Simpan Presentasi

Terakhir, simpan presentasi dengan data bagan yang diperbarui:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Kode Sumber Lengkap Untuk Mengatur Buku Kerja Eksternal Dengan Pembaruan Data Bagan di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://jalur/tidak/ada", salah);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Selamat! Anda telah mempelajari cara mengatur buku kerja eksternal dengan data bagan yang diperbarui di Java Slides menggunakan Aspose.Slides untuk Java. Ini bisa sangat berguna untuk memperbarui grafik secara dinamis dalam presentasi PowerPoint Anda dari sumber data eksternal.

## FAQ

### Bagaimana cara memperbarui data buku kerja eksternal untuk bagan?

Untuk memperbarui data buku kerja eksternal untuk bagan, Anda hanya perlu mengubah data di buku kerja eksternal pada URL yang ditentukan. Saat berikutnya Anda membuka presentasi, Aspose.Slides for Java akan mengambil data yang diperbarui dari buku kerja eksternal dan memperbarui bagan yang sesuai.

### Bisakah saya menggunakan file lokal sebagai buku kerja eksternal?

Ya, Anda bisa menggunakan file lokal sebagai buku kerja eksternal dengan menyediakan jalur file, bukan URL. Pastikan jalur file sudah benar dan dapat diakses dari aplikasi Java Anda.

### Apakah ada batasan dalam menggunakan buku kerja eksternal dengan Aspose.Slides untuk Java?

Meskipun menggunakan buku kerja eksternal adalah fitur canggih, perlu diingat bahwa ketersediaan data buku kerja eksternal bergantung pada aksesibilitasnya pada URL atau jalur file yang disediakan. Pastikan sumber data eksternal tersedia saat Anda membuka presentasi untuk menghindari masalah pengambilan data.

### Bisakah saya mengkustomisasi tampilan bagan setelah mengatur buku kerja eksternal?

Ya, Anda bisa mengkustomisasi tampilan bagan, termasuk judul, label, warna, dan lainnya, bahkan setelah mengatur buku kerja eksternal. Aspose.Slides untuk Java menyediakan opsi pemformatan bagan yang luas untuk memenuhi kebutuhan Anda.

### Di mana saya dapat menemukan lebih banyak dokumentasi dan sumber daya untuk Aspose.Slides untuk Java?

 Untuk dokumentasi terperinci dan sumber daya tambahan, kunjungi dokumentasi Aspose.Slides untuk Java di[Di Sini](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
