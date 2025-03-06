---
title: Java PowerPoint'te Dış Gölge Efektlerini Uygulayın
linktitle: Java PowerPoint'te Dış Gölge Efektlerini Uygulayın
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Ayrıntılı, adım adım kılavuzumuzla Aspose.Slides'ı kullanarak Java PowerPoint sunumlarında dış gölge efektlerini nasıl kolayca uygulayacağınızı öğrenin.
weight: 11
url: /tr/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint'te Dış Gölge Efektlerini Uygulayın

## giriiş
İlgi çekici sunumlar oluşturmak genellikle slaytlarınızın görsel çekiciliğini artırmak için çeşitli efektler eklemeyi gerektirir. Bu tür efektlerden biri, öğelerinizin öne çıkmasını ve içeriğinize derinlik katmasını sağlayan dış gölgedir. Bu eğitimde Aspose.Slides for Java'yı kullanarak bir PowerPoint sunumundaki şekillere dış gölge efektleri uygulama sürecini anlatacağız.
## Önkoşullar
Adım adım kılavuza dalmadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:
1.  Java Geliştirme Kiti (JDK): Makinenizde JDK'nın kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Oracle'ın web sitesi](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Java için Aspose.Slides Library: En son sürümü şu adresten indirin:[Aspose.Slides for Java](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): Java kodunuzu yazmak ve yürütmek için IntelliJ IDEA veya Eclipse gibi bir IDE kullanın.
4.  Geçerli bir Tahmin et Lisansı: Lisansı şu adresten satın alabilirsiniz:[Aspose](https://purchase.aspose.com/buy) veya bir tane al[geçici lisans](https://purchase.aspose.com/temporary-license/) Evrim için.
## Paketleri İçe Aktar
Öncelikle Aspose.Slides için gerekli paketleri içe aktarmanız gerekecek. Bu, kütüphanenin sağladığı güçlü işlevlerin kullanılmasına zemin hazırlar.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
Dış gölge efektlerini uygulama sürecini yönetilebilir adımlara ayıralım:
## Adım 1: Proje Dizinini Ayarlayın
Kodunuzu yazmaya başlamadan önce PowerPoint dosyalarınızın saklanacağı ve erişileceği proje dizinini ayarlamanız gerekir.
Proje dizininizin mevcut olduğundan emin olun. Değilse, aşağıdaki kodu kullanarak oluşturun:
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Henüz mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Adım 2: Sunumu Başlatın
Şimdi şekillerimizi ve efektlerimizi ekleyeceğimiz sunumu başlatmamız gerekiyor.

 Yeni bir örneğini oluşturun`Presentation` yeni bir PowerPoint dosyasıyla çalışmaya başlamak için sınıf.
```java
// PPTX sınıfını örnekleyin
Presentation pres = new Presentation();
```
## 3. Adım: Slayt ve Şekil Ekleme
Daha sonra sunumunuza bir slayt ekleyin ve ardından gölge efektini uygulayacağınız şekli ekleyin.
### Slayta Referans Alın
Sunumdaki ilk slayda referans alın.
```java
// Slaytın referansını alın
ISlide sld = pres.getSlides().get_Item(0);
```
### Otomatik Şekil Ekle
Belirtilen koordinatlarda slayda bir dikdörtgen Otomatik Şekil ekleyin.
```java
// Dikdörtgen türünde Otomatik Şekil ekleme
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Adım 4: Şekli Özelleştirin
Gölge efektini daha görünür hale getirmek için şeklinize metin ekleyin ve dolgu ayarlarını yapın.
### Şekle TextFrame Ekleme
Dikdörtgen şekline metin ekleyin.
```java
// TextFrame'i Dikdörtgen'e ekleyin
aShp.addTextFrame("Aspose TextBox");
```
### Şekil Doldurmayı Devre Dışı Bırak
Metin gölgesini vurgulamak için şeklin dolgusunu devre dışı bırakın.
```java
// Metnin gölgesini almak istediğimizde şekil doldurmayı devre dışı bırakın
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## Adım 5: Dış Gölge Efektini Uygulayın
Şimdi dış gölge efektini şekle uygulama zamanı.
### Dış Gölge Efektini Etkinleştir
Şekil için dış gölge efektini etkinleştirin.
```java
// Dış gölgeyi ekleyin ve gerekli tüm parametreleri ayarlayın
aShp.getEffectFormat().enableOuterShadowEffect();
```
### Gölge Parametrelerini Yapılandırma
Bulanıklık yarıçapı, yön, mesafe, hizalama ve renk gibi gölgenin çeşitli özelliklerini ayarlayın.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## Adım 6: Sunuyu Kaydetme
Son olarak sunumu diske kaydedin.
```java
//Sunuyu diske yaz
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## Adım 7: Kaynakları Bertaraf Edin
Sunum nesnesini elden çıkararak kaynakları serbest bıraktığınızdan emin olun.
```java
// Kaynakları temizleme
if (pres != null) pres.dispose();
```
## Çözüm
İşte buyur! Aspose.Slides for Java'yı kullanarak PowerPoint sunumundaki bir şekle başarıyla dış gölge efekti uyguladınız. Bu efekt, slaytlarınızın görsel çekiciliğini önemli ölçüde artırarak içeriğinizin öne çıkmasını sağlayabilir.
 Herhangi bir sorunla karşılaşırsanız veya daha fazla yardıma ihtiyacınız olursa, şuraya göz atmaktan çekinmeyin:[Aspose.Slides belgeleri](https://reference.aspose.com/slides/java/) veya ziyaret edin[destek Forumu](https://forum.aspose.com/c/slides/11). Mutlu kodlama!
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, Java uygulamalarında PowerPoint sunumları oluşturmanıza, değiştirmenize ve dönüştürmenize olanak tanıyan güçlü bir kitaplıktır.
### Aspose.Slides for Java'nın ücretsiz deneme sürümünü nasıl edinebilirim?
 Ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Web sitesi](https://releases.aspose.com/).
### Aspose.Slides for Java'yı herhangi bir IDE ile kullanabilir miyim?
Evet, Aspose.Slides for Java'yı IntelliJ IDEA, Eclipse veya NetBeans gibi herhangi bir Java IDE ile kullanabilirsiniz.
### Aspose.Slides için nasıl geçici lisans alabilirim?
 Geçici lisansı şu adresten alabilirsiniz:[Web sitesi](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides için daha fazla örnek ve belgeyi nerede bulabilirim?
 Daha fazla örnek ve ayrıntılı belgeleri şu adreste bulabilirsiniz:[Aspose.Slides dokümantasyon sayfası](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
