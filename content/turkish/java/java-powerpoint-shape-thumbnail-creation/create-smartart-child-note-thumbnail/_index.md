---
title: SmartArt Alt Notu Küçük Resmi Oluşturun
linktitle: SmartArt Alt Notu Küçük Resmi Oluşturun
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java'da SmartArt alt not küçük resimlerini nasıl oluşturacağınızı öğrenin ve PowerPoint sunumlarınızı zahmetsizce geliştirin.
type: docs
weight: 15
url: /tr/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---
## giriiş
Bu eğitimde Aspose.Slides kullanarak Java'da SmartArt alt not küçük resimlerinin nasıl oluşturulacağını keşfedeceğiz. Aspose.Slides, geliştiricilerin PowerPoint sunumlarıyla programlı olarak çalışmasına olanak tanıyan, slaytları kolaylıkla oluşturmalarına, değiştirmelerine ve işlemelerine olanak tanıyan güçlü bir Java API'sidir.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
2. Aspose.Slides for Java kütüphanesi indirildi ve projenizde yapılandırıldı. Kütüphaneyi adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Gerekli paketleri Java sınıfınıza aktardığınızdan emin olun:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1. Adım: Projenizi Kurun
Aspose.Slides kütüphanesiyle kurulu ve yapılandırılmış bir Java projeniz olduğundan emin olun.
## Adım 2: Bir Sunu Oluşturun
 Örnekleyin`Presentation` PPTX dosyasını temsil edecek sınıf:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## 3. Adım: SmartArt'ı ekleyin
SmartArt'ı sunum slaytınıza ekleyin:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Adım 4: Bir Düğüm Referansı Alın
Bir düğümün referansını indeksini kullanarak elde edin:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## 5. Adım: Küçük Resmi Alın
SmartArt düğümünün küçük resim görüntüsünü alın:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Adım 6: Küçük Resmi Kaydet
Küçük resim görüntüsünü bir dosyaya kaydedin:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Sunumunuzda gerektiği gibi her SmartArt düğümü için bu adımları tekrarlayın.

## Çözüm
Bu eğitimde Aspose.Slides'ı kullanarak Java'da SmartArt alt not küçük resimlerinin nasıl oluşturulacağını öğrendik. Bu bilgiyle PowerPoint sunumlarınızı programlı olarak geliştirebilir ve görsel olarak çekici öğeleri kolaylıkla ekleyebilirsiniz.
## SSS'ler
### Aspose.Slides'ı mevcut PowerPoint dosyalarını düzenlemek için kullanabilir miyim?
Evet, Aspose.Slides, slaytları ve içeriklerini eklemek, kaldırmak veya düzenlemek de dahil olmak üzere mevcut PowerPoint dosyalarını değiştirmenize olanak tanır.
### Aspose.Slides slaytların farklı dosya formatlarına aktarılmasını destekliyor mu?
Kesinlikle! Aspose.Slides, slaytların PDF, görseller ve HTML gibi çeşitli formatlara aktarılmasını destekler.
### Aspose.Slides kurumsal düzeyde PowerPoint otomasyonuna uygun mu?
Evet, Aspose.Slides, kurumsal düzeyde PowerPoint otomasyon görevlerini verimli ve güvenilir bir şekilde gerçekleştirmek üzere tasarlanmıştır.
### Aspose.Slides ile programlı olarak karmaşık SmartArt diyagramları oluşturabilir miyim?
Kesinlikle! Aspose.Slides, farklı karmaşıklıktaki SmartArt diyagramlarını oluşturmak ve değiştirmek için kapsamlı destek sağlar.
### Aspose.Slides geliştiricilere teknik destek sunuyor mu?
 Evet, Aspose.Slides geliştiricilere özel teknik destek sağlıyor.[forum](https://forum.aspose.com/c/slides/11) ve diğer kanallar.