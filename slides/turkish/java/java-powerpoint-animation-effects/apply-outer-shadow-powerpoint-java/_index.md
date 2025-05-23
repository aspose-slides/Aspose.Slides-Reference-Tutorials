---
"description": "Aspose.Slides ile Java kullanarak PowerPoint'te dış gölge efektinin nasıl uygulanacağını öğrenin. Sunumlarınızı derinlik ve görsel çekicilikle geliştirin."
"linktitle": "PowerPoint'te Java ile Dış Gölge Uygulama"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "PowerPoint'te Java ile Dış Gölge Uygulama"
"url": "/tr/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Java ile Dış Gölge Uygulama

## giriiş
Görsel olarak çekici PowerPoint sunumları oluşturmak genellikle şekillere ve metne çeşitli efektler eklemeyi içerir. Bu efektlerden biri de öğeleri öne çıkarabilen ve slaytlarınıza derinlik katabilen dış gölgedir. Bu eğitimde, Aspose.Slides ile Java kullanarak PowerPoint'te bir şekle dış gölge efektinin nasıl uygulanacağını öğreneceksiniz.
## Ön koşullar

Bu eğitime başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

1. Java Geliştirme Kiti (JDK): Sisteminizde Java'nın yüklü olduğundan emin olun. JDK'nın en son sürümünü Oracle web sitesinden indirip yükleyebilirsiniz.

2. Java için Aspose.Slides: Java için Aspose.Slides'ı indirin ve yükleyin [indirme sayfası](https://releases.aspose.com/slides/java/).

3. Entegre Geliştirme Ortamı (IDE): Java uygulamalarını kodlamak ve çalıştırmak için Eclipse, IntelliJ IDEA veya NetBeans gibi tercih ettiğiniz Java IDE'sini seçin.

4. Temel Java Bilgisi: Java programlama dilinin temelleri ve nesne yönelimli kavramlara aşinalık, kod örneklerini anlamak için faydalı olacaktır.

## Paketleri İçe Aktar

Öncelikle Java projenize Aspose.Slides ve ilgili işlevlerle çalışmak için gerekli paketleri içe aktarın:

```java
import com.aspose.slides.*;
```

Şimdi, PowerPoint'te Aspose.Slides ile Java kullanarak bir şekle dış gölge efektini uygulamak için örnek kodu birden fazla adıma bölelim:

## Adım 1: Proje ortamınızı kurun

Tercih ettiğiniz IDE'de yeni bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin derleme yoluna ekleyin.

## Adım 2: Sunum nesnesini başlatın

Bir örneğini oluşturun `Presentation` PowerPoint sunum dosyasını temsil eden sınıf.

```java
Presentation presentation = new Presentation();
```

## Adım 3: Bir slayt ve şekil ekleyin

Şekli eklemek istediğiniz slayda bir referans alın ve ardından slayda bir Otomatik Şekil (örneğin dikdörtgen) ekleyin.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Adım 4: Şekli özelleştirin

Şeklin dolgu türünü 'NoFill' olarak ayarlayın ve şekle metin ekleyin.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Adım 5: Metni özelleştirin

Şeklin metin özelliklerine erişin ve yazı tipi boyutunu özelleştirin.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Adım 6: Dış Gölge efektini etkinleştirin

Metin kısmı için dış gölge efektini etkinleştirin.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Adım 7: Gölge parametrelerini ayarlayın

Bulanıklaştırma yarıçapı, yön, mesafe ve gölge rengi gibi dış gölge efektinin parametrelerini tanımlayın.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Adım 8: Sunumu kaydedin

Değiştirilen sunumu, şekle uygulanan dış gölge efektiyle birlikte kaydedin.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Çözüm

Tebrikler! Aspose.Slides ile Java kullanarak PowerPoint'te bir şekle dış gölge efektini başarıyla uyguladınız. Sunumlarınızda istediğiniz görsel efektleri elde etmek için farklı parametrelerle denemeler yapın.

## SSS

### Dış gölge efektini dikdörtgenlerin dışında başka şekillere de uygulayabilir miyim?
Evet, Aspose.Slides tarafından desteklenen daireler, üçgenler ve özel şekiller gibi çeşitli şekillere dış gölge efektini uygulayabilirsiniz.

### Gölge rengini ve yoğunluğunu özelleştirmek mümkün mü?
Kesinlikle! Renk, bulanıklık yarıçapı, yön ve mesafe dahil olmak üzere gölge parametreleri üzerinde tam kontrole sahipsiniz.

### Aynı şekle birden fazla efekt uygulayabilir miyim?
Evet, sunumlarınızdaki şekillerin ve metinlerin görsel çekiciliğini artırmak için dış gölge, iç gölge, parıltı ve yansıma gibi birden fazla efekti birleştirebilirsiniz.

### Aspose.Slides metin öğelerine efekt uygulanmasını destekliyor mu?
Evet, efektleri yalnızca şekillere değil, şekillerin içindeki tek tek metin bölümlerine de uygulayabilirsiniz; bu da slaytlarınızı tasarlarken size geniş bir esneklik sağlar.

### Aspose.Slides için daha fazla kaynak ve desteği nerede bulabilirim?
Şuraya başvurabilirsiniz: [belgeleme](https://reference.aspose.com/slides/java/) Ayrıntılı API referansları için ve keşfedin [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) Topluluk desteği ve tartışmaları için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}