---
"date": "2025-04-22"
"description": "Pelajari cara membuat dan menyesuaikan diagram donat di PowerPoint menggunakan Aspose.Slides untuk Python. Tutorial ini mencakup pengaturan ukuran lubang, penyimpanan presentasi, dan praktik terbaik."
"title": "Cara Membuat Bagan Donat di PowerPoint dengan Ukuran Lubang Kustom Menggunakan Aspose.Slides untuk Python"
"url": "/id/python-net/charts-graphs/create-doughnut-chart-aspose-python-custom-hole-size/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Bagan Donat di PowerPoint dengan Ukuran Lubang Kustom Menggunakan Aspose.Slides untuk Python

## Perkenalan
Membuat bagan yang menarik secara visual di PowerPoint dapat membuat data Anda lebih menarik dan lebih mudah dipahami. Tantangan umum adalah kurangnya opsi penyesuaian saat membuat bagan ini secara terprogram. Tutorial ini mengatasinya dengan menunjukkan cara membuat bagan donat dengan ukuran lubang khusus menggunakan Aspose.Slides untuk Python.

**Kata kunci:** Aspose.Slides Python, Bagan Donat, Ukuran Lubang Kustom

### Apa yang Akan Anda Pelajari:
- Menyiapkan dan menggunakan Aspose.Slides untuk Python
- Membuat bagan donat di PowerPoint
- Menyesuaikan ukuran lubang pada diagram donat Anda
- Praktik terbaik untuk menyimpan dan mengekspor presentasi

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:
- **Bahasa Inggris Python 3.x** terinstal pada sistem Anda.
- Pengetahuan dasar tentang konsep pemrograman Python.
- Itu `aspose.slides` perpustakaan (petunjuk instalasi disediakan di bawah).

## Menyiapkan Aspose.Slides untuk Python
Untuk memulai, instal Aspose.Slides untuk Python menggunakan pip:

```bash
pip install aspose.slides
```

### Akuisisi Lisensi
Aspose menawarkan uji coba gratis yang memungkinkan Anda menjelajahi fitur-fiturnya tanpa batasan jumlah dokumen atau waktu penggunaan:
- **Uji Coba Gratis:** Mulailah dengan lisensi sementara untuk menguji kemampuan penuh.
- **Lisensi Sementara:** Tersedia untuk tujuan evaluasi.
- **Pembelian:** Untuk penggunaan jangka panjang, pertimbangkan untuk membeli lisensi.

Setelah instalasi dan pengaturan, Anda dapat mulai membuat presentasi secara terprogram. Berikut cara menginisialisasi Aspose.Slides:

```python
import aspose.slides as slides

# Inisialisasi objek presentasi
class PresentationCreator:
    def create_presentation(self):
        with slides.Presentation() as presentation:
            # Kode Anda ada di sini
```

## Panduan Implementasi
Bagian ini menguraikan langkah-langkah yang diperlukan untuk membuat dan menyesuaikan bagan donat di PowerPoint menggunakan Aspose.Slides.

### Langkah 1: Mengakses dan Memodifikasi Slide
Untuk memulai, akses slide pertama dari presentasi Anda. Di sinilah Anda akan menambahkan diagram donat kustom Anda.

```python
# Akses slide pertama
class SlideModifier:
    def modify_slide(self, presentation):
        first_slide = presentation.slides[0]
```

### Langkah 2: Menambahkan Bagan Donat
Anda dapat menambahkan diagram donat ke slide mana pun dengan menentukan posisi dan ukurannya. Di sini, kita akan meletakkannya pada koordinat (50, 50) dengan dimensi 400x400.

```python
class ChartAdder:
    def add_doughnut_chart(self, first_slide):
        # Tambahkan diagram donat
        chart = first_slide.shapes.add_chart(
            slides.charts.ChartType.DOUGHNUT,
            50, 50, 400, 400
        )
```

