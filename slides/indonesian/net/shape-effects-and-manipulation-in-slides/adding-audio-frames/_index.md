---
title: Menambahkan Bingkai Audio ke Slide Presentasi menggunakan Aspose.Slides
linktitle: Menambahkan Bingkai Audio ke Slide Presentasi menggunakan Aspose.Slides
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Sempurnakan presentasi dengan Aspose.Slides untuk .NET! Pelajari cara menambahkan bingkai audio dengan lancar, sehingga melibatkan pemirsa Anda dengan cara yang belum pernah ada sebelumnya.
weight: 14
url: /id/net/shape-effects-and-manipulation-in-slides/adding-audio-frames/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Perkenalan
Dalam dunia presentasi yang dinamis, menggabungkan elemen audio dapat meningkatkan keseluruhan pengalaman audiens Anda secara signifikan. Aspose.Slides for .NET memberdayakan pengembang untuk mengintegrasikan bingkai audio ke dalam slide presentasi dengan lancar, menambahkan lapisan keterlibatan dan interaktivitas baru. Panduan langkah demi langkah ini akan memandu Anda melalui proses menambahkan bingkai audio ke slide presentasi menggunakan Aspose.Slides untuk .NET.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Slides for .NET Library: Unduh dan instal perpustakaan Aspose.Slides for .NET dari[tautan unduhan](https://releases.aspose.com/slides/net/).
2. Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan yang berfungsi untuk .NET, seperti Visual Studio.
3. Direktori Dokumen: Buat direktori tempat Anda menyimpan dokumen, dan catat jalurnya.
## Impor Namespace
Di aplikasi .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Langkah 1: Buat Presentasi dan Slide
```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation())
{
    ISlide sld = pres.Slides[0];
    // Kode Anda untuk pembuatan slide ada di sini
}
```
## Langkah 2: Muat File Audio
```csharp
FileStream fstr = new FileStream(dataDir + "sampleaudio.wav", FileMode.Open, FileAccess.Read);
```
## Langkah 3: Tambahkan Bingkai Audio
```csharp
IAudioFrame audioFrame = sld.Shapes.AddAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## Langkah 4: Konfigurasikan Properti Audio
```csharp
audioFrame.PlayAcrossSlides = true;
audioFrame.RewindAudio = true;
audioFrame.PlayMode = AudioPlayModePreset.Auto;
audioFrame.Volume = AudioVolumeMode.Loud;
```
## Langkah 5: Simpan Presentasi
```csharp
pres.Save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```
Dengan mengikuti langkah-langkah ini, Anda telah berhasil mengintegrasikan bingkai audio ke dalam presentasi Anda menggunakan Aspose.Slides untuk .NET.
## Kesimpulan
Memasukkan elemen audio ke dalam presentasi Anda akan meningkatkan pengalaman pemirsa secara keseluruhan, menjadikan konten Anda lebih dinamis dan menarik. Aspose.Slides untuk .NET menyederhanakan proses ini, memungkinkan pengembang mengintegrasikan bingkai audio secara mulus hanya dengan beberapa baris kode.
## FAQ
### Apakah Aspose.Slides for .NET kompatibel dengan format audio yang berbeda?
Aspose.Slides untuk .NET mendukung berbagai format audio, termasuk WAV, MP3, dan lainnya. Periksa dokumentasi untuk daftar lengkap.
### Dapatkah saya mengontrol pengaturan pemutaran bingkai audio yang ditambahkan?
Ya, Aspose.Slides memberikan fleksibilitas dalam mengonfigurasi pengaturan pemutaran seperti volume, mode putar, dan lainnya.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides untuk .NET?
 Ya, Anda dapat menjelajahi fitur Aspose.Slides untuk .NET dengan[uji coba gratis](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan untuk Aspose.Slides untuk .NET?
 Mengunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11) untuk mencari bantuan dan terlibat dengan masyarakat.
### Bagaimana cara membeli Aspose.Slides untuk .NET?
 Anda dapat membeli perpustakaan dari[Asumsikan toko](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
