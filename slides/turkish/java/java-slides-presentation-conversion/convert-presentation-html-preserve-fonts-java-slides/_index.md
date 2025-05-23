---
"description": "Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarınızı orijinal yazı tiplerini koruyarak HTML'e dönüştürün."
"linktitle": "Java Slaytlarında Orijinal Yazı Tiplerini Koruyarak Sunumu HTML'ye Dönüştürme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Orijinal Yazı Tiplerini Koruyarak Sunumu HTML'ye Dönüştürme"
"url": "/tr/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Orijinal Yazı Tiplerini Koruyarak Sunumu HTML'ye Dönüştürme


## Java Slaytlarında Orijinal Yazı Tiplerini Koruyarak Sunumu HTML'ye Dönüştürmeye Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak orijinal yazı tiplerini koruyarak bir PowerPoint sunumunu (PPTX) HTML'ye nasıl dönüştüreceğimizi inceleyeceğiz. Bu, ortaya çıkan HTML'nin orijinal sunumun görünümüne yakın olmasını sağlayacaktır.

## Adım 1: Projenin Kurulumu
Koda dalmadan önce gerekli kurulumun yapıldığından emin olalım:

1. Aspose.Slides for Java'yı indirin: Eğer henüz yapmadıysanız, Aspose.Slides for Java kütüphanesini indirin ve projenize ekleyin.

2. Bir Java Projesi Oluşturun: Favori IDE'nizde bir Java projesi oluşturun ve Aspose.Slides JAR dosyasını yerleştirebileceğiniz bir "lib" klasörünüz olduğundan emin olun.

3. Gerekli Sınıfları İçe Aktar: Java dosyanızın başına gerekli sınıfları içe aktarın:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Adım 2: Sunumu Orijinal Yazı Tipleriyle HTML'ye Dönüştürme

Şimdi, orijinal yazı tiplerini koruyarak bir PowerPoint sunumunu HTML'e dönüştürelim:

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";

// Sunumu yükle
Presentation pres = new Presentation("input.pptx");

try {
    // Calibri ve Arial gibi varsayılan sunum yazı tiplerini hariç tutun
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // HTML seçenekleri oluşturun ve özel HTML biçimlendiricisini ayarlayın
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Sunumu HTML olarak kaydedin
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Sunum nesnesini elden çıkarın
    if (pres != null) pres.dispose();
}
```

Bu kod parçacığında:

- Giriş PowerPoint sunumunu kullanarak yüklüyoruz `Presentation`.

- Bir yazı tipleri listesi tanımlıyoruz (`fontNameExcludeList`) HTML'e yerleştirmekten hariç tutmak istediğimiz. Bu, dosya boyutunu azaltmak için Calibri ve Arial gibi yaygın yazı tiplerini hariç tutmak için yararlıdır.

- Bir örnek oluşturuyoruz `EmbedAllFontsHtmlController` ve font dışlama listesini ona iletin.

- Biz yaratıyoruz `HtmlOptions` ve kullanarak özel bir HTML biçimlendirici ayarlayın `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Son olarak sunumu belirtilen seçeneklerle HTML olarak kaydediyoruz.

## Java Slaytlarında Orijinal Yazı Tiplerini Koruyarak Sunumu HTML'ye Dönüştürmek İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
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

Bu eğitimde, Aspose.Slides for Java kullanarak orijinal yazı tiplerini koruyarak bir PowerPoint sunumunu HTML'ye nasıl dönüştüreceğinizi öğrendiniz. Bu, sunumlarınızı web'de paylaşırken görsel sadakatini korumak istediğinizde faydalıdır.

## SSS

### Aspose.Slides for Java'yı nasıl indirebilirim?

Aspose.Slides for Java'yı Aspose web sitesinden indirebilirsiniz. Ziyaret edin [Burada](https://downloads.aspose.com/slides/java/) En son sürümü edinmek için.

### Hariç tutulan yazı tiplerinin listesini özelleştirebilir miyim?

Evet, özelleştirebilirsiniz `fontNameExcludeList` İhtiyaçlarınıza göre belirli yazı tiplerini dahil etmek veya hariç tutmak için dizi.

### Bu yöntem PPT gibi eski PowerPoint formatlarında işe yarıyor mu?

Bu kod örneği PPTX dosyaları için tasarlanmıştır. Daha eski PPT dosyalarını dönüştürmeniz gerekiyorsa, kodda ayarlamalar yapmanız gerekebilir.

### HTML çıktısını nasıl daha fazla özelleştirebilirim?

Keşfedebilirsiniz `HtmlOptions` Slayt boyutu, resim kalitesi ve daha fazlası gibi HTML çıktısının çeşitli yönlerini özelleştirmek için kullanılan sınıf.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}