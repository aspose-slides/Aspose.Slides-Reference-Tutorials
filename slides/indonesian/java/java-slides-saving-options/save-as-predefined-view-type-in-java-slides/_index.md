---
"description": "Pelajari cara mengatur tipe tampilan yang telah ditetapkan sebelumnya di Java Slides menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan contoh kode dan Tanya Jawab Umum."
"linktitle": "Simpan sebagai Jenis Tampilan yang Telah Ditentukan di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Simpan sebagai Jenis Tampilan yang Telah Ditentukan di Java Slides"
"url": "/id/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Simpan sebagai Jenis Tampilan yang Telah Ditentukan di Java Slides


## Pengantar Menyimpan sebagai Jenis Tampilan yang Telah Ditentukan Sebelumnya di Java Slides

Dalam panduan langkah demi langkah ini, kita akan mempelajari cara menyimpan presentasi dengan tipe tampilan yang telah ditetapkan sebelumnya menggunakan Aspose.Slides untuk Java. Kami akan memberi Anda kode dan penjelasan yang diperlukan untuk menyelesaikan tugas ini dengan sukses.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar tentang pemrograman Java.
- Aspose.Slides untuk pustaka Java terinstal.
- Lingkungan pengembangan terintegrasi (IDE) pilihan Anda.

## Menyiapkan Lingkungan Anda

Untuk memulai, ikuti langkah-langkah berikut untuk menyiapkan lingkungan pengembangan Anda:

1. Buat proyek Java baru di IDE Anda.
2. Tambahkan pustaka Aspose.Slides untuk Java ke proyek Anda sebagai dependensi.

Sekarang lingkungan Anda sudah disiapkan, mari lanjutkan dengan kodenya.

## Langkah 1: Membuat Presentasi

Untuk mendemonstrasikan penyimpanan presentasi dengan tipe tampilan yang telah ditetapkan, pertama-tama kita akan membuat presentasi baru. Berikut kode untuk membuat presentasi:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Membuka file presentasi
Presentation presentation = new Presentation();
```

Dalam kode ini, kita membuat yang baru `Presentation` objek, yang merepresentasikan presentasi PowerPoint kita.

## Langkah 2: Mengatur Jenis Tampilan

Berikutnya, kita akan menetapkan jenis tampilan untuk presentasi kita. Jenis tampilan menentukan bagaimana presentasi ditampilkan saat dibuka. Dalam contoh ini, kita akan menetapkannya ke "Tampilan Master Slide". Berikut kodenya:

```java
// Mengatur jenis tampilan
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

Pada kode di atas, kita menggunakan `setLastView` metode dari `ViewProperties` kelas untuk mengatur tipe tampilan ke `SlideMasterView`Anda dapat memilih jenis tampilan lain sesuai kebutuhan.

## Langkah 3: Menyimpan Presentasi

Setelah kita membuat presentasi dan mengatur jenis tampilan, sekarang saatnya menyimpan presentasi. Kita akan menyimpannya dalam format PPTX. Berikut kodenya:

```java
// Menyimpan presentasi
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

Dalam kode ini, kita menggunakan `save` metode dari `Presentation` kelas untuk menyimpan presentasi dengan nama file dan format yang ditentukan.

## Source Code Lengkap Untuk Menyimpan Sebagai Jenis Tampilan Yang Telah Ditentukan Sebelumnya di Java Slides

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

Dalam tutorial ini, kita telah mempelajari cara menyimpan presentasi dengan tipe tampilan yang telah ditetapkan sebelumnya di Java menggunakan Aspose.Slides untuk Java. Dengan mengikuti kode dan langkah-langkah yang diberikan, Anda dapat dengan mudah mengatur tipe tampilan presentasi Anda dan menyimpannya dalam format yang diinginkan.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah jenis tampilan ke tampilan selain "Tampilan Master Slide"?

Untuk mengubah jenis tampilan ke sesuatu selain "Tampilan Master Slide", cukup ganti `ViewType.SlideMasterView` dengan jenis tampilan yang diinginkan, seperti `ViewType.NataumalView` or `ViewType.SlideSorterView`, dalam kode tempat kita mengatur tipe tampilan.

### Dapatkah saya mengatur properti tampilan untuk masing-masing slide dalam presentasi?

Ya, Anda dapat mengatur properti tampilan untuk slide individual menggunakan Aspose.Slides untuk Java. Anda dapat mengakses dan memanipulasi properti untuk setiap slide secara terpisah dengan mengulangi slide dalam presentasi.

### Format apa lagi yang dapat saya gunakan untuk menyimpan presentasi saya?

Aspose.Slides untuk Java mendukung berbagai format output, termasuk PPTX, PDF, TIFF, HTML, dan banyak lagi. Anda dapat menentukan format yang diinginkan saat menyimpan presentasi Anda dengan menggunakan perintah yang sesuai. `SaveFormat` nilai enum.

### Apakah Aspose.Slides untuk Java cocok untuk pemrosesan presentasi secara batch?

Ya, Aspose.Slides untuk Java sangat cocok untuk tugas pemrosesan batch. Anda dapat mengotomatiskan pemrosesan beberapa presentasi, menerapkan perubahan, dan menyimpannya secara massal menggunakan kode Java.

### Di mana saya dapat menemukan informasi dan dokumentasi lebih lanjut untuk Aspose.Slides untuk Java?

Untuk dokumentasi dan referensi lengkap terkait Aspose.Slides untuk Java, silakan kunjungi situs web dokumentasi: [Dokumentasi Aspose.Slides untuk Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}