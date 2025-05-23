---
"description": "Aspose.Slides for Java kullanarak PowerPoint slaytlarını notlarla birlikte Java'da PDF'ye nasıl dönüştüreceğinizi öğrenin. Java geliştiricileri için adım adım kılavuz. Sunum paylaşımınızı geliştirin."
"linktitle": "Java Slaytlarında Notlarla Slaytları PDF'ye Dönüştürme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Notlarla Slaytları PDF'ye Dönüştürme"
"url": "/tr/java/presentation-conversion/convert-slides-pdf-notes-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Notlarla Slaytları PDF'ye Dönüştürme


## Java'da Notlarla Slaytları PDF'ye Dönüştürmeye Giriş

Dijital sunumlar dünyasında, slaytları notlarla birlikte PDF'ye dönüştürme yeteneği değerli bir özelliktir. Java geliştiricileri, PowerPoint sunumlarıyla programatik olarak çalışmak için sağlam bir araç seti sağlayan Aspose.Slides for Java kitaplığını kullanarak bunu başarabilirler. Bu adım adım kılavuzda, Java ve Aspose.Slides for Java kullanarak slaytları notlarla birlikte PDF'ye nasıl dönüştüreceğinizi inceleyeceğiz.

## Ön koşullar

Koda dalmadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Sisteminizde Java Development Kit (JDK) yüklü.
- Java kütüphanesi için Aspose.Slides. Buradan indirebilirsiniz [Burada](https://releases.aspose.com/slides/java/).

Artık taslağımızı hazırladığımıza göre, adım adım uygulamaya geçelim.
## Adım 1: Projenin Kurulumu

Öncelikle bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin bağımlılıklarına ekleyin.

## Adım 2: Sunumu Yükleme

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Adım 3: Yeni Bir Sunum Oluşturma

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

## Java Slaytlarında Notlarla Slaytları PDF'ye Dönüştürmek İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir sunum dosyasını temsil eden bir Sunum nesnesi örneği oluşturun 
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Slayt Türü ve Boyutunu Ayarlama
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

Bu eğitimde, Java'da Aspose.Slides for Java kullanarak slaytları notlarla PDF'ye nasıl dönüştüreceğimizi öğrendik. Projeyi kurmayı, sunumu yüklemeyi, yeni bir sunum oluşturmayı, slaytları kopyalamayı, slayt boyutunu ayarlamayı, PDF seçeneklerini yapılandırmayı ve son olarak sunumu notlarla PDF olarak kaydetmeyi ele aldık.

## SSS

### Java için Aspose.Slides'ı nasıl yüklerim?

Java için Aspose.Slides'ı yüklemek için şu adımları izleyin:
1. Kütüphaneyi şu adresten indirin: [Burada](https://releases.aspose.com/slides/java/).
2. JAR dosyasını Java projenizin sınıf yoluna ekleyin.

### Oluşturulan PDF'deki notların konumunu özelleştirebilir miyim?

Evet, notların konumunu değiştirerek özelleştirebilirsiniz. `NotesPositions` PDF seçeneklerinde enum. Bu eğitimde, bunu şu şekilde ayarladık: `BottomFull`, ancak diğer seçenekleri de keşfedebilirsiniz.

### Aspose.Slides for Java'yı kullanmak için herhangi bir lisanslama gereksinimi var mı?

Evet, Aspose.Slides for Java ticari bir kütüphanedir ve onu üretimde kullanmak için bir lisans edinmeniz gerekebilir. Lisanslama ayrıntıları için Aspose web sitesini ziyaret edin.

### Birden fazla slaydı aynı anda dönüştürebilir miyim?

Elbette! Sunumunuzdaki slaytlar arasında geçiş yapabilir ve bunları yeni sunuma kopyalayabilir, böylece birden fazla slaydı tek seferde notlarla birlikte PDF'ye dönüştürebilirsiniz.

### Aspose.Slides for Java için daha fazla dokümanı nerede bulabilirim?

Aspose.Slides for Java için detaylı dokümanları şu sitede bulabilirsiniz: [Java API Referansı için Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}