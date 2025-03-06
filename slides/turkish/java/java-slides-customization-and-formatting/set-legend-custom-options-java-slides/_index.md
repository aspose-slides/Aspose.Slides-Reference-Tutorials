---
title: Java Slaytlarında Açıklama Özel Seçeneklerini Ayarlama
linktitle: Java Slaytlarında Açıklama Özel Seçeneklerini Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slides'ta özel gösterge seçeneklerini nasıl ayarlayacağınızı öğrenin. PowerPoint grafiklerinizde açıklama konumunu ve boyutunu özelleştirin.
weight: 14
url: /tr/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java Slaytlarında Gösterge Özel Seçeneklerini Ayarlamaya Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumunda bir grafiğin açıklama özelliklerinin nasıl özelleştirileceğini göstereceğiz. Sunum ihtiyaçlarınıza uyacak şekilde açıklamanın konumunu, boyutunu ve diğer özelliklerini değiştirebilirsiniz.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.Slides for Java API kuruldu.
- Java geliştirme ortamı kuruldu.

## Adım 1: Gerekli sınıfları içe aktarın:

```java
// Aspose.Slides'ı Java sınıfları için içe aktarın
import com.aspose.slides.*;
```

## Adım 2: Belge dizininizin yolunu belirtin:

```java
String dataDir = "Your Document Directory";
```

##  3. Adım: Bir örneğini oluşturun`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Adım 4: Sunuya slayt ekleyin:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Adım 5: Slayta kümelenmiş bir sütun grafiği ekleyin:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Adım 6. Açıklama Özelliklerini Ayarlayın:

- Göstergenin X konumunu ayarlayın (grafik genişliğine göre):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Göstergenin Y konumunu ayarlayın (grafik yüksekliğine göre):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Açıklamanın genişliğini ayarlayın (grafik genişliğine göre):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Göstergenin yüksekliğini ayarlayın (grafik yüksekliğine göre):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Adım 7: Sunuyu diske kaydedin:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Bu kadar! Aspose.Slides for Java'yı kullanarak PowerPoint sunumundaki bir grafiğin açıklama özelliklerini başarıyla özelleştirdiniz.

## Java Slaytlarında Legend Özel Seçeneklerini Ayarlamak İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum sınıfının bir örneğini oluşturun
Presentation presentation = new Presentation();
try
{
	// Slaytın referansını alın
	ISlide slide = presentation.getSlides().get_Item(0);
	// Slayda kümelenmiş sütun grafiği ekleme
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Açıklama Özelliklerini Ayarla
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Sunumu diske yaz
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Çözüm

Bu eğitimde Aspose.Slides for Java kullanarak bir PowerPoint sunumundaki grafiğin gösterge özelliklerini nasıl özelleştireceğimizi öğrendik. Görsel olarak çekici ve bilgilendirici sunumlar oluşturmak için açıklamanın konumunu, boyutunu ve diğer özelliklerini değiştirebilirsiniz.

## SSS'ler

## Efsanenin konumunu nasıl değiştirebilirim?

 Efsanenin konumunu değiştirmek için`setX` Ve`setY` efsane nesnesinin yöntemleri. Değerler grafiğin genişliğine ve yüksekliğine göre belirtilir.

## Efsanenin boyutunu nasıl ayarlayabilirim?

 Göstergenin boyutunu aşağıdaki düğmeyi kullanarak ayarlayabilirsiniz:`setWidth` Ve`setHeight` efsane nesnesinin yöntemleri. Bu değerler aynı zamanda grafiğin genişliğine ve yüksekliğine de bağlıdır.

## Diğer gösterge niteliklerini özelleştirebilir miyim?

Evet, yazı tipi stili, kenarlık, arka plan rengi ve daha fazlası gibi açıklamanın çeşitli özelliklerini özelleştirebilirsiniz. Göstergeleri daha fazla özelleştirme hakkında ayrıntılı bilgi için Aspose.Slides belgelerini inceleyin.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
