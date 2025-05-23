---
"description": "Aspose.Slides for Java kullanarak sunumları gömülü yazı tipleriyle HTML'ye nasıl dönüştüreceğinizi öğrenin. Bu adım adım kılavuz, sorunsuz paylaşım için tutarlı biçimlendirmeyi garanti eder."
"linktitle": "Java Slaytlarında Tüm Yazı Tiplerini Yerleştirerek Sunumu HTML'ye Dönüştürme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Tüm Yazı Tiplerini Yerleştirerek Sunumu HTML'ye Dönüştürme"
"url": "/tr/java/presentation-conversion/convert-presentation-html-embed-fonts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Tüm Yazı Tiplerini Yerleştirerek Sunumu HTML'ye Dönüştürme


## Java Slaytlarında Tüm Yazı Tiplerini Yerleştirerek Sunumu HTML'ye Dönüştürmeye Giriş

Günümüzün dijital çağında, sunumları HTML'ye dönüştürmek, çeşitli platformlar arasında sorunsuz bir şekilde bilgi paylaşımı için olmazsa olmaz hale geldi. Java Slaytları ile çalışırken, tutarlı biçimlendirmeyi korumak için sunumunuzda kullanılan tüm yazı tiplerinin yerleştirildiğinden emin olmak çok önemlidir. Bu adım adım kılavuzda, Java için Aspose.Slides'ı kullanarak tüm yazı tiplerini yerleştirirken bir sunumu HTML'ye dönüştürme sürecinde size yol göstereceğiz. Başlayalım!

## Ön koşullar

Koda ve dönüştürme sürecine dalmadan önce, aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Sisteminizde Java Development Kit (JDK) yüklü.
- Java API için Aspose.Slides'ı şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).
- Bir sunum dosyası (örneğin, `presentation.pptx`) HTML'e dönüştürmek istediğiniz.

## Adım 1: Java Ortamını Kurma

Sisteminizde Java ve Aspose.Slides for Java API'nin düzgün bir şekilde kurulu olduğundan emin olun. Kurulum talimatları için belgelere başvurabilirsiniz.

## Adım 2: Sunum Dosyasını Yükleme

Java kodunuzda, dönüştürmek istediğiniz sunum dosyasını yüklemeniz gerekir. Değiştir `"Your Document Directory"` sunum dosyanızın gerçek yolunu içerir.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Adım 3: Tüm Yazı Tiplerini Sunuma Yerleştirme

Sunumda kullanılan tüm yazı tiplerini yerleştirmek için aşağıdaki kod parçacığını kullanabilirsiniz. Bu, HTML çıktısının tutarlı işleme için gerekli tüm yazı tiplerini içereceğinden emin olmanızı sağlar.

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

Artık tüm fontları yerleştirdiğimize göre, sunumu HTML'e dönüştürme zamanı geldi. 3. Adımda sağlanan kod bu dönüşümü halledecektir.

## Adım 5: HTML Dosyasını Kaydetme

Son adım, gömülü fontlarla HTML dosyasını kaydetmektir. HTML dosyası belirtilen dizine kaydedilecek ve tüm fontların dahil edildiğinden emin olunacaktır.

İşte bu kadar! Aspose.Slides for Java kullanarak tüm yazı tiplerini yerleştirerek bir sunumu başarıyla HTML'e dönüştürdünüz.

## Tam Kaynak Kodu

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

Sunumları gömülü yazı tipleriyle HTML'ye dönüştürmek, farklı platformlarda tutarlı biçimlendirmeyi sürdürmek için çok önemlidir. Java için Aspose.Slides ile bu süreç basit ve verimli hale gelir. Artık eksik yazı tipleri konusunda endişelenmeden sunumlarınızı HTML biçiminde paylaşabilirsiniz.

## SSS

### HTML çıktısına tüm fontların gömülü olup olmadığını nasıl kontrol edebilirim?

HTML dosyasının kaynak kodunu inceleyebilir ve font referanslarını arayabilirsiniz. Sunumda kullanılan tüm fontlara HTML dosyasında referans verilmelidir.

### HTML çıktısını stil ve düzen gibi konularda daha fazla özelleştirebilir miyim?

Evet, HTML çıktısını değiştirerek özelleştirebilirsiniz. `HtmlOptions` ve biçimlendirme için kullanılan HTML şablonu. Java için Aspose.Slides bu konuda esneklik sağlar.

### HTML'e font eklerken herhangi bir sınırlama var mı?

Yazı tiplerini yerleştirmek tutarlı bir işlemeyi garantilerken, HTML çıktısının dosya boyutunu artırabileceğini unutmayın. Kalite ve dosya boyutunu dengelemek için sunumu optimize ettiğinizden emin olun.

### Bu yöntemi kullanarak karmaşık içerikli sunumları HTML'e dönüştürebilir miyim?

Evet, bu yöntem, resimler, animasyonlar ve multimedya öğeleri de dahil olmak üzere karmaşık içerikli sunumlar için işe yarar. Java için Aspose.Slides, dönüştürmeyi etkili bir şekilde gerçekleştirir.

### Aspose.Slides for Java için daha fazla kaynak ve belgeyi nerede bulabilirim?

Java için Aspose.Slides'a ilişkin kapsamlı belgelere ve kaynaklara şu adresten erişebilirsiniz: [Java API Referansları için Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}