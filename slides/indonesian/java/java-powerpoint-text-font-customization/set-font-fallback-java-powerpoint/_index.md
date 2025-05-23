---
"description": "Pelajari cara mengatur font fallback di Java PowerPoint menggunakan Aspose.Slides untuk Java untuk memastikan tampilan teks yang konsisten."
"linktitle": "Mengatur Font Fallback di Java PowerPoint"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Font Fallback di Java PowerPoint"
"url": "/id/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Font Fallback di Java PowerPoint

## Perkenalan
Dalam tutorial ini, kita akan mempelajari seluk-beluk pengaturan font fallback dalam presentasi PowerPoint Java menggunakan Aspose.Slides untuk Java. Font fallback sangat penting untuk memastikan bahwa teks dalam presentasi Anda ditampilkan dengan benar di berbagai perangkat dan sistem operasi, bahkan ketika font yang diperlukan tidak tersedia.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
- Java Development Kit (JDK) terinstal di sistem Anda.
- Aspose.Slides untuk pustaka Java. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).
- Pemahaman dasar tentang bahasa pemrograman Java.
- Lingkungan Pengembangan Terpadu (IDE) seperti IntelliJ IDEA atau Eclipse.

## Paket Impor
Pertama, sertakan paket Aspose.Slides for Java yang diperlukan di kelas Java Anda:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## Langkah 1: Inisialisasi Aturan Penggantian Font
Untuk menyetel font fallback, Anda perlu menentukan aturan yang menentukan rentang Unicode dan font fallback yang sesuai. Berikut cara menginisialisasi aturan ini:
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## Langkah 2: Terapkan Aturan Penggantian Font
Berikutnya, Anda menerapkan aturan ini ke presentasi atau slide tempat font fallback perlu ditetapkan. Berikut adalah contoh penerapan aturan ini ke slide dalam presentasi PowerPoint:
```java
// Mengasumsikan slide adalah objek Slide Anda
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## Kesimpulan
Menetapkan fallback font dalam presentasi PowerPoint Java menggunakan Aspose.Slides untuk Java sangat penting untuk memastikan tampilan teks yang konsisten di berbagai lingkungan. Dengan menetapkan aturan fallback seperti yang ditunjukkan dalam tutorial ini, Anda dapat menangani situasi saat font tertentu tidak tersedia, sehingga integritas presentasi Anda tetap terjaga.

## Pertanyaan yang Sering Diajukan
### Apa saja fallback font dalam presentasi PowerPoint?
Penggantian font memastikan teks ditampilkan dengan benar dengan mengganti font yang tersedia dengan font yang tidak diinstal.
### Bagaimana cara mengunduh Aspose.Slides untuk Java?
Anda dapat mengunduh Aspose.Slides untuk Java dari [Di Sini](https://releases.aspose.com/slides/java/).
### Apakah Aspose.Slides untuk Java kompatibel dengan semua IDE Java?
Ya, Aspose.Slides untuk Java kompatibel dengan IDE Java populer seperti IntelliJ IDEA dan Eclipse.
### Bisakah saya mendapatkan lisensi sementara untuk produk Aspose?
Ya, lisensi sementara untuk produk Aspose dapat diperoleh dari [Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat menemukan dukungan untuk Aspose.Slides untuk Java?
Untuk dukungan terkait Aspose.Slides untuk Java, kunjungi [Forum Aspose](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}