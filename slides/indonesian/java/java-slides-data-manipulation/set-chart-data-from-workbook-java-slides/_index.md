---
"description": "Pelajari cara mengatur data bagan dari buku kerja Excel di Java Slides menggunakan Aspose.Slides. Panduan langkah demi langkah dengan contoh kode untuk presentasi dinamis."
"linktitle": "Mengatur Data Bagan dari Buku Kerja di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Data Bagan dari Buku Kerja di Slide Java"
"url": "/id/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Data Bagan dari Buku Kerja di Slide Java


## Pengenalan Set Chart Data Dari Workbook di Java Slides

Aspose.Slides untuk Java adalah pustaka canggih yang memungkinkan pengembang untuk bekerja dengan presentasi PowerPoint secara terprogram. Pustaka ini menyediakan fitur-fitur yang lengkap untuk membuat, memanipulasi, dan mengelola slide PowerPoint. Salah satu persyaratan umum saat bekerja dengan presentasi adalah mengatur data bagan secara dinamis dari sumber data eksternal, seperti buku kerja Excel. Dalam tutorial ini, kami akan menunjukkan cara melakukannya menggunakan Java.

## Prasyarat

Sebelum kita mulai menerapkannya, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) terinstal di sistem Anda.
- Pustaka Aspose.Slides untuk Java ditambahkan ke proyek Anda.
- Buku kerja Excel dengan data yang ingin Anda gunakan untuk bagan.

## Langkah 1: Buat Presentasi

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Kita mulai dengan membuat presentasi PowerPoint baru menggunakan Aspose.Slides untuk Java.

## Langkah 2: Tambahkan Bagan

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Berikutnya, kita tambahkan diagram ke salah satu slide dalam presentasi. Dalam contoh ini, kita menambahkan diagram pai, tetapi Anda dapat memilih jenis diagram yang sesuai dengan kebutuhan Anda.

## Langkah 3: Hapus Data Bagan

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Kami menghapus semua data yang ada dari bagan untuk mempersiapkannya bagi data baru dari buku kerja Excel.

## Langkah 4: Muat Buku Kerja Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

Kami memuat buku kerja Excel yang berisi data yang ingin kami gunakan untuk bagan. Ganti `"book1.xlsx"` dengan jalur ke berkas Excel Anda.

## Langkah 5: Tulis Aliran Buku Kerja ke Data Bagan

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Kami mengubah data buku kerja Excel menjadi aliran dan menuliskannya ke data bagan.

## Langkah 6: Tetapkan Rentang Data Bagan

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Kami menentukan rentang sel dari buku kerja Excel yang harus digunakan sebagai data untuk bagan. Sesuaikan rentang sesuai kebutuhan untuk data Anda.

## Langkah 7: Kustomisasi Seri Bagan

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Anda dapat menyesuaikan berbagai properti rangkaian diagram agar sesuai dengan kebutuhan Anda. Dalam contoh ini, kami mengaktifkan berbagai warna untuk rangkaian diagram.

## Langkah 8: Simpan Presentasi

```java
pres.save(outPath, SaveFormat.Pptx);
```

Terakhir, kami menyimpan presentasi dengan data bagan yang diperbarui ke jalur keluaran yang ditentukan.

## Source Code Lengkap Untuk Set Chart Data Dari Workbook di Java Slides

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

Dalam tutorial ini, kita telah mempelajari cara mengatur data bagan dari buku kerja Excel di Java Slides menggunakan pustaka Aspose.Slides for Java. Dengan mengikuti panduan langkah demi langkah dan menggunakan contoh kode sumber yang disediakan, Anda dapat dengan mudah mengintegrasikan data bagan dinamis ke dalam presentasi PowerPoint Anda.

## Pertanyaan yang Sering Diajukan

### Bagaimana saya dapat menyesuaikan tampilan bagan dalam presentasi saya?

Anda dapat menyesuaikan tampilan bagan dengan mengubah properti seperti warna, font, label, dan lainnya. Lihat dokumentasi Aspose.Slides untuk Java untuk informasi terperinci tentang opsi penyesuaian bagan.

### Bisakah saya menggunakan data dari berkas Excel yang berbeda untuk bagan tersebut?

Ya, Anda dapat menggunakan data dari file Excel mana pun dengan menentukan jalur file yang benar saat memuat buku kerja dalam kode.

### Jenis bagan apa lagi yang dapat saya buat dengan Aspose.Slides untuk Java?

Aspose.Slides untuk Java mendukung berbagai jenis bagan, termasuk bagan batang, bagan garis, bagan sebar, dan banyak lagi. Anda dapat memilih jenis bagan yang paling sesuai dengan kebutuhan representasi data Anda.

### Apakah mungkin untuk memperbarui data bagan secara dinamis dalam presentasi yang sedang berjalan?

Ya, Anda dapat memperbarui data bagan secara dinamis dalam presentasi dengan memodifikasi buku kerja yang mendasarinya lalu menyegarkan data bagan.

### Di mana saya dapat menemukan lebih banyak contoh dan sumber daya untuk bekerja dengan Aspose.Slides untuk Java?

Anda dapat menjelajahi contoh dan sumber daya tambahan di [Situs web Aspose](https://www.aspose.com/)Selain itu, dokumentasi Aspose.Slides untuk Java menyediakan panduan lengkap tentang cara bekerja dengan pustaka tersebut.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}