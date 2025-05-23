---
"description": "Aspose.Slides ile Java kullanarak PowerPoint sunumlarındaki SmartArt'a özel alt düğümlerin nasıl ekleneceğini öğrenin. Slaytlarınızı profesyonel grafiklerle zahmetsizce geliştirin."
"linktitle": "Java kullanarak SmartArt'a Özel Alt Düğümler Ekleyin"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java kullanarak SmartArt'a Özel Alt Düğümler Ekleyin"
"url": "/tr/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak SmartArt'a Özel Alt Düğümler Ekleyin

## giriiş
SmartArt, kullanıcıların profesyonel görünümlü grafikleri hızlı ve kolay bir şekilde oluşturmasına olanak tanıyan PowerPoint'teki güçlü bir özelliktir. Bu eğitimde, Java ile Aspose.Slides kullanarak SmartArt'a özel alt düğümlerin nasıl ekleneceğini öğreneceğiz.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde Java'nın yüklü olduğundan emin olun.
2. Java için Aspose.Slides: Java için Aspose.Slides'ı indirin ve yükleyin [Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Başlamak için Java projenize gerekli paketleri içe aktarın:
```java
import com.aspose.slides.*;
```
## Adım 1: Sunumu Yükleyin
SmartArt'a özel alt düğümler eklemek istediğiniz PowerPoint sunumunu yükleyin:
```java
String dataDir = "Your Document Directory";
// İstediğiniz sunumu yükleyin
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Adım 2: Slayda SmartArt Ekleme
Şimdi slayda SmartArt ekleyelim:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Adım 3: SmartArt Şeklini Taşı
SmartArt şeklini yeni bir konuma taşıyın:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Adım 4: Şekil Genişliğini Değiştirin
SmartArt şeklinin genişliğini değiştirin:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Adım 5: Şekil Yüksekliğini Değiştirin
SmartArt şeklinin yüksekliğini değiştirin:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Adım 6: Şekli Döndürün
SmartArt şeklini döndürün:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Adım 7: Sunumu Kaydedin
Son olarak, değiştirilen sunumu kaydedin:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu eğitimde, Java ile Aspose.Slides kullanarak SmartArt'a özel alt düğümlerin nasıl ekleneceğini öğrendik. Bu adımları izleyerek, sunumlarınızı özelleştirilmiş grafiklerle geliştirebilir, onları daha ilgi çekici ve profesyonel hale getirebilirsiniz.
## SSS
### Aspose.Slides for Java'yı kullanarak farklı türlerde SmartArt düzenleri ekleyebilir miyim?
Evet, Aspose.Slides for Java çeşitli SmartArt düzenlerini destekler ve sunum ihtiyaçlarınıza en uygun olanı seçmenize olanak tanır.
### Aspose.Slides for Java, PowerPoint'in farklı sürümleriyle uyumlu mudur?
Java için Aspose.Slides, PowerPoint'in farklı sürümleriyle sorunsuz çalışacak şekilde tasarlanmıştır; böylece platformlar arasında uyumluluk ve tutarlılık sağlanır.
### SmartArt şekillerinin görünümünü program aracılığıyla özelleştirebilir miyim?
Kesinlikle! Aspose.Slides for Java ile SmartArt şekillerinin görünümünü, boyutunu, rengini ve düzenini tasarım tercihlerinize uyacak şekilde programlı bir şekilde özelleştirebilirsiniz.
### Aspose.Slides for Java dokümantasyon ve destek sağlıyor mu?
Evet, Aspose web sitesinde kapsamlı dokümantasyona ulaşabilir ve topluluk destek forumlarına erişebilirsiniz.
### Aspose.Slides for Java için deneme sürümü mevcut mu?
Evet, satın alma işlemi yapmadan önce özelliklerini ve yeteneklerini keşfetmek için Aspose.Slides for Java'nın ücretsiz deneme sürümünü web sitesinden indirebilirsiniz. [Burada](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}