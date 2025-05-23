---
"description": "Pelajari cara mengaktifkan properti Read-Only Recommended dalam presentasi PowerPoint Java menggunakan Aspose.Slides untuk Java. Ikuti panduan langkah demi langkah kami dengan contoh kode sumber untuk meningkatkan keamanan presentasi."
"linktitle": "Properti Rekomendasi Hanya Baca di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Properti Rekomendasi Hanya Baca di Java Slides"
"url": "/id/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Properti Rekomendasi Hanya Baca di Java Slides


## Pengantar untuk Mengaktifkan Properti Rekomendasi Hanya-Baca di Slide Java

Dalam tutorial ini, kita akan menjelajahi cara mengaktifkan properti Read-Only Recommended untuk presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Properti Read-Only Recommended dapat berguna saat Anda ingin mendorong pengguna untuk melihat presentasi tanpa membuat perubahan apa pun. Properti ini menyarankan agar presentasi dibuka dalam mode read-only. Kami akan memberi Anda panduan langkah demi langkah beserta kode sumber Java untuk mencapainya.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menyiapkan pustaka Aspose.Slides for Java di proyek Anda. Anda dapat mengunduhnya dari [Situs web Aspose.Slides untuk Java](https://products.aspose.com/slides/java/).

## Langkah 1: Buat Presentasi PowerPoint Baru

Kita akan mulai dengan membuat presentasi PowerPoint baru menggunakan Aspose.Slides for Java. Jika Anda sudah memiliki presentasi, Anda dapat melewati langkah ini.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Dalam kode di atas, kami telah menentukan jalur untuk file PowerPoint keluaran dan membuat objek presentasi baru.

## Langkah 2: Aktifkan Properti Rekomendasi Hanya Baca

Sekarang, mari aktifkan properti Read-Only Recommended untuk presentasi.

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

Dalam potongan kode ini, kami menggunakan `getProtectionManager().setReadOnlyRecommended(true)` metode untuk menyetel properti Read-Only Recommended ke `true`Ini memastikan bahwa saat seseorang membuka presentasi, mereka akan diminta untuk membukanya dalam mode baca-saja.

## Langkah 3: Simpan Presentasi

Terakhir, kami menyimpan presentasi dengan properti Read-Only Recommended diaktifkan.

## Kode Sumber Lengkap untuk Properti Rekomendasi Hanya-Baca di Java Slides

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

Dalam tutorial ini, Anda telah mempelajari cara mengaktifkan properti Read-Only Recommended untuk presentasi PowerPoint menggunakan Aspose.Slides for Java. Fitur ini dapat membantu saat Anda ingin membatasi penyuntingan dan mendorong pemirsa untuk menggunakan presentasi dalam mode read-only. Anda dapat lebih meningkatkan keamanan dengan menetapkan kata sandi untuk presentasi tersebut.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menonaktifkan properti Read-Only Recommended?

Untuk menonaktifkan properti Read-Only Recommended, cukup gunakan kode berikut:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Dapatkah saya menetapkan kata sandi untuk presentasi Rekomendasi Hanya-Baca?

Ya, Anda dapat mengatur kata sandi untuk presentasi Read-Only Recommended menggunakan Aspose.Slides untuk Java. Anda dapat menggunakan `setPassword` metode untuk menetapkan kata sandi untuk presentasi. Jika kata sandi ditetapkan, pengguna harus memasukkannya untuk membuka presentasi, bahkan dalam mode baca-saja.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

Ingat untuk mengganti `"YourPassword"` dengan kata sandi yang Anda inginkan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}