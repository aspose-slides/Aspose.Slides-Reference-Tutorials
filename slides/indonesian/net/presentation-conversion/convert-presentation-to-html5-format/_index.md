---
title: Konversi Presentasi ke Format HTML5
linktitle: Konversi Presentasi ke Format HTML5
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara mengonversi presentasi PowerPoint ke format HTML5 menggunakan Aspose.Slides untuk .NET. Konversi yang mudah dan efisien untuk berbagi web.
weight: 22
url: /id/net/presentation-conversion/convert-presentation-to-html5-format/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Konversikan Presentasi ke Format HTML5 menggunakan Aspose.Slides untuk .NET

Dalam panduan ini, kami akan memandu Anda melalui proses mengonversi presentasi PowerPoint (PPT/PPTX) ke format HTML5 menggunakan pustaka Aspose.Slides untuk .NET. Aspose.Slides adalah perpustakaan canggih yang memungkinkan Anda memanipulasi dan mengonversi presentasi PowerPoint dalam berbagai format.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Visual Studio: Anda perlu menginstal Visual Studio di sistem Anda.
2.  Aspose.Slides for .NET: Unduh dan instal perpustakaan Aspose.Slides for .NET dari[Di Sini](https://downloads.aspose.com/slides/net).

## Langkah Konversi

Ikuti langkah-langkah berikut untuk mengonversi presentasi ke format HTML5:

### Buat Proyek Baru

Buka Visual Studio dan buat proyek baru.

### Tambahkan Referensi ke Aspose.Slides

Di proyek Anda, klik kanan pada "Referensi" di Solution Explorer dan pilih "Tambahkan Referensi." Telusuri dan tambahkan Aspose.Slides DLL yang Anda unduh.

### Tulis Kode Konversi

Di editor kode, tulis kode berikut untuk mengonversi presentasi ke format HTML5:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

namespace PresentationToHTML5Converter
{
    class Program
    {
        static void Main(string[] args)
        {
            // Muat presentasi
            using (Presentation presentation = new Presentation("input.pptx"))
            {
                // Tentukan opsi HTML5
                Html5Options options = new Html5Options();

                // Simpan presentasi sebagai HTML5
                presentation.Save("output.html", SaveFormat.Html, options);
            }
        }
    }
}
```

 Mengganti`"input.pptx"` dengan jalur ke presentasi masukan Anda dan`"output.html"` dengan jalur file HTML keluaran yang diinginkan.

## Jalankan Aplikasi

Bangun dan jalankan aplikasi Anda. Ini akan mengkonversi presentasi ke format HTML5 dan menyimpannya sebagai file HTML.

## Kesimpulan

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengonversi presentasi PowerPoint ke format HTML5 menggunakan pustaka Aspose.Slides untuk .NET. Ini memungkinkan Anda berbagi presentasi di web tanpa memerlukan perangkat lunak PowerPoint.

## FAQ

### Bagaimana cara menyesuaikan tampilan keluaran HTML5?

 Anda dapat menyesuaikan tampilan keluaran HTML5 dengan mengatur berbagai pilihan di`Html5Options`kelas. Mengacu kepada[dokumentasi](https://reference.aspose.com/slides/net/aspose.slides.export/html5options) untuk opsi penyesuaian yang tersedia.

### Bisakah saya mengonversi presentasi dengan animasi dan transisi?

Ya, Aspose.Slides untuk .NET mendukung konversi presentasi dengan animasi dan transisi ke format HTML5.

### Apakah ada versi uji coba Aspose.Slides yang tersedia?

 Ya, Anda bisa mendapatkan versi uji coba gratis Aspose.Slides untuk .NET dari[Unduh Halaman](https://releases.aspose.com/slides/net).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
