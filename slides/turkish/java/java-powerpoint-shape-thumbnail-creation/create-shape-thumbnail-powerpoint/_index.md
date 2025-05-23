---
"description": "Aspose.Slides for Java kullanarak PowerPoint sunumlarında şekil küçük resimlerinin nasıl oluşturulacağını öğrenin. Adım adım kılavuz sağlanır."
"linktitle": "PowerPoint'te Şekil Küçük Resmi Oluşturma"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "PowerPoint'te Şekil Küçük Resmi Oluşturma"
"url": "/tr/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Şekil Küçük Resmi Oluşturma

## giriiş
Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint sunumlarında şekil küçük resimleri oluşturmayı inceleyeceğiz. Aspose.Slides, geliştiricilerin PowerPoint dosyalarıyla programatik olarak çalışmasını sağlayan ve şekil küçük resimleri oluşturma da dahil olmak üzere çeşitli görevlerin otomasyonuna olanak tanıyan güçlü bir kütüphanedir.
## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Temel Java programlama bilgisi.
- Sisteminizde Java Development Kit (JDK) yüklü.
- Java kütüphanesi için Aspose.Slides indirildi ve projenize kuruldu. Bunu şuradan indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Öncelikle, Aspose.Slides'ın işlevselliklerinden faydalanmak için gerekli paketleri Java kodunuza aktarmanız gerekir. Java dosyanızın başına aşağıdaki içe aktarma ifadelerini ekleyin:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Adım 1: Belge Dizinini Tanımlayın
```java
String dataDir = "Your Document Directory";
```
Yer değiştirmek `"Your Document Directory"` PowerPoint dosyanızın bulunduğu dizinin yolunu belirtin.
## Adım 2: Sunum Nesnesini Örneklendirin
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
Yeni bir örnek oluşturun `Presentation` sınıf, PowerPoint dosyanızın yolunu parametre olarak geçirerek.
## Adım 3: Şekil Küçük Resmini Oluşturun
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Sunumun ilk slaydından istediğiniz şeklin küçük resmini alın.
## Adım 4: Küçük Resim Görüntüsünü Kaydedin
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Oluşturulan küçük resim görüntüsünü PNG formatında belirtilen dosya adıyla diske kaydedin.

## Çözüm
Sonuç olarak, bu eğitim Aspose.Slides for Java kullanarak PowerPoint sunumlarında şekil küçük resimlerinin nasıl oluşturulacağını gösterdi. Adım adım kılavuzu izleyerek ve sağlanan kod parçacıklarını kullanarak, şekil küçük resimlerini programatik olarak verimli bir şekilde oluşturabilirsiniz.

## SSS
### Sunumdaki herhangi bir slayttaki şekiller için küçük resim oluşturabilir miyim?
Evet, slayt dizinini buna göre ayarlayarak kodu herhangi bir slayttaki şekilleri hedefleyecek şekilde değiştirebilirsiniz.
### Aspose.Slides küçük resimleri kaydetmek için diğer resim formatlarını destekliyor mu?
Evet, PNG'nin yanı sıra Aspose.Slides küçük resimleri JPEG, GIF ve BMP gibi çeşitli resim formatlarında kaydetmeyi de destekliyor.
### Aspose.Slides ticari kullanıma uygun mudur?
Evet, Aspose.Slides işletmeler ve kuruluşlar için ticari lisanslar sunar. Lisansı şu adresten satın alabilirsiniz: [Burada](https://purchase.aspose.com/buy).
### Satın almadan önce Aspose.Slides'ı deneyebilir miyim?
Kesinlikle! Aspose.Slides'ın ücretsiz deneme sürümünü şuradan indirebilirsiniz: [Burada](https://releases.aspose.com/) özelliklerini ve kabiliyetlerini değerlendirmek.
### Aspose.Slides için desteği nereden bulabilirim?
Aspose.Slides ile ilgili herhangi bir sorunuz varsa veya yardıma ihtiyacınız varsa, şu adresi ziyaret edebilirsiniz: [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) destek için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}