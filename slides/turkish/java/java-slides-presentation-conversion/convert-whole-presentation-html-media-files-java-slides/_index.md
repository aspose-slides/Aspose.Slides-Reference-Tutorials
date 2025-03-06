---
title: Java Slaytlarındaki Medya Dosyalarıyla Tüm Sunumu HTML'ye Dönüştürün
linktitle: Java Slaytlarındaki Medya Dosyalarıyla Tüm Sunumu HTML'ye Dönüştürün
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Java Slaytlar'ı kullanarak sunumları medya dosyalarıyla HTML'ye nasıl dönüştüreceğinizi öğrenin. Aspose.Slides for Java API ile adım adım kılavuzumuzu takip edin.
weight: 30
url: /tr/java/presentation-conversion/convert-whole-presentation-html-media-files-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java Slaytlarında Medya Dosyalarıyla Tüm Sunumu HTML'ye Dönüştürmeye Giriş

Günümüzün dijital çağında sunumları HTML dahil çeşitli formatlara dönüştürme ihtiyacı yaygın bir gereksinimdir. Java geliştiricileri genellikle kendilerini bu zorlukla görevlendirilmiş halde bulurlar. Neyse ki Aspose.Slides for Java API ile bu görev verimli bir şekilde gerçekleştirilebilir. Bu adım adım kılavuzda, Java Slaytlar'ı kullanarak medya dosyalarını korurken bir sunumun tamamını HTML'ye nasıl dönüştüreceğimizi keşfedeceğiz.

## Önkoşullar

Kodlama konusuna dalmadan önce her şeyin doğru şekilde kurulduğundan emin olalım:

- Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
-  Aspose.Slides for Java: Aspose.Slides for Java API'sinin kurulu olması gerekir. İndirebilirsin[Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Gerekli Paketleri İçe Aktarın

Başlamak için gerekli paketleri içe aktarmanız gerekir. Bu paketler görevimiz için gereken sınıfları ve yöntemleri sağlayacaktır.

```java
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SlideImageFormat;
import com.aspose.slides.SVGOptions;
import com.aspose.slides.VideoPlayerHtmlController;
```

## Adım 2: Belge Dizinini Belirleyin

 Sunum dosyasının bulunduğu belge dizininizin yolunu tanımlayın. Yer değiştirmek`"Your Document Directory"` gerçek yol ile.

```java
String dataDir = "Your Document Directory";
```

## 3. Adım: Sunumu Başlatın

 HTML'ye dönüştürmek istediğiniz sunuyu yükleyin. Değiştirdiğinizden emin olun`"presentationWith.pptx"` sununuzun dosya adıyla birlikte.

```java
Presentation pres = new Presentation("presentationWith.pptx");
```

## Adım 4: HTML Denetleyicisini Oluşturun

 Bir oluşturacağız`VideoPlayerHtmlController` dönüşüm sürecini yönetmek için. URL'yi istediğiniz web adresiyle değiştirin.

```java
VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
    "", htmlDocumentFileName, "http://www.example.com/");
```

## 5. Adım: HTML ve SVG Seçeneklerini Yapılandırın

Dönüşüm için HTML ve SVG seçeneklerini ayarlayın. Biçimlendirmeyi gerektiği gibi özelleştirebileceğiniz yer burasıdır.

```java
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);
htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
```

## Adım 6: Sunuyu HTML olarak kaydedin

Artık sunumu medya dosyaları da dahil olmak üzere bir HTML dosyası olarak kaydetmenin zamanı geldi.

```java
pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
```

## Java Slaytlarında Medya Dosyalarıyla Sunumun Tamamını HTML'ye Dönüştürmek İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
String htmlDocumentFileName = "presentationWithVideo.html";
Presentation pres = new Presentation("presentationWith.pptx");
try
{
	VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
			"", htmlDocumentFileName, "http://www.example.com/");
	HtmlOptions htmlOptions = new HtmlOptions(controller);
	SVGOptions svgOptions = new SVGOptions(controller);
	htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
	htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
	pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Java Slides ve Aspose.Slides for Java API'sini kullanarak bir sunumun tamamını medya dosyalarıyla HTML'ye dönüştürme sürecini anlattık. Bu adımları izleyerek sunumlarınızı etkili bir şekilde web dostu bir formata dönüştürebilir ve tüm temel medya unsurlarını koruyabilirsiniz.

## SSS'ler

### Aspose.Slides for Java'yı nasıl kurabilirim?

 Aspose.Slides for Java'yı yüklemek için şu adresteki indirme sayfasını ziyaret edin:[Burada](https://releases.aspose.com/slides/java/) ve verilen kurulum talimatlarını izleyin.

### HTML çıktısını daha da özelleştirebilir miyim?

 Evet, HTML çıktısını gereksinimlerinize göre özelleştirebilirsiniz.`HtmlOptions` class, biçimlendirme ve düzen seçenekleri de dahil olmak üzere dönüştürme sürecini kontrol etmek için çeşitli ayarlar sağlar.

### Aspose.Slides for Java diğer çıktı formatlarını destekliyor mu?

Evet, Aspose.Slides for Java; PDF, PPTX ve daha fazlası dahil olmak üzere çeşitli çıktı formatlarını destekler. Bu seçenekleri belgelerde keşfedebilirsiniz.

### Aspose.Slides for Java ticari projelere uygun mu?

Evet, Aspose.Slides for Java, Java uygulamalarında sunumla ilgili görevlerin yerine getirilmesi için sağlam ve ticari açıdan uygun bir çözümdür. Kurumsal düzeydeki projelerde yaygın olarak kullanılmaktadır.

### Dönüştürülen HTML sunumuna nasıl erişebilirim?

 Dönüşümü tamamladıktan sonra, belirtilen dosyayı bularak HTML sunumuna erişebilirsiniz.`htmlDocumentFileName` değişken.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
