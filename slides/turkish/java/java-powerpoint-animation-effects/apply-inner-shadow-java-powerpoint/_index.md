---
title: Java PowerPoint Sunumlarında İç Gölgeyi Uygulayın
linktitle: Java PowerPoint Sunumlarında İç Gölgeyi Uygulayın
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides'ı kullanarak Java PowerPoint sunumlarındaki şekillere iç gölge efektlerini nasıl uygulayacağınızı öğrenin. Bu adım adım kılavuzla slaytlarınızı geliştirin.
weight: 12
url: /tr/java/java-powerpoint-animation-effects/apply-inner-shadow-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Fikirlerinizi etkili bir şekilde iletmek için görsel olarak çekici sunumlar oluşturmak çok önemlidir. Sunumlarınızı önemli ölçüde geliştirebilecek araçlardan biri de iç gölgelerin kullanılmasıdır. Bu eğitim, Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki şekillere iç gölgeler uygulama sürecinde size rehberlik edecektir. Bu eğitimin sonunda, çarpıcı efektler oluşturmak için slayt öğelerini nasıl değiştireceğiniz konusunda kapsamlı bir anlayışa sahip olacaksınız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1.  Java Geliştirme Kiti (JDK): Makinenizde JDK'nın kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Java web sitesi](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: En son sürümü şuradan indirin:[Aspose.Slides indirme sayfası](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA veya Eclipse gibi bir IDE, projenizi daha verimli bir şekilde yönetmenize yardımcı olacaktır.
4.  Aspose.Slides Lisansı: Geçici lisans için şu adresi ziyaret edin:[Geçici lisans ver](https://purchase.aspose.com/temporary-license/) . Satın alma seçenekleri için kontrol edin[Satın alma sayfasını atayın](https://purchase.aspose.com/buy).
## Paketleri İçe Aktar
Öncelikle gerekli paketleri içe aktarmanız gerekir. Bunlar Aspose.Slides tarafından sağlanan sınıfları ve yöntemleri kullanmanızı sağlayacaktır.
```java
import com.aspose.slides.*;
import java.io.File;
```
## 1. Adım: Proje Dizininizi Kurun
Öncelikle proje dizininizi kurun. Burası PowerPoint dosyalarınızın ve Java sınıflarınızın bulunduğu yer olacaktır.
```java
String dataDir = "Your Document Directory";
// Henüz mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
Bu adımda proje dosyalarınızın bulunduğu dizinin mevcut olduğundan emin oluyoruz. Olmuyorsa biz yaratırız.
## Adım 2: Sunumu Başlatın
 Daha sonra, örneğinin bir örneğini oluşturmanız gerekir.`Presentation` sınıf. Bu nesne, PowerPoint sunumunu düzenlemek için birincil arayüzünüz olacaktır.
```java
Presentation pres = new Presentation();
```
## 3. Adım: İlk Slayta Erişin
Şimdi sununuzun ilk slaydına erişin. Slaytlar bir koleksiyonda saklanır ve ilkini dizinini kullanarak alabilirsiniz.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
## Adım 4: Slayda Şekil Ekleme
Slayta dikdörtgen şekli ekleyeceğiz. Bu şekle daha sonra metin ve bir iç gölge uygulanacaktır.
```java
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Adım 5: Şekle Metin Ekleme
### TextFrame'i Oluşturun ve Erişin
 Şekle metin eklemek için, şekli oluşturmanız ve erişmeniz gerekir.`TextFrame`.
```java
ashp.addTextFrame(" ");
ITextFrame txtFrame = ashp.getTextFrame();
```
### Metni Ayarla
Şuraya erişerek dikdörtgen şekline metin ekleyin:`Paragraph` Ve`Portion` nesneler.
```java
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## Adım 6: İç Gölgeyi Uygulayın
Bu adım, bir iç gölge efekti oluşturmayı ve onu şekle uygulamayı içerir.
```java
IEffectFormat effectFormat = ashp.getEffectFormat();
effectFormat.enableInnerShadowEffect();
IInnerShadowEffect innerShadow = effectFormat.getInnerShadowEffect();
innerShadow.setBlurRadius(5.0);
innerShadow.setDirection(45.0);
innerShadow.setDistance(4.0);
innerShadow.getShadowColor().setColor(java.awt.Color.BLACK);
```
## Adım 7: Sunuyu Kaydet
Son olarak sunuyu belirtilen dizine kaydedin. Bu adım, değişikliklerinizin bir dosyaya yazılmasını sağlar.
```java
pres.save(dataDir + "ApplyInnerShadow_out.pptx", SaveFormat.Pptx);
```
## Adım 8: Kaynakları Temizleyin
 Bellek sızıntılarını önlemek için, her zaman`Presentation` işiniz bittikten sonra itiraz edin.
```java
if (pres != null) pres.dispose();
```
## Çözüm
Tebrikler! Aspose.Slides for Java'yı kullanarak PowerPoint sunumundaki bir şekle iç gölgeyi başarıyla uyguladınız. Bu eğitim, projenizi oluşturmaktan son sunumu kaydetmeye kadar önemli adımları kapsıyordu. Bu becerilerle artık sunumlarınızı çeşitli efektlerle zenginleştirerek onları daha ilgi çekici ve görsel olarak çekici hale getirebilirsiniz.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak oluşturmak ve değiştirmek için kullanılan güçlü bir API'dir. Geliştiricilerin Microsoft PowerPoint'e ihtiyaç duymadan sunumlarla çalışmasına olanak tanır.
### Aspose.Slides'ı lisanssız kullanabilir miyim?
 Aspose.Slides, şu adresten indirebileceğiniz ücretsiz bir deneme sunuyor:[Ücretsiz deneme sayfasını aspose](https://releases.aspose.com/). Ancak tam işlevsellik için bir lisans gereklidir.
### Bir slayta nasıl farklı şekiller eklerim?
 kullanarak çeşitli şekiller ekleyebilirsiniz.`addAutoShape` yöntem ve şekil tipinin belirtilmesi gibi`ShapeType.Rectangle`, `ShapeType.Ellipse`, vesaire.
### Gölge efektlerini daha da özelleştirebilir miyim?
Evet, ihtiyaçlarınıza uyacak şekilde bulanıklık yarıçapı, yön, mesafe ve renk gibi gölge efektinin çeşitli parametrelerini özelleştirebilirsiniz.
### Daha ayrıntılı belgeleri nerede bulabilirim?
 Şuraya başvurabilirsiniz:[Aspose.Slides belgeleri](https://reference.aspose.com/slides/java/) detaylı bilgi ve örnekler için.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
