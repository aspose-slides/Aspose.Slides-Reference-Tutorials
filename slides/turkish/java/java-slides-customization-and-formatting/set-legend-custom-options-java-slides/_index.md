---
"description": "Java Slaytlarında Aspose.Slides for Java kullanarak özel efsane seçeneklerini nasıl ayarlayacağınızı öğrenin. PowerPoint grafiklerinizde efsane konumunu ve boyutunu özelleştirin."
"linktitle": "Java Slaytlarında Efsane Özel Seçeneklerini Ayarlama"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Efsane Özel Seçeneklerini Ayarlama"
"url": "/tr/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Efsane Özel Seçeneklerini Ayarlama


## Java Slaytlarında Efsane Özel Seçeneklerini Ayarlamaya Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumunda bir grafiğin gösterge özelliklerinin nasıl özelleştirileceğini göstereceğiz. Göstergenin konumunu, boyutunu ve diğer özniteliklerini sunum ihtiyaçlarınıza uyacak şekilde değiştirebilirsiniz.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.Slides for Java API'si kuruldu.
- Java geliştirme ortamı kuruldu.

## Adım 1: Gerekli sınıfları içe aktarın:

```java
// Java sınıfları için Aspose.Slides'ı içe aktarın
import com.aspose.slides.*;
```

## Adım 2: Belge dizininize giden yolu belirtin:

```java
String dataDir = "Your Document Directory";
```

## Adım 3: Bir örnek oluşturun `Presentation` sınıf:

```java
Presentation presentation = new Presentation();
```

## Adım 4: Sunuma bir slayt ekleyin:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Adım 5: Slayda kümelenmiş sütun grafiği ekleyin:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Adım 6. Efsane Özelliklerini Ayarlayın:

- Efsanenin X konumunu ayarlayın (grafik genişliğine göre):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Efsanenin Y konumunu ayarlayın (grafik yüksekliğine göre):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Efsanenin genişliğini ayarlayın (grafik genişliğine göre):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Efsanenin yüksekliğini ayarlayın (grafik yüksekliğine göre):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Adım 7: Sunumu diske kaydedin:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

İşte bu kadar! Aspose.Slides for Java kullanarak bir PowerPoint sunumundaki grafiğin gösterge özelliklerini başarıyla özelleştirdiniz.

## Java Slaytlarında Set Legend Özel Seçenekleri İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir Presentation sınıfı örneği oluşturun
Presentation presentation = new Presentation();
try
{
	// Slaytın referansını alın
	ISlide slide = presentation.getSlides().get_Item(0);
	// Slayta kümelenmiş sütun grafiği ekleyin
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Efsane Özelliklerini Ayarla
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

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumundaki bir grafiğin gösterge özelliklerinin nasıl özelleştirileceğini öğrendik. Göstergenin konumunu, boyutunu ve diğer özniteliklerini değiştirerek görsel olarak çekici ve bilgilendirici sunumlar oluşturabilirsiniz.

## SSS

## Efsanenin konumunu nasıl değiştirebilirim?

Efsanenin konumunu değiştirmek için şunu kullanın: `setX` Ve `setY` efsane nesnesinin yöntemleri. Değerler grafiğin genişliğine ve yüksekliğine göre belirtilir.

## Efsanenin boyutunu nasıl ayarlayabilirim?

Efsanenin boyutunu ayarlamak için `setWidth` Ve `setHeight` efsane nesnesinin yöntemleri. Bu değerler aynı zamanda grafiğin genişliğine ve yüksekliğine göredir.

## Diğer efsane özelliklerini özelleştirebilir miyim?

Evet, yazı tipi stili, kenarlık, arka plan rengi ve daha fazlası gibi efsanenin çeşitli niteliklerini özelleştirebilirsiniz. Efsaneleri daha fazla özelleştirme hakkında ayrıntılı bilgi için Aspose.Slides belgelerini inceleyin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}