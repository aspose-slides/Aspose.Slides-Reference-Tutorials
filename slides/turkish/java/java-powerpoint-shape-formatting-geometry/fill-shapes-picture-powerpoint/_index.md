---
"description": "Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki şekilleri resimlerle nasıl dolduracağınızı öğrenin. Görsel çekiciliği zahmetsizce artırın."
"linktitle": "PowerPoint'te Şekilleri Resimle Doldurun"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "PowerPoint'te Şekilleri Resimle Doldurun"
"url": "/tr/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Şekilleri Resimle Doldurun

## giriiş
PowerPoint sunumları, çekiciliğini artırmak ve bilgileri etkili bir şekilde iletmek için genellikle şekiller gibi görsel öğeler gerektirir. Aspose.Slides for Java, bu görevi sorunsuz bir şekilde gerçekleştirmek için güçlü bir araç seti sunar. Bu eğitimde, Aspose.Slides for Java kullanarak şekilleri resimlerle nasıl dolduracağımızı adım adım öğreneceğiz.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Development Kit (JDK) yüklü.
2. Java kütüphanesi için Aspose.Slides indirildi. Buradan alabilirsiniz [Burada](https://releases.aspose.com/slides/java/).
3. Temel Java programlama bilgisi.
## Paketleri İçe Aktar
Java projenizde gerekli paketleri içe aktarın:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Adım 1: Proje Dizinini Ayarlayın
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
Değiştirdiğinizden emin olun `"Your Document Directory"` projenizin dizinine giden yol ile.
## Adım 2: Bir Sunum Oluşturun
```java
Presentation pres = new Presentation();
```
Örneklemi oluştur `Presentation` Yeni bir PowerPoint sunumu oluşturmak için sınıf.
## Adım 3: Slayt ve Şekil Ekleyin
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Sunumunuza bir slayt ekleyin ve üzerinde dikdörtgen bir şekil oluşturun.
## Adım 4: Doldurma Türünü Resim olarak ayarlayın
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
Şeklin dolgu türünü resim olarak ayarlayın.
## Adım 5: Resim Doldurma Modunu Ayarlayın
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
Şeklin resim doldurma modunu ayarlayın.
## Adım 6: Resmi Ayarla
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
Resmi yükleyin ve şeklin dolgusu olarak ayarlayın.
## Adım 7: Sunumu Kaydedin
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
Değiştirilen sunumu bir dosyaya kaydedin.

## Çözüm
Aspose.Slides for Java ile PowerPoint sunumlarında şekilleri resimlerle doldurmak basit bir işlem haline gelir. Bu eğitimde özetlenen adımları izleyerek sunumlarınızı görsel olarak çekici öğelerle kolayca geliştirebilirsiniz.

## SSS
### Aspose.Slides for Java kullanarak farklı şekilleri resimlerle doldurabilir miyim?
Evet, Aspose.Slides for Java çeşitli şekillerin resimlerle doldurulmasını destekleyerek tasarımda esneklik sağlar.
### Aspose.Slides for Java, PowerPoint'in tüm sürümleriyle uyumlu mudur?
Aspose.Slides for Java, PowerPoint 97 ve üzeri sürümlerle uyumlu sunular oluşturarak geniş uyumluluğu garanti eder.
### Şeklin içindeki resmin boyutunu nasıl değiştirebilirim?
Şeklin boyutlarını ayarlayarak veya dolgu olarak ayarlamadan önce görüntüyü uygun şekilde ölçekleyerek şeklin içindeki görüntünün boyutunu değiştirebilirsiniz.
### Şekillerin doldurulması için desteklenen resim formatlarında herhangi bir sınırlama var mı?
Java için Aspose.Slides, JPEG, PNG, GIF, BMP ve TIFF dahil olmak üzere çok çeşitli resim formatlarını destekler.
### Doldurulmuş şekillere efekt uygulayabilir miyim?
Evet, Aspose.Slides for Java, doldurulmuş şekillere gölgeler, yansımalar ve 3B döndürmeler gibi çeşitli efektler uygulamak için kapsamlı API'ler sağlar.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}