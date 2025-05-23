---
"description": "Java ile Aspose.Slides kullanarak SmartArt'ta belirli konumlara düğümlerin nasıl ekleneceğini keşfedin. Zahmetsizce dinamik sunumlar oluşturun."
"linktitle": "Java kullanarak SmartArt'ta Belirli Bir Konuma Düğümler Ekleyin"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java kullanarak SmartArt'ta Belirli Bir Konuma Düğümler Ekleyin"
"url": "/tr/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak SmartArt'ta Belirli Bir Konuma Düğümler Ekleyin

## giriiş
Bu eğitimde, Java ile Aspose.Slides kullanarak SmartArt'ta belirli konumlara düğüm ekleme sürecinde size rehberlik edeceğiz. SmartArt, PowerPoint'te görsel olarak çekici diyagramlar ve grafikler oluşturmanıza olanak tanıyan bir özelliktir.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Development Kit (JDK) yüklü.
2. Java kütüphanesi için Aspose.Slides indirildi. Buradan indirebilirsiniz [Burada](https://releases.aspose.com/slides/java/).
3. Java programlama dilinin temel bilgisi.

## Paketleri İçe Aktar
Öncelikle Java kodumuza gerekli paketleri aktaralım:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Adım 1: Bir Sunum Örneği Oluşturun
Presentation sınıfının bir örneğini oluşturarak başlayın:
```java
Presentation pres = new Presentation();
```
## Adım 2: Sunum Slaydına Erişim
SmartArt'ı eklemek istediğiniz slayda erişin:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Adım 3: SmartArt Şeklini Ekle
Slayda bir SmartArt şekli ekleyin:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Adım 4: SmartArt Düğümüne Erişim
İstenilen dizindeki SmartArt düğümüne erişin:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Adım 5: Belirli Bir Konuma Alt Düğüm Ekleyin
Üst düğümdeki belirli bir konuma yeni bir alt düğüm ekleyin:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Adım 6: Düğüme Metin Ekleyin
Yeni eklenen düğüm için metni ayarlayın:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Adım 7: Sunumu Kaydedin
Değiştirilen sunumu kaydedin:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu eğitimde, Java ile Aspose.Slides kullanarak SmartArt'ta belirli konumlara düğüm eklemeyi öğrendiniz. Bu adımları izleyerek, dinamik sunumlar oluşturmak için SmartArt şekillerini programatik olarak düzenleyebilirsiniz.
## SSS
### Aynı anda birden fazla node ekleyebilir miyim?
Evet, istediğiniz konumlar üzerinde yineleme yaparak birden fazla düğümü programlı olarak ekleyebilirsiniz.
### Aspose.Slides PowerPoint'in tüm sürümleriyle uyumlu mudur?
Aspose.Slides birçok PowerPoint formatını destekleyerek çoğu sürümle uyumluluğu garanti eder.
### SmartArt düğümlerinin görünümünü özelleştirebilir miyim?
Evet, düğümlerin boyutunu, rengini ve stilini de içeren görünümünü özelleştirebilirsiniz.
### Aspose.Slides diğer programlama dillerini destekliyor mu?
Evet, Aspose.Slides .NET ve Python da dahil olmak üzere birden fazla programlama dili için kütüphaneler sağlar.
### Aspose.Slides için deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}