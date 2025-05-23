---
"description": "Sempurnakan presentasi PowerPoint menggunakan Aspose.Slides for .NET. Kontrol animasi dengan mudah, buat audiens Anda terpikat, dan tinggalkan kesan yang mendalam."
"linktitle": "Ulangi Animasi pada Slide"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Menguasai Animasi PowerPoint dengan Aspose.Slides .NET"
"url": "/id/net/slide-animation-control/repeat-animation-on-slide/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menguasai Animasi PowerPoint dengan Aspose.Slides .NET

## Perkenalan
Dalam dunia presentasi yang dinamis, kemampuan untuk mengendalikan animasi memegang peranan penting dalam menarik dan menangkap perhatian audiens. Aspose.Slides for .NET memberdayakan pengembang untuk mengendalikan jenis animasi dalam slide, sehingga menghasilkan presentasi yang lebih interaktif dan menarik secara visual. Dalam tutorial ini, kita akan mempelajari cara mengendalikan jenis animasi pada slide menggunakan Aspose.Slides for .NET, langkah demi langkah.
## Prasyarat
Sebelum kita masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1. Aspose.Slides untuk Pustaka .NET: Unduh dan instal pustaka dari [Di Sini](https://releases.aspose.com/slides/net/).
2. Lingkungan Pengembangan .NET: Siapkan lingkungan pengembangan .NET di komputer Anda.
## Mengimpor Ruang Nama
Dalam proyek .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk memanfaatkan fungsionalitas yang disediakan oleh Aspose.Slides:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Langkah 1: Siapkan Proyek
Buat direktori baru untuk proyek Anda dan buat kelas Presentasi untuk mewakili berkas presentasi.
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
Dapatkan efek pertama dari rangkaian utama untuk memanipulasi propertinya.
```csharp
IEffect effect = effectsSequence[0];
```
## Langkah 4: Ubah Pengaturan Pengulangan
Ubah properti Timing/Repeat efek menjadi "Sampai Akhir Slide."
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Langkah 5: Simpan Presentasi
Simpan presentasi yang dimodifikasi untuk memvisualisasikan perubahannya.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Ulangi langkah-langkah ini untuk efek tambahan atau sesuaikan menurut kebutuhan presentasi Anda.
## Kesimpulan
Memasukkan animasi dinamis ke dalam presentasi PowerPoint Anda tidak pernah semudah ini dengan Aspose.Slides for .NET. Panduan langkah demi langkah ini membekali Anda dengan pengetahuan untuk mengendalikan jenis animasi, memastikan slide Anda meninggalkan kesan abadi pada audiens Anda.
## Pertanyaan yang Sering Diajukan
### Dapatkah saya menerapkan animasi ini ke objek tertentu dalam slide?
Ya, Anda dapat menargetkan objek tertentu dengan mengakses efek individualnya dalam urutan tersebut.
### Apakah Aspose.Slides kompatibel dengan versi PowerPoint terbaru?
Aspose.Slides menyediakan dukungan untuk berbagai versi PowerPoint, memastikan kompatibilitas dengan versi lama dan baru.
### Di mana saya dapat menemukan contoh dan sumber daya tambahan?
Jelajahi [dokumentasi](https://reference.aspose.com/slides/net/) untuk contoh komprehensif dan penjelasan terperinci.
### Bagaimana cara memperoleh lisensi sementara untuk Aspose.Slides?
Mengunjungi [Di Sini](https://purchase.aspose.com/temporary-license/) untuk informasi tentang cara mendapatkan lisensi sementara.
### Butuh bantuan atau punya pertanyaan lebih lanjut?
Berinteraksi dengan komunitas Aspose.Slides di [forum dukungan](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}