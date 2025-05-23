---
"description": "Aspose.Slides for Java kullanarak PowerPoint slaytlarına paragraf madde işaretlerinin nasıl ekleneceğini öğrenin. Bu eğitim, kod örnekleriyle adım adım size rehberlik eder."
"linktitle": "Java kullanarak PowerPoint'te Paragraf Madde İşaretleri Ekleme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java kullanarak PowerPoint'te Paragraf Madde İşaretleri Ekleme"
"url": "/tr/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak PowerPoint'te Paragraf Madde İşaretleri Ekleme

## giriiş
Paragraf madde işaretleri eklemek, PowerPoint sunumlarının okunabilirliğini ve yapısını geliştirir. Java için Aspose.Slides, metni çeşitli madde işareti stilleriyle biçimlendirme yeteneği de dahil olmak üzere sunumları programatik olarak düzenlemek için sağlam araçlar sağlar. Bu eğitimde, Aspose.Slides'ı kullanarak Java kodunu kullanarak madde işaretlerini PowerPoint slaytlarına nasıl entegre edeceğinizi öğreneceksiniz.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Temel Java programlama bilgisi.
- Sisteminizde JDK (Java Development Kit) yüklü.
- Java kütüphanesi için Aspose.Slides. Buradan indirebilirsiniz [Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Başlamak için gerekli Aspose.Slides paketlerini Java projenize aktarın:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Adım 1: Projenizi Kurun
Öncelikle yeni bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin build path'ine ekleyin.
## Adım 2: Bir Sunumu Başlatın
Bir sunum nesnesini başlatın (`Presentation`) Slaytlarla çalışmaya başlamak için.
```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir sunum örneği oluşturma
Presentation pres = new Presentation();
```
## Adım 3: Slayt ve Metin Çerçevesine Erişim
Slayda erişin (`ISlide`) ve metin çerçevesi (`ITextFrame`) madde işareti eklemek istediğiniz yere.
```java
// İlk slayda erişim
ISlide slide = pres.getSlides().get_Item(0);
// Autoshape'i ekleme ve erişme
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// Oluşturulan otomatik şeklin metin çerçevesine erişim
ITextFrame txtFrm = aShp.getTextFrame();
```
## Adım 4: Madde İşaretleriyle Paragraflar Oluşturun ve Biçimlendirin
Paragraflar oluştur (`Paragraph`) ve madde işaretlerini, girintileri ve metinleri ayarlayabilirsiniz.
```java
// Bir paragraf oluşturma
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
## Adım 5: Sunumu Kaydedin
Değiştirilen sunumu bir PowerPoint dosyasına kaydedin (`PPTX`).
```java
// Sunumu PPTX dosyası olarak yazma
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## Adım 6: Kaynakları Temizleyin
Kaynakları serbest bırakmak için sunum nesnesini elden çıkarın.
```java
// Sunum nesnesini elden çıkarın
if (pres != null) {
    pres.dispose();
}
```

## Çözüm
PowerPoint'te Aspose.Slides for Java kullanarak paragraf madde işaretleri eklemek, sağlanan kod örnekleriyle basittir. Madde işaretlerini ve biçimlendirmeyi sunum ihtiyaçlarınıza sorunsuz bir şekilde uyacak şekilde özelleştirin.

## SSS
### Madde işaretlerinin renklerini özelleştirebilir miyim?
Evet, Aspose.Slides API'sini kullanarak madde işaretleri için özel renkler ayarlayabilirsiniz.
### İç içe madde işaretleri nasıl eklerim?
İç içe madde işaretleri, paragrafların içine paragraflar eklemeyi ve girintileri buna göre ayarlamayı içerir.
### Farklı slaytlar için farklı madde işaretleri oluşturabilir miyim?
Evet, farklı slaytlara program aracılığıyla benzersiz madde işaretleri stilleri uygulayabilirsiniz.
### Aspose.Slides Java 11 ile uyumlu mu?
Evet, Aspose.Slides Java 11 ve üzeri sürümleri destekler.
### Daha fazla örnek ve dokümanı nerede bulabilirim?
Ziyaret etmek [Java Belgeleri için Aspose.Slides](https://reference.aspose.com/slides/java/) Kapsamlı kılavuzlar ve örnekler için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}