---
title: Tambahkan Bilah Kesalahan di Slide Java
linktitle: Tambahkan Bilah Kesalahan di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menambahkan bilah kesalahan ke bagan PowerPoint di Java menggunakan Aspose.Slides. Panduan langkah demi langkah dengan kode sumber untuk menyesuaikan bilah kesalahan.
type: docs
weight: 13
url: /id/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Pengantar Menambahkan Bilah Kesalahan di Slide Java menggunakan Aspose.Slides

Dalam tutorial ini, kami akan mendemonstrasikan cara menambahkan bilah kesalahan ke bagan di slide PowerPoint menggunakan Aspose.Slides untuk Java. Bilah kesalahan memberikan informasi berharga tentang variabilitas atau ketidakpastian titik data dalam bagan. Kami akan membuat diagram gelembung dan menambahkan bilah kesalahan ke dalamnya. Mari kita mulai!

## Prasyarat

 Sebelum memulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda. Anda dapat mengunduh perpustakaan dari[Asumsikan situs web](https://downloads.aspose.com/slides/java).

## Langkah 1: Buat Presentasi Kosong

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Membuat presentasi kosong
Presentation presentation = new Presentation();
```

Pada langkah ini, kita membuat presentasi kosong di mana kita akan menambahkan bagan dengan bilah kesalahan.

## Langkah 2: Buat Bagan Gelembung

```java
// Membuat diagram gelembung
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Di sini, kita membuat bagan gelembung dan menentukan posisi serta dimensinya pada slide.

## Langkah 3: Menambahkan Bilah Kesalahan dan Mengatur Format

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

Pada langkah ini, kami menambahkan bilah kesalahan ke bagan dan mengatur formatnya. Anda dapat mengkustomisasi bilah kesalahan dengan mengubah nilai, tipe, dan properti lainnya.

- `errBarX` mewakili bilah kesalahan di sepanjang sumbu X.
- `errBarY` mewakili bilah kesalahan di sepanjang sumbu Y.
- Kami membuat bilah kesalahan X dan Y terlihat.
- `setValueType` menentukan jenis nilai untuk bilah kesalahan (misalnya, Tetap atau Persentase).
- `setValue` menetapkan nilai untuk bilah kesalahan.
- `setType` mendefinisikan jenis bilah kesalahan (misalnya, Plus atau Minus).
-  Kami mengatur lebar garis bilah kesalahan menggunakan`getFormat().getLine().setWidth(2)`.
- `setEndCap` menentukan apakah akan menyertakan batas akhir pada bilah kesalahan.

## Langkah 4: Simpan Presentasi

```java
// Menyimpan presentasi
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Terakhir, kami menyimpan presentasi dengan bilah kesalahan yang ditambahkan ke lokasi tertentu.

Itu dia! Anda telah berhasil menambahkan bilah kesalahan ke bagan di slide PowerPoint menggunakan Aspose.Slides untuk Java.

## Kode Sumber Lengkap Untuk Menambahkan Bilah Kesalahan di Slide Java

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

Dalam tutorial ini, kita telah menjelajahi cara menyempurnakan presentasi PowerPoint Anda dengan menambahkan bilah kesalahan ke bagan menggunakan Aspose.Slides untuk Java. Bilah kesalahan memberikan wawasan berharga mengenai variabilitas dan ketidakpastian data, menjadikan presentasi Anda lebih informatif dan menarik secara visual.

## FAQ

### Bagaimana cara menyesuaikan tampilan bilah kesalahan lebih lanjut?

Anda dapat menyesuaikan bilah kesalahan dengan mengubah propertinya, seperti gaya garis, warna, dan lebar, seperti yang ditunjukkan pada Langkah 3.

### Bisakah saya menambahkan bilah kesalahan ke jenis bagan lain?

Ya, Anda dapat menambahkan bilah kesalahan ke berbagai tipe bagan yang didukung oleh Aspose.Slides untuk Java. Cukup buat jenis bagan yang diinginkan dan ikuti langkah-langkah penyesuaian bilah kesalahan yang sama.

### Bagaimana cara mengatur posisi dan ukuran grafik pada slide?

Anda dapat mengontrol posisi dan dimensi grafik dengan menyesuaikan parameter di`addChart` metode, seperti yang ditunjukkan pada Langkah 2.

### Di mana saya dapat menemukan informasi lebih lanjut tentang Aspose.Slides untuk Java?

 Anda dapat merujuk ke[Aspose.Slides untuk dokumentasi Java](https://reference.aspose.com/slides/java/) untuk informasi rinci tentang penggunaan perpustakaan.