---
title: Menyematkan Panduan Objek OLE dengan Aspose.Slides untuk .NET
linktitle: Mengganti Judul Gambar Bingkai Objek OLE dalam Slide Presentasi
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara menyempurnakan slide presentasi Anda dengan objek OLE dinamis menggunakan Aspose.Slides untuk .NET. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar.
type: docs
weight: 15
url: /id/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---
## Perkenalan
Membuat slide presentasi yang dinamis dan menarik sering kali melibatkan penggabungan berbagai elemen multimedia. Dalam tutorial ini, kita akan mengeksplorasi cara mengganti judul gambar Bingkai Objek OLE (Penautan dan Penyematan Objek) dalam slide presentasi menggunakan pustaka Aspose.Slides untuk .NET yang canggih. Aspose.Slides menyederhanakan proses penanganan objek OLE, menyediakan alat bagi pengembang untuk menyempurnakan presentasi mereka dengan mudah.
## Prasyarat
Sebelum kita mendalami panduan langkah demi langkah, pastikan Anda memiliki prasyarat berikut:
-  Aspose.Slides for .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.Slides for .NET. Anda dapat mengunduhnya dari[Dokumentasi Aspose.Slides .NET](https://reference.aspose.com/slides/net/).
- Contoh Data: Siapkan contoh file Excel (misalnya, "ExcelObject.xlsx") yang ingin Anda sematkan sebagai objek OLE dalam presentasi. Selain itu, miliki file gambar (misalnya, "Image.png") yang akan berfungsi sebagai ikon untuk objek OLE.
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan dengan alat yang diperlukan, seperti Visual Studio atau IDE pilihan lainnya untuk pengembangan .NET.
## Impor Namespace
Di proyek .NET Anda, pastikan untuk mengimpor namespace yang diperlukan untuk bekerja dengan Aspose.Slides:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## Langkah 1: Siapkan Direktori Dokumen
```csharp
string dataDir = "Your Document Directory";
```
Pastikan untuk mengganti "Direktori Dokumen Anda" dengan jalur sebenarnya ke direktori dokumen Anda.
## Langkah 2: Tentukan File Sumber OLE dan Jalur File Ikon
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
Perbarui jalur ini dengan jalur sebenarnya ke contoh file Excel dan file gambar Anda.
## Langkah 3: Buat Instans Presentasi
```csharp
using (Presentation pres = new Presentation())
{
    // Kode untuk langkah selanjutnya akan ditempatkan di sini
}
```
 Inisialisasi instance baru dari`Presentation` kelas.
## Langkah 4: Tambahkan Bingkai Objek OLE
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
Tambahkan bingkai objek OLE ke slide, tentukan posisi dan dimensinya.
## Langkah 5: Tambahkan Objek Gambar
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
Baca file gambar dan tambahkan ke presentasi sebagai objek gambar.
## Langkah 6: Atur Keterangan ke Ikon OLE
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
Atur keterangan yang diinginkan untuk ikon OLE.
## Kesimpulan
Memasukkan objek OLE ke dalam slide presentasi Anda menggunakan Aspose.Slides untuk .NET adalah proses yang mudah. Tutorial ini telah memandu Anda melalui langkah-langkah penting, mulai dari menyiapkan direktori dokumen hingga menambahkan dan menyesuaikan objek OLE. Bereksperimenlah dengan berbagai jenis file dan keterangan untuk meningkatkan daya tarik visual presentasi Anda.
## FAQ
### Bisakah saya menyematkan jenis file lain sebagai objek OLE menggunakan Aspose.Slides?
Ya, Aspose.Slides mendukung penyematan berbagai jenis file, seperti spreadsheet Excel, dokumen Word, dan lainnya.
### Apakah ikon objek OLE dapat disesuaikan?
Sangat. Anda dapat mengganti ikon default dengan gambar apa pun pilihan Anda agar lebih sesuai dengan tema presentasi Anda.
### Apakah Aspose.Slides menyediakan dukungan untuk animasi dengan objek OLE?
Pada versi terbaru, Aspose.Slides berfokus pada penyematan dan tampilan objek OLE, dan tidak secara langsung menangani animasi dalam objek OLE.
### Bisakah saya memanipulasi objek OLE secara terprogram setelah menambahkannya ke slide?
Tentu. Anda memiliki kontrol terprogram penuh atas objek OLE, memungkinkan Anda mengubah properti dan tampilannya sesuai kebutuhan.
### Apakah ada batasan ukuran objek OLE yang disematkan?
Meskipun ada batasan ukuran, mereka umumnya murah hati. Disarankan untuk menguji dengan kasus penggunaan spesifik Anda untuk memastikan kinerja optimal.