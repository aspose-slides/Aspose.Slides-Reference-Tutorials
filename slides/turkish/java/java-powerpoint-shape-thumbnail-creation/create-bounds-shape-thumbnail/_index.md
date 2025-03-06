---
title: Sınır Şekli Küçük Resmi Oluşturma
linktitle: Sınır Şekli Küçük Resmi Oluşturma
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak sınırları olan şekil küçük resimleri oluşturmayı öğrenin. Bu adım adım eğitim, süreç boyunca size yol gösterir.
weight: 10
url: /tr/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sınır Şekli Küçük Resmi Oluşturma

## giriiş
Aspose.Slides for Java, Java geliştiricilerinin PowerPoint sunumlarını programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır. Bu eğitimde Aspose.Slides for Java'yı kullanarak sınırları olan bir şeklin küçük resmini nasıl oluşturacağımızı öğreneceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
2.  Aspose.Slides for Java kütüphanesi indirildi ve projenize eklendi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Gerekli paketleri Java kodunuza aktardığınızdan emin olun:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1. Adım: Projenizi Kurun
Tercih ettiğiniz IDE'de yeni bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin bağımlılıklarına ekleyin.
## Adım 2: Bir Sunum Nesnesini Örneklendirin
 Bir örnek oluştur`Presentation` PowerPoint sunum dosyanızın yolunu sağlayarak nesneyi seçin.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## 3. Adım: Sınır Şekli Küçük Resmi Oluşturun
Şimdi sunumdan sınırları olan bir şeklin küçük resmini oluşturalım.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Çözüm
Bu eğitimde Aspose.Slides for Java'yı kullanarak sınırları olan bir şeklin küçük resmini nasıl oluşturacağımızı öğrendik. Bu adımları izleyerek PowerPoint sunumlarınızda programlı olarak kolayca şekillerin küçük resimlerini oluşturabilirsiniz.
## SSS'ler
### Bir slayttaki belirli şekiller için küçük resimler oluşturabilir miyim?
Evet, Aspose.Slides for Java'yı kullanarak bir slayttaki şekillere ayrı ayrı erişebilir ve onlar için küçük resimler oluşturabilirsiniz.
### Aspose.Slides for Java, PowerPoint dosyalarının tüm sürümleriyle uyumlu mu?
Aspose.Slides for Java, PPT, PPTX, PPS, PPSX ve daha fazlası dahil olmak üzere çeşitli PowerPoint dosya formatlarını destekler.
### Oluşturulan küçük resimlerin görünümünü özelleştirebilir miyim?
Evet, küçük resimlerin boyut ve kalite gibi özelliklerini ihtiyaçlarınıza göre ayarlayabilirsiniz.
### Aspose.Slides for Java, küçük resim oluşturmanın yanı sıra diğer özellikleri de destekliyor mu?
Evet, Aspose.Slides for Java, PowerPoint sunumlarıyla çalışmak için slayt düzenleme, metin çıkarma ve grafik oluşturma dahil olmak üzere kapsamlı işlevsellik sağlar.
### Aspose.Slides for Java'nın deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
