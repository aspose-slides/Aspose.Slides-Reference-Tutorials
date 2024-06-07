---
title: Java Slaytlarında Orijinal Yazı Tiplerini Koruyarak Sunumu HTML'ye Dönüştürme
linktitle: Java Slaytlarında Orijinal Yazı Tiplerini Koruyarak Sunumu HTML'ye Dönüştürme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak orijinal yazı tiplerini korurken PowerPoint sunumlarınızı HTML'ye dönüştürün.
type: docs
weight: 14
url: /tr/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

## Java Slaytlarında Orijinal Yazı Tiplerini Koruyarak Sunumu HTML'ye Dönüştürmeye Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak orijinal yazı tiplerini koruyarak bir PowerPoint sunumunu (PPTX) HTML'ye nasıl dönüştürebileceğinizi keşfedeceğiz. Bu, ortaya çıkan HTML'nin orijinal sunumun görünümüne çok benzemesini sağlayacaktır.

## Adım 1: Projeyi Ayarlama
Koda dalmadan önce gerekli kurulumun yapıldığından emin olalım:

1. Aspose.Slides for Java'yı indirin: Henüz yapmadıysanız Aspose.Slides for Java kütüphanesini indirin ve projenize ekleyin.

2. Java Projesi Oluşturun: Favori IDE'nizde bir Java projesi oluşturun ve Aspose.Slides JAR dosyasını yerleştirebileceğiniz bir "lib" klasörünüz olduğundan emin olun.

3. Gerekli Sınıfları İçe Aktar: Java dosyanızın başında gerekli sınıfları içe aktarın:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Adım 2: Sunumu Orijinal Yazı Tipleriyle HTML'ye Dönüştürme

Şimdi orijinal yazı tiplerini koruyarak bir PowerPoint sunumunu HTML'ye dönüştürelim:

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";

// Sunuyu yükle
Presentation pres = new Presentation("input.pptx");

try {
    //Calibri ve Arial gibi varsayılan sunum yazı tiplerini hariç tutun
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // HTML seçenekleri oluşturun ve özel HTML biçimlendiriciyi ayarlayın
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Sunuyu HTML olarak kaydet
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Sunum nesnesini atın
    if (pres != null) pres.dispose();
}
```

Bu kod parçacığında:

-  Giriş PowerPoint sunumunu kullanarak yüklüyoruz`Presentation`.

- Bir yazı tipi listesi tanımlarız (`fontNameExcludeList`) HTML'ye yerleştirilmesinin dışında tutmak istediğimiz. Bu, dosya boyutunu küçültmek amacıyla Calibri ve Arial gibi yaygın yazı tiplerini hariç tutmak için kullanışlıdır.

-  Bir örneğini oluşturuyoruz`EmbedAllFontsHtmlController` ve yazı tipi hariç tutma listesini ona iletin.

-  Biz yaratırız`HtmlOptions` ve kullanarak özel bir HTML biçimlendirici ayarlayın.`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Son olarak belirtilen seçeneklerle sunumu HTML olarak kaydediyoruz.

## Java Slaytlarında Orijinal Yazı Tiplerini Koruyarak Sunumu HTML'ye Dönüştürmek İçin Eksiksiz Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// varsayılan sunum yazı tiplerini hariç tut
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides for Java kullanarak bir PowerPoint sunumunu orijinal yazı tiplerini koruyarak HTML'ye nasıl dönüştüreceğinizi öğrendiniz. Bu, sunumlarınızı web'de paylaşırken görsel doğruluğunu korumak istediğinizde kullanışlıdır.

## SSS'ler

### Aspose.Slides for Java'yı nasıl indirebilirim?

Aspose.Slides for Java'yı Aspose web sitesinden indirebilirsiniz. Ziyaret etmek[Burada](https://downloads.aspose.com/slides/java/) En son sürümü almak için.

### Hariç tutulan yazı tiplerinin listesini özelleştirebilir miyim?

 Evet, özelleştirebilirsiniz`fontNameExcludeList` Gereksinimlerinize göre belirli yazı tiplerini dahil etmek veya hariç tutmak için dizi.

### Bu yöntem PPT gibi eski PowerPoint formatlarında işe yarar mı?

Bu kod örneği PPTX dosyaları için tasarlanmıştır. Eski PPT dosyalarını dönüştürmeniz gerekiyorsa kodda ayarlamalar yapmanız gerekebilir.

### HTML çıktısını nasıl daha da özelleştirebilirim?

 Keşfedebilirsiniz`HtmlOptions` HTML çıktısının slayt boyutu, görüntü kalitesi ve daha fazlası gibi çeşitli yönlerini özelleştirmek için sınıf.