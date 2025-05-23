---
"description": "Java PowerPoint sunumlarına Aspose.Slides for Java kullanarak üst simge ve alt simge metninin nasıl ekleneceğini öğrenin. Slaytlarınızı geliştirmek için mükemmeldir."
"linktitle": "Java PowerPoint'te Üst Simge ve Alt Simge Metni Ekleme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java PowerPoint'te Üst Simge ve Alt Simge Metni Ekleme"
"url": "/tr/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint'te Üst Simge ve Alt Simge Metni Ekleme

## giriiş
İlgi çekici ve bilgilendirici PowerPoint sunumları oluşturmak genellikle üst simge ve alt simge metni gibi biçimlendirme özelliklerinin kullanılmasını gerektirir. Bu eğitim, Aspose.Slides for Java kullanarak Java PowerPoint sunumlarınıza üst simge ve alt simge metni ekleme sürecinde size rehberlik edecektir.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Sisteminizde Java Development Kit (JDK) yüklü.
- Java kütüphanesi için Aspose.Slides. Buradan indirebilirsiniz [Burada](https://releases.aspose.com/slides/java/).
- Java geliştirme için kurulmuş IntelliJ IDEA veya Eclipse gibi Entegre Geliştirme Ortamı (IDE).
- Java programlama ve PowerPoint sunumları konusunda temel bilgi.

## Paketleri İçe Aktar
Öncelikle Aspose.Slides for Java'dan gerekli paketleri import edelim:
```java
import com.aspose.slides.*;
```
## Adım 1: Sunumu Ayarlayın
```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Adım 2: Slayda Erişim
```java
// İlk slaydı alın
ISlide slide = presentation.getSlides().get_Item(0);
```
## Adım 3: Bir Metin Kutusu Oluşturun
```java
// Metin kutusu görevi görecek bir Otomatik Şekil oluşturun
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Adım 4: Üst Simge Metni Ekle
```java
// Ana metin için bir paragraf oluşturun
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Üst simge metni için bir bölüm oluşturun
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Üst simge için kaçış mekanizmasını ayarlayın
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// Üst simgeli ana paragrafı metin kutusuna ekleyin
textFrame.getParagraphs().add(mainParagraph);
```
## Adım 5: Alt Simge Metni Ekle
```java
// Alt simge metni için başka bir paragraf oluşturun
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Alt simge metni için bir bölüm oluşturun
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Abonelik için kaçış modunu ayarla
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Metin kutusuna alt simge paragrafı ekle
textFrame.getParagraphs().add(subscriptParagraph);
```
## Adım 6: Sunumu Kaydedin
```java
// Sunumu kaydet
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu eğitimde, Java PowerPoint sunumlarınızı Aspose.Slides for Java kullanarak üst simge ve alt simge metinlerle nasıl zenginleştireceğinizi inceledik. Bu adımları izleyerek, içeriğinizi etkili bir şekilde ileten görsel olarak daha çekici ve bilgilendirici slaytlar oluşturabilirsiniz.

## SSS
### Java için Aspose.Slides nedir?
Aspose.Slides for Java, geliştiricilerin PowerPoint sunumlarını programlı bir şekilde oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan sağlam bir kütüphanedir.
### Aspose.Slides for Java hakkında daha fazla dokümanı nerede bulabilirim?
Ayrıntılı dokümantasyon bulunabilir [Burada](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java için geçici lisansı nasıl alabilirim?
Geçici bir lisans alabilirsiniz [Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java'yı ücretsiz deneyebilir miyim?
Evet, ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/).
### Aspose.Slides for Java için desteği nereden alabilirim?
Destek ve tartışmalar için şu adresi ziyaret edin: [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}