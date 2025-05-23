---
"description": "Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarınıza göreli ölçek yüksekliğinde resim çerçeveleri eklemeyi öğrenin ve görsel içeriğinizi geliştirin."
"linktitle": "PowerPoint'te Göreceli Ölçek Yükseklik Resim Çerçevesi Ekleme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "PowerPoint'te Göreceli Ölçek Yükseklik Resim Çerçevesi Ekleme"
"url": "/tr/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Göreceli Ölçek Yükseklik Resim Çerçevesi Ekleme

## giriiş
Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint sunumlarına göreli ölçek yüksekliğine sahip bir resim çerçevesinin nasıl ekleneceğini öğreneceksiniz.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Development Kit (JDK) yüklü.
2. Aspose.Slides for Java kütüphanesi indirildi ve Java projenize eklendi.

## Paketleri İçe Aktar
Başlamak için Java projenize gerekli paketleri içe aktarın:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Adım 1: Projenizi Kurun
Öncelikle projeniz için bir dizin oluşturduğunuzdan ve Java ortamınızın düzgün şekilde yapılandırıldığından emin olun.
## Adım 2: Sunum Nesnesini Örneklendirin
Aspose.Slides kullanarak yeni bir sunum nesnesi oluşturun:
```java
Presentation presentation = new Presentation();
```
## Adım 3: Eklenecek Resmi Yükle
Sunuma eklemek istediğiniz görseli yükleyin:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Adım 4: Slayda Resim Çerçevesi Ekleyin
Sunumdaki bir slayda resim çerçevesi ekleyin:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Adım 5: Göreceli Ölçek Genişliğini ve Yüksekliğini Ayarlayın
Resim çerçevesi için göreceli ölçek genişliğini ve yüksekliğini ayarlayın:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Adım 6: Sunumu Kaydedin
Sunuyu eklenen resim çerçevesiyle kaydedin:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu adımları izleyerek, Aspose.Slides for Java kullanarak PowerPoint sunumlarınıza göreli ölçek yüksekliğine sahip bir resim çerçevesi kolayca ekleyebilirsiniz. Görüntüleriniz için istediğiniz görünümü elde etmek için farklı ölçek değerleriyle denemeler yapın.

## SSS
### Bu yöntemi kullanarak tek bir slayda birden fazla resim çerçevesi ekleyebilir miyim?
Evet, her resim için işlemi tekrarlayarak bir slayda birden fazla resim çerçevesi ekleyebilirsiniz.
### Aspose.Slides for Java, PowerPoint'in tüm sürümleriyle uyumlu mudur?
Aspose.Slides for Java, PowerPoint'in çeşitli sürümleriyle uyumludur ve bu sayede sunum oluşturmada esneklik sağlar.
### Resim çerçevesinin konumunu ve boyutunu özelleştirebilir miyim?
Kesinlikle, konum ve boyut parametrelerini ayarlayabilirsiniz. `addPictureFrame` İhtiyaçlarınıza uygun bir yöntem.
### Aspose.Slides for Java JPEG dışında diğer resim formatlarını da destekliyor mu?
Evet, Aspose.Slides for Java PNG, GIF, BMP ve daha fazlası dahil olmak üzere çeşitli resim formatlarını destekler.
### Aspose.Slides kullanıcıları için bir topluluk forumu veya destek kanalı var mı?
Evet, kütüphaneyle ilgili her türlü soru, tartışma veya yardım için Aspose.Slides forumunu ziyaret edebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}