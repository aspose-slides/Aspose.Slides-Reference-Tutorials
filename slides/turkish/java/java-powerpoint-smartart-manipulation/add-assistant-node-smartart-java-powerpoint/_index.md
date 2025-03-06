---
title: Java PowerPoint'te SmartArt'a Yardımcı Düğüm Ekleme
linktitle: Java PowerPoint'te SmartArt'a Yardımcı Düğüm Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides kullanarak Java PowerPoint sunumlarında SmartArt'a nasıl asistan düğüm ekleyeceğinizi öğrenin. PowerPoint düzenleme becerilerinizi geliştirin.
weight: 17
url: /tr/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint'te SmartArt'a Yardımcı Düğüm Ekleme

## giriiş
Bu eğitimde, Aspose.Slides'ı kullanarak Java PowerPoint sunumlarında SmartArt'a asistan düğüm ekleme sürecinde size rehberlik edeceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde Java'nın kurulu olduğundan emin olun. En son JDK'yı şuradan indirip yükleyebilirsiniz:[Burada](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java kütüphanesini şu adresten indirip yükleyin:[bu bağlantı](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Başlangıç olarak gerekli paketleri Java kodunuza aktarın:
```java
import com.aspose.slides.*;
```
## 1. Adım: Sunumu Hazırlayın
PowerPoint dosyanızın yolunu kullanarak bir Sunum örneği oluşturarak başlayın:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Adım 2: Şekiller Arasında Geçiş Yapın
Sunumun ilk slaydındaki her şeklin üzerinden geçin:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## 3. Adım: SmartArt Şekillerini kontrol edin
Şeklin SmartArt türünde olup olmadığını kontrol edin:
```java
if (shape instanceof ISmartArt)
```
## Adım 4: SmartArt Düğümleri Üzerinden Geçiş Yapın
SmartArt şeklinin tüm düğümleri arasında geçiş yapın:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## 5. Adım: Yardımcı Düğümü kontrol edin
Düğümün yardımcı düğüm olup olmadığını kontrol edin:
```java
if (node.isAssistant())
```
## Adım 6: Asistan Düğümünü Normal Olarak Ayarlayın
Düğüm bir yardımcı düğüm ise onu normal bir düğüme ayarlayın:
```java
node.setAssistant(false);
```
## Adım 7: Sunumu Kaydet
Değiştirilen sunumu kaydedin:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Çözüm
Tebrikler! Aspose.Slides'ı kullanarak Java PowerPoint sunumunuza SmartArt'a başarıyla bir asistan düğümü eklediniz.

## SSS'ler
### Sunumdaki bir SmartArt'a birden çok yardımcı düğüm ekleyebilir miyim?
Evet, her düğüm için işlemi tekrarlayarak birden fazla yardımcı düğüm ekleyebilirsiniz.
### Bu eğitim hem PowerPoint hem de PowerPoint şablonlarında çalışıyor mu?
Evet, bu eğitimi hem PowerPoint sunumlarına hem de şablonlara uygulayabilirsiniz.
### Aspose.Slides PowerPoint'in tüm sürümleriyle uyumlu mu?
Aspose.Slides, 97-2003 arası PowerPoint sürümlerini en son sürüme kadar destekler.
### Yardımcı düğümün görünümünü özelleştirebilir miyim?
Evet, Aspose.Slides tarafından sağlanan çeşitli özellik ve yöntemleri kullanarak görünümü özelleştirebilirsiniz.
### SmartArt'taki düğüm sayısında herhangi bir sınırlama var mı?
PowerPoint'teki SmartArt çok sayıda düğümü destekler ancak daha iyi okunabilirlik için bunun makul düzeyde tutulması önerilir.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