### Langkah 3: Menyesuaikan Ukuran Lubang
Menyesuaikan ukuran lubang pada diagram donat Anda mudah saja. Atur ke 90% untuk mendapatkan efek yang jelas.

```python
class ChartCustomizer:
    def customize_hole_size(self, chart):
        # Atur ukuran lubang khusus
        chart.chart_data.series_groups[0].doughnut_hole_size = 90
```

### Langkah 4: Menyimpan Presentasi Anda
Terakhir, simpan presentasi Anda ke lokasi yang diinginkan dengan nama file yang dipilih.

```python
class PresentationSaver:
    def save_presentation(self, presentation):
        # Simpan presentasi
        presentation.save(
            "charts_doughnut_chart_hole_out.pptx",
            slides.export.SaveFormat.PPTX
        )
```

## Aplikasi Praktis
Membuat diagram donat yang disesuaikan dapat berguna dalam berbagai skenario, termasuk:
- **Laporan Bisnis:** Menyorot indikator kinerja utama dengan segmen yang berbeda secara visual.
- **Konten Edukasi:** Mengilustrasikan data statistik kepada siswa atau kolega.
- **Materi Pemasaran:** Menampilkan rincian produk atau demografi pelanggan.

Integrasi dengan sistem lain dimungkinkan dengan mengekspor bagan sebagai gambar atau menanamkannya dalam aplikasi web menggunakan API Aspose yang komprehensif.

## Pertimbangan Kinerja
Saat bekerja dengan Aspose.Slides, pertimbangkan kiat-kiat berikut untuk kinerja yang optimal:
- Minimalkan penggunaan sumber daya dengan hanya memuat slide yang diperlukan.
- Kelola memori secara efektif dengan menutup presentasi segera setelah digunakan.
- Memanfaatkan pemrosesan batch untuk menghasilkan beberapa grafik sekaligus.

Mengikuti praktik terbaik memastikan aplikasi Anda berjalan lancar dan efisien.

## Kesimpulan
Dengan mengikuti panduan ini, Anda telah mempelajari cara membuat bagan donat dengan ukuran lubang khusus di PowerPoint menggunakan Aspose.Slides untuk Python. Ini tidak hanya meningkatkan daya tarik visual presentasi Anda tetapi juga memungkinkan fleksibilitas representasi data yang lebih besar.

Untuk lebih mengeksplorasi kemampuan Aspose.Slides, pertimbangkan untuk bereksperimen dengan jenis bagan dan fitur presentasi lainnya. Selamat membuat kode!

## Bagian FAQ
1. **Berapa ukuran lubang maksimum yang dapat saya atur untuk diagram donat?**
   - Anda dapat mengaturnya hingga 100% untuk diagram lingkaran penuh.
2. **Bisakah saya memodifikasi bagan yang ada dalam berkas PowerPoint menggunakan Aspose.Slides?**
   - Ya, Anda dapat memuat dan mengedit presentasi yang ada.
3. **Bagaimana cara menangani kesalahan saat menyimpan presentasi?**
   - Pastikan jalur keluaran dapat ditulis dan periksa masalah izin.
4. **Apakah ada dukungan untuk jenis bagan lain selain bagan donat?**
   - Tentu saja, Aspose.Slides mendukung berbagai jenis bagan.
5. **Bisakah Aspose.Slides digunakan dengan aplikasi web?**
   - Ya, API-nya dapat diintegrasikan ke dalam sistem backend dan diekspos melalui layanan web.

## Sumber daya
- [Dokumentasi](https://reference.aspose.com/slides/python-net/)
- [Unduh](https://releases.aspose.com/slides/python-net/)
- [Pembelian](https://purchase.aspose.com/buy)
- [Uji Coba Gratis](https://releases.aspose.com/slides/python-net/)
- [Lisensi Sementara](https://purchase.aspose.com/temporary-license/)
- [Forum Dukungan](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}