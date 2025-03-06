---
title: Aspose.Slides for Java kullanarak Fontları HTML'ye gömme
linktitle: Aspose.Slides for Java kullanarak Fontları HTML'ye gömme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Farklı platformlar ve cihazlarda tutarlı tipografi sağlamak için Aspose.Slides for Java'yı kullanarak yazı tiplerini HTML'ye nasıl yerleştireceğinizi öğrenin.
weight: 13
url: /tr/java/java-powerpoint-font-management/embed-fonts-in-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak değiştirmek isteyen Java geliştiricileri için güçlü bir araçtır. Bu eğitimde Aspose.Slides for Java kullanarak yazı tiplerini HTML'ye yerleştirme sürecini ayrıntılı olarak ele alacağız. Yazı tiplerini gömerek, gerekli yazı tipleri yerel olarak yüklenmemiş olsa bile sunumlarınızın farklı platformlarda ve cihazlarda amaçlanan görünümünü korumasını sağlarsınız.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Slides for Java: Aspose.Slides for Java'yı şu adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): Java geliştirme için IntelliJ IDEA veya Eclipse gibi tercih ettiğiniz IDE'yi seçin.

## Paketleri İçe Aktar
Aspose.Slides for Java'yı kullanarak yazı tiplerini HTML'ye gömmeye başlamak için öncelikle gerekli paketleri içe aktarmanız gerekir.
```java
import com.aspose.slides.*;
```
## Adım 1: Belge ve Çıktı Dizinlerini Tanımlayın
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
```
 Değiştirdiğinizden emin olun`"Your Document Directory"` Ve`"Your Output Directory"` sırasıyla giriş PowerPoint sunumunuza ve istenen çıktı dizinine giden yolları içerir.
## 2. Adım: Sunuyu Yükleyin
```java
Presentation pres = new Presentation(dataDir + "Presentation.pptx");
```
Bu adım, PowerPoint sunumunu belleğe yükleyerek üzerinde çeşitli işlemler gerçekleştirmenize olanak tanır.
## 3. Adım: Varsayılan Yazı Tiplerini Hariç Tut
```java
String[] fontNameExcludeList = { "Arial" };
```
Gömmenin dışında bırakmak istediğiniz yazı tiplerini belirtin. Bu örnekte Arial'ı hariç tutuyoruz.
## Adım 4: Yazı Tiplerini HTML'ye Gömme
```java
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
pres.save(outPath + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
```
 Bu adımda örneğini oluşturuyoruz.`EmbedAllFontsHtmlController` Hariç tutma listesinde belirtilenler dışındaki tüm yazı tiplerini gömmek için. Daha sonra tanımlarız`HtmlOptions`ve yazı tiplerini gömmek için özel bir HTML biçimlendirici ayarlayın. Son olarak sunumu gömülü fontlarla HTML olarak kaydediyoruz.

## Çözüm
Bu eğitimde Aspose.Slides for Java kullanarak yazı tiplerinin HTML'ye nasıl yerleştirileceğini araştırdık. Verilen adımları izleyerek sunumlarınızın farklı platformlar ve cihazlar arasında tutarlı tipografiyi korumasını sağlayarak genel görüntüleme deneyimini geliştirebilirsiniz.
## SSS'ler
### Belirli yazı tiplerini hariç tutmak yerine gömebilir miyim?
 Evet, eklemek istediğiniz yazı tiplerini değiştirerek belirleyebilirsiniz.`fontNameExcludeList` buna göre sıralayın.
### Aspose.Slides for Java, HTML'nin yanı sıra diğer formatlardaki yazı tiplerini de gömmeyi destekliyor mu?
Evet, Aspose.Slides, PDF ve görseller de dahil olmak üzere çeşitli çıktı formatlarına yazı tipi yerleştirmeyi destekler.
### Aspose.Slides for Java'nın deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Slides for Java ile ilgili ek destek veya yardımı nereden bulabilirim?
 Ziyaret edebilirsiniz[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) topluluk desteği için veya profesyonel yardım için Aspose desteğiyle iletişime geçin.
### Aspose.Slides for Java için geçici bir lisans satın alabilir miyim?
Evet, geçici lisansı şu adresten alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
