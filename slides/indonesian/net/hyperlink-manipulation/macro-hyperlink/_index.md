---
title: Cara Mengatur Makro Hyperlink Klik di Aspose.Slides untuk .NET
linktitle: Manajemen Hyperlink menggunakan Makro
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara mengatur hyperlink makro dalam presentasi Anda dengan Aspose.Slides untuk .NET. Tingkatkan interaktivitas dan libatkan audiens Anda.
weight: 13
url: /id/net/hyperlink-manipulation/macro-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengatur Makro Hyperlink Klik di Aspose.Slides untuk .NET


Dalam dunia pengembangan perangkat lunak modern, membuat presentasi yang dinamis dan interaktif adalah aspek kuncinya. Aspose.Slides for .NET adalah perpustakaan canggih yang memungkinkan Anda bekerja dengan presentasi dengan lancar. Baik Anda sedang membuat presentasi bisnis atau tayangan slide pendidikan, kemampuan untuk mengatur klik hyperlink makro dapat sangat meningkatkan pengalaman pengguna. Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses pengaturan klik hyperlink makro menggunakan Aspose.Slides untuk .NET. 

## Prasyarat

Sebelum kita mendalami tutorial langkah demi langkah, ada beberapa prasyarat yang harus Anda miliki:

1.Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda, karena ini akan menjadi lingkungan pengembangan kami.

 2.Aspose.Slides untuk .NET: Anda harus menginstal perpustakaan Aspose.Slides untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/net/).

3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# sangat penting untuk mengikuti tutorial ini.

## Impor Namespace

Pada langkah pertama, mari impor namespace yang diperlukan agar berfungsi dengan Aspose.Slides:

### Langkah 1: Impor Namespace

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 Kami telah mengimpornya`Aspose.Slides` namespace, yang merupakan namespace inti untuk bekerja dengan presentasi, dan`Aspose.Slides.Export` ruang nama.

## Setting Makro Hyperlink Klik

Sekarang, mari beralih ke bagian utama tutorial ini - mengatur klik hyperlink makro di presentasi Anda.

### Langkah 2: Inisialisasi Presentasi

Pertama, kita perlu menginisialisasi presentasi baru.

```csharp
using (Presentation presentation = new Presentation())
{
    // Kode Anda akan ditempatkan di sini.
}
```

Dalam pernyataan penggunaan ini, Anda membuat objek presentasi baru dan melakukan semua operasi di dalamnya.

### Langkah 3: Tambahkan BentukOtomatis

Untuk menyetel klik hyperlink makro, Anda memerlukan objek yang dapat diklik pengguna. Dalam contoh ini, kita akan menggunakan BentukOtomatis sebagai elemen yang dapat diklik.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Di sini, kita membuat BentukOtomatis dengan tipe "BlankButton" pada koordinat tertentu (20, 20) dan dengan dimensi 80x30. Anda dapat menyesuaikan nilai-nilai ini agar sesuai dengan tata letak presentasi Anda.

### Langkah 4: Atur Klik Hyperlink Makro

Sekarang sampai pada bagian di mana Anda mengatur klik hyperlink makro. Anda harus memberikan nama makro sebagai parameter.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

Dalam contoh ini, kami telah menyetel klik hyperlink makro ke "TestMacro". Saat pengguna mengklik BentukOtomatis, makro ini akan dipicu.

### Langkah 5: Ambil Informasi

Anda juga dapat mengambil informasi tentang hyperlink yang Anda tetapkan.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Baris kode ini memungkinkan Anda mencetak URL eksternal dan jenis tindakan hyperlink.

Dan itu saja! Anda telah berhasil menyetel klik hyperlink makro di presentasi Anda menggunakan Aspose.Slides untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara mengatur klik hyperlink makro di presentasi Anda menggunakan Aspose.Slides untuk .NET. Ini bisa menjadi fitur berharga untuk membuat presentasi interaktif dan dinamis yang melibatkan audiens Anda. Dengan Aspose.Slides untuk .NET, Anda memiliki alat canggih yang dapat digunakan untuk membawa pengembangan presentasi Anda ke tingkat berikutnya.

 Sekarang, saatnya Anda bereksperimen dan membuat presentasi menawan dengan hyperlink makro khusus. Jangan ragu untuk menjelajahinya[Aspose.Slides untuk dokumentasi .NET](https://reference.aspose.com/slides/net/) untuk informasi dan kemungkinan yang lebih mendalam.

## FAQ (Pertanyaan yang Sering Diajukan)

### Bisakah saya menggunakan Aspose.Slides untuk .NET dengan bahasa pemrograman lain?
Aspose.Slides terutama dirancang untuk .NET, tetapi Aspose menawarkan perpustakaan serupa untuk bahasa pemrograman lain, seperti Java.

### Apakah Aspose.Slides untuk .NET merupakan perpustakaan gratis?
Aspose.Slides for .NET adalah perpustakaan komersial dengan versi uji coba gratis yang tersedia. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/).

### Apakah ada batasan dalam menggunakan makro dalam presentasi yang dibuat dengan Aspose.Slides untuk .NET?
Aspose.Slides untuk .NET memungkinkan Anda bekerja dengan makro, namun Anda harus menyadari pertimbangan keamanan dan kompatibilitas saat menggunakan makro dalam presentasi.

### Bisakah saya menyesuaikan tampilan BentukOtomatis yang digunakan untuk hyperlink?
Ya, Anda dapat menyesuaikan tampilan BentukOtomatis dengan menyesuaikan propertinya, seperti ukuran, warna, dan font.

### Di mana saya bisa mendapatkan bantuan atau dukungan untuk Aspose.Slides untuk .NET?
 Jika Anda mengalami masalah atau memiliki pertanyaan, Anda dapat mencari bantuan di forum dukungan Aspose[Di Sini](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
