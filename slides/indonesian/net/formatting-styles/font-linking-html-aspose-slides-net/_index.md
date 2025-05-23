---
"date": "2025-04-15"
"description": "Pelajari cara memastikan rendering font yang konsisten saat mengubah presentasi menjadi HTML menggunakan Aspose.Slides untuk .NET dengan menyematkan font secara langsung."
"title": "Cara Menghubungkan Font dalam HTML Menggunakan Aspose.Slides untuk .NET&#58; Panduan Langkah demi Langkah"
"url": "/id/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menghubungkan Font dalam HTML Menggunakan Aspose.Slides untuk .NET

## Perkenalan

Mengubah presentasi menjadi HTML sambil mempertahankan konsistensi tampilan font di berbagai platform dapat menjadi tantangan. **Aspose.Slides untuk .NET** menawarkan solusi yang mudah dengan memungkinkan Anda menautkan semua font yang digunakan dalam presentasi langsung dalam output HTML melalui berkas font yang tertanam.

Dalam tutorial ini, kita akan menjelajahi cara menerapkan penautan font menggunakan Aspose.Slides untuk .NET dan memastikan konsistensi desain di berbagai platform. 

**Apa yang Akan Anda Pelajari:**
- Menyiapkan lingkungan Anda dengan Aspose.Slides untuk .NET
- Menghubungkan font dalam konversi HTML
- Menulis pengontrol khusus untuk penyematan font
- Aplikasi praktis dan pertimbangan kinerja

Mari kita bahas langkah-langkah yang diperlukan untuk mencapainya.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

### Pustaka dan Ketergantungan yang Diperlukan
- **Aspose.Slides untuk .NET** pustaka: Komponen inti untuk implementasi kami.

### Persyaratan Pengaturan Lingkungan
- Lingkungan pengembangan dengan .NET Framework atau .NET Core terpasang.

### Prasyarat Pengetahuan
- Pemahaman dasar tentang pemrograman C#.
- Keakraban dengan HTML dan CSS, khususnya `@font-face` aturan.

## Menyiapkan Aspose.Slides untuk .NET

Untuk menggunakan Aspose.Slides di proyek .NET Anda, Anda perlu menginstal pustaka tersebut. Berikut ini beberapa metode:

### Menggunakan .NET CLI
```bash
dotnet add package Aspose.Slides
```

### Menggunakan Konsol Pengelola Paket
```powershell
Install-Package Aspose.Slides
```

### Melalui UI Pengelola Paket NuGet
- Buka proyek Anda di Visual Studio.
- Navigasi ke "NuGet Package Manager."
- Cari "Aspose.Slides" dan instal versi terbaru.

### Langkah-langkah Memperoleh Lisensi
Anda dapat memperoleh lisensi uji coba gratis untuk menguji semua fitur tanpa batasan dengan mengikuti langkah-langkah berikut:
1. **Uji Coba Gratis**: Unduh lisensi sementara [Di Sini](https://releases.aspose.com/slides/net/).
2. **Lisensi Sementara**: Ajukan permohonan akses tambahan [Di Sini](https://purchase.aspose.com/temporary-license/).
3. **Pembelian**:Untuk fungsionalitas penuh, beli lisensi [Di Sini](https://purchase.aspose.com/buy).

### Inisialisasi dan Pengaturan Dasar
```csharp
// Buat instance dari kelas Lisensi
easpose.slides.License license = new aspose.slides.License();

// Terapkan lisensi dari jalur file
license.SetLicense("Aspose.Slides.lic");
```

## Panduan Implementasi

Sekarang, mari kita terapkan penautan font dalam konversi HTML menggunakan **Aspose.Slides untuk .NET**.

### Gambaran Umum Fitur: Menghubungkan Font dalam Konversi HTML
Fitur ini memastikan bahwa semua font yang digunakan dalam presentasi ditautkan langsung dalam berkas HTML yang dihasilkan dengan menyematkan berkas font tersebut. Metode ini memberikan solusi yang kuat untuk menjaga konsistensi desain di berbagai browser dan platform.

#### Langkah 1: Buat Pengontrol Kustom
Buat kelas pengontrol khusus `LinkAllFontsHtmlController` yang mewarisi dari `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // Atur direktori tempat file font akan disimpan
    }
}
```
#### Langkah 2: Terapkan Metode Penulisan Font
Itu `WriteFont` metode menulis data font ke dalam file dan menghasilkan kode HTML terkait untuk disematkan:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // Tentukan nama font yang akan digunakan, pilih font pengganti jika tersedia.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // Buat jalur berkas untuk berkas font .woff.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // Tulis data font ke jalur berkas yang ditentukan.
    File.WriteAllBytes(path, fontData);

    // Hasilkan blok gaya HTML dengan menyematkan font menggunakan aturan @font-face.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}