---
title: Java Slaytlarında Önceden Tanımlanmış Görünüm Türü Olarak Kaydetme
linktitle: Java Slaytlarında Önceden Tanımlanmış Görünüm Türü Olarak Kaydetme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slides'ta önceden tanımlanmış görünüm türlerini nasıl ayarlayacağınızı öğrenin. Kod örnekleri ve SSS içeren adım adım kılavuz.
type: docs
weight: 10
url: /tr/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

## Java Slaytlarında Önceden Tanımlanmış Görünüm Türü Olarak Kaydetmeye Giriş

Bu adım adım kılavuzda, Aspose.Slides for Java'yı kullanarak bir sunumun önceden tanımlanmış bir görünüm türüyle nasıl kaydedileceğini keşfedeceğiz. Bu görevi başarıyla gerçekleştirmek için size gerekli kodu ve açıklamaları sağlayacağız.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Java programlamanın temel bilgisi.
- Aspose.Slides for Java kütüphanesi kuruldu.
- Seçtiğiniz entegre geliştirme ortamı (IDE).

## Ortamınızı Kurma

Başlamak için geliştirme ortamınızı ayarlamak üzere şu adımları izleyin:

1. IDE'nizde yeni bir Java projesi oluşturun.
2. Aspose.Slides for Java kütüphanesini projenize bağımlılık olarak ekleyin.

Artık ortamınız ayarlandığına göre koda geçelim.

## Adım 1: Sunum Oluşturma

Bir sunumu önceden tanımlanmış bir görünüm türüyle kaydetmeyi göstermek için önce yeni bir sunum oluşturacağız. İşte sunum oluşturma kodu:

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum dosyasını açma
Presentation presentation = new Presentation();
```

 Bu kodda yeni bir tane oluşturuyoruz.`Presentation` PowerPoint sunumumuzu temsil eden nesne.

## Adım 2: Görünüm Türünü Ayarlama

Daha sonra sunumumuzun görünüm türünü ayarlayacağız. Görünüm türleri, sunumun açıldığında nasıl görüntüleneceğini tanımlar. Bu örnekte bunu "Ana Slayt Görünümü" olarak ayarlayacağız. İşte kod:

```java
// Görünüm türünü ayarlama
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 Yukarıdaki kodda şunu kullanıyoruz:`setLastView` yöntemi`ViewProperties` görünüm türünü ayarlamak için sınıf`SlideMasterView`. Gerektiğinde diğer görünüm türlerini seçebilirsiniz.

## Adım 3: Sunumu Kaydetme

Artık sunumuzu oluşturduğumuza ve görünüm türünü ayarladığımıza göre, sunuyu kaydetme zamanı geldi. PPTX formatında kaydedeceğiz. İşte kod:

```java
// Sunum kaydediliyor
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 Bu kodda şunu kullanıyoruz:`save` yöntemi`Presentation` Sunuyu belirtilen dosya adı ve biçimde kaydetmek için class.

## Java Slaytlarında Önceden Tanımlanmış Görünüm Türü Olarak Kaydetmek İçin Kaynak Kodunu Tamamlayın

```java
// Belgeler dizininin yolu.
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

Bu eğitimde, Aspose.Slides for Java kullanarak Java'da önceden tanımlanmış bir görünüm türüyle bir sunumun nasıl kaydedileceğini öğrendik. Verilen kodu ve adımları takip ederek sunumlarınızın görünüm türünü kolayca ayarlayabilir ve istediğiniz formatta kaydedebilirsiniz.

## SSS'ler

### Görünüm türünü "Ana Slayt Görünümü" dışında bir şeye nasıl değiştiririm?

 Görünüm türünü "Ana Slayt Görünümü" dışında bir şeye değiştirmek için, yalnızca`ViewType.SlideMasterView` istenilen görünüm tipiyle, örneğin`ViewType.NormalView` veya`ViewType.SlideSorterView`, görünüm türünü ayarladığımız kodda.

### Sunumdaki tek tek slaytların görünüm özelliklerini ayarlayabilir miyim?

Evet, Aspose.Slides for Java'yı kullanarak ayrı ayrı slaytların görünüm özelliklerini ayarlayabilirsiniz. Sunumdaki slaytları yineleyerek her slaytın özelliklerine ayrı ayrı erişebilir ve bunları değiştirebilirsiniz.

### Sunumumu başka hangi formatlarda kaydedebilirim?

Aspose.Slides for Java, PPTX, PDF, TIFF, HTML ve daha fazlası dahil olmak üzere çeşitli çıktı formatlarını destekler. Sununuzu kaydederken uygun formatı kullanarak istediğiniz formatı belirtebilirsiniz.`SaveFormat` numaralandırma değeri.

### Aspose.Slides for Java, sunumların toplu işlenmesi için uygun mudur?

Evet, Aspose.Slides for Java toplu işlem görevleri için çok uygundur. Birden fazla sunumun işlenmesini otomatikleştirebilir, değişiklikleri uygulayabilir ve Java kodunu kullanarak bunları toplu olarak kaydedebilirsiniz.

### Aspose.Slides for Java hakkında daha fazla bilgi ve belgeyi nerede bulabilirim?

 Aspose.Slides for Java ile ilgili kapsamlı dokümantasyon ve referanslar için lütfen dokümantasyon web sitesini ziyaret edin:[Aspose.Slides for Java Belgelendirmesi](https://reference.aspose.com/slides/java/).