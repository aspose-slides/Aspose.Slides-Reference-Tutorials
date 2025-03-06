---
title: Periksa Perlindungan Presentasi di Slide Java
linktitle: Periksa Perlindungan Presentasi di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara memeriksa perlindungan presentasi di slide Java menggunakan Aspose.Slides for Java. Panduan langkah demi langkah ini memberikan contoh kode untuk pemeriksaan proteksi tulis dan terbuka.
weight: 15
url: /id/java/presentation-properties/check-presentation-protection-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Pengantar Memeriksa Perlindungan Presentasi di Slide Java

Dalam tutorial ini, kita akan mempelajari cara memeriksa perlindungan presentasi menggunakan Aspose.Slides untuk Java. Kami akan membahas dua skenario: memeriksa proteksi penulisan dan memeriksa proteksi terbuka untuk presentasi. Kami akan memberikan contoh kode langkah demi langkah untuk setiap skenario.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda. Anda dapat mengunduhnya dari situs web Aspose dan menambahkannya ke dependensi proyek Anda.

### Ketergantungan Maven

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

 Mengganti`your_version_here` dengan versi Aspose.Slides untuk Java yang Anda gunakan.

## Langkah 1: Periksa Perlindungan Tulis

 Untuk memeriksa apakah presentasi dilindungi kata sandi, Anda dapat menggunakan`IPresentationInfo` antarmuka. Berikut kode untuk melakukan itu:

```java
// Jalur untuk presentasi sumber
String pptxFile = "path_to_presentation.pptx";

// Periksa Kata Sandi Perlindungan Tulis melalui Antarmuka IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

 Mengganti`"path_to_presentation.pptx"` dengan jalur sebenarnya ke file presentasi Anda dan`"password_here"` dengan kata sandi perlindungan tulis.

## Langkah 2: Periksa Perlindungan Terbuka

 Untuk memeriksa apakah presentasi dilindungi oleh kata sandi untuk pembukaan, Anda dapat menggunakan`IPresentationInfo` antarmuka. Berikut kode untuk melakukan itu:

```java
// Jalur untuk presentasi sumber
String pptFile = "path_to_presentation.ppt";

// Periksa Perlindungan Terbuka Presentasi melalui Antarmuka IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

 Mengganti`"path_to_presentation.ppt"` dengan jalur sebenarnya ke file presentasi Anda.

## Kode Sumber Lengkap Untuk Periksa Perlindungan Presentasi di Slide Java

```java
//Jalur untuk presentasi sumber
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// Periksa Kata Sandi Perlindungan Tulis melalui Antarmuka IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// Periksa Kata Sandi Perlindungan Tulis melalui Antarmuka IProteksiManager
Presentation presentation = new Presentation();
try
{
	boolean isWriteProtected = presentation.getProtectionManager().checkWriteProtection("pass2");
	System.out.println("Is presentation write protected = " + isWriteProtected);
}
finally
{
	if (presentation != null) presentation.dispose();
}
// Periksa Perlindungan Terbuka Presentasi melalui Antarmuka IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara memeriksa proteksi presentasi di slide Java menggunakan Aspose.Slides untuk Java. Kami membahas dua skenario: memeriksa proteksi penulisan dan memeriksa proteksi terbuka. Anda sekarang dapat mengintegrasikan pemeriksaan ini ke dalam aplikasi Java Anda untuk menangani presentasi yang dilindungi secara efektif.

## FAQ

### Bagaimana cara mendapatkan Aspose.Slides untuk Java?

Anda dapat mengunduh Aspose.Slides for Java dari situs web Aspose atau menambahkannya sebagai dependensi Maven di proyek Anda, seperti yang ditunjukkan di bagian prasyarat.

### Bisakah saya memeriksa proteksi penulisan dan proteksi terbuka untuk presentasi?

Ya, Anda dapat memeriksa proteksi penulisan dan proteksi terbuka untuk presentasi menggunakan contoh kode yang disediakan.

### Apa yang harus saya lakukan jika saya lupa kata sandi proteksi?

Jika Anda lupa kata sandi perlindungan untuk presentasi, tidak ada cara bawaan untuk memulihkannya. Pastikan untuk mencatat kata sandi Anda untuk menghindari situasi seperti itu.

### Apakah Aspose.Slides untuk Java kompatibel dengan format file PowerPoint terbaru?

Ya, Aspose.Slides untuk Java mendukung format file PowerPoint terbaru, termasuk file .pptx.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
