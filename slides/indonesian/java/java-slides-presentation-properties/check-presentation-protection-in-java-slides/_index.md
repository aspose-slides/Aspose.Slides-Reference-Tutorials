---
"description": "Pelajari cara memeriksa proteksi presentasi di slide Java menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah ini menyediakan contoh kode untuk pemeriksaan proteksi penulisan dan pembukaan."
"linktitle": "Periksa Proteksi Presentasi di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Periksa Proteksi Presentasi di Java Slides"
"url": "/id/java/presentation-properties/check-presentation-protection-in-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Periksa Proteksi Presentasi di Java Slides


## Pengantar untuk Memeriksa Perlindungan Presentasi di Java Slides

Dalam tutorial ini, kita akan menjelajahi cara memeriksa proteksi presentasi menggunakan Aspose.Slides untuk Java. Kita akan membahas dua skenario: memeriksa proteksi penulisan dan memeriksa proteksi pembukaan untuk presentasi. Kami akan memberikan contoh kode langkah demi langkah untuk setiap skenario.

## Prasyarat

Sebelum memulai, pastikan Anda telah menyiapkan pustaka Aspose.Slides for Java di proyek Java Anda. Anda dapat mengunduhnya dari situs web Aspose dan menambahkannya ke dependensi proyek Anda.

### Ketergantungan Maven

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

Mengganti `your_version_here` dengan versi Aspose.Slides untuk Java yang Anda gunakan.

## Langkah 1: Periksa Perlindungan Penulisan

Untuk memeriksa apakah presentasi dilindungi dari penulisan oleh kata sandi, Anda dapat menggunakan `IPresentationInfo` antarmuka. Berikut kode untuk melakukannya:

```java
// Jalur untuk presentasi sumber
String pptxFile = "path_to_presentation.pptx";

// Periksa Kata Sandi Perlindungan Penulisan melalui Antarmuka IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

Mengganti `"path_to_presentation.pptx"` dengan jalur sebenarnya ke file presentasi Anda dan `"password_here"` dengan kata sandi proteksi penulisan.

## Langkah 2: Periksa Perlindungan Terbuka

Untuk memeriksa apakah presentasi dilindungi oleh kata sandi untuk dibuka, Anda dapat menggunakan `IPresentationInfo` antarmuka. Berikut kode untuk melakukannya:

```java
// Jalur untuk presentasi sumber
String pptFile = "path_to_presentation.ppt";

// Periksa Perlindungan Presentasi Terbuka melalui Antarmuka IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

Mengganti `"path_to_presentation.ppt"` dengan jalur sebenarnya ke berkas presentasi Anda.

## Source Code Lengkap Untuk Cek Proteksi Presentasi di Java Slides

```java
//Jalur untuk presentasi sumber
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// Periksa Kata Sandi Perlindungan Penulisan melalui Antarmuka IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// Periksa Kata Sandi Perlindungan Penulisan melalui Antarmuka IProtectionManager
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
// Periksa Perlindungan Presentasi Terbuka melalui Antarmuka IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara memeriksa proteksi presentasi di slide Java menggunakan Aspose.Slides untuk Java. Kita membahas dua skenario: memeriksa proteksi penulisan dan memeriksa proteksi pembukaan. Kini Anda dapat mengintegrasikan pemeriksaan ini ke dalam aplikasi Java Anda untuk menangani presentasi yang dilindungi secara efektif.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mendapatkan Aspose.Slides untuk Java?

Anda dapat mengunduh Aspose.Slides untuk Java dari situs web Aspose atau menambahkannya sebagai dependensi Maven di proyek Anda, seperti yang ditunjukkan di bagian prasyarat.

### Dapatkah saya memeriksa proteksi penulisan dan proteksi pembukaan untuk sebuah presentasi?

Ya, Anda dapat memeriksa proteksi penulisan dan proteksi pembukaan untuk presentasi menggunakan contoh kode yang disediakan.

### Apa yang harus saya lakukan jika saya lupa kata sandi perlindungan?

Jika Anda lupa kata sandi perlindungan untuk presentasi, tidak ada cara bawaan untuk memulihkannya. Pastikan untuk menyimpan catatan kata sandi Anda untuk menghindari situasi seperti itu.

### Apakah Aspose.Slides untuk Java kompatibel dengan format file PowerPoint terbaru?

Ya, Aspose.Slides untuk Java mendukung format file PowerPoint terbaru, termasuk file .pptx.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}