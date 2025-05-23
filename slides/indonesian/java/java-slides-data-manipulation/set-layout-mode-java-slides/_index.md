---
"description": "Pelajari cara mengatur mode tata letak untuk slide Java menggunakan Aspose.Slides. Sesuaikan posisi dan ukuran bagan dalam panduan langkah demi langkah ini dengan kode sumber."
"linktitle": "Mengatur Mode Tata Letak di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Mode Tata Letak di Slide Java"
"url": "/id/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Mode Tata Letak di Slide Java


## Pengenalan Mode Tata Letak Set pada Slide Java

Dalam tutorial ini, kita akan mempelajari cara mengatur mode tata letak untuk bagan di slide Java menggunakan Aspose.Slides untuk Java. Mode tata letak menentukan posisi dan ukuran bagan di dalam slide.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menginstal dan mengatur pustaka Aspose.Slides for Java di proyek Java Anda. Anda dapat mengunduh pustaka tersebut dari [Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Buat Presentasi

Pertama, kita perlu membuat presentasi baru.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Langkah 2: Tambahkan Slide dan Bagan

Selanjutnya, kita akan menambahkan slide dan diagram ke dalamnya. Dalam contoh ini, kita akan membuat diagram kolom berkelompok.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Langkah 3: Mengatur Tata Letak Bagan

Sekarang, mari kita atur tata letak untuk grafik. Kita akan menyesuaikan posisi dan ukuran grafik di dalam slide menggunakan `setX`Bahasa Indonesia: `setY`Bahasa Indonesia: `setWidth`Bahasa Indonesia: `setHeight` metode. Selain itu, kami akan mengatur `LayoutTargetType` untuk menentukan mode tata letak.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

Dalam contoh ini, kami telah menetapkan bagan agar memiliki target jenis tata letak "Dalam", yang berarti bagan akan diposisikan dan berukuran relatif terhadap area dalam slide.

## Langkah 4: Simpan Presentasi

Terakhir, mari simpan presentasi dengan pengaturan tata letak bagan.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Source Code Lengkap Untuk Set Layout Mode di Java Slides

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

Dalam tutorial ini, kita telah mempelajari cara mengatur mode tata letak untuk bagan di slide Java menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan posisi dan ukuran bagan sesuai dengan kebutuhan spesifik Anda dengan menyesuaikan nilai-nilai di `setX`Bahasa Indonesia: `setY`Bahasa Indonesia: `setWidth`Bahasa Indonesia: `setHeight`, Dan `setLayoutTargetType` metode. Ini memberi Anda kendali atas penempatan grafik dalam slide Anda.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah mode tata letak untuk bagan di Aspose.Slides untuk Java?

Untuk mengubah mode tata letak untuk bagan di Aspose.Slides untuk Java, Anda dapat menggunakan `setLayoutTargetType` metode pada area plot grafik. Anda dapat mengaturnya ke `LayoutTargetType.Inner` atau `LayoutTargetType.Outer` tergantung pada tata letak yang Anda inginkan.

### Dapatkah saya menyesuaikan posisi dan ukuran bagan dalam slide?

Ya, Anda dapat menyesuaikan posisi dan ukuran grafik di dalam slide dengan menggunakan `setX`Bahasa Indonesia: `setY`Bahasa Indonesia: `setWidth`, Dan `setHeight` metode pada area plot grafik. Sesuaikan nilai-nilai ini untuk memposisikan dan mengukur grafik sesuai dengan kebutuhan Anda.

### Di mana saya dapat menemukan informasi lebih lanjut tentang Aspose.Slides untuk Java?

Anda dapat menemukan informasi lebih lanjut tentang Aspose.Slides untuk Java di [dokumentasi](https://reference.aspose.com/slides/java/)Termasuk referensi API terperinci dan contoh-contoh untuk membantu Anda bekerja dengan slide dan grafik secara efektif di Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}