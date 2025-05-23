---
"date": "2025-04-15"
"description": "Pelajari cara mengambil tipe sumber data bagan secara efisien dalam presentasi PowerPoint menggunakan Aspose.Slides for .NET. Otomatiskan dan integrasikan presentasi dengan mudah."
"title": "Cara Mendapatkan Jenis Sumber Data Bagan Menggunakan Aspose.Slides untuk .NET - Bagan & Grafik"
"url": "/id/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Mendapatkan Jenis Sumber Data Bagan Menggunakan Aspose.Slides untuk .NET

## Perkenalan

Apakah Anda kesulitan mengelola sumber data dalam bagan presentasi PowerPoint secara terprogram? Banyak pengembang menghadapi tantangan saat mencoba mengekstrak dan memanipulasi data bagan dalam file Microsoft Office menggunakan C#. Dalam tutorial ini, kami akan memandu Anda mengambil jenis sumber data bagan dalam presentasi PowerPoint dengan Aspose.Slides for .NET. Solusi ini ideal jika Anda perlu mengotomatiskan presentasi atau mengintegrasikannya ke dalam aplikasi Anda.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan dan menggunakan Aspose.Slides untuk .NET
- Mengambil tipe sumber data bagan di slide PowerPoint
- Menangani jalur buku kerja eksternal bila berlaku
- Menyimpan perubahan kembali ke presentasi

Sebelum kita mulai, mari kita bahas beberapa prasyarat.

## Prasyarat

Untuk mengikuti tutorial ini secara efektif, Anda memerlukan:
1. **Aspose.Slides untuk Pustaka .NET:** Pastikan Anda telah menginstal versi terbaru.
2. **Lingkungan Pengembangan:** Pengaturan Visual Studio yang berfungsi atau IDE pilihan apa pun yang mendukung pengembangan C#.
3. **Pengetahuan Dasar:** Keakraban dengan C#, konsep pemrograman berorientasi objek, dan penanganan jalur file di .NET.

## Menyiapkan Aspose.Slides untuk .NET

Pertama, Anda perlu menginstal pustaka Aspose.Slides. Berikut caranya:

**Menggunakan .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Menggunakan Manajer Paket:**
```powershell
Install-Package Aspose.Slides
```

**Melalui UI Pengelola Paket NuGet:**
Cari "Aspose.Slides" di NuGet Package Manager dan instal.

### Akuisisi Lisensi
- **Uji Coba Gratis:** Mulailah dengan uji coba gratis untuk menjelajahi fungsionalitasnya.
- **Lisensi Sementara:** Dapatkan lisensi sementara untuk akses lebih lanjut tanpa batasan.
- **Pembelian:** Pertimbangkan untuk membeli jika Anda merasa Aspose.Slides memenuhi kebutuhan Anda.

Setelah terinstal, inisialisasi proyek Anda dengan menyertakan namespace yang diperlukan:
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## Panduan Implementasi

Kami akan menguraikan fitur ini menjadi beberapa langkah agar lebih jelas. Mari kita bahas cara mengambil jenis sumber data diagram.

### Langkah 1: Muat Presentasi Anda

Pertama, muat presentasi PowerPoint yang berisi bagan Anda:
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Atur ke jalur direktori Anda

using (Presentation pres = new Presentation(dataDir + "/pres.pptx"))
{
    // Lanjutkan dengan langkah selanjutnya...
}
```

### Langkah 2: Mengakses Slide dan Bagannya

Akses slide pertama dan bagan di dalamnya:
```csharp
// Dapatkan slide pertama dari presentasi
ISlide slide = pres.Slides[0];

// Pastikan bentuknya memang bagan
IChart chart = (IChart)slide.Shapes[0];
```

### Langkah 3: Ambil Jenis Sumber Data

Sekarang, mari kita ambil tipe sumber datanya:
```csharp
// Dapatkan tipe sumber data bagan
ChartDataSourceType sourceType = chart.ChartData.DataSourceType;
```

### Langkah 4: Menangani Jalur Buku Kerja Eksternal

Jika bagan Anda menggunakan buku kerja eksternal, Anda dapat mengambil jalurnya seperti ini:
```csharp
if (sourceType == ChartDataSourceType.ExternalWorkbook)
{
    string path = chart.ChartData.ExternalWorkbookPath;
}
```

### Langkah 5: Simpan Presentasi Anda

Terakhir, simpan presentasi setelah melakukan modifikasi apa pun:
```csharp
pres.Save(dataDir + "/Result.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}