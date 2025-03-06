---
title: Properti Font untuk Legenda Individu di Slide Java
linktitle: Properti Font untuk Legenda Individu di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Sempurnakan presentasi PowerPoint dengan gaya, ukuran, dan warna font khusus untuk masing-masing legenda di Java Slides menggunakan Aspose.Slides untuk Java.
weight: 12
url: /id/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Properti Font untuk Legenda Individu di Slide Java


## Pengantar Properti Font untuk Legenda Individual di Slide Java

Dalam tutorial ini, kita akan mempelajari cara mengatur properti font untuk legenda individual di Java Slides menggunakan Aspose.Slides untuk Java. Dengan mengkustomisasi properti font, Anda bisa membuat legenda Anda lebih menarik secara visual dan informatif dalam presentasi PowerPoint Anda.

## Prasyarat

 Sebelum memulai, pastikan Anda memiliki perpustakaan Aspose.Slides untuk Java yang terintegrasi ke dalam proyek Anda. Anda dapat mengunduhnya dari[Aspose.Slide untuk Dokumentasi Java](https://reference.aspose.com/slides/java/).

## Langkah 1: Inisialisasi Presentasi dan Tambahkan Bagan

Pertama, mari kita mulai dengan menginisialisasi presentasi PowerPoint dan menambahkan bagan ke dalamnya. Dalam contoh ini, kita akan menggunakan bagan kolom berkerumun sebagai ilustrasi.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // Kode lainnya ada di sini
} finally {
    if (pres != null) pres.dispose();
}
```

 Mengganti`"Your Document Directory"` dengan direktori sebenarnya tempat dokumen PowerPoint Anda berada.

## Langkah 2: Sesuaikan Properti Font untuk Legenda

Sekarang, mari sesuaikan properti font untuk entri legenda individual dalam bagan. Dalam contoh ini, kami menargetkan entri legenda kedua (indeks 1), namun Anda dapat menyesuaikan indeks sesuai dengan kebutuhan spesifik Anda.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Inilah yang dilakukan setiap baris kode:

- `get_Item(1)` mengambil entri legenda kedua (indeks 1). Anda dapat mengubah indeks untuk menargetkan entri legenda yang berbeda.
- `setFontBold(NullableBool.True)` mengatur font menjadi tebal.
- `setFontHeight(20)` mengatur ukuran font menjadi 20 poin.
- `setFontItalic(NullableBool.True)` mengatur font menjadi miring.
- `setFillType(FillType.Solid)` menetapkan bahwa teks entri legenda harus memiliki isi yang solid.
- `getSolidFillColor().setColor(Color.BLUE)` mengatur warna isian menjadi biru. Anda bisa menggantinya`Color.BLUE` dengan warna yang Anda inginkan.

## Langkah 3: Simpan Presentasi yang Dimodifikasi

Terakhir, simpan presentasi yang dimodifikasi ke file baru untuk menyimpan perubahan Anda.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Mengganti`"output.pptx"` dengan nama file keluaran pilihan Anda.

Itu dia! Anda telah berhasil mengkustomisasi properti font untuk entri legenda individual dalam presentasi Java Slides menggunakan Aspose.Slides untuk Java.

## Kode Sumber Lengkap Untuk Properti Font untuk Legenda Individu di Slide Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menyesuaikan properti font untuk masing-masing legenda di Java Slides menggunakan Aspose.Slides untuk Java. Dengan menyesuaikan gaya font, ukuran, dan warna, Anda dapat meningkatkan daya tarik visual dan kejelasan presentasi PowerPoint Anda.

## FAQ

### Bagaimana cara mengubah warna font?

 Untuk mengubah warna font, gunakan`tf.getPortionFormat().getFontColor().setColor(yourColor)` alih-alih mengubah warna isian. Mengganti`yourColor` dengan warna font yang diinginkan.

### Bagaimana cara mengubah properti legenda lainnya?

Anda dapat memodifikasi berbagai properti legenda lainnya, seperti posisi, ukuran, dan format. Lihat dokumentasi Aspose.Slides untuk Java untuk informasi mendetail tentang bekerja dengan legenda.

### Bisakah saya menerapkan perubahan ini ke beberapa entri legenda?

 Ya, Anda dapat mengulang entri legenda dan menerapkan perubahan ini ke beberapa entri dengan menyesuaikan indeks`get_Item(index)` dan mengulangi kode penyesuaian.

Ingatlah untuk membuang objek presentasi setelah Anda selesai melepaskan sumber daya:

```java
if (pres != null) pres.dispose();
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
