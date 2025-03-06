---
title: Java PowerPoint'te Fallback Font ile İşleme
linktitle: Java PowerPoint'te Fallback Font ile İşleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides'ı kullanarak Java PowerPoint sunumlarında yedek yazı tipleriyle metni nasıl oluşturacağınızı öğrenin. Sorunsuz bir uygulama için bu adım adım kılavuzu izleyin.
weight: 13
url: /tr/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Java'da PowerPoint sunumları oluşturmak ve düzenlemek zorlayıcı olabilir ancak Aspose.Slides ile bunu verimli bir şekilde yapabilirsiniz. Önemli özelliklerden biri, metni yedek yazı tipleriyle oluşturma yeteneğidir. Bu makale, Aspose.Slides for Java kullanarak PowerPoint slaytlarınıza yedek yazı tiplerini nasıl uygulayacağınız konusunda ayrıntılı, adım adım bir kılavuz sağlar.
## Önkoşullar
Uygulamaya geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Slides for Java: Buradan indirebilirsiniz.[Aspose.Slides for Java İndirme sayfası](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA veya Eclipse gibi bir IDE, geliştirme sürecinizi daha sorunsuz hale getirecektir.
4. Bağımlılıklar: Aspose.Slides'ı projenizin bağımlılıklarına ekleyin.
## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java programımıza aktarmamız gerekiyor.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Süreci yönetilebilir adımlara ayıralım.
## 1. Adım: Projenizi Kurun
 Herhangi bir kod yazmadan önce projenizin doğru şekilde kurulduğundan emin olun. Buna Aspose.Slides kütüphanesini projenize eklemek de dahildir. Bunu kütüphaneyi indirerek yapabilirsiniz.[Java için Aspose.Slides](https://releases.aspose.com/slides/java/) ve onu derleme yolunuza ekleyin.
## 2. Adım: Font Geri Dönüş Kurallarını Başlatın
 Bir örneğini oluşturmanız gerekir`IFontFallBackRulesCollection` sınıfı seçin ve ona kurallar ekleyin. Bu kurallar, belirli Unicode aralıkları için yazı tipi yedeklerini tanımlar.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Kural koleksiyonunun yeni bir örneğini oluşturma
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Bir dizi kural oluşturun
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## 3. Adım: Geri Dönme Kurallarını Değiştirin
Bu adımda, mevcut yedek yazı tiplerini kaldırarak ve belirli Unicode aralıklarına ilişkin kuralları güncelleyerek geri dönüş kurallarını değiştireceğiz.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // FallBack yazı tipi "Tahoma" yüklü kurallardan kaldırılmaya çalışılıyor
    fallBackRule.remove("Tahoma");
    // Belirtilen aralık için kuralları güncelle
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//Mevcut kuralları listeden kaldırın
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## 4. Adım: Sunuyu Yükleyin
Değiştirmek istediğiniz PowerPoint sunumunu yükleyin.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## Adım 5: Sunuya Geri Dönme Kuralları Atayın
Hazırlanan geri dönüş kurallarını sunumun yazı tipi yöneticisine atayın.
```java
try {
    // Hazırlanan kural listesinin kullanıma atanması
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Başlatılan kurallar koleksiyonunu kullanarak küçük resim oluşturma ve bunu PNG'ye kaydetme
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Adım 6: Kaydet ve Test Et
Son olarak çalışmanızı kaydedin ve her şeyin beklendiği gibi çalıştığından emin olmak için uygulamayı test edin. Herhangi bir sorunla karşılaşırsanız kurulumunuzu bir kez daha kontrol edin ve tüm bağımlılıkların doğru şekilde eklendiğinden emin olun.
## Çözüm
Bu kılavuzu takip ederek, Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarınızda yedek yazı tipleriyle metni verimli bir şekilde oluşturabilirsiniz. Bu işlem, birincil yazı tipleri kullanılamasa bile sunumlarınızın tutarlı biçimlendirmeyi korumasını sağlar. Mutlu kodlama!
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, geliştiricilerin Java uygulamalarında PowerPoint sunumları oluşturmasına, değiştirmesine ve işlemesine olanak tanıyan bir kitaplıktır.
### Aspose.Slides'ı projeme nasıl eklerim?
 Kütüphaneyi adresinden indirebilirsiniz.[Aspose.Slides indirme sayfası](https://releases.aspose.com/slides/java/) ve bunu projenizin derleme yoluna ekleyin.
### Yedek yazı tipleri nelerdir?
Yedek yazı tipleri, belirtilen yazı tipi kullanılamadığında veya belirli karakterleri desteklemediğinde kullanılan alternatif yazı tipleridir.
### Birden çok geri dönüş kuralı kullanabilir miyim?
Evet, farklı Unicode aralıklarını ve yazı tiplerini işlemek için birden fazla geri dönüş kuralı ekleyebilirsiniz.
### Aspose.Slides için nereden destek alabilirim?
 adresinden destek alabilirsiniz.[Aspose.Slides destek forumu](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
