---
title: PowerPoint'te Şekilleri Klonlama
linktitle: PowerPoint'te Şekilleri Klonlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki şekilleri nasıl kopyalayacağınızı öğrenin. Takip edilmesi kolay bu eğitimle iş akışınızı kolaylaştırın.
weight: 16
url: /tr/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki şekillerin nasıl kopyalanacağını inceleyeceğiz. Şekilleri klonlamak, bir sunumdaki mevcut şekilleri çoğaltmanıza olanak tanır; bu, özellikle tutarlı düzenler oluşturmak veya slaytlar arasında öğeleri yinelemek için yararlı olabilir.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde Java Geliştirme Kitinin kurulu olduğundan emin olun. En son sürümü şuradan indirip yükleyebilirsiniz:[İnternet sitesi](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java Kütüphanesi: Aspose.Slides for Java kütüphanesini indirin ve Java projenize ekleyin. İndirme linkini bulabilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize aktarmanız gerekir. Bu paketler Aspose.Slides for Java kullanarak PowerPoint sunumlarıyla çalışmak için gereken işlevleri sağlar.
```java
import com.aspose.slides.*;

```
## 1. Adım: Sunuyu Yükleyin
 Öncelikle klonlamak istediğiniz şekilleri içeren PowerPoint sunumunu yüklemeniz gerekir. Kullan`Presentation` Kaynak sunumunu yüklemek için sınıf.
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## Adım 2: Şekilleri Klonlayın
Daha sonra, kaynak sunumdaki şekilleri kopyalayacak ve bunları aynı sunumdaki yeni bir slayda ekleyeceksiniz. Bu, kaynak şekillere erişmeyi, yeni bir slayt oluşturmayı ve ardından klonlanan şekilleri yeni slayda eklemeyi içerir.
```java
IShapeCollection sourceShapes = srcPres.getSlides().get_Item(0).getShapes();
ILayoutSlide blankLayout = srcPres.getMasters().get_Item(0).getLayoutSlides().getByType(SlideLayoutType.Blank);
ISlide destSlide = srcPres.getSlides().addEmptySlide(blankLayout);
IShapeCollection destShapes = destSlide.getShapes();
destShapes.addClone(sourceShapes.get_Item(1), 50, 150 + sourceShapes.get_Item(0).getHeight());
destShapes.addClone(sourceShapes.get_Item(2));
destShapes.insertClone(0, sourceShapes.get_Item(0), 50, 150);
```
## 3. Adım: Sunuyu Kaydetme
Son olarak, klonlanmış şekilleri içeren değiştirilmiş sunumu yeni bir dosyaya kaydedin.
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## Çözüm
Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki şekilleri klonlamak, sunum oluşturma iş akışınızı kolaylaştırmanıza yardımcı olabilecek basit bir işlemdir. Bu öğreticide özetlenen adımları izleyerek mevcut şekilleri kolayca çoğaltabilir ve bunları gerektiği gibi özelleştirebilirsiniz.

## SSS'ler
### Farklı slaytlarda şekilleri kopyalayabilir miyim?
Evet, Aspose.Slides for Java'yı kullanarak sunumdaki herhangi bir slayttaki şekilleri kopyalayabilir ve bunları başka bir slayda ekleyebilirsiniz.
### Şekilleri klonlamada herhangi bir sınırlama var mı?
Aspose.Slides for Java güçlü klonlama yetenekleri sunsa da karmaşık şekiller veya animasyonlar mükemmel şekilde kopyalanamayabilir.
### Klonlanan şekilleri slayta ekledikten sonra değiştirebilir miyim?
Kesinlikle, şekiller kopyalanıp bir slayta eklendiğinde özelliklerini, stillerini ve içeriğini gerektiği gibi değiştirebilirsiniz.
### Aspose.Slides for Java şekillerin yanı sıra diğer öğelerin klonlanmasını da destekliyor mu?
Evet, Aspose.Slides for Java'yı kullanarak bir PowerPoint sunumundaki slaytları, metinleri, görüntüleri ve diğer öğeleri kopyalayabilirsiniz.
### Aspose.Slides for Java'nın deneme sürümü mevcut mu?
 Evet, Aspose.Slides for Java'nın ücretsiz deneme sürümünü şuradan indirebilirsiniz:[İnternet sitesi](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
