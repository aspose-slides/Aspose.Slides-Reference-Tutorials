---
"description": "Aspose.Slides ile Java kullanarak PowerPoint sunumlarında yazı tipi yüksekliklerini nasıl ayarlayacağınızı öğrenin. Slaytlarınızdaki metin biçimlendirmesini zahmetsizce geliştirin."
"linktitle": "Java kullanarak PowerPoint'te Yerel Yazı Tipi Yükseklik Değerlerini Ayarlama"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java kullanarak PowerPoint'te Yerel Yazı Tipi Yükseklik Değerlerini Ayarlama"
"url": "/tr/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak PowerPoint'te Yerel Yazı Tipi Yükseklik Değerlerini Ayarlama

## giriiş
Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint sunumlarında çeşitli düzeylerde yazı tipi yüksekliklerini nasıl değiştireceğinizi öğreneceksiniz. Yazı tipi boyutlarını kontrol etmek, görsel olarak çekici ve yapılandırılmış sunumlar oluşturmak için çok önemlidir. Farklı metin öğeleri için yazı tipi yüksekliklerinin nasıl ayarlanacağını göstermek için adım adım örneklerle ilerleyeceğiz.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Sisteminizde yüklü Java Geliştirme Kiti (JDK)
- Aspose.Slides for Java kütüphanesi. İndirebilirsiniz [Burada](https://releases.aspose.com/slides/java/).
- Java programlama ve PowerPoint sunumları hakkında temel bir anlayış
## Paketleri İçe Aktar
Java dosyanıza gerekli Aspose.Slides paketlerini eklediğinizden emin olun:
```java
import com.aspose.slides.*;
```
## Adım 1: Bir Sunum Nesnesi Başlatın
Öncelikle yeni bir PowerPoint sunum nesnesi oluşturun:
```java
Presentation pres = new Presentation();
```
## Adım 2: Şekil ve Metin Çerçevesi Ekleme
İlk slayda metin çerçeveli bir otomatik şekil ekleyin:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Adım 3: Metin Bölümleri Oluşturun
Farklı yazı yüksekliklerine sahip metin bölümleri tanımlayın:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Adım 4: Yazı Tipi Yüksekliklerini Ayarlayın
Farklı seviyelerde yazı tipi yüksekliklerini ayarlayın:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Adım 5: Sunumu Kaydedin
Değiştirilen sunumu bir dosyaya kaydedin:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu eğitim, Aspose.Slides for Java kullanarak PowerPoint slaytlarındaki yazı tipi yüksekliklerinin programatik olarak nasıl ayarlanacağını gösterdi. Yazı tipi boyutlarını farklı düzeylerde (sunum genelinde, paragraf ve bölüm) değiştirerek, sunumlarınızdaki metin biçimlendirmesi üzerinde hassas kontrol elde edebilirsiniz.
## SSS
### Java için Aspose.Slides nedir?
Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak düzenlemek için güçlü bir API'dir.
### Aspose.Slides for Java'ya ilişkin belgeleri nerede bulabilirim?
Belgeleri bulabilirsiniz [Burada](https://reference.aspose.com/slides/java/).
### Satın almadan önce Aspose.Slides for Java'yı deneyebilir miyim?
Evet, ücretsiz deneme alabilirsiniz [Burada](https://releases.aspose.com/).
### Java için Aspose.Slides desteğini nasıl alabilirim?
Destek için şu adresi ziyaret edin: [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java lisansını nereden satın alabilirim?
Bir lisans satın alabilirsiniz [Burada](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}