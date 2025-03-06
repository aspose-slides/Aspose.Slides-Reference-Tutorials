---
title: Sematkan Font dalam HTML menggunakan Aspose.Slides untuk Java
linktitle: Sematkan Font dalam HTML menggunakan Aspose.Slides untuk Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menyematkan font dalam HTML menggunakan Aspose.Slides untuk Java untuk memastikan tipografi yang konsisten di berbagai platform dan perangkat.
weight: 13
url: /id/java/java-powerpoint-font-management/embed-fonts-in-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Perkenalan
Aspose.Slides untuk Java adalah alat yang ampuh untuk pengembang Java yang ingin memanipulasi presentasi PowerPoint secara terprogram. Dalam tutorial ini, kita akan mempelajari proses menyematkan font dalam HTML menggunakan Aspose.Slides untuk Java. Dengan menyematkan font, Anda memastikan bahwa presentasi Anda mempertahankan tampilan yang diinginkan di berbagai platform dan perangkat, meskipun font yang diperlukan tidak diinstal secara lokal.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  Aspose.Slides for Java: Unduh dan instal Aspose.Slides for Java dari[Unduh Halaman](https://releases.aspose.com/slides/java/).
3. Lingkungan Pengembangan Terpadu (IDE): Pilih IDE pilihan Anda untuk pengembangan Java, seperti IntelliJ IDEA atau Eclipse.

## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan untuk mulai menyematkan font dalam HTML menggunakan Aspose.Slides untuk Java.
```java
import com.aspose.slides.*;
```
## Langkah 1: Tentukan Direktori Dokumen dan Output
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
```
 Pastikan Anda menggantinya`"Your Document Directory"` Dan`"Your Output Directory"` dengan masing-masing jalur ke presentasi PowerPoint masukan dan direktori keluaran yang diinginkan.
## Langkah 2: Muat Presentasi
```java
Presentation pres = new Presentation(dataDir + "Presentation.pptx");
```
Langkah ini memuat presentasi PowerPoint ke dalam memori, memungkinkan Anda melakukan berbagai operasi di dalamnya.
## Langkah 3: Kecualikan Font Default
```java
String[] fontNameExcludeList = { "Arial" };
```
Tentukan font yang ingin Anda kecualikan dari penyematan. Dalam contoh ini, kami mengecualikan Arial.
## Langkah 4: Sematkan Font dalam HTML
```java
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
pres.save(outPath + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
```
 Pada langkah ini, kita membuat sebuah instance dari`EmbedAllFontsHtmlController` untuk menyematkan semua font kecuali yang ditentukan dalam daftar pengecualian. Lalu, kita definisikan`HtmlOptions`dan atur pemformat HTML khusus untuk menyematkan font. Terakhir, kami menyimpan presentasi sebagai HTML dengan font yang disematkan.

## Kesimpulan
Dalam tutorial ini, kita menjelajahi cara menyematkan font dalam HTML menggunakan Aspose.Slides untuk Java. Dengan mengikuti langkah-langkah yang diberikan, Anda dapat memastikan bahwa presentasi Anda mempertahankan tipografi yang konsisten di berbagai platform dan perangkat, sehingga meningkatkan pengalaman menonton secara keseluruhan.
## FAQ
### Bisakah saya menyematkan font tertentu dan tidak mengecualikannya?
 Ya, Anda dapat menentukan font yang ingin Anda sematkan dengan memodifikasinya`fontNameExcludeList` susunan yang sesuai.
### Apakah Aspose.Slides untuk Java mendukung penyematan font dalam format lain selain HTML?
Ya, Aspose.Slides mendukung penyematan font dalam berbagai format keluaran, termasuk PDF dan gambar.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides untuk Java?
 Ya, Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan atau bantuan tambahan dengan Aspose.Slides untuk Java?
 Anda dapat mengunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11) untuk dukungan komunitas atau hubungi dukungan Aspose untuk bantuan profesional.
### Bisakah saya membeli lisensi sementara untuk Aspose.Slides untuk Java?
Ya, Anda dapat memperoleh lisensi sementara dari[halaman pembelian](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
