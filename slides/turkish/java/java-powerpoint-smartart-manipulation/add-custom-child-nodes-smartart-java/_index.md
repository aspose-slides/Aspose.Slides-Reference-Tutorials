---
title: Java kullanarak SmartArt'a Özel Alt Düğümler ekleme
linktitle: Java kullanarak SmartArt'a Özel Alt Düğümler ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java kullanarak PowerPoint sunumlarında SmartArt'a nasıl özel alt düğümler ekleyeceğinizi öğrenin. Slaytlarınızı profesyonel grafiklerle zahmetsizce geliştirin.
weight: 11
url: /tr/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
SmartArt, PowerPoint'te kullanıcıların hızlı ve kolay bir şekilde profesyonel görünümlü grafikler oluşturmasına olanak tanıyan güçlü bir özelliktir. Bu eğitimde Aspose.Slides ile Java kullanarak SmartArt'a özel alt düğümlerin nasıl ekleneceğini öğreneceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde Java'nın kurulu olduğundan emin olun.
2.  Aspose.Slides for Java: Aspose.Slides for Java'yı şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize aktarın:
```java
import com.aspose.slides.*;
```
## 1. Adım: Sunuyu Yükleyin
SmartArt'a özel alt düğümler eklemek istediğiniz PowerPoint sunumunu yükleyin:
```java
String dataDir = "Your Document Directory";
// İstediğiniz sunumu yükleyin
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Adım 2: SmartArt'ı Slayt'a ekleyin
Şimdi slayda SmartArt'ı ekleyelim:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## 3. Adım: SmartArt Şeklini Taşı
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
## Adım 7: Sunuyu Kaydet
Son olarak değiştirilen sunumu kaydedin:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu eğitimde Aspose.Slides ile Java kullanarak SmartArt'a özel alt düğümlerin nasıl ekleneceğini öğrendik. Bu adımları izleyerek sunumlarınızı özelleştirilmiş grafiklerle geliştirebilir, daha ilgi çekici ve profesyonel hale getirebilirsiniz.
## SSS'ler
### Aspose.Slides for Java'yı kullanarak farklı türde SmartArt mizanpajları ekleyebilir miyim?
Evet, Aspose.Slides for Java, çeşitli SmartArt düzenlerini destekleyerek sunum ihtiyaçlarınıza en uygun olanı seçmenize olanak tanır.
### Aspose.Slides for Java, PowerPoint'in farklı sürümleriyle uyumlu mu?
Aspose.Slides for Java, PowerPoint'in farklı sürümleriyle sorunsuz çalışacak şekilde tasarlanmıştır ve platformlar arasında uyumluluk ve tutarlılık sağlar.
### SmartArt şekillerinin görünümünü programlı olarak özelleştirebilir miyim?
Kesinlikle! Aspose.Slides for Java ile SmartArt şekillerinin görünümünü, boyutunu, rengini ve düzenini tasarım tercihlerinize uyacak şekilde programlı olarak özelleştirebilirsiniz.
### Aspose.Slides for Java dokümantasyon ve destek sağlıyor mu?
Evet, Aspose web sitesinde kapsamlı belgeler bulabilir ve topluluk destek forumlarına erişim sağlayabilirsiniz.
### Aspose.Slides for Java'nın deneme sürümü mevcut mu?
 Evet, Aspose.Slides for Java'nın ücretsiz deneme sürümünü web sitesinden indirebilir ve satın almadan önce özelliklerini ve yeteneklerini keşfedebilirsiniz.[Burada](https://releases.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
