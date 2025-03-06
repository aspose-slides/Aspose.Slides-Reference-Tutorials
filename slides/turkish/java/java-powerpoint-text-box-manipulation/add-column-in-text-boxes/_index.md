---
title: Aspose.Slides for Java ile Metin Kutularına Sütun Ekleme
linktitle: Aspose.Slides for Java ile Metin Kutularına Sütun Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint'te metin kutularına nasıl sütun ekleyeceğinizi öğrenin. Bu adım adım kılavuzla sunumlarınızı geliştirin.
weight: 10
url: /tr/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Bu eğitimde Aspose.Slides for Java'yı kullanarak metin kutularını sütun ekleyerek nasıl geliştirebileceğimizi keşfedeceğiz. Aspose.Slides, geliştiricilerin Microsoft Office'e ihtiyaç duymadan program aracılığıyla PowerPoint sunumları oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir Java kitaplığıdır. Metin kutularına sütun eklemek, slaytlardaki içeriğin okunabilirliğini ve düzenini büyük ölçüde iyileştirerek sunumlarınızı daha ilgi çekici ve profesyonel hale getirebilir.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Java programlamanın temel bilgisi.
- Makinenizde JDK (Java Development Kit) yüklü.
-  Aspose.Slides for Java kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Başlamak için gerekli Aspose.Slides sınıflarını Java dosyanıza aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:
```java
import com.aspose.slides.*;
```
## Adım 1: Sunumu ve Slaytı Başlatın
Öncelikle yeni bir PowerPoint sunumu oluşturun ve ilk slaydı başlatın.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // Sunumun ilk slaydını alın
    ISlide slide = presentation.getSlides().get_Item(0);
```
## Adım 2: Otomatik Şekil Ekle (Dikdörtgen)
Daha sonra slayda Dikdörtgen türünde bir Otomatik Şekil ekleyin.
```java
    // Dikdörtgen türünde Otomatik Şekil ekleme
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Adım 3: Dikdörtgen'e TextFrame ekleyin
Şimdi Dikdörtgen Otomatik Şekil'e bir TextFrame ekleyin ve başlangıç metnini ayarlayın.
```java
    // TextFrame'i Dikdörtgen'e ekleyin
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## Adım 4: Sütun Sayısını Ayarlayın
TextFrame içindeki sütunların sayısını belirtin.
```java
    // TextFrame'in metin biçimini alın
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // TextFrame'de sütun sayısını belirtin
    format.setColumnCount(3);
```
## Adım 5: Sütun Aralığını Ayarlayın
TextFrame'deki sütunlar arasındaki boşluğu ayarlayın.
```java
    // Sütunlar arasındaki boşluğu belirtin
    format.setColumnSpacing(10);
```
## Adım 6: Sunuyu Kaydetme
Son olarak, değiştirilen sunuyu bir PowerPoint dosyasına kaydedin.
```java
    // Oluşturulan sunumu kaydet
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Çözüm
Bu adımları izleyerek Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarındaki metin kutularına kolayca sütun ekleyebilirsiniz. Bu özellik, slaytlarınızın yapısını ve okunabilirliğini geliştirerek onları görsel olarak daha çekici ve profesyonel hale getirmenize olanak tanır.
## SSS'ler
### Bir metin kutusuna üçten fazla sütun ekleyebilir miyim?
Evet, Aspose.Slides'ı kullanarak istediğiniz sayıda sütunu programlı olarak belirleyebilirsiniz.
### Aspose.Slides Java 11 ile uyumlu mu?
Evet, Aspose.Slides Java 11 ve üzeri sürümleri destekler.
### Aspose.Slides için nasıl geçici lisans alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides Microsoft Office'in kurulu olmasını gerektirir mi?
Hayır, Aspose.Slides makinede Microsoft Office'in kurulu olmasını gerektirmez.
### Aspose.Slides for Java hakkında daha fazla belgeyi nerede bulabilirim?
 Detaylı dokümantasyon mevcut[Burada](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
