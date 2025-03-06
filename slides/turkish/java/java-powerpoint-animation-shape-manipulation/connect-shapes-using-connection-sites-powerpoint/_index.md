---
title: PowerPoint'te Bağlantı Sitelerini Kullanarak Şekilleri Bağlama
linktitle: PowerPoint'te Bağlantı Sitelerini Kullanarak Şekilleri Bağlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak PowerPoint'te şekilleri nasıl bağlayacağınızı öğrenin. Sunumlarınızı zahmetsizce otomatikleştirin.
weight: 19
url: /tr/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint'teki bağlantı sitelerini kullanarak şekilleri nasıl bağlayacağınızı keşfedeceğiz. Bu güçlü kitaplık, PowerPoint sunumlarını programlı bir şekilde düzenlememize olanak tanıyarak şekilleri bağlama gibi görevleri sorunsuz ve verimli hale getirir.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde Java'nın kurulu olduğundan emin olun. adresinden indirip kurabilirsiniz.[İnternet sitesi](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java'yı şu adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): Java geliştirme için IntelliJ IDEA, Eclipse veya NetBeans gibi bir IDE seçin.

## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize aktarın:
```java
import com.aspose.slides.*;

```
## 1. Adım: Şekiller Koleksiyonuna Erişim
Seçilen slaydın şekil koleksiyonuna erişin:
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// PPTX dosyasını temsil eden Örnek Sunum sınıfını oluşturun
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Adım 2: Bağlayıcı Şekli Ekleme
Slayt şekli koleksiyonuna bir bağlayıcı şekli ekleyin:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## 3. Adım: Otomatik Şekiller Ekleme
Elips ve dikdörtgen gibi otomatik şekiller ekleyin:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Adım 4: Şekilleri Bağlayıcılara Birleştirme
Şekilleri bağlayıcıya birleştirin:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Adım 5: Bağlantı Sitesi Dizinini Ayarlama
Şekiller için istediğiniz bağlantı sitesi dizinini ayarlayın:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Çözüm
Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint'teki bağlantı sitelerini kullanarak şekilleri nasıl bağlayacağımızı öğrendik. Bu bilgiyle artık PowerPoint sunumlarınızı kolaylıkla otomatikleştirebilir ve özelleştirebilirsiniz.
## SSS'ler
### Aspose.Slides for Java diğer PowerPoint düzenleme görevleri için kullanılabilir mi?
Evet, Aspose.Slides for Java, PowerPoint sunumları oluşturmak, düzenlemek ve dönüştürmek için çok çeşitli işlevler sağlar.
### Aspose.Slides for Java'nın kullanımı ücretsiz mi?
 Aspose.Slides for Java ticari bir kütüphanedir ancak özelliklerini ücretsiz deneme sürümüyle keşfedebilirsiniz. Ziyaret etmek[Burada](https://releases.aspose.com/) başlamak.
### Aspose.Slides for Java'yı kullanırken herhangi bir sorunla karşılaşırsam destek alabilir miyim?
 Evet, Aspose topluluk forumlarından destek alabilirsiniz[Burada](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java için geçici lisanslar mevcut mu?
 Evet, test ve değerlendirme amaçlı geçici lisanslar mevcuttur. Bir tane alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java lisansını nereden satın alabilirim?
Aspose web sitesinden lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
