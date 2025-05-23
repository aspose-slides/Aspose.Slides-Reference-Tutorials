---
"description": "Java ile Aspose.Slides kullanarak SmartArt'ta madde işareti doldurma biçimini nasıl ayarlayacağınızı öğrenin. Verimli sunum düzenlemesi için adım adım kılavuz."
"linktitle": "Java kullanarak SmartArt'ta Madde İşareti Doldurma Biçimini Ayarlama"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java kullanarak SmartArt'ta Madde İşareti Doldurma Biçimini Ayarlama"
"url": "/tr/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak SmartArt'ta Madde İşareti Doldurma Biçimini Ayarlama

## giriiş
Java programlama alanında, sunumların etkili bir şekilde işlenmesi, özellikle SmartArt öğeleriyle uğraşırken yaygın bir gerekliliktir. Java için Aspose.Slides, bu tür görevler için güçlü bir araç olarak ortaya çıkar ve sunumları programatik olarak işlemek için bir dizi işlevsellik sunar. Bu eğitimde, Java'da Aspose.Slides ile SmartArt'ta madde işareti doldurma biçimini ayarlama sürecini adım adım ele alacağız.
## Ön koşullar
Bu eğitime başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
### Java Geliştirme Kiti (JDK)
Sisteminizde JDK'nın yüklü olması gerekir. Bunu şuradan indirebilirsiniz: [web sitesi](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) ve kurulum talimatlarını izleyin.
### Java için Aspose.Slides
Java için Aspose.Slides'ı indirin ve yükleyin [indirme bağlantısı](https://releases.aspose.com/slides/java/). İşletim sisteminize özel belgelerde verilen kurulum talimatlarını izleyin.

## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize aktarın:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Azpose.Slides ile Java kullanarak SmartArt'ta madde işareti doldurma biçiminin nasıl ayarlanacağını daha net anlamak için verilen örneği birden fazla adıma bölelim.
## Adım 1: Sunum Nesnesi Oluşturun
```java
Presentation presentation = new Presentation();
```
İlk olarak, bir PowerPoint sunumunu temsil eden Presentation sınıfının yeni bir örneğini oluşturun.
## Adım 2: SmartArt ekleyin
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Sonra, slayda bir SmartArt şekli ekleyin. Bu kod satırı, belirtilen boyutlar ve düzene sahip yeni bir SmartArt şekli başlatır.
## Adım 3: SmartArt Düğümüne Erişim
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Şimdi, SmartArt şeklinin içindeki ilk düğüme (veya istediğiniz herhangi bir düğüme) erişerek özelliklerini değiştirin.
## Adım 4: Madde İşareti Doldurma Biçimini Ayarlayın
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Burada, mermi dolgusu biçiminin desteklenip desteklenmediğini kontrol ediyoruz. Destekleniyorsa, bir resim dosyası yükleyip bunu SmartArt düğümü için mermi dolgusu olarak ayarlıyoruz.
## Adım 5: Sunumu Kaydedin
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Son olarak değiştirilen sunumu belirtilen yere kaydedin.

## Çözüm
Tebrikler! Java ile Aspose.Slides kullanarak SmartArt'ta madde işareti doldurma biçimini nasıl ayarlayacağınızı başarıyla öğrendiniz. Bu yetenek, Java uygulamalarında dinamik ve görsel olarak çekici sunumlar için bir olasılıklar dünyasının kapılarını açar.
## SSS
### Aspose.Slides for Java'yı sıfırdan sunumlar oluşturmak için kullanabilir miyim?
Kesinlikle! Aspose.Slides, tamamen kod aracılığıyla sunumlar oluşturmak, değiştirmek ve düzenlemek için kapsamlı API'ler sağlar.
### Aspose.Slides farklı PowerPoint sürümleriyle uyumlu mudur?
Evet, Aspose.Slides Microsoft PowerPoint'in çeşitli sürümleriyle uyumluluğu garanti ederek iş akışınıza sorunsuz bir şekilde entegre olmasını sağlar.
### SmartArt öğelerini madde işareti doldurma biçiminin ötesinde özelleştirebilir miyim?
Aspose.Slides, düzen, stil, içerik ve daha fazlası dahil olmak üzere SmartArt şekillerinin her yönünü özelleştirmenize olanak tanır.
### Aspose.Slides for Java için deneme sürümü mevcut mu?
Evet, Aspose.Slides'ın özelliklerini ücretsiz denemeyle keşfedebilirsiniz. Bunu şuradan indirin: [web sitesi](https://releases.aspose.com/slides/java/) ve keşfetmeye başlayın.
### Aspose.Slides for Java desteğini nerede bulabilirim?
Herhangi bir soru veya yardım için Aspose.Slides forumunu ziyaret edebilirsiniz. [bu bağlantı](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}