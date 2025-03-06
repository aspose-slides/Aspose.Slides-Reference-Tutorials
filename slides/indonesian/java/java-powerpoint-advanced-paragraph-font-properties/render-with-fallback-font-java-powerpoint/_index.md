---
title: Render dengan Font Fallback di Java PowerPoint
linktitle: Render dengan Font Fallback di Java PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara merender teks dengan font fallback dalam presentasi Java PowerPoint menggunakan Aspose.Slides. Ikuti panduan langkah demi langkah ini untuk penerapan yang lancar.
weight: 13
url: /id/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Membuat dan memanipulasi presentasi PowerPoint di Java dapat menjadi tantangan, namun dengan Aspose.Slides, Anda dapat melakukannya secara efisien. Salah satu fitur penting adalah kemampuan untuk merender teks dengan font fallback. Artikel ini memberikan panduan langkah demi langkah terperinci tentang cara menerapkan font fallback di slide PowerPoint Anda menggunakan Aspose.Slides untuk Java.
## Prasyarat
Sebelum mendalami penerapannya, pastikan Anda memiliki semua yang Anda perlukan:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  Aspose.Slides untuk Java: Anda dapat mendownloadnya dari[Aspose.Slide untuk halaman Unduhan Java](https://releases.aspose.com/slides/java/).
3. Lingkungan Pengembangan Terintegrasi (IDE): IDE seperti IntelliJ IDEA atau Eclipse akan membuat proses pengembangan Anda lebih lancar.
4. Dependensi: Sertakan Aspose.Slides dalam dependensi proyek Anda.
## Paket Impor
Pertama, kita perlu mengimpor paket yang diperlukan dalam program Java kita.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Mari kita bagi prosesnya menjadi langkah-langkah yang dapat dikelola.
## Langkah 1: Siapkan Proyek Anda
 Sebelum menulis kode apa pun, pastikan proyek Anda sudah diatur dengan benar. Ini termasuk menambahkan perpustakaan Aspose.Slides ke proyek Anda. Anda dapat melakukan ini dengan mengunduh perpustakaan dari[Aspose.Slide untuk Java](https://releases.aspose.com/slides/java/) dan menambahkannya ke jalur build Anda.
## Langkah 2: Inisialisasi Aturan Penggantian Font
 Anda perlu membuat sebuah instance dari`IFontFallBackRulesCollection` kelas dan menambahkan aturan ke dalamnya. Aturan ini menentukan penggantian font untuk rentang Unicode tertentu.
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance baru dari kumpulan aturan
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Buat sejumlah aturan
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## Langkah 3: Ubah Aturan Penggantian
Pada langkah ini, kita akan mengubah aturan fallback dengan menghapus font fallback yang ada dan memperbarui aturan untuk rentang Unicode tertentu.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // Mencoba menghapus font FallBack "Tahoma" dari aturan yang dimuat
    fallBackRule.remove("Tahoma");
    // Perbarui aturan untuk rentang yang ditentukan
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//Hapus semua aturan yang ada dari daftar
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## Langkah 4: Muat Presentasi
Muat presentasi PowerPoint yang ingin Anda modifikasi.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## Langkah 5: Tetapkan Aturan Penggantian ke Presentasi
Tetapkan aturan fallback yang telah disiapkan ke pengelola font presentasi.
```java
try {
    // Menetapkan daftar aturan yang telah disiapkan untuk penggunaan
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Merender gambar mini menggunakan kumpulan aturan yang diinisialisasi dan menyimpannya ke PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Langkah 6: Simpan dan Uji
Terakhir, simpan pekerjaan Anda dan uji penerapannya untuk memastikan semuanya berjalan sesuai harapan. Jika Anda mengalami masalah apa pun, periksa kembali pengaturan Anda dan pastikan semua dependensi ditambahkan dengan benar.
## Kesimpulan
Dengan mengikuti panduan ini, Anda dapat merender teks dengan font fallback secara efisien di presentasi PowerPoint Anda menggunakan Aspose.Slides untuk Java. Proses ini memastikan bahwa presentasi Anda mempertahankan format yang konsisten, meskipun font utama tidak tersedia. Selamat membuat kode!
## FAQ
### Apa itu Aspose.Slide untuk Java?
Aspose.Slides for Java adalah pustaka yang memungkinkan pengembang membuat, memodifikasi, dan merender presentasi PowerPoint dalam aplikasi Java.
### Bagaimana cara menambahkan Aspose.Slides ke proyek saya?
 Anda dapat mengunduh perpustakaan dari[Halaman unduh Aspose.Slide](https://releases.aspose.com/slides/java/) dan menambahkannya ke jalur pembangunan proyek Anda.
### Apa itu font cadangan?
Font cadangan adalah font alternatif yang digunakan ketika font tertentu tidak tersedia atau tidak mendukung karakter tertentu.
### Bisakah saya menggunakan beberapa aturan cadangan?
Ya, Anda dapat menambahkan beberapa aturan cadangan untuk menangani rentang dan font Unicode yang berbeda.
### Di mana saya bisa mendapatkan dukungan untuk Aspose.Slides?
 Anda bisa mendapatkan dukungan dari[Forum dukungan Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
