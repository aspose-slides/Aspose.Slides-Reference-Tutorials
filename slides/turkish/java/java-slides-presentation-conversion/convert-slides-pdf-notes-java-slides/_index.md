---
title: Java Slaytlarındaki Notlarla Slaytları PDF'ye Dönüştürme
linktitle: Java Slaytlarındaki Notlarla Slaytları PDF'ye Dönüştürme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint slaytlarını Java'da not içeren PDF'ye nasıl dönüştüreceğinizi öğrenin. Java geliştiricileri için adım adım kılavuz. Sunum paylaşımınızı geliştirin.
weight: 19
url: /tr/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java'da Notlarla Slaytları PDF'ye Dönüştürmeye Giriş

Dijital sunum dünyasında, slaytları notlarla birlikte PDF'ye dönüştürme yeteneği değerli bir özelliktir. Java geliştiricileri bunu, PowerPoint sunumlarıyla programlı olarak çalışmak için güçlü bir araç seti sağlayan Aspose.Slides for Java kitaplığını kullanarak başarabilirler. Bu adım adım kılavuzda, Java ve Aspose.Slides for Java kullanarak slaytları notlarla birlikte PDF'ye nasıl dönüştürebileceğinizi keşfedeceğiz.

## Önkoşullar

Kodun ayrıntılarına girmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Slides for Java kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

Artık taslağımızı hazırladığımıza göre adım adım uygulamaya geçelim.
## Adım 1: Projeyi Kurma

Öncelikle bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin bağımlılıklarına ekleyin.

## Adım 2: Sunumu Yükleme

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Adım 3: Yeni Bir Sunu Oluşturma

```java
Presentation auxPresentation = new Presentation();
```

## Adım 4: Slaytları Kopyalama

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## Adım 5: Slayt Boyutunu Ayarlama

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## Adım 6: PDF Seçeneklerini Yapılandırma

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Adım 7: PDF olarak kaydetme

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Java Slaytlarındaki Notlarla Slaytları PDF'ye Dönüştürmek İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Bir sunum dosyasını temsil eden bir Sunum nesnesinin örneğini oluşturun
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Slayt Türünü ve Boyutunu Ayarlama
		//auxPresentation.getSlideSize().setSize(sunum.getSlideSize().getSize().getWidth(), sunum.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides for Java kullanarak slaytları Java'da not içeren PDF'ye nasıl dönüştüreceğimizi öğrendik. Projeyi kurmayı, sunumu yüklemeyi, yeni bir sunum oluşturmayı, slaytları kopyalamayı, slayt boyutunu ayarlamayı, PDF seçeneklerini yapılandırmayı ve son olarak sunumu notlarla birlikte PDF olarak kaydetmeyi anlattık.

## SSS'ler

### Aspose.Slides for Java'yı nasıl yüklerim?

Aspose.Slides for Java'yı yüklemek için şu adımları izleyin:
1.  Kütüphaneyi şuradan indirin:[Burada](https://releases.aspose.com/slides/java/).
2. JAR dosyasını Java projenizin sınıf yoluna ekleyin.

### Oluşturulan PDF'deki notların konumunu özelleştirebilir miyim?

 Evet, notların konumunu değiştirerek özelleştirebilirsiniz.`NotesPositions` PDF seçeneklerinde numaralandırın. Bu eğitimde bunu şu şekilde ayarladık:`BottomFull`, ancak diğer seçenekleri de keşfedebilirsiniz.

### Aspose.Slides for Java'yı kullanmak için herhangi bir lisans gereksinimi var mı?

Evet, Aspose.Slides for Java ticari bir kütüphanedir ve onu üretimde kullanmak için lisans almanız gerekebilir. Lisans ayrıntıları için Aspose web sitesini ziyaret edin.

### Aynı anda birden fazla slaytı dönüştürebilir miyim?

Kesinlikle! Sununuzdaki slaytlar arasında geçiş yapabilir ve bunları yeni sunuma kopyalayabilirsiniz; böylece tek seferde birden fazla slaytı notlarla birlikte PDF'ye dönüştürebilirsiniz.

### Aspose.Slides for Java ile ilgili daha fazla belgeyi nerede bulabilirim?

 Aspose.Slides for Java ile ilgili ayrıntılı belgeleri şu sitede bulabilirsiniz:[Java API Referansı için Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
