---
"description": "Pelajari cara menyimpan presentasi PowerPoint sebagai read-only di Java menggunakan Aspose.Slides. Lindungi konten Anda dengan petunjuk langkah demi langkah dan contoh kode."
"linktitle": "Simpan sebagai Hanya-Baca di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Simpan sebagai Hanya-Baca di Java Slides"
"url": "/id/java/saving-options/save-as-read-only-in-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Simpan sebagai Hanya-Baca di Java Slides


## Pengantar Menyimpan sebagai Hanya-Baca di Slide Java Menggunakan Aspose.Slides untuk Java

Di era digital saat ini, memastikan keamanan dan integritas dokumen Anda adalah yang terpenting. Jika Anda bekerja dengan presentasi PowerPoint di Java, Anda mungkin perlu menyimpannya sebagai read-only untuk mencegah modifikasi yang tidak sah. Dalam panduan lengkap ini, kami akan membahas cara mencapainya menggunakan Aspose.Slides for Java API yang canggih. Kami akan memberi Anda petunjuk langkah demi langkah dan contoh kode sumber untuk membantu Anda menjaga keamanan presentasi Anda secara efektif.

## Prasyarat

Sebelum kita menyelami detail implementasi, pastikan Anda memiliki prasyarat berikut:

1. Aspose.Slides untuk Java: Anda harus sudah menginstal Aspose.Slides untuk Java. Jika belum, Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).

2. Lingkungan Pengembangan Java: Pastikan Anda telah menyiapkan lingkungan pengembangan Java di sistem Anda.

3. Pengetahuan Dasar Java: Keakraban dengan pemrograman Java akan bermanfaat.

## Langkah 1: Menyiapkan Proyek Anda

Untuk memulai, buat proyek Java baru di Lingkungan Pengembangan Terpadu (IDE) pilihan Anda. Pastikan untuk menyertakan pustaka Aspose.Slides for Java di proyek Anda.

## Langkah 2: Membuat Presentasi

Pada langkah ini, kita akan membuat presentasi PowerPoint baru menggunakan Aspose.Slides for Java. Berikut kode Java untuk melakukannya:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Membuat instance objek Presentasi yang mewakili file PPT
Presentation presentation = new Presentation();
```

Pastikan untuk mengganti `"Your Document Directory"` dengan jalur ke direktori yang Anda inginkan di mana Anda ingin menyimpan presentasi.

## Langkah 3: Menambahkan Konten (Opsional)

Anda dapat menambahkan konten ke presentasi sesuai kebutuhan. Langkah ini bersifat opsional dan bergantung pada konten spesifik yang ingin Anda sertakan.

## Langkah 4: Mengatur Proteksi Penulisan

Untuk membuat presentasi hanya dapat dibaca, kami akan mengatur proteksi penulisan dengan memberikan kata sandi. Berikut cara melakukannya:

```java
// Pengaturan Perlindungan Penulisan Kata Sandi
presentation.getProtectionManager().setWriteProtection("your_password");
```

Mengganti `"your_password"` dengan kata sandi yang ingin Anda atur untuk proteksi penulisan.

## Langkah 5: Menyimpan Presentasi

Terakhir, kita akan menyimpan presentasi ke dalam sebuah berkas dengan proteksi baca-saja:

```java
// Simpan presentasi Anda ke sebuah file
presentation.save(dataDir + "ReadonlyPresentation.pptx", SaveFormat.Pptx);
```

Pastikan Anda mengganti `"ReadonlyPresentation.pptx"` dengan nama berkas yang Anda inginkan.

## Kode Sumber Lengkap Untuk Menyimpan Sebagai Hanya-Baca di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Membuat instance objek Presentasi yang mewakili file PPT
Presentation presentation = new Presentation();
try
{
	//....kerjakan beberapa pekerjaan di sini.....
	// Pengaturan Perlindungan Penulisan Kata Sandi
	presentation.getProtectionManager().setWriteProtection("test");
	// Simpan presentasi Anda ke sebuah file
	presentation.save(dataDir + "WriteProtected_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara menyimpan presentasi PowerPoint sebagai read-only di Java menggunakan pustaka Aspose.Slides for Java. Fitur keamanan ini akan membantu Anda melindungi konten berharga Anda dari modifikasi yang tidak sah.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menghapus proteksi penulisan dari presentasi?

Untuk menghapus proteksi penulisan dari presentasi, Anda dapat menggunakan `removeWriteProtection()` metode yang disediakan oleh Aspose.Slides untuk Java. Berikut contohnya:

```java
// Hapus perlindungan penulisan
presentation.getProtectionManager().removeWriteProtection();
```

### Dapatkah saya mengatur kata sandi yang berbeda untuk perlindungan baca-saja dan tulis?

Ya, Anda dapat mengatur kata sandi yang berbeda untuk perlindungan baca-saja dan perlindungan tulis. Cukup gunakan metode yang sesuai untuk mengatur kata sandi yang diinginkan:

- `setReadProtection(String password)` untuk perlindungan baca-saja.
- `setWriteProtection(String password)` untuk perlindungan penulisan.

### Apakah mungkin untuk melindungi slide tertentu dalam presentasi?

Ya, Anda dapat melindungi slide tertentu dalam presentasi dengan mengatur proteksi penulisan pada slide individual. Gunakan `Slide` objek `getProtectionManager()` metode untuk mengelola perlindungan untuk slide tertentu.

### Apa yang terjadi jika saya lupa kata sandi perlindungan penulisan?

Jika Anda lupa kata sandi proteksi penulisan, tidak ada cara bawaan untuk memulihkannya. Pastikan untuk menyimpan catatan kata sandi Anda di lokasi yang aman untuk menghindari ketidaknyamanan.

### Bisakah saya mengubah kata sandi hanya-baca setelah mengaturnya?

Ya, Anda dapat mengubah kata sandi hanya-baca setelah mengaturnya. Gunakan `setReadProtection(String newPassword)` metode dengan kata sandi baru untuk memperbarui kata sandi perlindungan baca-saja.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}