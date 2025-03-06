---
title: Java PowerPoint'te Paragraf Resim Madde İşaretlerini Yönetme
linktitle: Java PowerPoint'te Paragraf Resim Madde İşaretlerini Yönetme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint slaytlarına nasıl özel resim madde işaretleri ekleyeceğinizi öğrenin. Sorunsuz entegrasyon için bu ayrıntılı, adım adım kılavuzu izleyin.
weight: 11
url: /tr/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
İlgi çekici ve görsel olarak çekici sunumlar oluşturmak, modern iş dünyasında çok önemli bir beceridir. Java geliştiricileri, PowerPoint slaytlarındaki özelleştirilmiş resim maddeleriyle sunumlarını geliştirmek için Aspose.Slides'tan yararlanabilir. Bu eğitim, süreç boyunca size adım adım rehberlik edecek ve sunumlarınıza güvenle resim madde işaretleri ekleyebilmenizi sağlayacaktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Java Geliştirme Kiti (JDK) yüklü
- Eclipse veya IntelliJ IDEA gibi Entegre Geliştirme Ortamı (IDE)
- Aspose.Slides for Java kütüphanesi
- Java programlamayla ilgili temel bilgiler
- Madde işareti resmi için resim dosyası
 Aspose.Slides for Java kütüphanesini indirmek için şu adresi ziyaret edin:[indirme sayfası](https://releases.aspose.com/slides/java/) . Belgeler için şurayı kontrol edin:[dokümantasyon](https://reference.aspose.com/slides/java/).
## Paketleri İçe Aktar
Öncelikle projeniz için gerekli paketleri içe aktardığınızdan emin olun. Aşağıdaki içe aktarmaları Java dosyanızın başına ekleyin:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Süreci yönetilebilir adımlara ayıralım.
## 1. Adım: Proje Dizininizi Kurun
Projeniz için yeni bir dizin oluşturun. Bu dizin Java dosyanızı, Aspose.Slides kütüphanesini ve madde işaretinin görüntü dosyasını içerecektir.
```java
String dataDir = "Your Document Directory";
```
## Adım 2: Sunumu Başlatın
 Yeni bir örneğini başlat`Presentation` sınıf. Bu nesne PowerPoint sunumunuzu temsil eder.
```java
Presentation presentation = new Presentation();
```
## 3. Adım: İlk Slayta Erişin
Sunumun ilk slaytına erişin. Slaytlar sıfır dizinlidir, dolayısıyla ilk slayt 0 dizinindedir.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Adım 4: Madde İşareti Görüntüsünü Yükleyin
Madde işaretleri için kullanmak istediğiniz görüntüyü yükleyin. Bu görsel proje dizininize yerleştirilmelidir.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Adım 5: Slayda Otomatik Şekil Ekleme
Slayta Otomatik Şekil ekleyin. Şekil, özel madde işaretleri içeren metni içerecektir.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Adım 6: Metin Çerçevesine Erişin
Paragraflarını değiştirmek için Otomatik Şekil'in metin çerçevesine erişin.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Adım 7: Varsayılan Paragrafı Kaldır
Metin çerçevesine otomatik olarak eklenen varsayılan paragrafı kaldırın.
```java
textFrame.getParagraphs().removeAt(0);
```
## Adım 8: Yeni Bir Paragraf Oluşturun
Yeni bir paragraf oluşturun ve metnini ayarlayın. Bu paragraf özel resim madde işaretlerini içerecektir.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Adım 9: Madde İşareti Stilini ve Görüntüsünü Ayarlayın
Madde işareti stilini daha önce yüklenen özel görüntüyü kullanacak şekilde ayarlayın.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Adım 10: Madde İşareti Yüksekliğini Ayarlayın
Sunumda iyi göründüğünden emin olmak için madde işaretinin yüksekliğini ayarlayın.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Adım 11: Paragrafı Metin Çerçevesine Ekleme
Yeni oluşturulan paragrafı Otomatik Şekil'in metin çerçevesine ekleyin.
```java
textFrame.getParagraphs().add(paragraph);
```
## Adım 12: Sunumu Kaydedin
Son olarak sunumu hem PPTX hem de PPT dosyası olarak kaydedin.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Çözüm
 İşte buyur! Bu adımları izleyerek Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarınıza kolayca özel resim madde işaretleri ekleyebilirsiniz. Bu güçlü kitaplık, profesyonel ve görsel olarak çekici sunumlar oluşturmanıza yardımcı olacak çok çeşitli özellikler sunar. Keşfetmeyi unutmayın[dokümantasyon](https://reference.aspose.com/slides/java/)daha gelişmiş özellikler ve kişiselleştirme seçenekleri için.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, Java geliştiricilerinin PowerPoint sunumlarını programlı olarak oluşturmasına, değiştirmesine ve işlemesine olanak tanıyan güçlü bir kütüphanedir.
### Resim madde işaretleri için herhangi bir görsel kullanabilir miyim?
Evet, proje dizininizden erişilebildiği sürece resim madde işaretleri için herhangi bir görseli kullanabilirsiniz.
### Aspose.Slides for Java'yı kullanmak için lisansa ihtiyacım var mı?
 Aspose.Slides for Java'nın tam işlevselliği için lisans gerekir. adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/) veya tam lisans satın alın[Burada](https://purchase.aspose.com/buy).
### Tek bir Otomatik Şekilde farklı madde işareti stillerine sahip birden fazla paragraf ekleyebilir miyim?
Evet, her paragrafı ayrı ayrı oluşturup yapılandırarak tek bir Otomatik Şekil'e farklı madde işareti stillerine sahip birden çok paragraf ekleyebilirsiniz.
### Daha fazla örneği ve desteği nerede bulabilirim?
 Daha fazla örneği şurada bulabilirsiniz[dokümantasyon](https://reference.aspose.com/slides/java/) ve Aspose topluluğundan destek alın[forumlar](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
