---
"date": "2025-04-16"
"description": "Pelajari cara mengatur atribut bahasa untuk teks dalam bentuk menggunakan Aspose.Slides untuk .NET. Panduan ini mencakup penambahan bentuk otomatis, pengaturan ID bahasa, dan penyimpanan presentasi."
"title": "Cara Mengatur Bahasa dalam Bentuk PowerPoint Menggunakan Aspose.Slides untuk .NET"
"url": "/id/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Mengatur Bahasa dalam Bentuk PowerPoint Menggunakan Aspose.Slides untuk .NET

Dalam dunia presentasi digital, memastikan konten Anda dapat diakses dan diformat dengan benar dalam berbagai bahasa dapat menjadi tantangan. Dengan Aspose.Slides untuk .NET, Anda dapat dengan mudah mengatur atribut bahasa untuk teks dalam bentuk di slide PowerPoint. Fitur ini sangat bermanfaat saat menyiapkan dokumen multibahasa atau memastikan konsistensi dalam komunikasi global.

**Apa yang Akan Anda Pelajari:**
- Menambahkan bentuk otomatis dan memasukkan teks ke dalamnya.
- Mengatur ID bahasa untuk bagian teks menggunakan Aspose.Slides.
- Menyimpan presentasi dengan konfigurasi khusus.

Mari selami bagaimana Anda dapat menerapkan fitur ini dengan lancar.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

- **Perpustakaan dan Ketergantungan**: Anda perlu menginstal Aspose.Slides for .NET. Pustaka ini penting untuk memanipulasi presentasi PowerPoint dalam C#.
  
- **Pengaturan Lingkungan**: Diperlukan lingkungan pengembangan dengan .NET Core atau .NET Framework.

- **Prasyarat Pengetahuan**:Keakraban dengan konsep dasar pemrograman C# dan pemahaman prinsip pemrograman berorientasi objek akan sangat membantu.

## Menyiapkan Aspose.Slides untuk .NET

Untuk memulai, Anda perlu menginstal pustaka Aspose.Slides. Anda dapat melakukannya dengan salah satu metode berikut:

**.KLIK NET**
```shell
dotnet add package Aspose.Slides
```

**Manajer Paket**
```powershell
Install-Package Aspose.Slides
```

**Antarmuka Pengguna Pengelola Paket NuGet**
Cari "Aspose.Slides" dan instal versi terbaru.

### Akuisisi Lisensi

Anda dapat memulai dengan uji coba gratis dengan mengunduh lisensi sementara dari [Di Sini](https://purchase.aspose.com/temporary-license/)Untuk penggunaan berkelanjutan, pertimbangkan untuk membeli lisensi melalui [tautan ini](https://purchase.aspose.com/buy).

Setelah pengaturan Anda siap, inisialisasi Aspose.Slides di proyek Anda:

```csharp
using Aspose.Slides;
```

## Panduan Implementasi

Sekarang setelah pengaturannya selesai, mari terapkan fitur untuk mengatur bahasa untuk teks bentuk.

### Gambaran Umum Fitur: Pengaturan Bentuk Bahasa Teks

Fitur ini memungkinkan Anda menentukan bahasa teks dalam bentuk PowerPoint. Dengan menetapkan ID bahasa, Anda memastikan bahwa fitur pemeriksaan ejaan dan fitur khusus bahasa lainnya diterapkan dengan benar.

#### Langkah 1: Inisialisasi Presentasi

Mulailah dengan membuat contoh `Presentation` kelas.

```csharp
using (Presentation pres = new Presentation())
{
    // Kode Anda di sini
}
```

Ini menginisialisasi objek presentasi PowerPoint baru yang akan kita manipulasi.

#### Langkah 2: Tambahkan Bentuk Otomatis dan Bingkai Teks

Tambahkan bentuk persegi panjang ke slide Anda dan masukkan teks ke dalamnya:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Di Sini, `AddAutoShape` menambahkan persegi panjang ke slide pertama. Parameter menentukan posisi dan ukurannya.

#### Langkah 3: Atur ID Bahasa

Atur bahasa untuk bagian teks dalam bentuk:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

Ini menetapkan Bahasa Inggris (UK) sebagai bahasa untuk pemeriksaan ejaan.

#### Langkah 4: Simpan Presentasi

Terakhir, simpan presentasi Anda ke jalur yang ditentukan:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}