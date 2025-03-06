---
title: Simpan sebagai Jenis Tampilan Standar di Slide Java
linktitle: Simpan sebagai Jenis Tampilan Standar di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengatur tipe tampilan yang telah ditentukan sebelumnya di Java Slides menggunakan Aspose.Slides for Java. Panduan langkah demi langkah dengan contoh kode dan FAQ.
weight: 10
url: /id/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengantar Simpan sebagai Tipe Tampilan Standar di Slide Java

Dalam panduan langkah demi langkah ini, kita akan mempelajari cara menyimpan presentasi dengan tipe tampilan yang telah ditentukan sebelumnya menggunakan Aspose.Slides untuk Java. Kami akan memberi Anda kode dan penjelasan yang diperlukan untuk menyelesaikan tugas ini dengan sukses.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar tentang pemrograman Java.
- Aspose.Slides untuk perpustakaan Java diinstal.
- Lingkungan pengembangan terintegrasi (IDE) pilihan Anda.

## Menyiapkan Lingkungan Anda

Untuk memulai, ikuti langkah-langkah berikut untuk menyiapkan lingkungan pengembangan Anda:

1. Buat proyek Java baru di IDE Anda.
2. Tambahkan pustaka Aspose.Slides for Java ke proyek Anda sebagai dependensi.

Sekarang lingkungan Anda sudah siap, mari lanjutkan dengan kodenya.

## Langkah 1: Membuat Presentasi

Untuk mendemonstrasikan penyimpanan presentasi dengan tipe tampilan yang telah ditentukan sebelumnya, pertama-tama kita akan membuat presentasi baru. Berikut kode untuk membuat presentasi:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Membuka file presentasi
Presentation presentation = new Presentation();
```

 Dalam kode ini, kami membuat yang baru`Presentation` objek, yang mewakili presentasi PowerPoint kami.

## Langkah 2: Mengatur Jenis Tampilan

Selanjutnya, kita akan mengatur tipe tampilan untuk presentasi kita. Tipe tampilan menentukan bagaimana presentasi ditampilkan saat dibuka. Dalam contoh ini, kami akan menyetelnya ke "Slide Master View". Berikut kodenya:

```java
// Mengatur jenis tampilan
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 Pada kode di atas, kita menggunakan`setLastView` metode`ViewProperties` kelas untuk mengatur tipe tampilan`SlideMasterView`. Anda dapat memilih jenis tampilan lain sesuai kebutuhan.

## Langkah 3: Menyimpan Presentasi

Sekarang kita telah membuat presentasi dan mengatur tipe tampilan, sekarang saatnya menyimpan presentasi. Kami akan menyimpannya dalam format PPTX. Berikut kodenya:

```java
// Menyimpan presentasi
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 Dalam kode ini, kami menggunakan`save` metode`Presentation` kelas untuk menyimpan presentasi dengan nama file dan format yang ditentukan.

## Kode Sumber Lengkap Untuk Simpan sebagai Jenis Tampilan Standar di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Membuka file presentasi
Presentation presentation = new Presentation();
try
{
	// Mengatur jenis tampilan
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Menyimpan presentasi
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara menyimpan presentasi dengan tipe tampilan yang telah ditentukan sebelumnya di Java menggunakan Aspose.Slides untuk Java. Dengan mengikuti kode dan langkah-langkah yang diberikan, Anda dapat dengan mudah mengatur jenis tampilan presentasi Anda dan menyimpannya dalam format yang diinginkan.

## FAQ

### Bagaimana cara mengubah tipe tampilan menjadi selain "Slide Master View"?

 Untuk mengubah tipe tampilan menjadi selain "Slide Master View", cukup ganti`ViewType.SlideMasterView` dengan jenis tampilan yang diinginkan, seperti`ViewType.NormalView` atau`ViewType.SlideSorterView`, dalam kode tempat kita mengatur tipe tampilan.

### Bisakah saya mengatur properti tampilan untuk masing-masing slide dalam presentasi?

Ya, Anda dapat mengatur properti tampilan untuk masing-masing slide menggunakan Aspose.Slides untuk Java. Anda dapat mengakses dan memanipulasi properti untuk setiap slide secara terpisah dengan melakukan iterasi melalui slide dalam presentasi.

### Dalam format apa lagi saya dapat menyimpan presentasi saya?

Aspose.Slides untuk Java mendukung berbagai format output, termasuk PPTX, PDF, TIFF, HTML, dan banyak lagi. Anda dapat menentukan format yang diinginkan saat menyimpan presentasi Anda dengan menggunakan yang sesuai`SaveFormat` nilai enum.

### Apakah Aspose.Slides untuk Java cocok untuk pemrosesan presentasi secara batch?

Ya, Aspose.Slides untuk Java sangat cocok untuk tugas pemrosesan batch. Anda dapat mengotomatiskan pemrosesan beberapa presentasi, menerapkan perubahan, dan menyimpannya secara massal menggunakan kode Java.

### Di mana saya dapat menemukan informasi dan dokumentasi lebih lanjut untuk Aspose.Slides untuk Java?

 Untuk dokumentasi dan referensi lengkap terkait Aspose.Slides untuk Java, silakan kunjungi situs web dokumentasi:[Aspose.Slide untuk Dokumentasi Java](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
