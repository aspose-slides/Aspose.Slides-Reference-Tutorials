---
title: Java PowerPoint'te Özel Bilgi İstemi Metni Ekleme
linktitle: Java PowerPoint'te Özel Bilgi İstemi Metni Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides'ı kullanarak Java PowerPoint'te özel bilgi istemi metnini nasıl ekleyeceğinizi öğrenin. Bu eğitimle kullanıcı etkileşimini zahmetsizce geliştirin.
weight: 12
url: /tr/java/java-powerpoint-text-box-manipulation/add-custom-prompt-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint'te Özel Bilgi İstemi Metni Ekleme

## giriiş
Günümüzün dijital çağında dinamik ve ilgi çekici sunumlar oluşturmak etkili iletişim için çok önemlidir. Aspose.Slides for Java, slaytları, şekilleri, metinleri ve daha fazlasını özelleştirmek için kapsamlı özellikler sunarak geliştiricilerin PowerPoint sunumlarını programlı olarak değiştirmelerine olanak tanır. Bu eğitim, Aspose.Slides kullanarak Java PowerPoint sunumlarındaki yer tutuculara özel bilgi istemi metni ekleme sürecinde size rehberlik edecektir.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Java programlamanın temel bilgisi.
- JDK (Java Development Kit) sisteminizde kuruludur.
-  Aspose.Slides for Java kuruldu. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).
- IntelliJ IDEA veya Eclipse gibi bir Entegre Geliştirme Ortamı (IDE) kuruldu.

## Paketleri İçe Aktar
Başlamak için gerekli Aspose.Slides sınıflarını Java dosyanıza aktarın:
```java
import com.aspose.slides.*;
```

## 1. Adım: Sunuyu Yükleyin
Öncelikle, yer tutuculara özel bilgi istemi metni eklemek istediğiniz PowerPoint sunumunu yükleyin.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Presentation2.pptx");
```
## Adım 2: Slayt Şekillerini Yineleyin
Slayta erişin ve yer tutucuları bulmak için şekilleri yineleyin.
```java
try {
    ISlide slide = pres.getSlides().get_Item(0);
    for (IShape shape : slide.getShapes()) {
        if (shape.getPlaceholder() != null && shape instanceof AutoShape) {
            // Yalnızca Otomatik Şekil yer tutucularını işle
            String text = "";
            if (shape.getPlaceholder().getType() == PlaceholderType.CenteredTitle) {
                text = "Click to add custom title";
            } else if (shape.getPlaceholder().getType() == PlaceholderType.Subtitle) {
                text = "Click to add custom subtitle";
            }
            
            // Özel bilgi istemi metnini ayarlayın
            ((IAutoShape) shape).getTextFrame().setText(text);
            
            // Doğrulama için yer tutucu metnini yazdırın
            System.out.println(String.format("Placeholder with text: %s", text));
        }
    }
    
    //Değiştirilen sunuyu kaydet
    pres.save(dataDir + "Placeholders_PromptText.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Çözüm
Sonuç olarak Aspose.Slides for Java, PowerPoint sunumlarını program aracılığıyla özelleştirme görevini basitleştirir. Bu öğreticiyi izleyerek, yer tutuculara zahmetsizce anlamlı bilgi istemi metni ekleyerek kullanıcı etkileşimini artırabilirsiniz.
## SSS'ler
### Aspose.Slides for Java'yı kullanarak PowerPoint slaytındaki herhangi bir yer tutucuya bilgi istemi metni ekleyebilir miyim?
Evet, çeşitli yer tutucu türleri için özel bilgi istemi metnini program aracılığıyla ayarlayabilirsiniz.
### Aspose.Slides for Java, PowerPoint'in tüm sürümleriyle uyumlu mu?
Aspose.Slides, çok çeşitli PowerPoint sürümlerini destekleyerek uyumluluk ve güvenilirlik sağlar.
### Aspose.Slides for Java için daha fazla örneği ve belgeyi nerede bulabilirim?
 Ziyaret edin[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/) Kapsamlı kılavuzlar ve örnekler için.
### Aspose.Slides for Java için nasıl geçici lisans alabilirim?
 Alabilirsin[geçici lisans](https://purchase.aspose.com/temporary-license/) Aspose.Slides'ın tüm özelliklerini değerlendirmek için.
### Aspose.Slides for Java, slaytlara özel animasyonlar eklemeyi destekliyor mu?
Evet, Aspose.Slides slayt animasyonlarını programlı bir şekilde yönetmek için API'ler sağlar.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
