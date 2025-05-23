---
"description": "Java için Aspose.Slides kullanarak sınırlarla şekil küçük resimlerinin nasıl oluşturulacağını öğrenin. Bu adım adım eğitim sizi süreç boyunca yönlendirir."
"linktitle": "Sınırlar Şekil Küçük Resmini Oluştur"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Sınırlar Şekil Küçük Resmini Oluştur"
"url": "/tr/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Sınırlar Şekil Küçük Resmini Oluştur

## giriiş
Aspose.Slides for Java, Java geliştiricilerinin PowerPoint sunumlarını programatik olarak oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan güçlü bir kütüphanedir. Bu eğitimde, Aspose.Slides for Java kullanarak sınırları olan bir şeklin küçük resim görüntüsünün nasıl oluşturulacağını öğreneceğiz.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Development Kit (JDK) yüklü.
2. Java kütüphanesi için Aspose.Slides indirildi ve projenize eklendi. Buradan indirebilirsiniz [Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Java kodunuza gerekli paketleri aktardığınızdan emin olun:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Adım 1: Projenizi Kurun
Tercih ettiğiniz IDE'de yeni bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin bağımlılıklarına ekleyin.
## Adım 2: Bir Sunum Nesnesi Oluşturun
Bir örnek oluştur `Presentation` PowerPoint sunum dosyanıza giden yolu sağlayarak nesneyi bulun.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Adım 3: Sınır Şekli Küçük Resmini Oluşturun
Şimdi sunumdaki şeklin sınırlarıyla birlikte küçük resmini oluşturalım.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Çözüm
Bu eğitimde, Aspose.Slides for Java kullanarak sınırları olan bir şeklin küçük resim görüntüsünün nasıl oluşturulacağını öğrendik. Bu adımları izleyerek, PowerPoint sunumlarınızdaki şekillerin küçük resimlerini programatik olarak kolayca oluşturabilirsiniz.
## SSS
### Bir slayttaki belirli şekiller için küçük resimler oluşturabilir miyim?
Evet, Aspose.Slides for Java'yı kullanarak bir slayttaki ayrı şekillere erişebilir ve bunlar için küçük resimler oluşturabilirsiniz.
### Aspose.Slides for Java, PowerPoint dosyalarının tüm sürümleriyle uyumlu mudur?
Aspose.Slides for Java, PPT, PPTX, PPS, PPSX ve daha fazlası dahil olmak üzere çeşitli PowerPoint dosya biçimlerini destekler.
### Oluşturulan küçük resimlerin görünümünü özelleştirebilir miyim?
Evet, ihtiyaçlarınıza göre küçük resim görsellerinin boyut ve kalite gibi özelliklerini ayarlayabilirsiniz.
### Aspose.Slides for Java küçük resim oluşturmanın dışında başka özellikleri de destekliyor mu?
Evet, Aspose.Slides for Java, slayt düzenleme, metin çıkarma ve grafik oluşturma dahil olmak üzere PowerPoint sunumlarıyla çalışmak için kapsamlı işlevler sağlar.
### Aspose.Slides for Java için deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}