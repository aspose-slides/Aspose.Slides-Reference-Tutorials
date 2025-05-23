---
"description": "Pelajari cara menambahkan bilah kesalahan ke diagram PowerPoint di Java menggunakan Aspose.Slides. Panduan langkah demi langkah dengan kode sumber untuk menyesuaikan bilah kesalahan."
"linktitle": "Menambahkan Error Bar di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Menambahkan Error Bar di Slide Java"
"url": "/id/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Error Bar di Slide Java


## Pengantar Menambahkan Error Bar di Java Slides menggunakan Aspose.Slides

Dalam tutorial ini, kami akan menunjukkan cara menambahkan batang kesalahan ke bagan di slide PowerPoint menggunakan Aspose.Slides untuk Java. Batang kesalahan memberikan informasi berharga tentang variabilitas atau ketidakpastian titik data dalam bagan. Kami akan membuat bagan gelembung dan menambahkan batang kesalahan ke dalamnya. Mari kita mulai!

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal dan mengatur pustaka Aspose.Slides for Java di proyek Java Anda. Anda dapat mengunduh pustaka tersebut dari [Situs web Aspose](https://downloads.aspose.com/slides/java).

## Langkah 1: Buat Presentasi Kosong

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Membuat presentasi kosong
Presentation presentation = new Presentation();
```

Pada langkah ini, kita membuat presentasi kosong di mana kita akan menambahkan bagan dengan batang kesalahan.

## Langkah 2: Buat Bagan Gelembung

```java
// Membuat diagram gelembung
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Di sini, kita membuat bagan gelembung dan menentukan posisi dan dimensinya pada slide.

## Langkah 3: Menambahkan Bar Kesalahan dan Mengatur Format

```java
// Menambahkan bilah Kesalahan dan mengatur formatnya
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

Pada langkah ini, kami menambahkan bilah kesalahan ke bagan dan mengatur formatnya. Anda dapat menyesuaikan bilah kesalahan dengan mengubah nilai, jenis, dan properti lainnya.

- `errBarX` menggambarkan batang kesalahan sepanjang sumbu X.
- `errBarY` menggambarkan batang kesalahan sepanjang sumbu Y.
- Kami membuat batang kesalahan X dan Y terlihat.
- `setValueType` menentukan jenis nilai untuk batang kesalahan (misalnya, Tetap atau Persentase).
- `setValue` mengatur nilai untuk batang kesalahan.
- `setType` mendefinisikan jenis batang kesalahan (misalnya, Plus atau Minus).
- Kami mengatur lebar garis batang kesalahan menggunakan `getFormat().getLine().setWidth(2)`.
- `setEndCap` menentukan apakah akan menyertakan tutup ujung pada batang kesalahan.

## Langkah 4: Simpan Presentasi

```java
// Menyimpan presentasi
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Terakhir, kami menyimpan presentasi dengan menambahkan bilah kesalahan ke lokasi yang ditentukan.

Selesai! Anda telah berhasil menambahkan bilah kesalahan ke bagan di slide PowerPoint menggunakan Aspose.Slides untuk Java.

## Source Code Lengkap Untuk Menambahkan Error Bar di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Membuat presentasi kosong
Presentation presentation = new Presentation();
try
{
	// Membuat diagram gelembung
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Menambahkan bilah Kesalahan dan mengatur formatnya
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Menyimpan presentasi
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kami telah menjajaki cara menyempurnakan presentasi PowerPoint Anda dengan menambahkan bilah kesalahan ke bagan menggunakan Aspose.Slides untuk Java. Bilah kesalahan memberikan wawasan berharga tentang variabilitas dan ketidakpastian data, menjadikan presentasi Anda lebih informatif dan menarik secara visual.

## Pertanyaan yang Sering Diajukan

### Bagaimana saya dapat menyesuaikan tampilan bilah kesalahan lebih lanjut?

Anda dapat menyesuaikan bilah kesalahan dengan memodifikasi propertinya, seperti gaya garis, warna, dan lebar, seperti yang ditunjukkan pada Langkah 3.

### Dapatkah saya menambahkan batang kesalahan ke jenis grafik yang berbeda?

Ya, Anda dapat menambahkan bilah kesalahan ke berbagai jenis bagan yang didukung oleh Aspose.Slides untuk Java. Cukup buat jenis bagan yang diinginkan dan ikuti langkah-langkah penyesuaian bilah kesalahan yang sama.

### Bagaimana cara menyesuaikan posisi dan ukuran grafik pada slide?

Anda dapat mengontrol posisi dan dimensi grafik dengan menyesuaikan parameter di `addChart` metode, seperti yang ditunjukkan pada Langkah 2.

### Di mana saya dapat menemukan informasi lebih lanjut tentang Aspose.Slides untuk Java?

Anda dapat merujuk ke [Dokumentasi Aspose.Slides untuk Java](https://reference.aspose.com/slides/java/) untuk informasi terperinci tentang penggunaan perpustakaan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}