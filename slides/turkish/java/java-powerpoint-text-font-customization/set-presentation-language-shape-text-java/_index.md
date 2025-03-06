---
title: Java'da Sunum Dilini ve Şekil Metnini Ayarlama
linktitle: Java'da Sunum Dilini ve Şekil Metnini Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarını nasıl otomatikleştireceğinizi öğrenin. Slaytları programlı bir şekilde kolaylıkla oluşturun, değiştirin ve geliştirin.
weight: 19
url: /tr/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
PowerPoint sunumlarını Java'da programlı bir şekilde oluşturmak ve değiştirmek, iş akışı otomasyonunu kolaylaştırabilir ve üretkenliği artırabilir. Aspose.Slides for Java, bu görevleri verimli bir şekilde gerçekleştirmek için güçlü bir araç seti sağlar. Bu eğitim, Aspose.Slides for Java'yı kullanarak sunum dilini ayarlamak ve metni şekillendirmek için gerekli adımlarda size rehberlik eder.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Java Geliştirme Kiti (JDK) yüklü
-  Aspose.Slides for Java kütüphanesini şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/slides/java/)
- Sisteminizde kurulu IntelliJ IDEA veya Eclipse gibi Entegre Geliştirme Ortamı (IDE)
- Java programlama dili hakkında temel bilgiler
## Paketleri İçe Aktar
Başlamak için gerekli Aspose.Slides paketlerini Java dosyanıza aktarın:
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## Adım 1: Sunum Nesnesi Oluşturun
 Bir başlatarak başlayın`Presentation` nesne:
```java
Presentation pres = new Presentation();
```
Bu, yeni bir PowerPoint sunusu oluşturur.
## 2. Adım: Otomatik Şekil Ekleme ve Yapılandırma
Daha sonra, ilk slayda bir Otomatik Şekil ekleyin ve özelliklerini yapılandırın:
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
Burada (50, 50) koordinatlarında 200x50 piksel boyutunda bir dikdörtgen Otomatik Şekil ekliyoruz.
## 3. Adım: Metni ve Dili Ayarlayın
Metin içeriğini ayarlayın ve yazım denetimi için dili belirtin:
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
 Yer değiştirmek`"Text to apply spellcheck language"` İstediğiniz metinle. Dil kimliği`"en-EN"`İngilizceyi (Amerika Birleşik Devletleri) belirtir.
## 4. Adım: Sunuyu Kaydetme
Değiştirilen sunumu belirtilen çıktı dizinine kaydedin:
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
 Değiştirildiğinden emin olun`"Your Output Directory"` dosyayı kaydetmek istediğiniz gerçek dizin yolunuzla.
## Adım 5: Kaynakları Bertaraf Edin
 Uygun şekilde imha edin`Presentation` Kaynakların serbest bırakılmasına itiraz:
```java
pres.dispose();
```
Bu adım, bellek sızıntılarını önlemek için çok önemlidir.

## Çözüm
Sonuç olarak Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak oluşturma ve değiştirme sürecini basitleştirir. Bu adımları izleyerek sunum dilini verimli bir şekilde ayarlayabilir ve metin özelliklerini gereksinimlerinize göre yapılandırabilirsiniz.
## SSS'ler
### Sıfırdan PowerPoint sunumları oluşturmak için Aspose.Slides for Java'yı kullanabilir miyim?
Evet, Aspose.Slides sunumların tamamen programlı olarak oluşturulması için kapsamlı API'ler sağlar.
### Aspose.Slides for Java'yı kullanarak PowerPoint slaytlarındaki metne farklı yazı tiplerini nasıl uygulayabilirim?
 Yazı tipi özelliklerini aracılığıyla ayarlayabilirsiniz.`IPortionFormat` metin bölümleriyle ilişkili nesneler.
### Aspose.Slides for Java'nın deneme sürümü mevcut mu?
 Evet, şu adresten ücretsiz deneme alabilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Slides for Java belgelerini nerede bulabilirim?
 Detaylı dokümantasyon mevcut[Burada](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java için hangi destek seçenekleri mevcut?
 Aspose.Slides forumunu ziyaret edebilirsiniz[Burada](https://forum.aspose.com/c/slides/11) topluluk desteği için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
