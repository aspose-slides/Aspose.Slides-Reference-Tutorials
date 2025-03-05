---
title: Java kullanarak SmartArt'ta Madde İşareti Doldurma Formatını Ayarlama
linktitle: Java kullanarak SmartArt'ta Madde İşareti Doldurma Formatını Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java kullanarak SmartArt'ta madde işareti dolgusu formatını nasıl ayarlayacağınızı öğrenin. Verimli sunum manipülasyonu için adım adım kılavuz.
type: docs
weight: 18
url: /tr/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---
## giriiş
Java programlama alanında, özellikle SmartArt öğeleriyle uğraşırken sunumların etkili bir şekilde değiştirilmesi ortak bir gerekliliktir. Aspose.Slides for Java bu tür görevler için güçlü bir araç olarak ortaya çıkıyor ve sunumları programlı bir şekilde yönetmek için bir dizi işlevsellik sunuyor. Bu eğitimde, Aspose.Slides ile Java kullanarak SmartArt'ta madde işareti doldurma formatını ayarlama işlemini adım adım ele alacağız.
## Önkoşullar
Bu eğitime başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
### Java Geliştirme Kiti (JDK)
 Sisteminizde JDK'nın kurulu olması gerekmektedir. adresinden indirebilirsiniz.[İnternet sitesi](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) ve kurulum talimatlarını takip edin.
### Java için Aspose.Slides
 Aspose.Slides for Java'yı şu adresten indirip yükleyin:[İndirme: {link](https://releases.aspose.com/slides/java/). İşletim sisteminize özel belgelerde sağlanan kurulum talimatlarını izleyin.

## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize aktarın:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Aspose.Slides ile Java kullanarak SmartArt'ta madde işareti doldurma formatının nasıl ayarlanacağını net bir şekilde anlamak için verilen örneği birden fazla adıma ayıralım.
## Adım 1: Sunum Nesnesi Oluşturun
```java
Presentation presentation = new Presentation();
```
İlk olarak, PowerPoint sunumunu temsil eden Sunum sınıfının yeni bir örneğini oluşturun.
## 2. Adım: SmartArt'ı ekleyin
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Daha sonra slayda bir SmartArt şekli ekleyin. Bu kod satırı, belirtilen boyutlara ve düzene sahip yeni bir SmartArt şeklini başlatır.
## 3. Adım: SmartArt Node'a erişin
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Şimdi özelliklerini değiştirmek için SmartArt şekli içindeki ilk düğüme (veya istediğiniz herhangi bir düğüme) erişin.
## Adım 4: Madde İşareti Doldurma Formatını Ayarlayın
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Burada madde işareti doldurma formatının desteklenip desteklenmediğini kontrol ediyoruz. Öyleyse, bir görüntü dosyası yüklüyoruz ve bunu SmartArt düğümü için madde işareti dolgusu olarak ayarlıyoruz.
## Adım 5: Sunuyu Kaydet
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Son olarak, değiştirilen sunumu belirtilen bir konuma kaydedin.

## Çözüm
Tebrikler! Aspose.Slides ile Java kullanarak SmartArt'ta madde işareti doldurma formatını nasıl ayarlayacağınızı başarıyla öğrendiniz. Bu yetenek, Java uygulamalarında dinamik ve görsel olarak çekici sunumlar için bir olasılıklar dünyasının kapılarını açar.
## SSS'ler
### Sıfırdan sunumlar oluşturmak için Aspose.Slides for Java'yı kullanabilir miyim?
Kesinlikle! Aspose.Slides, sunumları tamamen kod aracılığıyla oluşturmak, değiştirmek ve değiştirmek için kapsamlı API'ler sağlar.
### Aspose.Slides PowerPoint'in farklı sürümleriyle uyumlu mu?
Evet, Aspose.Slides, Microsoft PowerPoint'in çeşitli sürümleriyle uyumluluk sağlayarak iş akışınıza kusursuz entegrasyon sağlar.
### SmartArt öğelerini madde işareti doldurma formatının ötesinde özelleştirebilir miyim?
Aslında Aspose.Slides, düzen, stil, içerik ve daha fazlası dahil olmak üzere SmartArt şekillerinin her yönünü özelleştirmenizi sağlar.
### Aspose.Slides for Java'nın deneme sürümü mevcut mu?
 Evet, Aspose.Slides'ın özelliklerini ücretsiz deneme sürümüyle keşfedebilirsiniz. Basitçe şuradan indirin:[İnternet sitesi](https://releases.aspose.com/slides/java/) ve keşfetmeye başlayın.
### Aspose.Slides for Java desteğini nerede bulabilirim?
 Sorularınız veya yardım için Aspose.Slides forumunu ziyaret edebilirsiniz:[bu bağlantı](https://forum.aspose.com/c/slides/11).