---
title: Java Slaytlarına Tüm Yazı Tiplerini Gömerek Sunumu HTML'ye Dönüştürme
linktitle: Java Slaytlarına Tüm Yazı Tiplerini Gömerek Sunumu HTML'ye Dönüştürme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak sunumları gömülü yazı tipleriyle HTML'ye nasıl dönüştüreceğinizi öğrenin. Bu adım adım kılavuz, kusursuz paylaşım için tutarlı biçimlendirme sağlar.
weight: 13
url: /tr/java/presentation-conversion/convert-presentation-html-embed-fonts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarına Tüm Yazı Tiplerini Gömerek Sunumu HTML'ye Dönüştürme


## Java Slaytlarına Tüm Yazı Tiplerini Gömerek Sunumu HTML'ye Dönüştürmeye Giriş

Günümüzün dijital çağında, çeşitli platformlarda bilgilerin sorunsuz bir şekilde paylaşılması için sunumların HTML'ye dönüştürülmesi zorunlu hale geldi. Java Slaytları ile çalışırken tutarlı biçimlendirmeyi korumak için sunumunuzda kullanılan tüm yazı tiplerinin gömülü olduğundan emin olmak çok önemlidir. Bu adım adım kılavuzda, Aspose.Slides for Java kullanarak tüm yazı tiplerini gömerken bir sunumu HTML'ye dönüştürme sürecinde size yol göstereceğiz. Başlayalım!

## Önkoşullar

Koda ve dönüştürme sürecine dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Slides for Java API'sini şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/slides/java/).
-  Bir sunum dosyası (örn.`presentation.pptx`) HTML'ye dönüştürmek istediğiniz.

## 1. Adım: Java Ortamını Kurma

Sisteminizde Java ve Aspose.Slides for Java API'nin düzgün şekilde kurulu olduğundan emin olun. Kurulum talimatları için belgelere başvurabilirsiniz.

## Adım 2: Sunum Dosyasını Yükleme

Java kodunuzda dönüştürmek istediğiniz sunum dosyasını yüklemeniz gerekmektedir. Yer değiştirmek`"Your Document Directory"` sunum dosyanızın gerçek yolunu belirtin.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## 3. Adım: Tüm Yazı Tiplerini Sunuma Gömme

Sunumda kullanılan tüm yazı tiplerini gömmek için aşağıdaki kod parçasını kullanabilirsiniz. Bu, HTML çıktısının tutarlı görüntü oluşturma için gerekli tüm yazı tiplerini içermesini sağlar.

```java
try
{
    // Varsayılan sunum yazı tiplerini hariç tut
    String[] fontNameExcludeList = {  };
    LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, "C:\\Windows\\Fonts\\");
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(linkcont));
    pres.save("Your Output Directory" + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Adım 4: Sunumu HTML'ye Dönüştürme

Artık tüm yazı tiplerini yerleştirdiğimize göre sunumu HTML'ye dönüştürmenin zamanı geldi. Adım 3'te verilen kod bu dönüşümü gerçekleştirecektir.

## Adım 5: HTML Dosyasını Kaydetme

Son adım, HTML dosyasını gömülü yazı tipleriyle kaydetmektir. HTML dosyası, tüm yazı tiplerinin dahil edildiğinden emin olmak için belirtilen dizine kaydedilecektir.

Bu kadar! Aspose.Slides for Java'yı kullanarak tüm yazı tiplerini gömerken bir sunumu başarıyla HTML'ye dönüştürdünüz.

## Kaynak Kodunu Tamamlayın

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
try
{
	// varsayılan sunum yazı tiplerini hariç tut
	String[] fontNameExcludeList = {  };
	LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, "C:\\Windows\\Fonts\\");
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(linkcont));
	pres.save("Your Output Directory" + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Sunumları gömülü yazı tipleriyle HTML'ye dönüştürmek, farklı platformlarda tutarlı biçimlendirmeyi korumak için çok önemlidir. Aspose.Slides for Java ile bu süreç basit ve verimli hale geliyor. Artık yazı tiplerinin eksik olmasından endişe etmeden sunumlarınızı HTML formatında paylaşabilirsiniz.

## SSS

### Tüm yazı tiplerinin HTML çıktısına gömülü olup olmadığını nasıl kontrol edebilirim?

HTML dosyasının kaynak kodunu inceleyebilir ve yazı tipi referanslarını arayabilirsiniz. Sunumda kullanılan tüm yazı tiplerine HTML dosyasında başvurulmalıdır.

### HTML çıktısını stil ve düzen gibi daha da özelleştirebilir miyim?

 Evet, HTML çıktısını değiştirerek özelleştirebilirsiniz.`HtmlOptions` ve biçimlendirme için kullanılan HTML şablonu. Aspose.Slides for Java bu konuda esneklik sağlar.

### Yazı tiplerini HTML'ye gömerken herhangi bir sınırlama var mı?

Yazı tiplerini gömmek tutarlı görüntü oluşturmayı sağlarken, bunun HTML çıktısının dosya boyutunu artırabileceğini unutmayın. Kaliteyi ve dosya boyutunu dengelemek için sunuyu optimize ettiğinizden emin olun.

### Bu yöntemi kullanarak karmaşık içeriğe sahip sunumları HTML'ye dönüştürebilir miyim?

Evet, bu yöntem resimler, animasyonlar ve multimedya öğeleri dahil olmak üzere karmaşık içeriğe sahip sunumlar için işe yarar. Aspose.Slides for Java, dönüştürme işlemini etkili bir şekilde gerçekleştirir.

### Aspose.Slides for Java için daha fazla kaynağı ve belgeyi nerede bulabilirim?

 Aspose.Slides for Java'ya ilişkin kapsamlı belgelere ve kaynaklara şu adresten ulaşabilirsiniz:[Java API Referansları için Aspose.Slides](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
