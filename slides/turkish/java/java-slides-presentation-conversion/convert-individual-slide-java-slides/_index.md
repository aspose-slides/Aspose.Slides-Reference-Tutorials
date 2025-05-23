---
"description": "Aspose.Slides for Java kullanarak kod örnekleriyle tek tek PowerPoint slaytlarını adım adım HTML'ye nasıl dönüştüreceğinizi öğrenin."
"linktitle": "Java Slaytlarında Bireysel Slaytları Dönüştürme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Bireysel Slaytları Dönüştürme"
"url": "/tr/java/presentation-conversion/convert-individual-slide-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Bireysel Slaytları Dönüştürme


## Java Slaytlarında Bireysel Slaytları Dönüştürmeye Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumundan tek tek slaytları HTML'ye dönüştürme sürecini ele alacağız. Bu adım adım kılavuz, bu görevi başarmanıza yardımcı olacak kaynak kodu ve açıklamaları sağlayacaktır.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Java için Aspose.Slides kütüphanesi kuruldu.
- Bir PowerPoint sunum dosyası (`Individual-Slide.pptx`) dönüştürmek istediğiniz.
- Java geliştirme ortamı kuruldu.

## Adım 1: Projeyi Kurun

1. Tercih ettiğiniz geliştirme ortamında bir Java projesi oluşturun.
2. Projenize Aspose.Slides for Java kütüphanesini ekleyin.

## Adım 2: Gerekli Sınıfları İçeri Aktarın

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

Tek tek slaytların dönüşümünü gerçekleştirmek için bir yöntem oluşturun. Değiştirdiğinizden emin olun `"Your Document Directory"` belge dizininize giden gerçek yol ile.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // Dosya kaydediliyor
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Adım 4: CustomFormattingController'ı uygulayın

Oluştur `CustomFormattingController` Dönüştürme sırasında özel biçimlendirmeyi işleyen sınıf.

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

## Adım 5: Dönüştürmeyi Gerçekleştirin

Son olarak, şunu arayın: `convertIndividualSlides` dönüştürme işlemini yürütme yöntemi.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Java Slaytlarında Bireysel Slaytları Dönüştürmek İçin Tam Kaynak Kodu

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// Dosya kaydediliyor              
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

Aspose.Slides for Java kullanarak bir PowerPoint sunumundan tek tek slaytları başarıyla HTML'ye dönüştürdünüz. Bu eğitim size bu görevi başarmanız için gereken kodu ve adımları sağladı. Çıktıyı ve biçimlendirmeyi özel gereksinimleriniz için gerektiği gibi özelleştirmekten çekinmeyin.

## SSS

### HTML çıktısını daha fazla nasıl özelleştirebilirim?

HTML çıktısını değiştirerek özelleştirebilirsiniz. `CustomFormattingController` sınıf. Ayarla `writeSlideStart` Ve `writeSlideEnd` Slayt HTML yapısını ve stilini değiştirme yöntemleri.

### Birden fazla PowerPoint sunumunu tek seferde dönüştürebilir miyim?

Evet, kodu birden fazla sunum dosyası arasında geçiş yapacak ve bunları tek tek dönüştürecek şekilde değiştirebilirsiniz. `convertIndividualSlides` Her sunum için bir yöntem.

### Slaytlardaki şekiller ve metinler için ek biçimlendirmeyi nasıl hallederim?

Uzatabilirsiniz `CustomFormattingController` şekil-özel biçimlendirmeyi uygulayarak işlemek için sınıf `writeShapeStart` Ve `writeShapeEnd` yöntemleri ve bunlar içinde özel biçimlendirme mantığının uygulanması.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}