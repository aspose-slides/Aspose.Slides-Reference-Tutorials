---
title: Menguasai Animasi PowerPoint dengan Aspose.Slides .NET
linktitle: Ulangi Animasi pada Slide
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Sempurnakan presentasi PowerPoint menggunakan Aspose.Slides untuk .NET. Kontrol animasi dengan mudah, pikat penonton Anda, dan tinggalkan kesan mendalam.
weight: 12
url: /id/net/slide-animation-control/repeat-animation-on-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menguasai Animasi PowerPoint dengan Aspose.Slides .NET

## Perkenalan
Dalam dunia presentasi yang dinamis, kemampuan mengontrol animasi memainkan peran penting dalam menarik dan menarik perhatian audiens. Aspose.Slides untuk .NET memberdayakan pengembang untuk mengambil alih jenis animasi dalam slide, memungkinkan presentasi yang lebih interaktif dan menarik secara visual. Dalam tutorial ini, kita akan menjelajahi cara mengontrol tipe animasi pada slide menggunakan Aspose.Slides untuk .NET, langkah demi langkah.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Slides untuk .NET Library: Unduh dan instal perpustakaan dari[Di Sini](https://releases.aspose.com/slides/net/).
2. Lingkungan Pengembangan .NET: Siapkan lingkungan pengembangan .NET di mesin Anda.
## Impor Namespace
Dalam proyek .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk memanfaatkan fungsionalitas yang disediakan oleh Aspose.Slides:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Langkah 1: Siapkan Proyek
Buat direktori baru untuk proyek Anda dan buat instance kelas Presentasi untuk mewakili file presentasi.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // Kode Anda ada di sini
}
```
## Langkah 2: Akses Urutan Efek
Ambil urutan efek untuk slide pertama menggunakan properti MainSequence.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## Langkah 3: Akses Efek Pertama
Dapatkan efek pertama dari deret utama untuk memanipulasi propertinya.
```csharp
IEffect effect = effectsSequence[0];
```
## Langkah 4: Ubah Pengaturan Pengulangan
Ubah properti Timing/Repeat efek menjadi "Sampai Akhir Slide".
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Langkah 5: Simpan Presentasi
Simpan presentasi yang dimodifikasi untuk memvisualisasikan perubahan.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Ulangi langkah-langkah ini untuk efek tambahan atau sesuaikan sesuai dengan kebutuhan presentasi Anda.
## Kesimpulan
Memasukkan animasi dinamis dalam presentasi PowerPoint Anda tidak pernah semudah ini dengan Aspose.Slides untuk .NET. Panduan langkah demi langkah ini membekali Anda dengan pengetahuan untuk mengontrol jenis animasi, memastikan slide Anda meninggalkan kesan mendalam pada audiens Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menerapkan animasi ini ke objek tertentu dalam slide?
Ya, Anda dapat menargetkan objek tertentu dengan mengakses efek individualnya dalam urutan.
### Apakah Aspose.Slides kompatibel dengan versi PowerPoint terbaru?
Aspose.Slides menyediakan dukungan untuk berbagai versi PowerPoint, memastikan kompatibilitas dengan versi lama dan baru.
### Di mana saya dapat menemukan contoh dan sumber tambahan?
 Jelajahi[dokumentasi](https://reference.aspose.com/slides/net/) untuk contoh lengkap dan penjelasan detail.
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Slides?
 Mengunjungi[Di Sini](https://purchase.aspose.com/temporary-license/) untuk informasi tentang cara memperoleh izin sementara.
### Butuh bantuan atau memiliki pertanyaan lebih lanjut?
 Terlibat dengan komunitas Aspose.Slides di[forum dukungan](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
