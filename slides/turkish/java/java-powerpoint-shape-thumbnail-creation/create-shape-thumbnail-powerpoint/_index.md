---
title: PowerPoint'te Şekil Küçük Resmi Oluşturma
linktitle: PowerPoint'te Şekil Küçük Resmi Oluşturma
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarında şekil küçük resimleri oluşturmayı öğrenin. Adım adım kılavuz sağlanmıştır.
weight: 14
url: /tr/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Bu eğitimde Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarında şekil küçük resimleri oluşturmayı ele alacağız. Aspose.Slides, geliştiricilerin PowerPoint dosyalarıyla programlı olarak çalışmasına olanak tanıyan, şekil küçük resimleri oluşturmak da dahil olmak üzere çeşitli görevlerin otomasyonuna olanak tanıyan güçlü bir kitaplıktır.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Java programlamanın temel bilgisi.
- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Slides for Java kütüphanesini indirip projenize kurun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Aspose.Slides'ın fonksiyonlarını kullanabilmek için öncelikle Java kodunuza gerekli paketleri içe aktarmanız gerekiyor. Java dosyanızın başına aşağıdaki içe aktarma ifadelerini ekleyin:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1. Adım: Belge Dizinini Tanımlayın
```java
String dataDir = "Your Document Directory";
```
 Yer değiştirmek`"Your Document Directory"` PowerPoint dosyanızı içeren dizinin yolu ile birlikte.
## Adım 2: Sunum Nesnesini Örneklendirin
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
 Yeni bir örneğini oluşturun`Presentation` sınıf, PowerPoint dosyanızın yolunu parametre olarak iletir.
## 3. Adım: Şekil Küçük Resmi Oluşturun
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Sununun ilk slaytından istediğiniz şeklin küçük resmini alın.
## Adım 4: Küçük Resim Resmini Kaydedin
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Oluşturulan küçük resim görüntüsünü belirtilen dosya adıyla PNG formatında diske kaydedin.

## Çözüm
Sonuç olarak bu eğitimde Aspose.Slides for Java kullanılarak PowerPoint sunumlarında şekil küçük resimlerinin nasıl oluşturulacağı gösterildi. Adım adım kılavuzu izleyerek ve sağlanan kod parçacıklarını kullanarak, programlı olarak etkili bir şekilde şekil küçük resimleri oluşturabilirsiniz.

## SSS'ler
### Sunumdaki herhangi bir slayttaki şekiller için küçük resimler oluşturabilir miyim?
Evet, slayt dizinini uygun şekilde ayarlayarak kodu herhangi bir slayttaki şekilleri hedefleyecek şekilde değiştirebilirsiniz.
### Aspose.Slides küçük resimlerin kaydedilmesi için diğer görüntü formatlarını destekliyor mu?
Evet, Aspose.Slides PNG'nin yanı sıra küçük resimlerin JPEG, GIF ve BMP gibi çeşitli görüntü formatlarında kaydedilmesini de destekler.
### Aspose.Slides ticari kullanıma uygun mudur?
 Evet, Aspose.Slides işletmeler ve kuruluşlar için ticari lisanslar sunmaktadır. adresinden lisans satın alabilirsiniz.[Burada](https://purchase.aspose.com/buy).
### Satın almadan önce Aspose.Slides'ı deneyebilir miyim?
 Kesinlikle! Aspose.Slides'ın ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/) özelliklerini ve yeteneklerini değerlendirmek.
### Aspose.Slides için nereden destek bulabilirim?
 Aspose.Slides ile ilgili herhangi bir sorunuz varsa veya yardıma ihtiyacınız varsa şu adresi ziyaret edebilirsiniz:[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) destek için.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
