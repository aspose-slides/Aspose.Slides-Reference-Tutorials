---
"date": "2025-04-16"
"description": "Pelajari cara menerapkan aturan fallback font di Aspose.Slides untuk .NET untuk memastikan presentasi Anda menampilkan teks dengan benar di berbagai bahasa dan skrip."
"title": "Cara Menetapkan Aturan Penggantian Font di Aspose.Slides untuk .NET&#58; Panduan Lengkap"
"url": "/id/net/shapes-text-frames/implement-font-fallback-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menetapkan Aturan Penggantian Font di Aspose.Slides untuk .NET: Panduan Lengkap

## Perkenalan

Membuat presentasi dengan Aspose.Slides for .NET terkadang memerlukan penanganan karakter yang tidak dapat didukung oleh font tertentu, seperti Hiragana Tamil atau Jepang. Menetapkan aturan fallback font sangat penting untuk memastikan presentasi Anda menampilkan teks dengan benar dalam berbagai bahasa dan simbol.

Dalam tutorial ini, kami akan memandu Anda menerapkan aturan fallback font menggunakan Aspose.Slides for .NET. Dari instalasi hingga aplikasi praktis, panduan ini memastikan bahwa presentasi Anda mempertahankan konsistensi visual apa pun kontennya.

**Apa yang Akan Anda Pelajari:**
- Tentukan rentang Unicode untuk skrip yang berbeda-beda.
- Siapkan font cadangan untuk karakter yang tidak didukung.
- Terapkan fallback font dalam skenario presentasi dunia nyata.
- Kiat untuk mengoptimalkan kinerja dan integrasi dengan sistem lain.

Mari kita mulai dengan meninjau prasyaratnya.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- **Aspose.Slides untuk .NET** pustaka terinstal. Instal menggunakan salah satu metode berikut:
  - **.KLIK NET**: Berlari `dotnet add package Aspose.Slides`
  - **Manajer Paket**: Eksekusi `Install-Package Aspose.Slides`
  - **Antarmuka Pengguna Pengelola Paket NuGet**: Cari dan instal versi terbaru.
- Lingkungan pengembangan yang disiapkan dengan .NET Core atau .NET Framework (versi 4.5 atau lebih baru).
- Pemahaman dasar tentang pemrograman C#.

## Menyiapkan Aspose.Slides untuk .NET

Untuk mulai menggunakan Aspose.Slides, dapatkan lisensi dari [Situs web Aspose](https://purchase.aspose.com/buy)Berikut cara mengaturnya:

1. **Instalasi**Ikuti langkah-langkah instalasi yang disebutkan di atas.
2. **Pengaturan Lisensi**:
   - Muat berkas lisensi Anda ke proyek Anda menggunakan:
     ```csharp
     License license = new License();
     license.SetLicense("path_to_your_license_file.lic");
     ```

Pengaturan ini memungkinkan Anda mulai bekerja dengan Aspose.Slides untuk .NET.

## Panduan Implementasi

Di bagian ini, kami akan menguraikan proses pengaturan aturan fallback font dalam langkah-langkah yang jelas.

### 1. Tentukan Rentang Unicode dan Font Cadangan

Setiap skrip atau set simbol memerlukan rentang Unicode tertentu dan font fallback yang sesuai untuk memastikan tampilan yang tepat.

#### Aksara Tamil

- **Ringkasan**: Gunakan "Vijaya" untuk karakter Tamil jika font utama tidak mendukung.

**Langkah-langkah Implementasi:**

##### Langkah 1: Tentukan Rentang Unicode
```csharp
uint startUnicodeIndexTamil = 0x0B80; // Awal mula rentang Tamil
uint endUnicodeIndexTamil = 0x0BFF;   // Akhir dari jangkauan Tamil
```
Cuplikan ini mendefinisikan rentang Unicode untuk karakter Tamil.

##### Langkah 2: Buat Aturan Fallback
```csharp
IFontFallBackRule tamilFallbackRule = new FontFallBackRule(startUnicodeIndexTamil, endUnicodeIndexTamil, "Vijaya");
```
Di sini, kami membuat aturan fallback menggunakan "Vijaya" sebagai font alternatif.

#### Hiragana Jepang

- **Ringkasan**: Gunakan "MS Mincho" atau "MS Gothic" untuk karakter Hiragana yang tidak didukung.

**Langkah-langkah Implementasi:**

##### Langkah 1: Tentukan Rentang Unicode
```csharp
uint startUnicodeIndexHiragana = 0x3040; // Awal dari rentang Hiragana
uint endUnicodeIndexHiragana = 0x309F;   // Akhir dari rentang Hiragana
```
Cuplikan ini menetapkan batasan Unicode untuk Hiragana.

##### Langkah 2: Buat Aturan Fallback
```csharp
IFontFallBackRule hiraganaFallbackRule = new FontFallBackRule(startUnicodeIndexHiragana, endUnicodeIndexHiragana, "MS Mincho, MS Gothic");
```
Aturan ini menentukan beberapa font cadangan untuk karakter Hiragana.

#### Karakter Emoji

- **Ringkasan**: Pastikan emoji ditampilkan menggunakan font yang sesuai seperti "Segoe UI Emoji".

**Langkah-langkah Implementasi:**

##### Langkah 1: Tentukan Rentang Unicode
```csharp
uint startUnicodeIndexEmoji = 0x1F300; // Awal rentang emoji
uint endUnicodeIndexEmoji = 0x1F64F;   // Akhir rentang emoji
```
Ini mendefinisikan rentang Unicode untuk emoji.

##### Langkah 2: Buat Aturan Fallback
```csharp
string[] fontNamesEmoji = { "Segoe UI Emoji, Segoe UI Symbol\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}