---
"description": "Aspose.Slides for Java kullanarak PowerPoint slaytlarına özel resim madde işaretlerinin nasıl ekleneceğini öğrenin. Sorunsuz entegrasyon için bu ayrıntılı, adım adım kılavuzu izleyin."
"linktitle": "Java PowerPoint'te Paragraf Resim Madde İşaretlerini Yönetin"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java PowerPoint'te Paragraf Resim Madde İşaretlerini Yönetin"
"url": "/tr/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint'te Paragraf Resim Madde İşaretlerini Yönetin

## giriiş
Modern iş dünyasında ilgi çekici ve görsel olarak çekici sunumlar oluşturmak önemli bir beceridir. Java geliştiricileri, PowerPoint slaytlarındaki özelleştirilmiş resimli maddelerle sunumlarını geliştirmek için Aspose.Slides'ı kullanabilirler. Bu eğitim, sunumlarınıza güvenle resimli maddeler ekleyebilmenizi sağlayarak sizi adım adım süreç boyunca yönlendirecektir.
## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
- Java Geliştirme Kiti (JDK) yüklendi
- Eclipse veya IntelliJ IDEA gibi Entegre Geliştirme Ortamı (IDE)
- Java kütüphanesi için Aspose.Slides
- Java programlamanın temel bilgisi
- Mermi resmi için resim dosyası
Aspose.Slides for Java kitaplığını indirmek için şu adresi ziyaret edin: [indirme sayfası](https://releases.aspose.com/slides/java/)Belgeler için, şuraya bakın: [belgeleme](https://reference.aspose.com/slides/java/).
## Paketleri İçe Aktar
Öncelikle projeniz için gerekli paketleri içe aktardığınızdan emin olun. Java dosyanızın başına aşağıdaki içe aktarımları ekleyin:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Süreci yönetilebilir adımlara bölelim.
## Adım 1: Proje Dizininizi Ayarlayın
Projeniz için yeni bir dizin oluşturun. Bu dizin Java dosyanızı, Aspose.Slides kütüphanesini ve madde işareti için resim dosyasını içerecektir.
```java
String dataDir = "Your Document Directory";
```
## Adım 2: Sunumu Başlatın
Yeni bir örneğini başlatın `Presentation` sınıf. Bu nesne PowerPoint sunumunuzu temsil eder.
```java
Presentation presentation = new Presentation();
```
## Adım 3: İlk Slayda Erişim
Sunumun ilk slaydına erişin. Slaytlar sıfır indekslidir, bu nedenle ilk slayt 0 indeksindedir.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Adım 4: Bullet Görüntüsünü Yükleyin
Madde işaretleri için kullanmak istediğiniz resmi yükleyin. Bu resim proje dizininize yerleştirilmelidir.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Adım 5: Slayda Otomatik Şekil Ekleme
Slayda bir Otomatik Şekil ekleyin. Şekil, özel madde işaretli metni içerecektir.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Adım 6: Metin Çerçevesine Erişim
Paragraflarını düzenlemek için Otomatik Şeklin metin çerçevesine erişin.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Adım 7: Varsayılan Paragrafı Kaldırın
Metin çerçevesine otomatik olarak eklenen varsayılan paragrafı kaldırın.
```java
textFrame.getParagraphs().removeAt(0);
```
## Adım 8: Yeni Bir Paragraf Oluşturun
Yeni bir paragraf oluşturun ve metnini ayarlayın. Bu paragraf özel resimli madde işaretlerini içerecektir.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Adım 9: Madde İşareti Stilini ve Görüntüyü Ayarlayın
Madde işareti stilini daha önce yüklenen özel görseli kullanacak şekilde ayarlayın.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Adım 10: Mermi Yüksekliğini Ayarlayın
Madde işaretinin yüksekliğini, sunumda güzel görünecek şekilde ayarlayın.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Adım 11: Paragrafı Metin Çerçevesine Ekleyin
Yeni oluşturulan paragrafı Otomatik Şeklin metin çerçevesine ekleyin.
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
İşte bu kadar! Bu adımları izleyerek, Aspose.Slides for Java kullanarak PowerPoint sunumlarınıza kolayca özel resim maddeleri ekleyebilirsiniz. Bu güçlü kütüphane, profesyonel ve görsel olarak çekici sunumlar oluşturmanıza yardımcı olacak çok çeşitli özellikler sunar. [belgeleme](https://reference.aspose.com/slides/java/) Daha gelişmiş özellikler ve özelleştirme seçenekleri için.
## SSS
### Java için Aspose.Slides nedir?
Aspose.Slides for Java, Java geliştiricilerinin PowerPoint sunumlarını programlı bir şekilde oluşturmalarına, değiştirmelerine ve düzenlemelerine olanak tanıyan güçlü bir kütüphanedir.
### Resimli maddeler için herhangi bir görseli kullanabilir miyim?
Evet, proje dizininizden erişilebildiği sürece resim maddelerinde herhangi bir resmi kullanabilirsiniz.
### Aspose.Slides for Java'yı kullanmak için lisansa ihtiyacım var mı?
Aspose.Slides for Java'nın tam işlevselliği için bir lisansa ihtiyacı vardır. Geçici bir lisansı şuradan edinebilirsiniz: [Burada](https://purchase.aspose.com/temporary-license/) veya tam lisans satın alın [Burada](https://purchase.aspose.com/buy).
### Tek bir Otomatik Şekil'e farklı madde işareti stillerine sahip birden fazla paragraf ekleyebilir miyim?
Evet, her paragrafı ayrı ayrı oluşturup yapılandırarak tek bir Otomatik Şekle farklı madde işareti stillerine sahip birden fazla paragraf ekleyebilirsiniz.
### Daha fazla örnek ve desteği nerede bulabilirim?
Daha fazla örnek için buraya bakabilirsiniz. [belgeleme](https://reference.aspose.com/slides/java/) ve Aspose topluluğundan destek alın [forumlar](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}