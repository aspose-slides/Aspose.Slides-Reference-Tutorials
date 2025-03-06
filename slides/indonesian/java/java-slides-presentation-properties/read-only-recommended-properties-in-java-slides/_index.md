---
title: Properti yang Direkomendasikan Hanya Baca di Slide Java
linktitle: Properti yang Direkomendasikan Hanya Baca di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengaktifkan properti Baca-Saja yang Direkomendasikan dalam presentasi Java PowerPoint menggunakan Aspose.Slides untuk Java. Ikuti panduan langkah demi langkah kami dengan contoh kode sumber untuk meningkatkan keamanan presentasi.
type: docs
weight: 17
url: /id/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

## Pengantar Mengaktifkan Properti yang Direkomendasikan Hanya Baca di Slide Java

Dalam tutorial ini, kita akan mempelajari cara mengaktifkan properti Read-Only Direkomendasikan untuk presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Properti Baca-Saja Direkomendasikan dapat berguna ketika Anda ingin mendorong pengguna untuk melihat presentasi tanpa melakukan perubahan apa pun. Properti ini menyarankan agar presentasi dibuka dalam mode baca-saja. Kami akan memberi Anda panduan langkah demi langkah bersama dengan kode sumber Java untuk mencapai hal ini.

## Prasyarat

 Sebelum kita mulai, pastikan Anda telah menyiapkan pustaka Aspose.Slides untuk Java di proyek Anda. Anda dapat mengunduhnya dari[Aspose.Slide untuk situs web Java](https://products.aspose.com/slides/java/).

## Langkah 1: Buat Presentasi PowerPoint Baru

Kita akan mulai dengan membuat presentasi PowerPoint baru menggunakan Aspose.Slides for Java. Jika Anda sudah memiliki presentasi, Anda dapat melewati langkah ini.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Dalam kode di atas, kita telah menentukan jalur untuk file output PowerPoint dan membuat objek presentasi baru.

## Langkah 2: Aktifkan Properti Rekomendasi Hanya Baca

Sekarang, mari aktifkan properti Read-Only Direkomendasikan untuk presentasi.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

 Dalam cuplikan kode ini, kami menggunakan`getProtectionManager().setReadOnlyRecommended(true)` metode untuk mengatur properti Read-Only Direkomendasikan ke`true`. Hal ini memastikan bahwa ketika seseorang membuka presentasi, mereka akan diminta untuk membukanya dalam mode baca-saja.

## Langkah 3: Simpan Presentasi

Terakhir, kami menyimpan presentasi dengan properti Read-Only Direkomendasikan diaktifkan.

## Kode Sumber Lengkap Untuk Properti Rekomendasi Read-Only di Java Slides

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengaktifkan properti Read-Only Direkomendasikan untuk presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Fitur ini dapat berguna ketika Anda ingin membatasi pengeditan dan mendorong pemirsa untuk menggunakan presentasi dalam mode baca-saja. Anda dapat lebih meningkatkan keamanan dengan menetapkan kata sandi untuk presentasi.

## FAQ

### Bagaimana cara menonaktifkan properti Read-Only Direkomendasikan?

Untuk menonaktifkan properti Read-Only Direkomendasikan, cukup gunakan kode berikut:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Bisakah saya menetapkan kata sandi untuk presentasi Rekomendasi Hanya Baca?

Ya, Anda dapat mengatur kata sandi untuk presentasi Rekomendasi Read-Only menggunakan Aspose.Slides untuk Java. Anda dapat menggunakan`setPassword` metode untuk mengatur kata sandi untuk presentasi. Jika kata sandi disetel, pengguna harus memasukkannya untuk membuka presentasi, bahkan dalam mode baca-saja.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 Ingatlah untuk mengganti`"YourPassword"` dengan kata sandi yang Anda inginkan.