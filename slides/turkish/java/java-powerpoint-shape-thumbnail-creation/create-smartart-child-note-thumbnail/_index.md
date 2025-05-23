---
"description": "Aspose.Slides ile Java'da SmartArt alt not küçük resimlerinin nasıl oluşturulacağını öğrenin ve PowerPoint sunumlarınızı zahmetsizce geliştirin."
"linktitle": "SmartArt Çocuk Notu Küçük Resmi Oluştur"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "SmartArt Çocuk Notu Küçük Resmi Oluştur"
"url": "/tr/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# SmartArt Çocuk Notu Küçük Resmi Oluştur

## giriiş
Bu eğitimde, Aspose.Slides kullanarak Java'da SmartArt alt not küçük resimlerinin nasıl oluşturulacağını inceleyeceğiz. Aspose.Slides, geliştiricilerin PowerPoint sunumlarıyla programatik olarak çalışmasına olanak tanıyan güçlü bir Java API'sidir ve slaytları kolaylıkla oluşturmalarını, değiştirmelerini ve düzenlemelerini sağlar.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Development Kit (JDK) yüklü.
2. Projenizde indirilen ve yapılandırılan Java kütüphanesi için Aspose.Slides. Kütüphaneyi şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Java sınıfınıza gerekli paketleri aktardığınızdan emin olun:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Adım 1: Projenizi Kurun
Aspose.Slides kütüphanesi ile kurulu ve yapılandırılmış bir Java projeniz olduğundan emin olun.
## Adım 2: Bir Sunum Oluşturun
Örneklemi oluştur `Presentation` PPTX dosyasını temsil eden sınıf:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Adım 3: SmartArt ekleyin
Sunum slaydınıza SmartArt ekleyin:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Adım 4: Bir Düğüm Referansı Edinin
Bir düğümün referansını dizinini kullanarak elde edin:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Adım 5: Küçük resmi alın
SmartArt düğümünün küçük resim görüntüsünü alın:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Adım 6: Küçük resmi kaydedin
Küçük resim görüntüsünü bir dosyaya kaydedin:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Sunumunuzda ihtiyaç duyduğunuz her SmartArt düğümü için bu adımları tekrarlayın.

## Çözüm
Bu eğitimde, Aspose.Slides kullanarak Java'da SmartArt alt not küçük resimlerinin nasıl oluşturulacağını öğrendik. Bu bilgiyle, PowerPoint sunumlarınızı programatik olarak geliştirebilir, görsel olarak çekici öğeleri kolaylıkla ekleyebilirsiniz.
## SSS
### Mevcut PowerPoint dosyalarını düzenlemek için Aspose.Slides'ı kullanabilir miyim?
Evet, Aspose.Slides mevcut PowerPoint dosyalarını değiştirmenize, slaytları ve içeriklerini eklemenize, kaldırmanıza veya düzenlemenize olanak tanır.
### Aspose.Slides slaytların farklı dosya formatlarına aktarılmasını destekliyor mu?
Kesinlikle! Aspose.Slides slaytları PDF, resim ve HTML gibi çeşitli formatlara aktarmayı destekler.
### Aspose.Slides kurumsal düzeyde PowerPoint otomasyonu için uygun mudur?
Evet, Aspose.Slides kurumsal düzeydeki PowerPoint otomasyon görevlerini etkin ve güvenilir bir şekilde gerçekleştirmek üzere tasarlanmıştır.
### Aspose.Slides ile karmaşık SmartArt diyagramlarını program aracılığıyla oluşturabilir miyim?
Elbette! Aspose.Slides, farklı karmaşıklık düzeylerindeki SmartArt diyagramlarının oluşturulması ve düzenlenmesi için kapsamlı destek sağlar.
### Aspose.Slides geliştiricilere teknik destek sunuyor mu?
Evet, Aspose.Slides geliştiricilere özel teknik destek sağlar [forum](https://forum.aspose.com/c/slides/11) ve diğer kanallar.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}