---
"description": "Pelajari cara mengatur buku kerja eksternal dan memperbarui data bagan di Java Slides menggunakan Aspose.Slides untuk Java. Tingkatkan keterampilan otomatisasi PowerPoint Anda."
"linktitle": "Mengatur Buku Kerja Eksternal Dengan Memperbarui Data Bagan di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Buku Kerja Eksternal Dengan Memperbarui Data Bagan di Slide Java"
"url": "/id/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Buku Kerja Eksternal Dengan Memperbarui Data Bagan di Slide Java


## Pengantar untuk Mengatur Buku Kerja Eksternal dengan Memperbarui Data Bagan di Slide Java

Dalam panduan lengkap ini, kami akan memandu Anda melalui proses pengaturan buku kerja eksternal dengan data bagan yang diperbarui di Java Slides menggunakan Aspose.Slides for Java API. Pustaka canggih ini memungkinkan Anda untuk memanipulasi presentasi PowerPoint secara terprogram, sehingga memudahkan untuk mengotomatiskan tugas-tugas seperti memperbarui data bagan dari sumber eksternal. Di akhir tutorial ini, Anda akan memiliki pemahaman yang jelas tentang cara mencapai tugas ini dengan petunjuk langkah demi langkah dan kode Java yang menyertainya.

## Prasyarat

Sebelum kita mulai menerapkannya, pastikan Anda telah memenuhi prasyarat berikut:

1. Aspose.Slides untuk Java: Anda harus menginstal pustaka Aspose.Slides untuk Java. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).

2. Lingkungan Pengembangan Java: Pastikan Anda telah menyiapkan lingkungan pengembangan Java di sistem Anda.

## Langkah 1: Buat Presentasi Baru

Untuk memulai, mari buat presentasi PowerPoint baru menggunakan Aspose.Slides untuk Java. Berikut kode Java untuk melakukannya:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Bagan

Sekarang, mari tambahkan diagram ke presentasi kita. Kita akan membuat diagram Pai dalam contoh ini:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Langkah 3: Mengatur Buku Kerja Eksternal

Di sinilah kita menetapkan buku kerja eksternal sebagai sumber data untuk bagan kita. Anda perlu memberikan URL ke buku kerja eksternal, meskipun saat ini belum ada:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://jalur/tidak/ada", salah);
```

## Langkah 4: Simpan Presentasi

Terakhir, simpan presentasi dengan data grafik yang diperbarui:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Source Code Lengkap Untuk Set External Workbook Dengan Update Chart Data di Java Slides

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

Selamat! Anda telah mempelajari cara mengatur buku kerja eksternal dengan data bagan yang diperbarui di Java Slides menggunakan Aspose.Slides untuk Java. Ini dapat sangat berguna untuk memperbarui bagan secara dinamis dalam presentasi PowerPoint Anda dari sumber data eksternal.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara memperbarui data buku kerja eksternal untuk bagan?

Untuk memperbarui data buku kerja eksternal untuk bagan, Anda hanya perlu mengubah data dalam buku kerja eksternal di URL yang ditentukan. Saat berikutnya Anda membuka presentasi, Aspose.Slides untuk Java akan mengambil data yang diperbarui dari buku kerja eksternal dan memperbarui bagan sebagaimana mestinya.

### Bisakah saya menggunakan berkas lokal sebagai buku kerja eksternal?

Ya, Anda dapat menggunakan file lokal sebagai buku kerja eksternal dengan memberikan jalur file, bukan URL. Pastikan jalur file sudah benar dan dapat diakses dari aplikasi Java Anda.

### Apakah ada batasan dalam menggunakan buku kerja eksternal dengan Aspose.Slides untuk Java?

Meskipun menggunakan buku kerja eksternal merupakan fitur yang hebat, perlu diingat bahwa ketersediaan data buku kerja eksternal bergantung pada aksesibilitasnya di URL atau jalur file yang disediakan. Pastikan bahwa sumber data eksternal tersedia saat Anda membuka presentasi untuk menghindari masalah pengambilan data.

### Dapatkah saya menyesuaikan tampilan bagan setelah mengatur buku kerja eksternal?

Ya, Anda dapat menyesuaikan tampilan bagan, termasuk judul, label, warna, dan lainnya, bahkan setelah mengatur buku kerja eksternal. Aspose.Slides untuk Java menyediakan opsi pemformatan bagan yang lengkap untuk memenuhi kebutuhan Anda.

### Di mana saya dapat menemukan lebih banyak dokumentasi dan sumber daya untuk Aspose.Slides untuk Java?

Untuk dokumentasi terperinci dan sumber daya tambahan, kunjungi dokumentasi Aspose.Slides untuk Java di [Di Sini](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}