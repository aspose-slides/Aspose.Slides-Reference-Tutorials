---
"description": "Pelajari cara mengatur opsi legenda khusus di Java Slides menggunakan Aspose.Slides untuk Java. Sesuaikan posisi dan ukuran legenda di bagan PowerPoint Anda."
"linktitle": "Mengatur Opsi Kustom Legenda di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Opsi Kustom Legenda di Slide Java"
"url": "/id/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Opsi Kustom Legenda di Slide Java


## Pengantar untuk Mengatur Opsi Kustom Legenda di Slide Java

Dalam tutorial ini, kami akan menunjukkan cara menyesuaikan properti legenda bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Anda dapat mengubah posisi, ukuran, dan atribut legenda lainnya agar sesuai dengan kebutuhan presentasi Anda.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Aspose.Slides untuk API Java terinstal.
- Lingkungan pengembangan Java telah disiapkan.

## Langkah 1: Impor kelas yang diperlukan:

```java
// Impor Aspose.Slides untuk kelas Java
import com.aspose.slides.*;
```

## Langkah 2: Tentukan jalur ke direktori dokumen Anda:

```java
String dataDir = "Your Document Directory";
```

## Langkah 3: Buat contoh dari `Presentation` kelas:

```java
Presentation presentation = new Presentation();
```

## Langkah 4: Tambahkan slide ke presentasi:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Langkah 5: Tambahkan bagan kolom berkelompok ke slide:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Langkah 6. Tetapkan Properti Legenda:

- Mengatur posisi X legenda (relatif terhadap lebar grafik):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Tetapkan posisi Y legenda (relatif terhadap tinggi grafik):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Mengatur lebar legenda (relatif terhadap lebar grafik):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Mengatur tinggi legenda (relatif terhadap tinggi grafik):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Langkah 7: Simpan presentasi ke disk:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Selesai! Anda telah berhasil menyesuaikan properti legenda bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java.

## Source Code Lengkap Untuk Set Legend Custom Options di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
try
{
	// Dapatkan referensi slide
	ISlide slide = presentation.getSlides().get_Item(0);
	// Tambahkan bagan kolom berkelompok pada slide
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Tetapkan Properti Legenda
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Tulis presentasi ke disk
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menyesuaikan properti legenda bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Anda dapat mengubah posisi, ukuran, dan atribut legenda lainnya untuk membuat presentasi yang menarik secara visual dan informatif.

## Pertanyaan yang Sering Diajukan

## Bagaimana cara mengubah posisi legenda?

Untuk mengubah posisi legenda, gunakan `setX` Dan `setY` metode objek legenda. Nilai ditentukan relatif terhadap lebar dan tinggi bagan.

## Bagaimana cara menyesuaikan ukuran legenda?

Anda dapat menyesuaikan ukuran legenda dengan menggunakan `setWidth` Dan `setHeight` metode objek legenda. Nilai-nilai ini juga relatif terhadap lebar dan tinggi bagan.

## Bisakah saya menyesuaikan atribut legenda lainnya?

Ya, Anda dapat menyesuaikan berbagai atribut legenda, seperti gaya font, border, warna latar belakang, dan banyak lagi. Jelajahi dokumentasi Aspose.Slides untuk informasi terperinci tentang penyesuaian legenda lebih lanjut.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}