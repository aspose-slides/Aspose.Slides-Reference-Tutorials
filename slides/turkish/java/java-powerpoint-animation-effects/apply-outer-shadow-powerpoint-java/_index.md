---
title: Java ile PowerPoint'te Dış Gölgeyi Uygulayın
linktitle: Java ile PowerPoint'te Dış Gölgeyi Uygulayın
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java kullanarak PowerPoint'te dış gölge efektini nasıl uygulayacağınızı öğrenin. Sunumlarınızı derinlik ve görsel çekicilikle geliştirin.
weight: 13
url: /tr/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
Görsel olarak çekici PowerPoint sunumları oluşturmak genellikle şekillere ve metne çeşitli efektler eklemeyi içerir. Bu tür efektlerden biri, öğelerin öne çıkmasını sağlayan ve slaytlarınıza derinlik katan dış gölgedir. Bu eğitimde, Aspose.Slides ile Java kullanarak PowerPoint'te bir şekle dış gölge efektinin nasıl uygulanacağını öğreneceksiniz.
## Önkoşullar

Bu eğitime başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1. Java Geliştirme Kiti (JDK): Sisteminizde Java'nın kurulu olduğundan emin olun. JDK'nın en son sürümünü Oracle web sitesinden indirip yükleyebilirsiniz.

2.  Aspose.Slides for Java: Aspose.Slides for Java'yı şu adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/slides/java/).

3. Entegre Geliştirme Ortamı (IDE): Java uygulamalarını kodlamak ve çalıştırmak için Eclipse, IntelliJ IDEA veya NetBeans gibi tercih ettiğiniz Java IDE'yi seçin.

4. Temel Java Bilgisi: Java programlama dilinin temellerine ve nesne yönelimli kavramlara aşina olmak, kod örneklerini anlamak için faydalı olacaktır.

## Paketleri İçe Aktar

Öncelikle Java projenizde Aspose.Slides ve ilgili işlevlerle çalışmak için gerekli paketleri içe aktarın:

```java
import com.aspose.slides.*;
```

Şimdi Aspose.Slides ile Java kullanarak dış gölge efektini PowerPoint'teki bir şekle uygulamak için örnek kodu birden fazla adıma ayıralım:

## 1. Adım: Proje ortamınızı ayarlayın

Tercih ettiğiniz IDE'de yeni bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin derleme yoluna ekleyin.

## Adım 2: Sunum nesnesini başlatın

 Bir örneğini oluşturun`Presentation` Bir PowerPoint sunum dosyasını temsil eden sınıf.

```java
Presentation presentation = new Presentation();
```

## 3. Adım: Slayt ve şekil ekleyin

Şekli eklemek istediğiniz slayda bir başvuru alın ve ardından slayda bir Otomatik Şekil (örneğin, dikdörtgen) ekleyin.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## 4. Adım: Şekli özelleştirin

Şeklin dolgu türünü 'Doldurma Yok' olarak ayarlayın ve şekle metin ekleyin.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## 5. Adım: Metni özelleştirin

Şeklin metin özelliklerine erişin ve yazı tipi boyutunu özelleştirin.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## 6. Adım: Dış Gölge efektini etkinleştirin

Metin kısmı için dış gölge efektini etkinleştirin.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Adım 7: Gölge parametrelerini ayarlayın

Bulanıklık yarıçapı, yön, mesafe ve gölge rengi gibi dış gölge efektine ilişkin parametreleri tanımlayın.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## 8. Adım: Sunuyu kaydedin

Değiştirilen sunumu, şekle uygulanan dış gölge efektiyle kaydedin.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Çözüm

Tebrikler! Aspose.Slides ile Java kullanarak PowerPoint'te bir şekle dış gölge efektini başarıyla uyguladınız. Sunumlarınızda istediğiniz görsel efektleri elde etmek için farklı parametrelerle denemeler yapın.

## SSS'ler

### Dış gölge efektini dikdörtgenlerin yanı sıra diğer şekillere de uygulayabilir miyim?
Evet, dış gölge efektini Aspose.Slides tarafından desteklenen daireler, üçgenler ve özel şekiller gibi çeşitli şekillere uygulayabilirsiniz.

### Gölge rengini ve yoğunluğunu özelleştirmek mümkün mü?
Kesinlikle! Renk, bulanıklık yarıçapı, yön ve mesafe dahil olmak üzere gölge parametreleri üzerinde tam kontrole sahipsiniz.

### Aynı şekle birden fazla efekt uygulayabilir miyim?
Evet, sunumlarınızdaki şekillerin ve metinlerin görsel çekiciliğini artırmak için dış gölge, iç gölge, parlaklık ve yansıma gibi birden çok efekti birleştirebilirsiniz.

### Aspose.Slides metin öğelerine efekt uygulamayı destekliyor mu?
Evet, efektleri yalnızca şekillere değil, şekillerin içindeki tek tek metin bölümlerine de uygulayabilirsiniz; bu, slaytlarınızı tasarlarken size kapsamlı bir esneklik sağlar.

### Aspose.Slides için daha fazla kaynağı ve desteği nerede bulabilirim?
 Şuraya başvurabilirsiniz:[dokümantasyon](https://reference.aspose.com/slides/java/) ayrıntılı API referansları için[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) topluluk desteği ve tartışmalar için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
