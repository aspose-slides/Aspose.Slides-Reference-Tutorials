---
title: Java kullanarak PowerPoint'te Yerel Yazı Tipi Yüksekliği Değerlerini Ayarlama
linktitle: Java kullanarak PowerPoint'te Yerel Yazı Tipi Yüksekliği Değerlerini Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java kullanarak PowerPoint sunumlarında yazı tipi yüksekliklerini nasıl ayarlayacağınızı öğrenin. Slaytlarınızdaki metin biçimlendirmesini zahmetsizce geliştirin.
weight: 17
url: /tr/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak PowerPoint'te Yerel Yazı Tipi Yüksekliği Değerlerini Ayarlama

## giriiş
Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint sunumlarında yazı tipi yüksekliklerini çeşitli düzeylerde nasıl değiştireceğinizi öğreneceksiniz. Yazı tipi boyutlarını kontrol etmek, görsel olarak çekici ve yapılandırılmış sunumlar oluşturmak için çok önemlidir. Farklı metin öğeleri için yazı tipi yüksekliklerinin nasıl ayarlanacağını göstermek için adım adım örnekler üzerinden ilerleyeceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Sisteminizde kurulu Java Geliştirme Kiti (JDK)
-  Aspose.Slides for Java kütüphanesi. İndirebilirsin[Burada](https://releases.aspose.com/slides/java/).
- Java programlama ve PowerPoint sunumlarına ilişkin temel anlayış
## Paketleri İçe Aktar
Gerekli Aspose.Slides paketlerini Java dosyanıza eklediğinizden emin olun:
```java
import com.aspose.slides.*;
```
## Adım 1: Sunum Nesnesini Başlatın
İlk önce yeni bir PowerPoint sunum nesnesi oluşturun:
```java
Presentation pres = new Presentation();
```
## 2. Adım: Şekil ve Metin Çerçevesi Ekleme
İlk slayda metin çerçevesi içeren bir otomatik şekil ekleyin:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## 3. Adım: Metin Bölümleri Oluşturun
Farklı yazı tipi yüksekliklerine sahip metin bölümlerini tanımlayın:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Adım 4: Yazı Tipi Yüksekliklerini Ayarlayın
Yazı tipi yüksekliklerini farklı düzeylerde ayarlayın:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Adım 5: Sunuyu Kaydetme
Değiştirilen sunumu bir dosyaya kaydedin:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu eğitimde Aspose.Slides for Java kullanılarak PowerPoint slaytlarındaki yazı tipi yüksekliklerinin programlı olarak nasıl ayarlanacağı gösterildi. Yazı tipi boyutlarını farklı düzeylerde (sunum genelinde, paragraf ve bölüm) değiştirerek, sunumlarınızdaki metin biçimlendirmesi üzerinde hassas kontrol elde edebilirsiniz.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak düzenlemek için güçlü bir API'dir.
### Aspose.Slides for Java belgelerini nerede bulabilirim?
 Belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/slides/java/).
### Satın almadan önce Aspose.Slides for Java'yı deneyebilir miyim?
 Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Slides for Java için nasıl destek alabilirim?
 Destek için şu adresi ziyaret edin:[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java lisansını nereden satın alabilirim?
 Lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
