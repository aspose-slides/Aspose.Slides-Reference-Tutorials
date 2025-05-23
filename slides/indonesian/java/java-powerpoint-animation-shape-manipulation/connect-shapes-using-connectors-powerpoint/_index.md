---
"description": "Pelajari cara menghubungkan bentuk menggunakan konektor dalam presentasi PowerPoint dengan Aspose.Slides untuk Java. Tutorial langkah demi langkah untuk pemula."
"linktitle": "Hubungkan Bentuk menggunakan Konektor di PowerPoint"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Hubungkan Bentuk menggunakan Konektor di PowerPoint"
"url": "/id/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hubungkan Bentuk menggunakan Konektor di PowerPoint

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menghubungkan bentuk menggunakan konektor dalam presentasi PowerPoint dengan bantuan Aspose.Slides untuk Java. Ikuti petunjuk langkah demi langkah ini untuk menghubungkan bentuk secara efisien dan membuat slide yang menarik secara visual.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang bahasa pemrograman Java.
- Terpasang Java Development Kit (JDK) pada sistem Anda.
- Unduh dan atur Aspose.Slides untuk Java. Jika Anda belum menginstalnya, Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).
- Editor kode seperti Eclipse atau IntelliJ IDEA.

## Paket Impor
Pertama, impor paket yang diperlukan untuk bekerja dengan Aspose.Slides di proyek Java Anda.
```java
import com.aspose.slides.*;

```
## Langkah 1: Buat Kelas Presentasi
Membuat contoh `Presentation` kelas, yang mewakili berkas PPTX yang sedang Anda kerjakan.
```java
// Jalur ke direktori dokumen.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Langkah 2: Akses Koleksi Bentuk
Akses koleksi bentuk untuk slide yang dipilih tempat Anda ingin menambahkan bentuk dan konektor.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Langkah 3: Tambahkan Bentuk
Tambahkan bentuk yang diinginkan ke slide. Dalam contoh ini, kita akan menambahkan elips dan persegi panjang.
```java
// Tambahkan bentuk otomatis Elips
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Tambahkan bentuk otomatis Persegi Panjang
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Langkah 4: Tambahkan Konektor
Tambahkan bentuk konektor ke koleksi bentuk slide.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Langkah 5: Gabungkan Bentuk ke Konektor
Hubungkan bentuk-bentuk tersebut ke konektor.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Langkah 6: Ubah Rute Konektor
Panggil pengalihan rute untuk mengatur jalur terpendek otomatis antar bentuk.
```java
connector.reroute();
```
## Langkah 7: Simpan Presentasi
Simpan presentasi setelah menghubungkan bentuk menggunakan konektor.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Terakhir, jangan lupa untuk membuang objek Presentasi.
```java
if (input != null) input.dispose();
```
Sekarang Anda telah berhasil menghubungkan bentuk menggunakan konektor di PowerPoint menggunakan Aspose.Slides untuk Java.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menghubungkan bentuk menggunakan konektor dalam presentasi PowerPoint dengan Aspose.Slides untuk Java. Dengan mengikuti langkah-langkah sederhana ini, Anda dapat menyempurnakan presentasi Anda dengan diagram dan diagram alur yang menarik secara visual.
## Pertanyaan yang Sering Diajukan
### Dapatkah saya menyesuaikan tampilan konektor di Aspose.Slides untuk Java?
Ya, Anda dapat menyesuaikan berbagai properti konektor seperti warna, gaya garis, dan ketebalan agar sesuai dengan kebutuhan presentasi Anda.
### Apakah Aspose.Slides untuk Java kompatibel dengan semua versi PowerPoint?
Aspose.Slides untuk Java mendukung berbagai format PowerPoint, termasuk PPTX, PPT, dan ODP.
### Bisakah saya menghubungkan lebih dari dua bentuk dengan satu konektor?
Ya, Anda dapat menghubungkan beberapa bentuk menggunakan konektor kompleks yang disediakan oleh Aspose.Slides untuk Java.
### Apakah Aspose.Slides untuk Java menawarkan dukungan untuk menambahkan teks ke bentuk?
Tentu saja, Anda dapat dengan mudah menambahkan teks ke bentuk dan konektor secara terprogram menggunakan Aspose.Slides untuk Java.
### Apakah ada forum komunitas atau saluran dukungan yang tersedia untuk pengguna Aspose.Slides untuk Java?
Ya, Anda dapat menemukan sumber daya yang bermanfaat, mengajukan pertanyaan, dan berinteraksi dengan pengguna lain di forum Aspose.Slides [Di Sini](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}