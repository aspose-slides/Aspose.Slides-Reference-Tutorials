---
"description": "Aspose.Slides for Java kullanarak PowerPoint sunumlarını gizli slaytlarla PDF'ye nasıl dönüştüreceğinizi öğrenin. Sorunsuz PDF üretimi için kaynak kodlu adım adım kılavuzumuzu izleyin."
"linktitle": "Java Slaytlarında Gizli Slaytlarla PDF'ye Dönüştürme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Gizli Slaytlarla PDF'ye Dönüştürme"
"url": "/tr/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Gizli Slaytlarla PDF'ye Dönüştürme


## Aspose.Slides for Java kullanarak PowerPoint Sunumunu Gizli Slaytlarla PDF'ye Dönüştürmeye Giriş

Bu adım adım kılavuzda, Aspose.Slides for Java kullanarak gizli slaytları koruyarak bir PowerPoint sunumunu PDF'ye nasıl dönüştüreceğinizi öğreneceksiniz. Gizli slaytlar, normal bir sunum sırasında görüntülenmeyen ancak PDF çıktısına dahil edilebilen slaytlardır. Bu görevi başarmanız için size kaynak kodu ve ayrıntılı talimatlar sağlayacağız.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. Aspose.Slides for Java Kütüphanesi: Java projenizde Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun. Bunu şuradan indirebilirsiniz: [Java belgeleri için Aspose.Slides](https://reference.aspose.com/slides/java/).

2. Java Geliştirme Ortamı: Sisteminizde bir Java geliştirme ortamının yüklü olması gerekir.

## Adım 1: Java için Aspose.Slides'ı içe aktarın

Öncelikle Aspose.Slides kütüphanesini Java projenize aktarmanız gerekiyor. Kütüphaneyi projenizin yapı yoluna eklediğinizden emin olun.

```java
import com.aspose.slides.*;
```

## Adım 2: PowerPoint Sunumunu Yükleyin

PDF'ye dönüştürmek istediğiniz PowerPoint sunumunu yükleyerek başlayacaksınız. Değiştir `"Your Document Directory"` Ve `"HiddingSlides.pptx"` uygun dosya yolu ile.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Adım 3: PDF Seçeneklerini Yapılandırın

PDF seçeneklerini, PDF çıktısına gizli slaytları ekleyecek şekilde yapılandırın. Bunu, `setShowHiddenSlides` mülkiyeti `PdfOptions` sınıfa `true`.

```java
// PdfOptions sınıfını örneklendirin
PdfOptions pdfOptions = new PdfOptions();
// Oluşturulan belgenin gizli slaytları içermesi gerektiğini belirtin
pdfOptions.setShowHiddenSlides(true);
```

## Adım 4: Sunumu PDF olarak kaydedin

Şimdi, sunumu belirtilen seçeneklerle bir PDF dosyasına kaydedin. Değiştir `"PDFWithHiddenSlides_out.pdf"` İstediğiniz çıktı dosya adı ile.

```java
// Sunuyu belirtilen seçeneklerle PDF'e kaydedin
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Adım 5: Kaynakları Temizleme

Sunumunuz bittiğinde kullandığınız kaynakları yayınlamayı unutmayın.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Java Slaytlarında Gizli Slaytlarla PDF'ye Dönüştürmek İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// PdfOptions sınıfını örneklendirin
	PdfOptions pdfOptions = new PdfOptions();
	// Oluşturulan belgenin gizli slaytları içermesi gerektiğini belirtin
	pdfOptions.setShowHiddenSlides(true);
	// Sunuyu belirtilen seçeneklerle PDF'e kaydedin
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Bu kapsamlı kılavuzda, Aspose.Slides for Java kullanarak gizli slaytları koruyarak bir PowerPoint sunumunu PDF'ye nasıl dönüştüreceğinizi öğrendiniz. Bu görevi sorunsuz bir şekilde başarmanız için gerekli kaynak koduyla birlikte adım adım bir eğitim sağladık.

## SSS

### PowerPoint sunumunda slaytları nasıl gizleyebilirim?

PowerPoint sunumunda bir slaydı gizlemek için şu adımları izleyin:
1. Slayt Sıralayıcısı görünümünde gizlemek istediğiniz slaydı seçin.
2. Seçili slayta sağ tıklayın.
3. Bağlam menüsünden "Slaydı Gizle" seçeneğini seçin.

### Aspose.Slides for Java'da gizli slaytları program aracılığıyla gösterebilir miyim?

Evet, Java için Aspose.Slides'da gizli slaytları programatik olarak gösterebilirsiniz. `Hidden` mülkiyeti `Slide` sınıfa `false`İşte bir örnek:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // slideIndex'i gizli slaydın diziniyle değiştirin
slide.setHidden(false);
```

### Aspose.Slides for Java'yı nasıl indirebilirim?

Aspose.Slides for Java'yı Aspose web sitesinden indirebilirsiniz. [Aspose.Slides for Java indirme sayfası](https://releases.aspose.com/slides/java/) En son sürümü edinmek için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}