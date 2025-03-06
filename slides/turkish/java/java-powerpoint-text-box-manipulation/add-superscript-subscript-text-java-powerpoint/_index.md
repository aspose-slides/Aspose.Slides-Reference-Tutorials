---
title: Java PowerPoint'te Üst Simge ve Alt Simge Metni Ekleme
linktitle: Java PowerPoint'te Üst Simge ve Alt Simge Metni Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak Java PowerPoint sunumlarına üst simge ve alt simge metnini nasıl ekleyeceğinizi öğrenin. Slaytlarınızı geliştirmek için mükemmeldir.
weight: 13
url: /tr/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
İlgi çekici ve bilgilendirici PowerPoint sunumları oluşturmak genellikle üst simge ve alt simge metni gibi biçimlendirme özelliklerinin kullanılmasını gerektirir. Bu eğitim, Aspose.Slides for Java kullanarak Java PowerPoint sunumlarınıza üst simge ve alt simge metni ekleme sürecinde size rehberlik edecektir.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Slides for Java kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).
- Java geliştirme için IntelliJ IDEA veya Eclipse gibi bir Entegre Geliştirme Ortamı (IDE).
- Java programlama ve PowerPoint sunumlarına ilişkin temel bilgi.

## Paketleri İçe Aktar
Öncelikle gerekli paketleri Aspose.Slides for Java'dan içe aktarın:
```java
import com.aspose.slides.*;
```
## 1. Adım: Sunumu Hazırlayın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## 2. Adım: Slayta Erişin
```java
// İlk slaydı alın
ISlide slide = presentation.getSlides().get_Item(0);
```
## 3. Adım: Metin Kutusu Oluşturun
```java
// Metin kutusu görevi görecek bir Otomatik Şekil oluşturma
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## 4. Adım: Üst Simge Metni Ekleyin
```java
// Ana metin için bir paragraf oluşturun
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Üst simge metni için bir bölüm oluşturun
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Üst simge için eşapmanı ayarlayın
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Üst simge içeren ana paragrafı metin kutusuna ekleyin
textFrame.getParagraphs().add(mainParagraph);
```
## Adım 5: Abonelik Metni Ekleyin
```java
// Alt simge metni için başka bir paragraf oluşturun
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Alt simge metni için bir bölüm oluşturun
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Abonelik için eşapmanı ayarlayın
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Alt simge paragrafını metin kutusuna ekleme
textFrame.getParagraphs().add(subscriptParagraph);
```
## Adım 6: Sunuyu Kaydetme
```java
// Sunuyu kaydet
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu eğitimde, Aspose.Slides for Java kullanarak Java PowerPoint sunumlarınızı üst simge ve alt simge metinleriyle nasıl geliştirebileceğinizi araştırdık. Bu adımları izleyerek içeriğinizi etkili bir şekilde ileten görsel olarak daha çekici ve bilgilendirici slaytlar oluşturabilirsiniz.

## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, geliştiricilerin PowerPoint sunumlarını programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır.
### Aspose.Slides for Java ile ilgili daha fazla belgeyi nerede bulabilirim?
 Ayrıntılı belgeler bulunabilir[Burada](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java için nasıl geçici lisans alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java'yı ücretsiz deneyebilir miyim?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Slides for Java için nereden destek alabilirim?
 Destek ve tartışmalar için şu adresi ziyaret edin:[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
