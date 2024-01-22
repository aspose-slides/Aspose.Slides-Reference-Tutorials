---
title: Atur Mode Tata Letak di Slide Java
linktitle: Atur Mode Tata Letak di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengatur mode tata letak untuk slide Java menggunakan Aspose.Slides. Sesuaikan posisi dan ukuran bagan dalam panduan langkah demi langkah ini dengan kode sumber.
type: docs
weight: 23
url: /id/java/data-manipulation/set-layout-mode-java-slides/
---

## Pengantar Mengatur Mode Tata Letak di Slide Java

Dalam tutorial ini, kita akan mempelajari cara mengatur mode tata letak untuk bagan di slide Java menggunakan Aspose.Slides untuk Java. Mode tata letak menentukan posisi dan ukuran grafik dalam slide.

## Prasyarat

 Sebelum kita mulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda. Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Buat Presentasi

Pertama, kita perlu membuat presentasi baru.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Langkah 2: Tambahkan Slide dan Bagan

Selanjutnya, kita akan menambahkan slide dan grafik ke dalamnya. Dalam contoh ini, kita akan membuat bagan kolom berkerumun.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Langkah 3: Atur Tata Letak Bagan

 Sekarang, mari kita atur tata letak grafiknya. Kami akan menyesuaikan posisi dan ukuran grafik dalam slide menggunakan`setX`, `setY`, `setWidth`, `setHeight` metode. Selain itu, kami akan mengatur`LayoutTargetType` untuk menentukan mode tata letak.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

Dalam contoh ini, kita telah menetapkan bagan agar memiliki tipe target tata letaknya sebagai "Bagian Dalam", yang berarti bagan tersebut akan diposisikan dan berukuran relatif terhadap area dalam slide.

## Langkah 4: Simpan Presentasi

Terakhir, simpan presentasi dengan pengaturan tata letak bagan.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Kode Sumber Lengkap Untuk Mengatur Mode Tata Letak di Slide Java

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

 Dalam tutorial ini, kita telah mempelajari cara mengatur mode tata letak untuk bagan di slide Java menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan posisi dan ukuran bagan sesuai kebutuhan spesifik Anda dengan menyesuaikan nilai di`setX`, `setY`, `setWidth`, `setHeight` , Dan`setLayoutTargetType`metode. Ini memberi Anda kendali atas penempatan bagan dalam slide Anda.

## FAQ

### Bagaimana cara mengubah mode tata letak bagan di Aspose.Slides untuk Java?

 Untuk mengubah mode tata letak bagan di Aspose.Slides untuk Java, Anda dapat menggunakan`setLayoutTargetType` metode pada area plot grafik. Anda dapat mengaturnya menjadi keduanya`LayoutTargetType.Inner` atau`LayoutTargetType.Outer` tergantung pada tata letak yang Anda inginkan.

### Bisakah saya menyesuaikan posisi dan ukuran grafik dalam slide?

 Ya, Anda dapat menyesuaikan posisi dan ukuran grafik dalam slide dengan menggunakan`setX`, `setY`, `setWidth` , Dan`setHeight` metode pada area plot grafik. Sesuaikan nilai-nilai ini dengan posisi dan ukuran bagan sesuai dengan kebutuhan Anda.

### Di mana saya dapat menemukan informasi lebih lanjut tentang Aspose.Slides untuk Java?

 Anda dapat menemukan informasi lebih lanjut tentang Aspose.Slides untuk Java di[dokumentasi](https://reference.aspose.com/slides/java/). Ini mencakup referensi dan contoh API terperinci untuk membantu Anda bekerja dengan slide dan bagan secara efektif di Java.