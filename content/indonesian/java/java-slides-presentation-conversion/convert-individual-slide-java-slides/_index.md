---
title: Konversi Slide Individu di Slide Java
linktitle: Konversi Slide Individu di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengonversi setiap slide PowerPoint ke HTML selangkah demi selangkah dengan contoh kode menggunakan Aspose.Slides untuk Java.
type: docs
weight: 12
url: /id/java/presentation-conversion/convert-individual-slide-java-slides/
---

## Pengantar Mengonversi Slide Individual di Slide Java

Dalam tutorial ini, kita akan memandu proses mengonversi masing-masing slide dari presentasi PowerPoint ke HTML menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah ini akan memberi Anda kode sumber dan penjelasan untuk membantu Anda mencapai tugas ini.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

- Aspose.Slides untuk perpustakaan Java diinstal.
- File presentasi PowerPoint (`Individual-Slide.pptx`) yang ingin Anda konversi.
- Lingkungan pengembangan Java disiapkan.

## Langkah 1: Siapkan Proyek

1. Buat proyek Java di lingkungan pengembangan pilihan Anda.
2. Tambahkan perpustakaan Aspose.Slides untuk Java ke proyek Anda.

## Langkah 2: Impor Kelas yang Diperlukan

Di kelas Java Anda, impor kelas yang diperlukan dan atur konfigurasi awal.

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.IHtmlFormattingController;
import com.aspose.slides.IHtmlGenerator;
import com.aspose.slides.ISlide;
import com.aspose.slides.IShape;
```

## Langkah 3: Tentukan Metode Konversi Utama

 Buat metode untuk melakukan konversi masing-masing slide. Pastikan untuk mengganti`"Your Document Directory"` dengan jalur sebenarnya ke direktori dokumen Anda.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // Menyimpan Berkas
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Langkah 4: Terapkan CustomFormattingController

 Buat`CustomFormattingController` kelas untuk menangani pemformatan khusus selama konversi.

```java
public static class CustomFormattingController implements IHtmlFormattingController {
    public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeSlideStart(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
    }
    
    public void writeSlideEnd(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(SlideFooter);
    }
    
    public void writeShapeStart(IHtmlGenerator generator, IShape shape) {
    }
    
    public void writeShapeEnd(IHtmlGenerator generator, IShape shape) {
    }
    
    private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
    private static String SlideFooter = "</div>";
}
```

## Langkah 5: Jalankan Konversi

 Terakhir, hubungi`convertIndividualSlides` metode untuk menjalankan proses konversi.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Kode Sumber Lengkap Untuk Mengonversi Slide Individual di Slide Java

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// Menyimpan Berkas
		for (int i = 0; i < presentation.getSlides().size(); i++)
			presentation.save(dataDir + "Individual Slide" + i + 1 + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
	}
	finally
	{
		if (presentation != null) presentation.dispose();
	}
}
public static class CustomFormattingController implements IHtmlFormattingController
{
	public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeSlideStart(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
	}
	public void writeSlideEnd(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(SlideFooter);
	}
	public void writeShapeStart(IHtmlGenerator generator, IShape shape)
	{
	}
	public void writeShapeEnd(IHtmlGenerator generator, IShape shape)
	{
	}
	private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
	private static String SlideFooter = "</div>";
```

## Kesimpulan

Anda telah berhasil mengonversi setiap slide dari presentasi PowerPoint ke HTML menggunakan Aspose.Slides untuk Java. Tutorial ini memberi Anda kode dan langkah-langkah yang diperlukan untuk mencapai tugas ini. Jangan ragu untuk menyesuaikan keluaran dan pemformatan sesuai kebutuhan untuk kebutuhan spesifik Anda.

## FAQ

### Bagaimana cara menyesuaikan keluaran HTML lebih lanjut?

 Anda dapat menyesuaikan keluaran HTML dengan memodifikasi`CustomFormattingController` kelas. Sesuaikan`writeSlideStart` Dan`writeSlideEnd` metode untuk mengubah struktur dan gaya HTML slide.

### Bisakah saya mengonversi beberapa presentasi PowerPoint sekaligus?

 Ya, Anda dapat memodifikasi kode untuk mengulang beberapa file presentasi dan mengonversinya satu per satu dengan memanggil`convertIndividualSlides` metode untuk setiap presentasi.

### Bagaimana cara menangani pemformatan tambahan untuk bentuk dan teks dalam slide?

Anda dapat memperpanjang`CustomFormattingController` kelas untuk menangani pemformatan bentuk tertentu dengan mengimplementasikan`writeShapeStart` Dan`writeShapeEnd` metode dan menerapkan logika pemformatan khusus di dalamnya.