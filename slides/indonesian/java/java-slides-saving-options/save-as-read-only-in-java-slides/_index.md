---
title: Simpan sebagai Read-Only di Java Slides
linktitle: Simpan sebagai Read-Only di Java Slides
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menyimpan presentasi PowerPoint sebagai baca-saja di Java menggunakan Aspose.Slides. Lindungi konten Anda dengan petunjuk langkah demi langkah dan contoh kode.
weight: 11
url: /id/java/saving-options/save-as-read-only-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengantar Simpan sebagai Read-Only di Slide Java Menggunakan Aspose.Slides untuk Java

Di era digital saat ini, memastikan keamanan dan integritas dokumen Anda adalah hal yang terpenting. Jika Anda bekerja dengan presentasi PowerPoint di Java, Anda mungkin perlu menyimpannya sebagai hanya-baca untuk mencegah modifikasi yang tidak sah. Dalam panduan komprehensif ini, kita akan menjelajahi cara mencapai hal ini menggunakan Aspose.Slides for Java API yang canggih. Kami akan memberi Anda petunjuk langkah demi langkah dan contoh kode sumber untuk membantu Anda menjaga presentasi Anda secara efektif.

## Prasyarat

Sebelum kita mendalami detail penerapannya, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Slides for Java: Anda harus menginstal Aspose.Slides for Java. Jika Anda belum melakukannya, Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).

2. Lingkungan Pengembangan Java: Pastikan Anda telah menyiapkan lingkungan pengembangan Java di sistem Anda.

3. Pengetahuan Dasar Java: Keakraban dengan pemrograman Java akan bermanfaat.

## Langkah 1: Menyiapkan Proyek Anda

Untuk memulai, buat proyek Java baru di Lingkungan Pengembangan Terpadu (IDE) pilihan Anda. Pastikan untuk menyertakan perpustakaan Aspose.Slides untuk Java dalam proyek Anda.

## Langkah 2: Membuat Presentasi

Pada langkah ini, kita akan membuat presentasi PowerPoint baru menggunakan Aspose.Slides for Java. Berikut kode Java untuk mencapai hal ini:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Buat instance objek Presentasi yang mewakili file PPT
Presentation presentation = new Presentation();
```

 Pastikan untuk mengganti`"Your Document Directory"` dengan jalur ke direktori yang Anda inginkan tempat Anda ingin menyimpan presentasi.

## Langkah 3: Menambahkan Konten (Opsional)

Anda dapat menambahkan konten ke presentasi Anda sesuai kebutuhan. Langkah ini bersifat opsional dan bergantung pada konten spesifik yang ingin Anda sertakan.

## Langkah 4: Mengatur Perlindungan Tulis

Untuk membuat presentasi hanya-baca, kami akan mengatur perlindungan penulisan dengan memberikan kata sandi. Inilah cara Anda melakukannya:

```java
// Mengatur Perlindungan Tulis Kata Sandi
presentation.getProtectionManager().setWriteProtection("your_password");
```

 Mengganti`"your_password"` dengan kata sandi yang ingin Anda atur untuk perlindungan penulisan.

## Langkah 5: Menyimpan Presentasi

Terakhir, kami akan menyimpan presentasi ke file dengan perlindungan read-only:

```java
// Simpan presentasi Anda ke file
presentation.save(dataDir + "ReadonlyPresentation.pptx", SaveFormat.Pptx);
```

 Pastikan Anda menggantinya`"ReadonlyPresentation.pptx"` dengan nama file yang Anda inginkan.

## Kode Sumber Lengkap Untuk Simpan sebagai Read-Only di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Buat instance objek Presentasi yang mewakili file PPT
Presentation presentation = new Presentation();
try
{
	//....melakukan beberapa pekerjaan di sini.....
	// Mengatur Perlindungan Tulis Kata Sandi
	presentation.getProtectionManager().setWriteProtection("test");
	// Simpan presentasi Anda ke file
	presentation.save(dataDir + "WriteProtected_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara menyimpan presentasi PowerPoint sebagai baca-saja di Java menggunakan pustaka Aspose.Slides untuk Java. Fitur keamanan ini akan membantu Anda melindungi konten berharga Anda dari modifikasi yang tidak sah.

## FAQ

### Bagaimana cara menghapus proteksi penulisan dari presentasi?

 Untuk menghapus perlindungan penulisan dari presentasi, Anda dapat menggunakan`removeWriteProtection()` metode yang disediakan oleh Aspose.Slides untuk Java. Berikut ini contohnya:

```java
// Hapus perlindungan penulisan
presentation.getProtectionManager().removeWriteProtection();
```

### Dapatkah saya menetapkan kata sandi yang berbeda untuk proteksi baca-saja dan tulis?

Ya, Anda dapat mengatur kata sandi berbeda untuk proteksi baca-saja dan proteksi tulis. Cukup gunakan metode yang sesuai untuk mengatur kata sandi yang diinginkan:

- `setReadProtection(String password)` untuk perlindungan hanya-baca.
- `setWriteProtection(String password)` untuk perlindungan penulisan.

### Apakah mungkin untuk melindungi slide tertentu dalam presentasi?

 Ya, Anda dapat melindungi slide tertentu dalam presentasi dengan mengatur perlindungan penulisan pada masing-masing slide. Menggunakan`Slide` objek`getProtectionManager()`metode untuk mengelola perlindungan untuk slide tertentu.

### Apa yang terjadi jika saya lupa kata sandi perlindungan tulis?

Jika Anda lupa kata sandi perlindungan penulisan, tidak ada cara bawaan untuk memulihkannya. Pastikan untuk menyimpan catatan kata sandi Anda di lokasi yang aman untuk menghindari ketidaknyamanan.

### Bisakah saya mengubah kata sandi read-only setelah mengaturnya?

 Ya, Anda dapat mengubah kata sandi read-only setelah mengaturnya. Menggunakan`setReadProtection(String newPassword)` metode dengan kata sandi baru untuk memperbarui kata sandi perlindungan read-only.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
