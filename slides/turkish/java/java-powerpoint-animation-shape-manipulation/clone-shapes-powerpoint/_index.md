---
"description": "Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki şekilleri nasıl klonlayacağınızı öğrenin. Bu kolay takip edilebilir eğitimle iş akışınızı kolaylaştırın."
"linktitle": "PowerPoint'te Şekilleri Klonla"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "PowerPoint'te Şekilleri Klonla"
"url": "/tr/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Şekilleri Klonla

## giriiş
Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki şekillerin nasıl klonlanacağını inceleyeceğiz. Şekillerin klonlanması, bir sunumdaki mevcut şekilleri çoğaltmanıza olanak tanır; bu, özellikle tutarlı düzenler oluşturmak veya slaytlar arasında öğeleri tekrarlamak için yararlı olabilir.
## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde Java Geliştirme Kitinin yüklü olduğundan emin olun. En son sürümü şu adresten indirip yükleyebilirsiniz: [web sitesi](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java Kütüphanesi: Aspose.Slides for Java kütüphanesini indirin ve Java projenize ekleyin. İndirme bağlantısını bulabilirsiniz [Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Başlamak için, gerekli paketleri Java projenize aktarmanız gerekir. Bu paketler, Aspose.Slides for Java kullanarak PowerPoint sunumlarıyla çalışmak için gereken işlevleri sağlar.
```java
import com.aspose.slides.*;

```
## Adım 1: Sunumu Yükleyin
Öncelikle, klonlamak istediğiniz şekilleri içeren PowerPoint sunumunu yüklemeniz gerekir. `Presentation` Kaynak sunumu yüklemek için sınıf.
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## Adım 2: Şekilleri Klonlayın
Sonra, şekilleri kaynak sunumundan kopyalayıp aynı sunumdaki yeni bir slayta ekleyeceksiniz. Bu, kaynak şekillere erişmeyi, yeni bir slayt oluşturmayı ve ardından kopyalanan şekilleri yeni slayta eklemeyi içerir.
```java
IShapeCollection sourceShapes = srcPres.getSlides().get_Item(0).getShapes();
ILayoutSlide blankLayout = srcPres.getMasters().get_Item(0).getLayoutSlides().getByType(SlideLayoutType.Blank);
ISlide destSlide = srcPres.getSlides().addEmptySlide(blankLayout);
IShapeCollection destShapes = destSlide.getShapes();
destShapes.addClone(sourceShapes.get_Item(1), 50, 150 + sourceShapes.get_Item(0).getHeight());
destShapes.addClone(sourceShapes.get_Item(2));
destShapes.insertClone(0, sourceShapes.get_Item(0), 50, 150);
```
## Adım 3: Sunumu Kaydedin
Son olarak, değiştirilmiş sunumu klonlanmış şekillerle birlikte yeni bir dosyaya kaydedin.
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## Çözüm
Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki şekilleri klonlamak, sunum oluşturma iş akışınızı kolaylaştırmaya yardımcı olabilecek basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek, mevcut şekilleri kolayca çoğaltabilir ve gerektiği gibi özelleştirebilirsiniz.

## SSS
### Şekilleri farklı slaytlara kopyalayabilir miyim?
Evet, sunumdaki herhangi bir slayttan şekilleri kopyalayabilir ve Aspose.Slides for Java'yı kullanarak başka bir slayda ekleyebilirsiniz.
### Şekilleri klonlamada herhangi bir sınırlama var mı?
Java için Aspose.Slides güçlü klonlama yetenekleri sağlasa da, karmaşık şekiller veya animasyonlar mükemmel şekilde kopyalanamayabilir.
### Klonlanmış şekilleri bir slayda ekledikten sonra değiştirebilir miyim?
Kesinlikle, şekiller klonlanıp bir slayda eklendiğinde, özelliklerini, stillerini ve içeriklerini gerektiği gibi değiştirebilirsiniz.
### Aspose.Slides for Java şekillerin dışında başka öğelerin de klonlanmasını destekliyor mu?
Evet, Aspose.Slides for Java'yı kullanarak bir PowerPoint sunumundaki slaytları, metinleri, görüntüleri ve diğer öğeleri klonlayabilirsiniz.
### Aspose.Slides for Java için deneme sürümü mevcut mu?
Evet, Aspose.Slides for Java'nın ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [web sitesi](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}