---
"description": "Aspose.Slides for Java kullanarak PowerPoint'te metin kutularına sütun eklemeyi öğrenin. Bu adım adım kılavuzla sunumlarınızı geliştirin."
"linktitle": "Java için Aspose.Slides ile Metin Kutularına Sütun Ekleme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java için Aspose.Slides ile Metin Kutularına Sütun Ekleme"
"url": "/tr/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java için Aspose.Slides ile Metin Kutularına Sütun Ekleme

## giriiş
Bu eğitimde, Java için Aspose.Slides kullanarak sütunlar ekleyerek metin kutularını nasıl geliştirebileceğimizi inceleyeceğiz. Aspose.Slides, geliştiricilerin Microsoft Office gerektirmeden PowerPoint sunumlarını programatik olarak oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan güçlü bir Java kütüphanesidir. Metin kutularına sütun eklemek, slaytlardaki içeriğin okunabilirliğini ve organizasyonunu büyük ölçüde iyileştirebilir ve sunumlarınızı daha ilgi çekici ve profesyonel hale getirebilir.
## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Temel Java programlama bilgisi.
- Bilgisayarınızda JDK (Java Development Kit) kurulu olmalıdır.
- Java kütüphanesi için Aspose.Slides. Buradan indirebilirsiniz [Burada](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Başlamak için gerekli Aspose.Slides sınıflarını Java dosyanıza aktarmanız gerekir. Bunu şu şekilde yapabilirsiniz:
```java
import com.aspose.slides.*;
```
## Adım 1: Sunumu ve Slaydı Başlatın
Öncelikle yeni bir PowerPoint sunumu oluşturun ve ilk slaydı başlatın.
```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // Sunumun ilk slaydını alın
    ISlide slide = presentation.getSlides().get_Item(0);
```
## Adım 2: Otomatik Şekil Ekle (Dikdörtgen)
Daha sonra slayda Dikdörtgen türünde bir AutoShape ekleyin.
```java
    // Dikdörtgen türünde bir Otomatik Şekil ekleyin
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Adım 3: Dikdörtgene TextFrame ekleyin
Şimdi Dikdörtgen Otomatik Şekline bir TextFrame ekleyin ve başlangıç metnini ayarlayın.
```java
    // Dikdörtgene TextFrame Ekle
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## Adım 4: Sütun Sayısını Ayarlayın
TextFrame içindeki sütun sayısını belirtin.
```java
    // TextFrame'in metin biçimini al
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // TextFrame'deki sütun sayısını belirtin
    format.setColumnCount(3);
```
## Adım 5: Sütun Aralığını Ayarlayın
TextFrame'deki sütunlar arasındaki boşlukları ayarlayın.
```java
    // Sütunlar arasındaki aralığı belirtin
    format.setColumnSpacing(10);
```
## Adım 6: Sunumu Kaydedin
Son olarak, değiştirdiğiniz sunumu bir PowerPoint dosyasına kaydedin.
```java
    // Oluşturulan sunuyu kaydet
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Çözüm
Bu adımları izleyerek, Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki metin kutularına kolayca sütun ekleyebilirsiniz. Bu özellik, slaytlarınızın yapısını ve okunabilirliğini geliştirmenize, onları görsel olarak daha çekici ve profesyonel hale getirmenize olanak tanır.
## SSS
### Bir metin kutusuna üçten fazla sütun ekleyebilir miyim?
Evet, Aspose.Slides'ı kullanarak program aracılığıyla istediğiniz sayıda sütun belirtebilirsiniz.
### Aspose.Slides Java 11 ile uyumlu mu?
Evet, Aspose.Slides Java 11 ve üzeri sürümleri destekler.
### Aspose.Slides için geçici lisansı nasıl alabilirim?
Geçici bir lisans alabilirsiniz [Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides'ı kullanmak için Microsoft Office'in yüklü olması gerekiyor mu?
Hayır, Aspose.Slides'ı çalıştırmak için bilgisayarınızda Microsoft Office'in yüklü olması gerekmez.
### Aspose.Slides for Java hakkında daha fazla dokümanı nerede bulabilirim?
Ayrıntılı dokümantasyon mevcuttur [Burada](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}