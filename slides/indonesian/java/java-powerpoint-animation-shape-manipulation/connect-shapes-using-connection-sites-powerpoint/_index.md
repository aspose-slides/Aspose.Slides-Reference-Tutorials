---
"description": "Pelajari cara menghubungkan bentuk di PowerPoint menggunakan Aspose.Slides untuk Java. Otomatiskan presentasi Anda dengan mudah."
"linktitle": "Hubungkan Bentuk menggunakan Situs Koneksi di PowerPoint"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Hubungkan Bentuk menggunakan Situs Koneksi di PowerPoint"
"url": "/id/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hubungkan Bentuk menggunakan Situs Koneksi di PowerPoint

## Perkenalan
Dalam tutorial ini, kita akan menjelajahi cara menghubungkan bentuk menggunakan situs koneksi di PowerPoint menggunakan Aspose.Slides untuk Java. Pustaka canggih ini memungkinkan kita untuk memanipulasi presentasi PowerPoint secara terprogram, membuat tugas seperti menghubungkan bentuk menjadi mudah dan efisien.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal Java di sistem Anda. Anda dapat mengunduh dan menginstalnya dari [situs web](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides untuk Java: Unduh dan instal Aspose.Slides untuk Java dari [halaman unduhan](https://releases.aspose.com/slides/java/).
3. Lingkungan Pengembangan Terpadu (IDE): Pilih IDE untuk pengembangan Java, seperti IntelliJ IDEA, Eclipse, atau NetBeans.

## Paket Impor
Untuk memulai, impor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.slides.*;

```
## Langkah 1: Mengakses Koleksi Bentuk
Akses koleksi bentuk untuk slide yang dipilih:
```java
// Jalur ke direktori dokumen.                    
String dataDir = "Your Document Directory";
// Membuat instance kelas Presentasi yang mewakili file PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Langkah 2: Menambahkan Bentuk Konektor
Tambahkan bentuk konektor ke koleksi bentuk slide:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Langkah 3: Menambahkan BentukOtomatis
Tambahkan bentuk otomatis seperti elips dan persegi panjang:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Langkah 4: Menggabungkan Bentuk ke Konektor
Gabungkan bentuk-bentuk tersebut ke konektor:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Langkah 5: Mengatur Indeks Situs Koneksi
Tetapkan indeks situs koneksi yang diinginkan untuk bentuk:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menghubungkan bentuk menggunakan situs koneksi di PowerPoint menggunakan Aspose.Slides untuk Java. Dengan pengetahuan ini, Anda sekarang dapat mengotomatiskan dan menyesuaikan presentasi PowerPoint Anda dengan mudah.
## Pertanyaan yang Sering Diajukan
### Bisakah Aspose.Slides untuk Java digunakan untuk tugas manipulasi PowerPoint lainnya?
Ya, Aspose.Slides untuk Java menyediakan berbagai fungsi untuk membuat, mengedit, dan mengonversi presentasi PowerPoint.
### Apakah Aspose.Slides untuk Java gratis untuk digunakan?
Aspose.Slides untuk Java adalah pustaka komersial, tetapi Anda dapat menjelajahi fitur-fiturnya dengan uji coba gratis. Kunjungi [Di Sini](https://releases.aspose.com/) untuk memulai.
### Dapatkah saya memperoleh dukungan jika saya menemui masalah saat menggunakan Aspose.Slides untuk Java?
Ya, Anda bisa mendapatkan dukungan dari forum komunitas Aspose [Di Sini](https://forum.aspose.com/c/slides/11).
### Apakah lisensi sementara tersedia untuk Aspose.Slides untuk Java?
Ya, lisensi sementara tersedia untuk tujuan pengujian dan evaluasi. Anda dapat memperolehnya [Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat membeli lisensi Aspose.Slides untuk Java?
Anda dapat membeli lisensi dari situs web Aspose [Di Sini](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}