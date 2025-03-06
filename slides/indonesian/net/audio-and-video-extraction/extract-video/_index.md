---
title: Cara Mengekstrak Video dari Slide Menggunakan Aspose.Slides untuk .NET
linktitle: Ekstrak Video dari Slide
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara mengekstrak video dari slide PowerPoint menggunakan Aspose.Slides untuk .NET. Panduan langkah demi langkah ini menyederhanakan proses untuk Anda.
weight: 14
url: /id/net/audio-and-video-extraction/extract-video/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengekstrak Video dari Slide Menggunakan Aspose.Slides untuk .NET


Aspose.Slides for .NET adalah pustaka canggih yang memungkinkan Anda bekerja dengan presentasi PowerPoint di lingkungan .NET. Salah satu fitur berguna yang disediakannya adalah kemampuan untuk mengekstrak video dari slide. Dalam panduan langkah demi langkah ini, kami akan menunjukkan cara mengekstrak video dari slide PowerPoint menggunakan Aspose.Slides untuk .NET.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Slides untuk .NET: Anda harus menginstal Aspose.Slides untuk .NET. Anda dapat memperolehnya dari[situs web](https://purchase.aspose.com/buy).

- Presentasi PowerPoint: Siapkan presentasi PowerPoint (misalnya, Video.pptx) yang berisi video yang ingin Anda ekstrak.

## Impor Namespace

Anda perlu mengimpor namespace yang diperlukan agar berfungsi dengan Aspose.Slides untuk .NET. Inilah cara Anda melakukannya:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Sekarang, mari kita uraikan proses mengekstraksi video dari slide menjadi beberapa langkah.

## Langkah 1: Atur Direktori Dokumen

```csharp
string dataDir = "Your Document Directory";
```

 Mengganti`"Your Document Directory"` dengan jalur ke direktori tempat presentasi PowerPoint Anda berada.

## Langkah 2: Muat Presentasi

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Kode ini menginisialisasi objek Presentasi, yang mewakili file presentasi PowerPoint Anda.

## Langkah 3: Iterasi Melalui Slide dan Bentuk

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Di sini, kita mengulang setiap slide dalam presentasi dan kemudian mengulangi bentuk-bentuk di slide pertama (modifikasi sesuai kebutuhan).

## Langkah 4: Periksa apakah Bentuknya adalah Bingkai Video

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Langkah ini memeriksa apakah bentuk pada slide adalah bingkai video.

## Langkah 5: Ekstrak Data Video

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Kode ini mengekstrak informasi tentang video, termasuk jenis konten dan data binernya.

## Langkah 6: Simpan Videonya

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Terakhir, langkah ini menyimpan video ke file baru di direktori yang ditentukan.

Setelah Anda menyelesaikan langkah-langkah ini, Anda akan berhasil mengekstrak video dari slide PowerPoint menggunakan Aspose.Slides untuk .NET.

## Kesimpulan

Aspose.Slides untuk .NET menyederhanakan proses bekerja dengan presentasi PowerPoint, memungkinkan Anda melakukan tugas seperti mengekstrak video dari slide dengan mudah. Dengan mengikuti panduan langkah demi langkah ini dan memanfaatkan pustaka Aspose.Slides, Anda dapat menyempurnakan aplikasi .NET Anda dengan fitur PowerPoint yang canggih.

## Pertanyaan yang Sering Diajukan (FAQ)

### Apa itu Aspose.Slide untuk .NET?
Aspose.Slides for .NET adalah pustaka yang memungkinkan aplikasi .NET bekerja dengan presentasi PowerPoint, termasuk membuat, mengedit, dan mengekstraksi konten.

### Di mana saya dapat menemukan dokumentasi Aspose.Slides untuk .NET?
 Anda dapat menemukan dokumentasinya[Di Sini](https://reference.aspose.com/slides/net/).

### Apakah Aspose.Slides untuk .NET tersedia untuk uji coba gratis?
 Ya, Anda bisa mendapatkan versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).

### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Slides untuk .NET?
 Anda dapat meminta lisensi sementara dari[Link ini](https://purchase.aspose.com/temporary-license/).

### Di mana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk .NET?
 Anda dapat menemukan dukungan di[Forum Aspose.Slide](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
