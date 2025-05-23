---
"description": "Java için Aspose.Slides'ı kullanarak Java'da ölçekleme faktörü küçük resimlerinin nasıl oluşturulacağını öğrenin. Adım adım talimatlarla kolay takip edilebilir kılavuz."
"linktitle": "Ölçekleme Faktörü Küçük Resmini Oluştur"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Ölçekleme Faktörü Küçük Resmini Oluştur"
"url": "/tr/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ölçekleme Faktörü Küçük Resmini Oluştur

## giriiş
Bu eğitimde, Aspose.Slides for Java kullanarak bir ölçekleme faktörü küçük resmi oluşturma sürecinde size rehberlik edeceğiz. İstediğiniz sonucu elde etmek için bu adım adım talimatları izleyin.
## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Sisteminizde Java Development Kit (JDK) yüklü.
- Java için Aspose.Slides kütüphanesini indirip Java projenize kurun.
- Java programlama dilinin temel düzeyde anlaşılması.

## Paketleri İçe Aktar
Öncelikle Aspose.Slides ile çalışmak için gerekli paketleri Java kodunuza aktarın. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Şimdi verilen örneği birden fazla adıma bölelim:
## Adım 1: Belge Dizinini Ayarlayın
PowerPoint sunum dosyasının bulunduğu belge dizinine giden yolu tanımlayın.
```java
String dataDir = "Your Document Directory";
```
Yer değiştirmek `"Your Document Directory"` gerçek belge dizininize giden yol ile.
## Adım 2: Sunum Nesnesini Örneklendirin
PowerPoint sunum dosyasını temsil edecek bir Sunum sınıfı örneği oluşturun.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
Değiştirdiğinizden emin olun `"HelloWorld.pptx"` PowerPoint sunum dosyanızın adıyla.
## Adım 3: Tam Ölçekli Görüntü Oluşturun
Sunumdan istediğiniz slaydın tam ölçekli görüntüsünü oluşturun.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Bu kod sunumun ilk slaydındaki ilk şeklin küçük resmini alır.
## Adım 4: Görüntüyü Kaydedin
Oluşturulan görüntüyü PNG formatında diske kaydedin.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
Değiştirdiğinizden emin olun `"Scaling Factor Thumbnail_out.png"` İstenilen çıktı dosya adı ile.

## Çözüm
Sonuç olarak, Java için Aspose.Slides kullanarak bir ölçekleme faktörü küçük resmini başarıyla oluşturdunuz. Sağlanan adımları izleyerek, bu işlevselliği Java uygulamalarınıza kolayca entegre edebilirsiniz.
## SSS
### Aspose.Slides for Java'yı herhangi bir Java IDE ile kullanabilir miyim?
Evet, Aspose.Slides for Java, Eclipse, IntelliJ IDEA veya NetBeans gibi herhangi bir Java Entegre Geliştirme Ortamı (IDE) ile kullanılabilir.
### Aspose.Slides for Java için ücretsiz deneme sürümü mevcut mu?
Evet, Aspose.Slides for Java'nın ücretsiz deneme sürümünden yararlanmak için şu adresi ziyaret edin: [web sitesi](https://releases.aspose.com/).
### Aspose.Slides for Java desteğini nerede bulabilirim?
Java için Aspose.Slides desteğini şu adreste bulabilirsiniz: [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java'yı nasıl satın alabilirim?
Java için Aspose.Slides'ı şu adresten satın alabilirsiniz: [satın alma sayfası](https://purchase.aspose.com/buy).
### Aspose.Slides for Java'yı kullanmak için geçici bir lisansa ihtiyacım var mı?
Evet, geçici bir lisans alabilirsiniz. [geçici lisans sayfası](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}