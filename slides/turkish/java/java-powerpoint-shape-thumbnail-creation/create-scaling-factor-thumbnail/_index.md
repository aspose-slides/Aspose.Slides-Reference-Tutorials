---
title: Ölçeklendirme Faktörü Küçük Resmi Oluştur
linktitle: Ölçeklendirme Faktörü Küçük Resmi Oluştur
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java'da ölçeklendirme faktörü küçük resimlerini nasıl oluşturacağınızı öğrenin. Adım adım talimatlar içeren takip edilmesi kolay kılavuz.
type: docs
weight: 12
url: /tr/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---
## giriiş
Bu eğitimde Aspose.Slides for Java'yı kullanarak ölçeklendirme faktörü küçük resmi oluşturma sürecinde size rehberlik edeceğiz. İstediğiniz sonuca ulaşmak için bu adım adım talimatları izleyin.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
- Aspose.Slides for Java kütüphanesini indirip Java projenize kurun.
- Java programlama dilinin temel anlayışı.

## Paketleri İçe Aktar
Öncelikle Aspose.Slides ile çalışmak için gerekli olan paketleri Java kodunuza aktarın. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Şimdi verilen örneği birden çok adıma ayıralım:
## 1. Adım: Belge Dizinini Ayarlayın
PowerPoint sunum dosyasının bulunduğu belge dizininizin yolunu tanımlayın.
```java
String dataDir = "Your Document Directory";
```
 Yer değiştirmek`"Your Document Directory"` gerçek belge dizininizin yolu ile.
## Adım 2: Sunum Nesnesini Örneklendirin
PowerPoint sunum dosyasını temsil edecek Sunum sınıfının bir örneğini oluşturun.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Değiştirildiğinden emin olun`"HelloWorld.pptx"` PowerPoint sunum dosyanızın adıyla.
## 3. Adım: Tam Ölçekli Görüntü Oluşturun
Sunudan istediğiniz slaydın tam ölçekli görüntüsünü oluşturun.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Bu kod, sunumun ilk slaydındaki ilk şeklin küçük resmini alır.
## Adım 4: Görüntüyü Kaydedin
Oluşturulan görüntüyü PNG formatında diske kaydedin.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Değiştirildiğinden emin olun`"Scaling Factor Thumbnail_out.png"` İstenilen çıktı dosyası adı ile.

## Çözüm
Sonuç olarak, Aspose.Slides for Java'yı kullanarak başarıyla bir ölçeklendirme faktörü küçük resmi oluşturdunuz. Verilen adımları takip ederek bu işlevselliği Java uygulamalarınıza kolayca entegre edebilirsiniz.
## SSS'ler
### Aspose.Slides for Java'yı herhangi bir Java IDE ile kullanabilir miyim?
Evet, Aspose.Slides for Java, Eclipse, IntelliJ IDEA veya NetBeans gibi herhangi bir Java Entegre Geliştirme Ortamı (IDE) ile kullanılabilir.
### Aspose.Slides for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, adresini ziyaret ederek Aspose.Slides for Java'nın ücretsiz denemesinden yararlanabilirsiniz.[İnternet sitesi](https://releases.aspose.com/).
### Aspose.Slides for Java desteğini nerede bulabilirim?
 Aspose.Slides for Java desteğini şu adreste bulabilirsiniz:[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java'yı nasıl satın alabilirim?
 Aspose.Slides for Java'yı şu adresten satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).
### Aspose.Slides for Java'yı kullanmak için geçici bir lisansa ihtiyacım var mı?
 Evet, geçici lisansı şu adresten alabilirsiniz:[geçici lisans sayfası](https://purchase.aspose.com/temporary-license/).