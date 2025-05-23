---
"description": "Java Slaytlarında Aspose.Slides for Java kullanarak önceden tanımlanmış görünüm türlerinin nasıl ayarlanacağını öğrenin. Kod örnekleri ve SSS içeren adım adım kılavuz."
"linktitle": "Java Slaytlarında Önceden Tanımlanmış Görünüm Türü Olarak Kaydet"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Önceden Tanımlanmış Görünüm Türü Olarak Kaydet"
"url": "/tr/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Önceden Tanımlanmış Görünüm Türü Olarak Kaydet


## Java Slaytlarında Önceden Tanımlanmış Görünüm Türü Olarak Kaydetmeye Giriş

Bu adım adım kılavuzda, Aspose.Slides for Java kullanarak önceden tanımlanmış bir görünüm türüyle bir sunumun nasıl kaydedileceğini inceleyeceğiz. Bu görevi başarıyla tamamlamanız için gerekli kodu ve açıklamaları sağlayacağız.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Temel Java programlama bilgisi.
- Java için Aspose.Slides kütüphanesi kuruldu.
- Tercih ettiğiniz entegre geliştirme ortamı (IDE).

## Ortamınızı Kurma

Başlamak için geliştirme ortamınızı kurmak üzere şu adımları izleyin:

1. IDE'nizde yeni bir Java projesi oluşturun.
2. Aspose.Slides for Java kütüphanesini projenize bağımlılık olarak ekleyin.

Artık ortamınız hazır olduğuna göre kod yazmaya geçebiliriz.

## Adım 1: Bir Sunum Oluşturma

Önceden tanımlanmış bir görünüm türüyle bir sunumu kaydetmeyi göstermek için önce yeni bir sunum oluşturacağız. İşte bir sunum oluşturmak için kod:

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Sunum dosyasını açma
Presentation presentation = new Presentation();
```

Bu kodda yeni bir tane oluşturuyoruz `Presentation` PowerPoint sunumuzu temsil eden nesne.

## Adım 2: Görünüm Türünü Ayarlama

Sonra, sunumumuzun görünüm türünü ayarlayacağız. Görünüm türleri, sununun açıldığında nasıl görüntüleneceğini tanımlar. Bu örnekte, bunu "Slayt Ana Görünümü" olarak ayarlayacağız. İşte kod:

```java
// Görünüm türünü ayarlama
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

Yukarıdaki kodda şunu kullanıyoruz: `setLastView` yöntemi `ViewProperties` görünüm türünü ayarlamak için sınıf `SlideMasterView`İhtiyacınıza göre diğer görünüm tiplerini seçebilirsiniz.

## Adım 3: Sunumu Kaydetme

Artık sunumumuzu oluşturduğumuza ve görünüm türünü ayarladığımıza göre, sunumu kaydetme zamanı geldi. Bunu PPTX formatında kaydedeceğiz. İşte kod:

```java
// Sunum kaydediliyor
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

Bu kodda şunu kullanıyoruz: `save` yöntemi `Presentation` Sunuyu belirtilen dosya adı ve formatıyla kaydetmek için kullanılan sınıf.

## Java Slaytlarında Önceden Tanımlanmış Görünüm Türü Olarak Kaydetme İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Sunum dosyasını açma
Presentation presentation = new Presentation();
try
{
	// Görünüm türünü ayarlama
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Sunum kaydediliyor
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Bu eğitimde, Java'da Aspose.Slides for Java kullanarak önceden tanımlanmış bir görünüm türüyle bir sunumun nasıl kaydedileceğini öğrendik. Sağlanan kodu ve adımları izleyerek, sunumlarınızın görünüm türünü kolayca ayarlayabilir ve bunları istediğiniz biçimde kaydedebilirsiniz.

## SSS

### Görünüm türünü "Slayt Ana Görünümü"nden başka bir şeye nasıl değiştirebilirim?

Görünüm türünü "Slayt Ana Görünümü"nden farklı bir şeye değiştirmek için, basitçe değiştirin `ViewType.SlideMasterView` İstenilen görünüm türüyle, örneğin `ViewType.NveyamalView` or `ViewType.SlideSorterView`, görünüm türünü ayarladığımız kodda.

### Sunumdaki her bir slayt için görünüm özelliklerini ayarlayabilir miyim?

Evet, Aspose.Slides for Java kullanarak tek tek slaytlar için görünüm özelliklerini ayarlayabilirsiniz. Sunumdaki slaytlar arasında yineleme yaparak her slayt için özelliklere ayrı ayrı erişebilir ve bunları düzenleyebilirsiniz.

### Sunumumu hangi formatlarda kaydedebilirim?

Java için Aspose.Slides, PPTX, PDF, TIFF, HTML ve daha fazlası dahil olmak üzere çeşitli çıktı biçimlerini destekler. Uygun biçimi kullanarak sunumunuzu kaydederken istediğiniz biçimi belirtebilirsiniz `SaveFormat` enum değeri.

### Aspose.Slides for Java sunumların toplu işlenmesi için uygun mudur?

Evet, Java için Aspose.Slides toplu işleme görevleri için oldukça uygundur. Java kodunu kullanarak birden fazla sunumun işlenmesini otomatikleştirebilir, değişiklikler uygulayabilir ve bunları toplu olarak kaydedebilirsiniz.

### Aspose.Slides for Java hakkında daha fazla bilgi ve belgeyi nerede bulabilirim?

Aspose.Slides for Java ile ilgili kapsamlı dokümantasyon ve referanslar için lütfen dokümantasyon web sitesini ziyaret edin: [Java Belgeleri için Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}