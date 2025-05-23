---
"date": "2025-04-23"
"description": "Pelajari cara mengatur presentasi PowerPoint sebagai read-only dan menghitung slide secara terprogram menggunakan Aspose.Slides untuk Python. Sempurna untuk berbagi dokumen yang aman dan pelaporan otomatis."
"title": "Mengatur PowerPoint Hanya Baca dan Menghitung Slide dengan Python menggunakan Aspose.Slides"
"url": "/id/python-net/security-protection/powerpoint-read-only-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Mengatur PowerPoint Hanya Baca dan Menghitung Slide dengan Python

## Perkenalan
Pernahkah Anda menghadapi tantangan dalam mendistribusikan presentasi sambil memastikannya tetap tidak berubah? Atau mungkin Anda menginginkan cara mudah untuk memverifikasi berapa banyak slide dalam presentasi Anda tanpa membukanya? Dengan **Aspose.Slides untuk Python**, tugas-tugas ini menjadi mudah. Tutorial ini akan memandu Anda dalam mengatur presentasi PowerPoint sebagai read-only dan menghitung slide menggunakan Aspose.Slides, menawarkan solusi yang tangguh untuk mengelola file PowerPoint Anda secara terprogram.

**Apa yang Akan Anda Pelajari:**
- Cara mengatur proteksi penulisan pada presentasi PowerPoint.
- Cara menyimpan berkas PowerPoint dengan batasan baca-saja.
- Cara memuat presentasi dan menghitung jumlah slide secara efisien.

Mari selami bagaimana Anda dapat menyelesaikan tugas-tugas ini dengan lancar di Python.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:
- **Bahasa Inggris Python 3.6+** terinstal pada sistem Anda.
- Akses ke antarmuka baris perintah untuk menginstal paket.

Anda juga perlu memasang Aspose.Slides untuk Python. Pustaka canggih ini memungkinkan manipulasi file PowerPoint tingkat lanjut langsung dari lingkungan Python Anda. Meskipun versi gratisnya menyediakan fungsionalitas terbatas, memperoleh lisensi (baik melalui uji coba gratis atau pembelian) akan memperluas kemampuan secara signifikan.

## Menyiapkan Aspose.Slides untuk Python
Untuk mulai bekerja dengan Aspose.Slides dalam Python, Anda perlu menginstalnya terlebih dahulu. Berikut caranya:

### Instalasi pip
Jalankan perintah berikut di terminal atau prompt perintah Anda:

```bash
pip install aspose.slides
```

Ini akan mengunduh dan menginstal versi terbaru Aspose.Slides untuk Python.

### Langkah-langkah Memperoleh Lisensi
1. **Uji Coba Gratis**: Mulailah dengan uji coba gratis untuk menjelajahi fungsionalitas dasar.
2. **Lisensi Sementara**: Dapatkan lisensi sementara untuk membuka fitur lengkap selama periode evaluasi Anda.
3. **Pembelian**: Pertimbangkan untuk membeli lisensi untuk akses dan dukungan berkelanjutan.

Setelah Anda memiliki berkas lisensi, muat dalam skrip Anda seperti ini:

```python
class LicenseLoader:
    def __init__(self):
        self.license = aspose.slides.License()

    def set_license(self, path_to_license_file):
        self.license.set_license(path_to_license_file)
```

## Panduan Implementasi
Di bagian ini, kami akan menguraikan implementasi menjadi dua fitur utama: menetapkan presentasi sebagai hanya-baca dan menghitung slide.

### Fitur 1: Simpan Presentasi sebagai Hanya-Baca
#### Ringkasan
Fitur ini memungkinkan Anda untuk mengatur proteksi penulisan pada file PowerPoint, memastikan file tersebut tidak dapat dimodifikasi tanpa memasukkan kata sandi. Fitur ini sangat berguna untuk mendistribusikan presentasi yang tidak boleh diubah oleh penerimanya.

#### Tangga
##### Langkah 1: Membuat Objek Presentasi
Mulailah dengan membuat `Presentation` objek. Ini mewakili berkas PPT Anda dalam Python.

```python
import aspose.slides as slides

class ReadWriteProtection:
    def __init__(self, password):
        self.password = password

    def set_write_protection(self, presentation_path, output_directory):
        with slides.Presentation(presentation_path) as presentation:
            presentation.protection_manager.set_write_protection(self.password)
            presentation.save(f"{output_directory}/save_as_read_only_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}