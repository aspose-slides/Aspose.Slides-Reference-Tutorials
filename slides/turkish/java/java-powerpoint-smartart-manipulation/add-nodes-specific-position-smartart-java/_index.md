---
title: Java kullanarak SmartArt'ta Belirli Konumdaki Düğümleri Ekleme
linktitle: Java kullanarak SmartArt'ta Belirli Konumdaki Düğümleri Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java kullanarak SmartArt'ta belirli konumlara nasıl düğüm ekleyeceğinizi keşfedin. Zahmetsizce dinamik sunumlar oluşturun.
type: docs
weight: 16
url: /tr/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---
## giriiş
Bu eğitimde, Aspose.Slides ile Java kullanarak SmartArt'ta belirli konumlara düğüm ekleme sürecinde size rehberlik edeceğiz. SmartArt, PowerPoint'te görsel olarak çekici diyagramlar ve grafikler oluşturmanıza olanak tanıyan bir özelliktir.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
2.  Aspose.Slides for Java kütüphanesi indirildi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).
3. Java programlama dili hakkında temel bilgiler.

## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java kodumuza aktaralım:
```java
import com.aspose.slides.*;
import java.io.File;
```
## 1. Adım: Bir Sunum Örneği Oluşturun
Sunum sınıfının bir örneğini oluşturarak başlayın:
```java
Presentation pres = new Presentation();
```
## Adım 2: Sunum Slaytına Erişin
SmartArt'ı eklemek istediğiniz slayda erişin:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 3. Adım: SmartArt Şeklini Ekleyin
Slayta bir SmartArt şekli ekleyin:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Adım 4: SmartArt Node'a erişin
İstediğiniz dizindeki SmartArt düğümüne erişin:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Adım 5: Belirli Bir Konuma Alt Düğüm Ekleme
Ana düğümdeki belirli bir konuma yeni bir alt düğüm ekleyin:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Adım 6: Düğüme Metin Ekleme
Yeni eklenen düğümün metnini ayarlayın:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Adım 7: Sunuyu Kaydet
Değiştirilen sunumu kaydedin:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu eğitimde Aspose.Slides ile Java kullanarak SmartArt'ta belirli konumlara nasıl düğüm ekleyeceğinizi öğrendiniz. Bu adımları izleyerek, dinamik sunumlar oluşturmak için SmartArt şekillerini programlı olarak değiştirebilirsiniz.
## SSS'ler
### Aynı anda birden fazla düğüm ekleyebilir miyim?
Evet, istediğiniz konumları yineleyerek programlı olarak birden fazla düğüm ekleyebilirsiniz.
### Aspose.Slides PowerPoint'in tüm sürümleriyle uyumlu mu?
Aspose.Slides çeşitli PowerPoint formatlarını destekleyerek çoğu sürümle uyumluluk sağlar.
### SmartArt düğümlerinin görünümünü özelleştirebilir miyim?
Evet, düğümlerin görünümünü, boyutları, renkleri ve stilleri de dahil olmak üzere özelleştirebilirsiniz.
### Aspose.Slides diğer programlama dilleri için destek sunuyor mu?
Evet, Aspose.Slides, .NET ve Python da dahil olmak üzere birçok programlama dili için kütüphaneler sağlar.
### Aspose.Slides'ın deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).