---
title: Java kullanarak PowerPoint'e Paragraf Madde İşaretleri Ekleme
linktitle: Java kullanarak PowerPoint'e Paragraf Madde İşaretleri Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint slaytlarına nasıl paragraf madde işaretleri ekleyeceğinizi öğrenin. Bu eğitim, kod örnekleriyle adım adım size yol gösterir.
type: docs
weight: 15
url: /tr/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---
## giriiş
Paragraf madde işaretleri eklemek PowerPoint sunumlarının okunabilirliğini ve yapısını geliştirir. Aspose.Slides for Java, metni çeşitli madde işareti stilleriyle biçimlendirme yeteneği de dahil olmak üzere, sunumları programlı olarak değiştirmek için güçlü araçlar sağlar. Bu eğitimde, Aspose.Slides'ı kullanarak Java kodunu kullanarak madde işaretlerini PowerPoint slaytlarına nasıl entegre edeceğinizi öğreneceksiniz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Java programlamanın temel bilgisi.
- JDK (Java Development Kit) sisteminizde kuruludur.
-  Aspose.Slides for Java kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Başlamak için gerekli Aspose.Slides paketlerini Java projenize aktarın:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## 1. Adım: Projenizi Kurun
Öncelikle yeni bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin derleme yoluna ekleyin.
## Adım 2: Sunumu Başlatın
Bir sunum nesnesini başlat (`Presentation`) slaytlarla çalışmaya başlamak için.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum örneği oluşturma
Presentation pres = new Presentation();
```
## 3. Adım: Slayt ve Metin Çerçevesine Erişin
Slayta erişin (`ISlide`ve metin çerçevesi (`ITextFrame`) madde işaretleri eklemek istediğiniz yere tıklayın.
```java
// İlk slayda erişim
ISlide slide = pres.getSlides().get_Item(0);
// Autoshape'i ekleme ve erişme
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// Oluşturulan otomatik şeklin metin çerçevesine erişme
ITextFrame txtFrm = aShp.getTextFrame();
```
## Adım 4: Madde İşaretleriyle Paragraflar Oluşturun ve Biçimlendirin
Paragraflar oluştur (`Paragraph`) ve madde işareti stillerini, girintisini ve metnini ayarlayın.
```java
// Paragraf oluşturma
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// Başka bir paragraf oluşturma
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## Adım 5: Sunuyu Kaydetme
Değiştirilen sunuyu bir PowerPoint dosyasına kaydedin (`PPTX`).
```java
// Sunuyu PPTX dosyası olarak yazma
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## Adım 6: Kaynakları Temizleyin
Kaynakları serbest bırakmak için sunum nesnesini atın.
```java
// Sunum nesnesini atın
if (pres != null) {
    pres.dispose();
}
```

## Çözüm
Aspose.Slides for Java'yı kullanarak PowerPoint'e paragraf madde işaretleri eklemek, sağlanan kod örnekleriyle basittir. Madde işareti stillerini ve biçimlendirmeyi sunum ihtiyaçlarınıza sorunsuz bir şekilde uyacak şekilde özelleştirin.

## SSS
### Madde işareti renklerini özelleştirebilir miyim?
Evet, Aspose.Slides API'sini kullanarak madde işaretleri için özel renkler ayarlayabilirsiniz.
### İç içe madde işaretlerini nasıl eklerim?
Madde işaretlerinin iç içe yerleştirilmesi, paragrafların içine paragrafların eklenmesini ve girintilerin buna göre ayarlanmasını içerir.
### Farklı slaytlar için farklı madde işareti stilleri oluşturabilir miyim?
Evet, program aracılığıyla farklı slaytlara benzersiz madde işareti stilleri uygulayabilirsiniz.
### Aspose.Slides Java 11 ile uyumlu mu?
Evet, Aspose.Slides Java 11 ve üzeri sürümleri destekler.
### Daha fazla örnek ve belgeyi nerede bulabilirim?
 Ziyaret etmek[Aspose.Slides for Java Belgelendirmesi](https://reference.aspose.com/slides/java/) Kapsamlı kılavuzlar ve örnekler için.