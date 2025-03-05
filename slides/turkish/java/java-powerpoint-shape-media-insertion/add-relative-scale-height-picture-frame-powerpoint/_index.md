---
title: PowerPoint'te Göreli Ölçekli Yükseklik Resim Çerçevesi Ekleme
linktitle: PowerPoint'te Göreli Ölçekli Yükseklik Resim Çerçevesi Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak PowerPoint sunumlarınıza göreli ölçek yüksekliğinde resim çerçeveleri eklemeyi öğrenin ve görsel içeriğinizi geliştirin.
type: docs
weight: 15
url: /tr/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---
## giriiş
Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint sunumlarına göreceli ölçek yüksekliğine sahip bir resim çerçevesinin nasıl ekleneceğini öğreneceksiniz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
2. Aspose.Slides for Java kütüphanesi indirildi ve Java projenize eklendi.

## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize aktarın:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1. Adım: Projenizi Kurun
Öncelikle projeniz için bir dizin oluşturduğunuzdan ve Java ortamınızın doğru şekilde yapılandırıldığından emin olun.
## Adım 2: Sunum Nesnesini Örneklendirin
Aspose.Slides'ı kullanarak yeni bir sunum nesnesi oluşturun:
```java
Presentation presentation = new Presentation();
```
## 3. Adım: Eklenecek Resmi Yükleyin
Sunuya eklemek istediğiniz resmi yükleyin:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Adım 4: Slayta Resim Çerçevesi Ekleme
Sunudaki bir slayda resim çerçevesi ekleyin:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Adım 5: Göreli Ölçek Genişliğini ve Yüksekliğini Ayarlayın
Resim çerçevesinin göreceli ölçek genişliğini ve yüksekliğini ayarlayın:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Adım 6: Sunuyu Kaydet
Sunuyu eklenen resim çerçevesiyle kaydedin:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu adımları izleyerek Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarınıza kolayca göreli ölçek yüksekliğine sahip bir resim çerçevesi ekleyebilirsiniz. Resimlerinizde istediğiniz görünümü elde etmek için farklı ölçek değerleriyle denemeler yapın.

## SSS'ler
### Bu yöntemi kullanarak tek bir slayda birden fazla resim çerçevesi ekleyebilir miyim?
Evet, her görüntü için işlemi tekrarlayarak bir slayda birden fazla resim çerçevesi ekleyebilirsiniz.
### Aspose.Slides for Java, PowerPoint'in tüm sürümleriyle uyumlu mu?
Aspose.Slides for Java, PowerPoint'in çeşitli sürümleriyle uyumlu olduğundan sunum oluşturmada esneklik sağlar.
### Resim çerçevesinin konumunu ve boyutunu özelleştirebilir miyim?
 Kesinlikle konum ve boyut parametrelerini ayarlayabilirsiniz.`addPictureFrame` gereksinimlerinize uygun yöntem.
### Aspose.Slides for Java, JPEG'in yanı sıra diğer görüntü formatlarını da destekliyor mu?
Evet, Aspose.Slides for Java PNG, GIF, BMP ve daha fazlası dahil olmak üzere çeşitli görüntü formatlarını destekler.
### Aspose.Slides kullanıcıları için bir topluluk forumu veya destek kanalı var mı?
Evet, kütüphaneyle ilgili her türlü soru, tartışma veya yardım için Aspose.Slides forumunu ziyaret edebilirsiniz.