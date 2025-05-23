---
"description": "Sempurnakan Slide Java Anda dengan Garis Kustom. Panduan langkah demi langkah menggunakan Aspose.Slides untuk Java. Pelajari cara menambahkan dan menyesuaikan garis dalam presentasi untuk visual yang memukau."
"linktitle": "Menambahkan Baris Kustom di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Menambahkan Baris Kustom di Java Slides"
"url": "/id/java/customization-and-formatting/adding-custom-lines-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Baris Kustom di Java Slides


## Pengantar Menambahkan Baris Kustom di Slide Java

Dalam tutorial ini, Anda akan mempelajari cara menambahkan baris kustom ke slide Java Anda menggunakan Aspose.Slides for Java. Baris kustom dapat digunakan untuk meningkatkan tampilan visual slide Anda dan menyorot konten tertentu. Kami akan memberikan petunjuk langkah demi langkah beserta kode sumber untuk mencapainya. Mari kita mulai!

## Prasyarat

Sebelum memulai, pastikan Anda telah menyiapkan pustaka Aspose.Slides for Java di proyek Java Anda. Anda dapat mengunduh pustaka tersebut dari situs web: [Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/)

## Langkah 1: Inisialisasi Presentasi

Pertama, Anda perlu membuat presentasi baru. Dalam contoh ini, kita akan membuat presentasi kosong.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Bagan

Berikutnya, kita akan menambahkan diagram ke slide. Dalam contoh ini, kita akan menambahkan diagram kolom berkelompok. Anda dapat memilih jenis diagram yang sesuai dengan kebutuhan Anda.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## Langkah 3: Tambahkan Garis Kustom

Sekarang, mari tambahkan garis khusus ke grafik. Kita akan membuat `IAutoShape` bertipe `ShapeType.Line` dan posisikan di dalam bagan.

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## Langkah 4: Sesuaikan Garis

Anda dapat menyesuaikan tampilan garis dengan mengatur propertinya. Dalam contoh ini, kami mengatur warna garis menjadi merah.

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Langkah 5: Simpan Presentasi

Terakhir, simpan presentasi ke lokasi yang Anda inginkan.

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## Kode Sumber Lengkap Untuk Menambahkan Baris Kustom di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
	shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
	shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
	pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Selamat! Anda telah berhasil menambahkan garis kustom ke slide Java Anda menggunakan Aspose.Slides for Java. Anda dapat menyesuaikan properti garis lebih lanjut untuk mendapatkan efek visual yang Anda inginkan.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah warna garis?

Untuk mengubah warna garis, gunakan kode berikut:
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

Mengganti `YOUR_COLOR` dengan warna yang diinginkan.

### Bisakah saya menambahkan garis khusus ke bentuk lain?

Ya, Anda dapat menambahkan garis khusus ke berbagai bentuk, bukan hanya diagram. Cukup buat `IAutoShape` dan menyesuaikannya menurut kebutuhan Anda.

### Bagaimana cara mengubah ketebalan garis?

Anda dapat mengubah ketebalan garis dengan mengatur `Width` properti format baris. Misalnya:
```java
shape.getLineFormat().setWidth(2); // Atur ketebalan garis menjadi 2 titik
```

### Apakah mungkin untuk menambahkan beberapa baris ke satu slide?

Ya, Anda dapat menambahkan beberapa baris ke slide dengan mengulangi langkah-langkah yang disebutkan dalam tutorial ini. Setiap baris dapat disesuaikan secara independen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}