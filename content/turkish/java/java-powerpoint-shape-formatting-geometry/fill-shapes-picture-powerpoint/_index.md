---
title: PowerPoint'te Şekilleri Resimle Doldurma
linktitle: PowerPoint'te Şekilleri Resimle Doldurma
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarında şekilleri resimlerle nasıl dolduracağınızı öğrenin. Görsel çekiciliği zahmetsizce geliştirin.
type: docs
weight: 12
url: /tr/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/
---
## giriiş
PowerPoint sunumları, çekiciliğini artırmak ve bilgileri etkili bir şekilde iletmek için genellikle resimlerle dolu şekiller gibi görsel öğeler gerektirir. Aspose.Slides for Java, bu görevi sorunsuz bir şekilde gerçekleştirmek için güçlü bir araç seti sağlar. Bu derste Aspose.Slides for Java kullanarak şekilleri resimlerle nasıl dolduracağımızı adım adım öğreneceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
2.  Aspose.Slides for Java kütüphanesi indirildi. Şu adresten alabilirsiniz:[Burada](https://releases.aspose.com/slides/java/).
3. Java programlamanın temel bilgisi.
## Paketleri İçe Aktar
Java projenizde gerekli paketleri içe aktarın:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1. Adım: Proje Dizinini Ayarlayın
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
 Değiştirildiğinden emin olun`"Your Document Directory"` proje dizininizin yolu ile.
## Adım 2: Bir Sunu Oluşturun
```java
Presentation pres = new Presentation();
```
 Örnekleyin`Presentation` Yeni bir PowerPoint sunusu oluşturmak için sınıfa gidin.
## 3. Adım: Slayt ve Şekil Ekleme
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Sunuya bir slayt ekleyin ve üzerinde dikdörtgen bir şekil oluşturun.
## Adım 4: Doldurma Türünü Resim Olarak Ayarlayın
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
Şeklin dolgu türünü resim olarak ayarlayın.
## Adım 5: Resim Doldurma Modunu Ayarlayın
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
Şeklin resim doldurma modunu ayarlayın.
## Adım 6: Resmi Ayarlayın
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
Görüntüyü yükleyin ve şeklin dolgusu olarak ayarlayın.
## Adım 7: Sunumu Kaydet
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
Değiştirilen sunumu bir dosyaya kaydedin.

## Çözüm
Aspose.Slides for Java ile PowerPoint sunumlarındaki şekilleri resimlerle doldurmak basit bir süreç haline geliyor. Bu eğitimde özetlenen adımları izleyerek sunumlarınızı görsel olarak çekici öğelerle kolayca geliştirebilirsiniz.

## SSS'ler
### Aspose.Slides for Java'yı kullanarak farklı şekilleri resimlerle doldurabilir miyim?
Evet, Aspose.Slides for Java, çeşitli şekillerin resimlerle doldurulmasını destekleyerek tasarımda esneklik sağlar.
### Aspose.Slides for Java, PowerPoint'in tüm sürümleriyle uyumlu mu?
Aspose.Slides for Java, PowerPoint 97 ve üzeri ile uyumlu sunumlar oluşturarak geniş uyumluluk sağlar.
### Şeklin içindeki görüntüyü nasıl yeniden boyutlandırabilirim?
Şeklin boyutlarını ayarlayarak veya görüntüyü dolgu olarak ayarlamadan önce buna göre ölçeklendirerek şeklin içindeki görüntüyü yeniden boyutlandırabilirsiniz.
### Şekilleri doldurmak için desteklenen görüntü formatlarında herhangi bir sınırlama var mı?
Aspose.Slides for Java, aralarında JPEG, PNG, GIF, BMP ve TIFF'in de bulunduğu çok çeşitli görüntü formatlarını destekler.
### Doldurulan şekillere efekt uygulayabilir miyim?
Evet, Aspose.Slides for Java, doldurulmuş şekillere gölgeler, yansımalar ve 3D döndürmeler gibi çeşitli efektleri uygulamak için kapsamlı API'ler sağlar.