---
title: Tambahkan Properti Dokumen Kustom di Slide Java
linktitle: Tambahkan Properti Dokumen Kustom di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menyempurnakan presentasi PowerPoint dengan properti dokumen khusus di Java Slides. Panduan langkah demi langkah dengan contoh kode menggunakan Aspose.Slides untuk Java.
weight: 13
url: /id/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengantar Menambahkan Properti Dokumen Kustom di Slide Java

Dalam tutorial ini, kami akan memandu Anda melalui proses menambahkan properti dokumen kustom ke presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Properti dokumen kustom memungkinkan Anda menyimpan informasi tambahan tentang presentasi untuk referensi atau kategorisasi.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda.

## Langkah 1: Impor Paket yang Diperlukan

```java
import com.aspose.slides.*;
```

## Langkah 2: Buat Presentasi Baru

Pertama, Anda perlu membuat objek presentasi baru. Anda dapat melakukannya sebagai berikut:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";

// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
```

## Langkah 3: Mendapatkan Properti Dokumen

Selanjutnya, Anda akan mengambil properti dokumen presentasi. Properti ini mencakup properti bawaan seperti judul, penulis, dan properti khusus yang dapat Anda tambahkan.

```java
// Mendapatkan Properti Dokumen
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## Langkah 4: Menambahkan Properti Kustom

Sekarang, mari tambahkan properti khusus ke presentasi. Properti khusus terdiri dari nama dan nilai. Anda dapat menggunakannya untuk menyimpan informasi apa pun yang Anda inginkan.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## Langkah 5: Mendapatkan Nama Properti pada Indeks Tertentu

Anda juga dapat mengambil nama properti khusus pada indeks tertentu. Ini bisa berguna jika Anda perlu bekerja dengan properti tertentu.

```java
// Mendapatkan nama properti pada indeks tertentu
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## Langkah 6: Menghapus Properti yang Dipilih

Jika Anda ingin menghapus properti khusus, Anda dapat melakukannya dengan menentukan namanya. Di sini, kami menghapus properti yang kami peroleh pada Langkah 5.

```java
// Menghapus properti yang dipilih
documentProperties.removeCustomProperty(getPropertyName);
```

## Langkah 7: Menyimpan Presentasi

Terakhir, simpan presentasi dengan properti khusus yang ditambahkan dan dihapus ke file.

```java
// Menyimpan presentasi
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Kode Sumber Lengkap Untuk Menambahkan Properti Dokumen Kustom di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi
Presentation presentation = new Presentation();
// Mendapatkan Properti Dokumen
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// Menambahkan properti Kustom
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// Mendapatkan nama properti pada indeks tertentu
String getPropertyName = documentProperties.getCustomPropertyName(2);
// Menghapus properti yang dipilih
documentProperties.removeCustomProperty(getPropertyName);
// Menyimpan presentasi
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Anda telah mempelajari cara menambahkan properti dokumen kustom ke presentasi PowerPoint di Java menggunakan Aspose.Slides. Properti khusus dapat berguna untuk menyimpan informasi tambahan terkait presentasi Anda. Anda dapat memperluas pengetahuan ini untuk menyertakan lebih banyak properti khusus sesuai kebutuhan untuk kasus penggunaan spesifik Anda.

## FAQ

### Bagaimana cara mengambil nilai properti khusus?

 Untuk mengambil nilai properti khusus, Anda dapat menggunakan`get_Item` metode pada`documentProperties` obyek. Misalnya:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### Bisakah saya menambahkan properti khusus dari tipe data berbeda?

Ya, Anda bisa menambahkan properti kustom dari berbagai tipe data, termasuk angka, string, tanggal, dan lainnya, seperti yang ditunjukkan dalam contoh. Aspose.Slides untuk Java menangani tipe data yang berbeda dengan mulus.

### Apakah ada batasan jumlah properti khusus yang dapat saya tambahkan?

Tidak ada batasan ketat mengenai jumlah properti khusus yang dapat Anda tambahkan. Namun, perlu diingat bahwa menambahkan properti dalam jumlah berlebihan dapat memengaruhi performa dan ukuran file presentasi Anda.

### Bagaimana cara membuat daftar semua properti khusus dalam presentasi?

Anda dapat menelusuri semua properti khusus untuk mencantumkannya. Berikut ini contoh cara melakukannya:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

Kode ini akan menampilkan nama dan nilai semua properti kustom dalam presentasi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
