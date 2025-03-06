---
title: Atur Data Bagan Dari Buku Kerja di Slide Java
linktitle: Atur Data Bagan Dari Buku Kerja di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengatur data bagan dari buku kerja Excel di Java Slides menggunakan Aspose.Slides. Panduan langkah demi langkah dengan contoh kode untuk presentasi dinamis.
weight: 15
url: /id/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengantar Mengatur Data Bagan Dari Buku Kerja di Slide Java

Aspose.Slides untuk Java adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan presentasi PowerPoint secara terprogram. Ini menyediakan fitur ekstensif untuk membuat, memanipulasi, dan mengelola slide PowerPoint. Salah satu persyaratan umum saat bekerja dengan presentasi adalah mengatur data bagan secara dinamis dari sumber data eksternal, seperti buku kerja Excel. Dalam tutorial ini, kami akan mendemonstrasikan cara mencapai hal ini menggunakan Java.

## Prasyarat

Sebelum kita mendalami penerapannya, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) diinstal pada sistem Anda.
- Aspose.Slides untuk perpustakaan Java ditambahkan ke proyek Anda.
- Buku kerja Excel dengan data yang ingin Anda gunakan untuk bagan.

## Langkah 1: Buat Presentasi

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Kita mulai dengan membuat presentasi PowerPoint baru menggunakan Aspose.Slides for Java.

## Langkah 2: Tambahkan Bagan

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Selanjutnya, kita menambahkan bagan ke salah satu slide dalam presentasi. Dalam contoh ini, kami menambahkan diagram lingkaran, namun Anda dapat memilih jenis diagram yang sesuai dengan kebutuhan Anda.

## Langkah 3: Hapus Data Grafik

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Kami menghapus semua data yang ada dari bagan untuk mempersiapkannya bagi data baru dari buku kerja Excel.

## Langkah 4: Muat Buku Kerja Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

 Kami memuat buku kerja Excel yang berisi data yang ingin kami gunakan untuk bagan. Mengganti`"book1.xlsx"` dengan jalur ke file Excel Anda.

## Langkah 5: Tulis Aliran Buku Kerja ke Data Bagan

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Kami mengonversi data buku kerja Excel menjadi aliran dan menuliskannya ke data bagan.

## Langkah 6: Tetapkan Rentang Data Bagan

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Kami menentukan rentang sel dari buku kerja Excel yang harus digunakan sebagai data untuk bagan. Sesuaikan rentang sesuai kebutuhan data Anda.

## Langkah 7: Sesuaikan Seri Bagan

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Anda dapat menyesuaikan berbagai properti rangkaian bagan agar sesuai dengan kebutuhan Anda. Dalam contoh ini, kami mengaktifkan beragam warna untuk rangkaian bagan.

## Langkah 8: Simpan Presentasi

```java
pres.save(outPath, SaveFormat.Pptx);
```

Terakhir, kami menyimpan presentasi dengan data bagan yang diperbarui ke jalur keluaran yang ditentukan.

## Kode Sumber Lengkap Untuk Kumpulan Data Bagan Dari Buku Kerja di Slide Java

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara mengatur data bagan dari buku kerja Excel di Java Slides menggunakan pustaka Aspose.Slides untuk Java. Dengan mengikuti panduan langkah demi langkah dan menggunakan contoh kode sumber yang disediakan, Anda dapat dengan mudah mengintegrasikan data grafik dinamis ke dalam presentasi PowerPoint Anda.

## FAQ

### Bagaimana cara mengkustomisasi tampilan bagan dalam presentasi saya?

Anda dapat menyesuaikan tampilan bagan dengan memodifikasi properti seperti warna, font, label, dan lainnya. Lihat dokumentasi Aspose.Slides untuk Java untuk informasi detail tentang opsi penyesuaian bagan.

### Bisakah saya menggunakan data dari file Excel lain untuk bagan?

Ya, Anda bisa menggunakan data dari file Excel mana pun dengan menentukan jalur file yang benar saat memuat buku kerja dalam kode.

### Jenis bagan apa lagi yang bisa saya buat dengan Aspose.Slides untuk Java?

Aspose.Slides untuk Java mendukung berbagai jenis bagan, termasuk bagan batang, bagan garis, bagan sebar, dan banyak lagi. Anda dapat memilih jenis bagan yang paling sesuai dengan kebutuhan representasi data Anda.

### Apakah mungkin untuk memperbarui data bagan secara dinamis dalam presentasi yang sedang berjalan?

Ya, Anda bisa memperbarui data bagan secara dinamis dalam presentasi dengan memodifikasi buku kerja yang mendasarinya lalu menyegarkan data bagan.

### Di mana saya dapat menemukan lebih banyak contoh dan sumber daya untuk bekerja dengan Aspose.Slides untuk Java?

 Anda dapat menjelajahi contoh dan sumber tambahan di[Asumsikan situs web](https://www.aspose.com/). Selain itu, dokumentasi Aspose.Slides untuk Java memberikan panduan komprehensif tentang cara bekerja dengan perpustakaan.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
