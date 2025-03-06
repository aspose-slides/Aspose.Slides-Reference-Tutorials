---
title: Java Slaytlarında Bireysel Slaydı Dönüştürme
linktitle: Java Slaytlarında Bireysel Slaydı Dönüştürme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak ayrı ayrı PowerPoint slaytlarını adım adım kod örnekleriyle HTML'ye nasıl dönüştüreceğinizi öğrenin.
weight: 12
url: /tr/java/presentation-conversion/convert-individual-slide-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java Slaytlarında Bireysel Slaytları Dönüştürmeye Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak tek tek slaytları PowerPoint sunumundan HTML'ye dönüştürme sürecini anlatacağız. Bu adım adım kılavuz, bu görevi başarmanıza yardımcı olacak kaynak kodunu ve açıklamaları sağlayacaktır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.Slides for Java kütüphanesi kuruldu.
- Bir PowerPoint sunum dosyası (`Individual-Slide.pptx`) dönüştürmek istediğinizi seçin.
- Java geliştirme ortamı kuruldu.

## 1. Adım: Projeyi Kurun

1. Tercih ettiğiniz geliştirme ortamında bir Java projesi oluşturun.
2. Aspose.Slides for Java kütüphanesini projenize ekleyin.

## Adım 2: Gerekli Sınıfları İçe Aktarın

Java sınıfınızda gerekli sınıfları içe aktarın ve ilk yapılandırmayı ayarlayın.

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

## Adım 3: Ana Dönüşüm Yöntemini Tanımlayın

 Tek tek slaytların dönüştürülmesini gerçekleştirmek için bir yöntem oluşturun. Değiştirdiğinizden emin olun`"Your Document Directory"` belge dizininizin gerçek yolu ile.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // Dosya Kaydediliyor
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Adım 4: CustomFormattingController'ı uygulayın

 Oluştur`CustomFormattingController` dönüştürme sırasında özel biçimlendirmeyi işlemek için sınıf.

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

## Adım 5: Dönüşümü Gerçekleştirin

 Son olarak, şu numarayı arayın:`convertIndividualSlides` Dönüştürme işlemini yürütme yöntemi.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Java Slaytlarında Bireysel Slaydı Dönüştürmek İçin Tam Kaynak Kodu

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// Dosya Kaydediliyor
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

## Çözüm

Aspose.Slides for Java'yı kullanarak tek tek slaytları PowerPoint sunumundan HTML'ye başarıyla dönüştürdünüz. Bu eğitimde size bu görevi gerçekleştirmek için gerekli kod ve adımlar sağlanmıştır. Çıktıyı ve biçimlendirmeyi özel gereksinimlerinize göre özelleştirmekten çekinmeyin.

## SSS'ler

### HTML çıktısını nasıl daha da özelleştirebilirim?

 HTML çıktısını değiştirerek özelleştirebilirsiniz.`CustomFormattingController` sınıf. Ayarlayın`writeSlideStart` Ve`writeSlideEnd` Slayt HTML yapısını ve stilini değiştirme yöntemleri.

### Birden fazla PowerPoint sunumunu tek seferde dönüştürebilir miyim?

 Evet, kodu birden fazla sunum dosyası arasında geçiş yapacak şekilde değiştirebilir ve bunları tek tek dönüştürebilirsiniz.`convertIndividualSlides` Her sunum için yöntem.

### Slaytlardaki şekiller ve metinler için ek biçimlendirmeyi nasıl hallederim?

 Uzatabilirsiniz`CustomFormattingController` sınıfını uygulayarak şekle özgü biçimlendirmeyi işlemek için`writeShapeStart` Ve`writeShapeEnd` yöntemler ve bunların içinde özel biçimlendirme mantığının uygulanması.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
