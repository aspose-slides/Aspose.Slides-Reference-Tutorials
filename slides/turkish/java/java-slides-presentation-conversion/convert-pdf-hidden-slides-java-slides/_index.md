---
title: Java Slaytlarında Gizli Slaytlarla PDF'ye Dönüştürme
linktitle: Java Slaytlarında Gizli Slaytlarla PDF'ye Dönüştürme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarını gizli slaytlarla PDF'ye nasıl dönüştüreceğinizi öğrenin. Sorunsuz PDF oluşturmak için kaynak kodlu adım adım kılavuzumuzu izleyin.
weight: 27
url: /tr/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Gizli Slaytlarla PDF'ye Dönüştürme


## Aspose.Slides for Java kullanarak PowerPoint Sunumunu Gizli Slaytlarla PDF'ye Dönüştürmeye Giriş

Bu adım adım kılavuzda, Aspose.Slides for Java kullanarak gizli slaytları korurken bir PowerPoint sunumunu PDF'ye nasıl dönüştüreceğinizi öğreneceksiniz. Gizli slaytlar, normal bir sunum sırasında görüntülenmeyen ancak PDF çıktısına eklenebilen slaytlardır. Bu görevi gerçekleştirmek için size kaynak kodunu ve ayrıntılı talimatları sağlayacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Aspose.Slides for Java Kütüphanesi: Java projenizde Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/).

2. Java Geliştirme Ortamı: Sisteminizde Java geliştirme ortamının kurulu olması gerekmektedir.

## Adım 1: Aspose.Slides for Java'yı içe aktarın

Öncelikle Aspose.Slides kütüphanesini Java projenize aktarmanız gerekiyor. Kütüphaneyi projenizin derleme yoluna eklediğinizden emin olun.

```java
import com.aspose.slides.*;
```

## Adım 2: PowerPoint Sunumunu Yükleyin

 PDF'ye dönüştürmek istediğiniz PowerPoint sunumunu yükleyerek başlayacaksınız. Yer değiştirmek`"Your Document Directory"` Ve`"HiddingSlides.pptx"` uygun dosya yolu ile.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## 3. Adım: PDF Seçeneklerini Yapılandırın

PDF çıktısına gizli slaytları dahil etmek için PDF seçeneklerini yapılandırın. Bunu ayarlayarak yapabilirsiniz`setShowHiddenSlides` mülkiyeti`PdfOptions` sınıf`true`.

```java
// PdfOptions sınıfını örnekleyin
PdfOptions pdfOptions = new PdfOptions();
// Oluşturulan belgenin gizli slaytlar içermesi gerektiğini belirtin
pdfOptions.setShowHiddenSlides(true);
```

## Adım 4: Sunuyu PDF olarak kaydedin

 Şimdi sunuyu belirtilen seçeneklerle bir PDF dosyasına kaydedin. Yer değiştirmek`"PDFWithHiddenSlides_out.pdf"` İstediğiniz çıktı dosyası adı ile.

```java
// Sunuyu belirtilen seçeneklerle PDF'ye kaydedin
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Adım 5: Kaynakları Temizleme

Sunumla işiniz bittiğinde, sunum tarafından kullanılan kaynakları serbest bıraktığınızdan emin olun.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Java Slaytlarında Gizli Slaytlarla PDF'ye Dönüştürmek İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// PdfOptions sınıfını örnekleyin
	PdfOptions pdfOptions = new PdfOptions();
	// Oluşturulan belgenin gizli slaytlar içermesi gerektiğini belirtin
	pdfOptions.setShowHiddenSlides(true);
	// Sunuyu belirtilen seçeneklerle PDF'ye kaydedin
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Bu kapsamlı kılavuzda, Aspose.Slides for Java kullanarak bir PowerPoint sunumunu gizli slaytları korurken PDF'ye nasıl dönüştüreceğinizi öğrendiniz. Bu görevi sorunsuz bir şekilde gerçekleştirmek için size gerekli kaynak koduyla birlikte adım adım bir eğitim sağladık.

## SSS'ler

### PowerPoint sunumundaki slaytları nasıl gizleyebilirim?

PowerPoint sunumundaki bir slaydı gizlemek için şu adımları izleyin:
1. Slayt Sıralayıcısı görünümünde gizlemek istediğiniz slaydı seçin.
2. Seçilen slayda sağ tıklayın.
3. Bağlam menüsünden "Slaytı Gizle" seçeneğini seçin.

### Aspose.Slides for Java'da gizli slaytları programlı olarak gösterebilir miyim?

 Evet, Aspose.Slides for Java'da gizli slaytları program aracılığıyla gösterebilirsiniz.`Hidden` mülkiyeti`Slide` sınıf`false`. İşte bir örnek:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // SlideIndex'i gizli slaydın indeksiyle değiştirin
slide.setHidden(false);
```

### Aspose.Slides for Java'yı nasıl indirebilirim?

 Aspose.Slides for Java'yı Aspose web sitesinden indirebilirsiniz. Ziyaret edin[Aspose.Slides for Java indirme sayfası](https://releases.aspose.com/slides/java/) En son sürümü almak için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
