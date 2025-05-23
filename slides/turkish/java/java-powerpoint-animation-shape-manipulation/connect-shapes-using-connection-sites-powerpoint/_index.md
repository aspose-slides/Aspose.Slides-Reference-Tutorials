---
"description": "Aspose.Slides for Java kullanarak PowerPoint'te şekilleri nasıl bağlayacağınızı öğrenin. Sunumlarınızı zahmetsizce otomatikleştirin."
"linktitle": "PowerPoint'te Bağlantı Sitelerini kullanarak Şekilleri Bağlayın"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "PowerPoint'te Bağlantı Sitelerini kullanarak Şekilleri Bağlayın"
"url": "/tr/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Bağlantı Sitelerini kullanarak Şekilleri Bağlayın

## giriiş
Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint'te bağlantı sitelerini kullanarak şekilleri nasıl bağlayacağımızı keşfedeceğiz. Bu güçlü kütüphane, PowerPoint sunumlarını programatik olarak düzenlememizi ve şekilleri bağlama gibi görevleri sorunsuz ve verimli hale getirmemizi sağlar.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde Java'nın yüklü olduğundan emin olun. Java'yı şu adresten indirip yükleyebilirsiniz: [web sitesi](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Java için Aspose.Slides: Java için Aspose.Slides'ı indirin ve yükleyin [indirme sayfası](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA, Eclipse veya NetBeans gibi Java geliştirme için bir IDE seçin.

## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize aktarın:
```java
import com.aspose.slides.*;

```
## Adım 1: Şekiller Koleksiyonuna Erişim
Seçili slayt için şekiller koleksiyonuna erişin:
```java
// Belgeler dizinine giden yol.                    
String dataDir = "Your Document Directory";
// PPTX dosyasını temsil eden Sunum sınıfını örneklendirin
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Adım 2: Bağlayıcı Şekli Ekleme
Slayt şekli koleksiyonuna bir bağlayıcı şekli ekleyin:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Adım 3: Otomatik Şekiller Ekleme
Elips ve dikdörtgen gibi otomatik şekiller ekleyin:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Adım 4: Şekilleri Bağlayıcılara Birleştirme
Şekilleri bağlayıcıya bağlayın:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Adım 5: Bağlantı Sitesi Dizini Ayarlama
Şekiller için istenilen bağlantı yeri indeksini ayarlayın:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Çözüm
Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint'te bağlantı sitelerini kullanarak şekilleri nasıl bağlayacağımızı öğrendik. Bu bilgiyle artık PowerPoint sunumlarınızı kolaylıkla otomatikleştirebilir ve özelleştirebilirsiniz.
## SSS
### Aspose.Slides for Java diğer PowerPoint düzenleme görevlerinde kullanılabilir mi?
Evet, Aspose.Slides for Java, PowerPoint sunumları oluşturmak, düzenlemek ve dönüştürmek için geniş bir işlevsellik yelpazesi sunar.
### Aspose.Slides for Java'yı kullanmak ücretsiz mi?
Aspose.Slides for Java ticari bir kütüphanedir, ancak ücretsiz denemeyle özelliklerini keşfedebilirsiniz. Ziyaret edin [Burada](https://releases.aspose.com/) Başlamak için.
### Aspose.Slides for Java kullanırken herhangi bir sorunla karşılaşırsam destek alabilir miyim?
Evet, Aspose topluluk forumlarından destek alabilirsiniz [Burada](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java için geçici lisanslar mevcut mu?
Evet, test ve değerlendirme amaçları için geçici lisanslar mevcuttur. Bir tane alabilirsiniz [Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java lisansını nereden satın alabilirim?
Lisansı Aspose web sitesinden satın alabilirsiniz [Burada](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}