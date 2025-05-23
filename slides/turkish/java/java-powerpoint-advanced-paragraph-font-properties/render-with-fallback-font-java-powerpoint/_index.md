---
"description": "Aspose.Slides kullanarak Java PowerPoint sunumlarında yedek yazı tipleriyle metin oluşturmayı öğrenin. Sorunsuz bir uygulama için bu adım adım kılavuzu izleyin."
"linktitle": "Java PowerPoint'te Fallback Font ile Render"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java PowerPoint'te Fallback Font ile Render"
"url": "/tr/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint'te Fallback Font ile Render

## giriiş
Java'da PowerPoint sunumları oluşturmak ve düzenlemek zor olabilir, ancak Aspose.Slides ile bunu verimli bir şekilde yapabilirsiniz. Önemli bir özellik, metni yedek yazı tipleriyle işleme yeteneğidir. Bu makale, Aspose.Slides for Java kullanarak PowerPoint slaytlarınıza yedek yazı tiplerini nasıl uygulayacağınıza dair ayrıntılı, adım adım bir kılavuz sağlar.
## Ön koşullar
Uygulamaya geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın yüklü olduğundan emin olun.
2. Java için Aspose.Slides: Bunu şu adresten indirebilirsiniz: [Aspose.Slides for Java İndirme sayfası](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA veya Eclipse gibi bir IDE, geliştirme sürecinizi daha sorunsuz hale getirecektir.
4. Bağımlılıklar: Aspose.Slides'ı projenizin bağımlılıklarına ekleyin.
## Paketleri İçe Aktar
Öncelikle Java programımıza gerekli paketleri import etmemiz gerekiyor.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Süreci yönetilebilir adımlara bölelim.
## Adım 1: Projenizi Kurun
Herhangi bir kod yazmadan önce, projenizin doğru şekilde ayarlandığından emin olun. Bu, projenize Aspose.Slides kütüphanesini eklemeyi içerir. Bunu, kütüphaneyi şu adresten indirerek yapabilirsiniz: [Java için Aspose.Slides](https://releases.aspose.com/slides/java/) ve bunu yapı yolunuza ekleyin.
## Adım 2: Yazı Tipi Geri Dönüş Kurallarını Başlatın
Bir örneğini oluşturmanız gerekiyor `IFontFallBackRulesCollection` sınıfını oluşturun ve ona kurallar ekleyin. Bu kurallar belirli Unicode aralıkları için yazı tipi yedeklerini tanımlar.
```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Kural koleksiyonunun yeni bir örneğini oluşturun
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Bir dizi kural oluşturun
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## Adım 3: Yedek Kuralları Değiştirin
Bu adımda, mevcut yedek yazı tiplerini kaldırarak ve belirli Unicode aralıkları için kuralları güncelleyerek yedek kurallarını değiştireceğiz.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // Yüklenen kurallardan FallBack fontu "Tahoma" kaldırılmaya çalışılıyor
    fallBackRule.remove("Tahoma");
    // Belirtilen aralık için kuralları güncelle
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
// Mevcut kuralları listeden kaldırın
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## Adım 4: Sunumu Yükleyin
Değiştirmek istediğiniz PowerPoint sunumunu yükleyin.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## Adım 5: Sunuma Yedek Kurallar Atamak
Hazırladığınız yedek kuralları sunumun yazı tipi yöneticisine atayın.
```java
try {
    // Hazırlanan kurallar listesinin kullanıma atanması
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Başlatılan kurallar koleksiyonunu kullanarak bir küçük resmin oluşturulması ve PNG'ye kaydedilmesi
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Adım 6: Kaydedin ve Test Edin
Son olarak, çalışmanızı kaydedin ve her şeyin beklendiği gibi çalıştığından emin olmak için uygulamayı test edin. Herhangi bir sorunla karşılaşırsanız, kurulumunuzu iki kez kontrol edin ve tüm bağımlılıkların doğru şekilde eklendiğinden emin olun.
## Çözüm
Bu kılavuzu izleyerek, Aspose.Slides for Java kullanarak PowerPoint sunumlarınızda yedek yazı tipleriyle metni verimli bir şekilde işleyebilirsiniz. Bu süreç, birincil yazı tipleri kullanılamıyor olsa bile sunumlarınızın tutarlı biçimlendirmeyi korumasını sağlar. İyi kodlamalar!
## SSS
### Java için Aspose.Slides nedir?
Aspose.Slides for Java, geliştiricilerin Java uygulamalarında PowerPoint sunumları oluşturmasına, değiştirmesine ve işlemesine olanak tanıyan bir kütüphanedir.
### Aspose.Slides'ı projeme nasıl eklerim?
Kütüphaneyi şu adresten indirebilirsiniz: [Aspose.Slides indirme sayfası](https://releases.aspose.com/slides/java/) ve bunu projenizin derleme yoluna ekleyin.
### Yedek fontlar nelerdir?
Yedek yazı tipleri, belirtilen yazı tipi mevcut olmadığında veya belirli karakterleri desteklemediğinde kullanılan alternatif yazı tipleridir.
### Birden fazla yedek kural kullanabilir miyim?
Evet, farklı Unicode aralıklarını ve yazı tiplerini işlemek için birden fazla geri dönüş kuralı ekleyebilirsiniz.
### Aspose.Slides için desteği nereden alabilirim?
Destek alabilirsiniz [Aspose.Slides destek forumu](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}