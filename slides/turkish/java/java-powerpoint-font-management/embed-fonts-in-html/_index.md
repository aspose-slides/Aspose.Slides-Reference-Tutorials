---
"description": "Farklı platformlar ve cihazlarda tutarlı tipografi sağlamak için Aspose.Slides for Java'yı kullanarak HTML'e font yerleştirmeyi öğrenin."
"linktitle": "Aspose.Slides for Java kullanarak HTML'e Fontları Gömün"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Aspose.Slides for Java kullanarak HTML'e Fontları Gömün"
"url": "/tr/java/java-powerpoint-font-management/embed-fonts-in-html/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for Java kullanarak HTML'e Fontları Gömün

## giriiş
Aspose.Slides for Java, PowerPoint sunumlarını programatik olarak düzenlemek isteyen Java geliştiricileri için güçlü bir araçtır. Bu eğitimde, Aspose.Slides for Java kullanarak HTML'e font yerleştirme sürecini inceleyeceğiz. Font yerleştirerek, gerekli fontlar yerel olarak yüklenmemiş olsa bile sunumlarınızın farklı platformlarda ve cihazlarda amaçlanan görünümünü korumasını sağlarsınız.
## Ön koşullar
Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın yüklü olduğundan emin olun.
2. Java için Aspose.Slides: Java için Aspose.Slides'ı indirin ve yükleyin [indirme sayfası](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA veya Eclipse gibi Java geliştirme için tercih ettiğiniz IDE'yi seçin.

## Paketleri İçe Aktar
Öncelikle Aspose.Slides for Java kullanarak HTML'e font gömmeye başlamak için gerekli paketleri içe aktarmanız gerekiyor.
```java
import com.aspose.slides.*;
```
## Adım 1: Belge ve Çıktı Dizinlerini Tanımlayın
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
```
Değiştirdiğinizden emin olun `"Your Document Directory"` Ve `"Your Output Directory"` sırasıyla giriş PowerPoint sunumunuzun yollarını ve istediğiniz çıktı dizinini belirtin.
## Adım 2: Sunumu Yükleyin
```java
Presentation pres = new Presentation(dataDir + "Presentation.pptx");
```
Bu adım, PowerPoint sunumunu belleğe yükleyerek üzerinde çeşitli işlemler yapmanıza olanak tanır.
## Adım 3: Varsayılan Yazı Tiplerini Hariç Tut
```java
String[] fontNameExcludeList = { "Arial" };
```
Gömmeden hariç tutmak istediğiniz yazı tiplerini belirtin. Bu örnekte Arial'ı hariç tutuyoruz.
## Adım 4: Yazı Tiplerini HTML'ye Gömün
```java
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
pres.save(outPath + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
```
Bu adımda, bir örnek oluşturuyoruz `EmbedAllFontsHtmlController` hariç tutma listesinde belirtilenler dışında tüm yazı tiplerini gömmek için. Sonra, tanımlarız `HtmlOptions` ve yazı tiplerini yerleştirmek için özel bir HTML biçimlendirici ayarlayın. Son olarak, sunumu gömülü yazı tipleriyle HTML olarak kaydederiz.

## Çözüm
Bu eğitimde, Aspose.Slides for Java kullanarak HTML'e fontların nasıl yerleştirileceğini inceledik. Sağlanan adımları izleyerek, sunumlarınızın farklı platformlar ve cihazlarda tutarlı tipografiyi koruyarak genel görüntüleme deneyimini iyileştirebilirsiniz.
## SSS
### Belirli yazı tiplerini hariç tutmak yerine gömebilir miyim?
Evet, eklemek istediğiniz yazı tiplerini değiştirerek belirtebilirsiniz. `fontNameExcludeList` dizilimi buna göre yapın.
### Aspose.Slides for Java, HTML dışındaki formatlardaki yazı tiplerini de destekliyor mu?
Evet, Aspose.Slides PDF ve resimler dahil olmak üzere çeşitli çıktı biçimlerine yazı tiplerinin gömülmesini destekler.
### Aspose.Slides for Java için deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/).
### Aspose.Slides for Java ile ilgili ek destek veya yardımı nerede bulabilirim?
Ziyaret edebilirsiniz [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) Topluluk desteği için veya profesyonel yardım için Aspose destek ile iletişime geçin.
### Aspose.Slides for Java için geçici bir lisans satın alabilir miyim?
Evet, geçici bir lisans alabilirsiniz. [satın alma sayfası](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}