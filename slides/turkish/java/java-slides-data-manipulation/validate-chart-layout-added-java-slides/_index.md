---
"description": "Aspose.Slides for Java ile PowerPoint'te grafik düzeni doğrulamasını yönetin. Çarpıcı sunumlar için grafikleri programatik olarak düzenlemeyi öğrenin."
"linktitle": "Java Slaytlarına Eklenen Grafik Düzenini Doğrula"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarına Eklenen Grafik Düzenini Doğrula"
"url": "/tr/java/data-manipulation/validate-chart-layout-added-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarına Eklenen Grafik Düzenini Doğrula


## Java için Aspose.Slides'ta Grafik Düzenini Doğrulamaya Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumundaki grafik düzeninin nasıl doğrulanacağını inceleyeceğiz. Bu kütüphane, PowerPoint sunumlarıyla programatik olarak çalışmanıza olanak tanır ve grafikler de dahil olmak üzere çeşitli öğeleri kolayca düzenlemenizi ve doğrulamanızı sağlar.

## Adım 1: Sunumu Başlatma

İlk olarak bir sunum nesnesi başlatmamız ve mevcut bir PowerPoint sunumunu yüklememiz gerekir. Değiştir `"Your Document Directory"` sunum dosyanızın gerçek yolu ile (`test.pptx` (bu örnekte).

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Adım 2: Grafik Ekleme

Sonra, sunuma bir grafik ekleyeceğiz. Bu örnekte, kümelenmiş bir sütun grafiği ekliyoruz, ancak bunu değiştirebilirsiniz `ChartType` ihtiyaç duyulduğu takdirde.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## Adım 3: Grafik Düzenini Doğrulama

Şimdi, grafik düzenini kullanarak doğrulayacağız `validateChartLayout()` yöntem. Bu, grafiğin slayt içerisinde düzgün bir şekilde yerleştirilmesini sağlar.

```java
chart.validateChartLayout();
```

## Adım 4: Grafik Pozisyonunu ve Boyutunu Alma

Grafik düzenini doğruladıktan sonra, konumu ve boyutu hakkında bilgi almak isteyebilirsiniz. Gerçek X ve Y koordinatlarını ve grafiğin çizim alanının genişliğini ve yüksekliğini alabiliriz.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## Adım 5: Sunumu Kaydetme

Son olarak, değiştirilen sunumu kaydetmeyi unutmayın. Bu örnekte, bunu şu şekilde kaydediyoruz: `Result.pptx`, ancak gerekirse farklı bir dosya adı belirtebilirsiniz.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Java Slaytlarına Eklenen Doğrulama Tablosu Düzeni İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Sunum kaydediliyor
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint sunumlarında grafiklerle çalışma dünyasına daldık. Grafik düzenini doğrulamak, konumunu ve boyutunu almak ve değiştirilmiş sunumu kaydetmek için gerekli adımları ele aldık. İşte kısa bir özet:

## SSS

### Grafik türünü nasıl değiştirebilirim?

Grafik türünü değiştirmek için, basitçe değiştirin `ChartType.ClusteredColumn` istenilen grafik türüyle `addChart()` yöntem.

### Grafik verilerini özelleştirebilir miyim?

Evet, veri serilerini, kategorileri ve değerleri ekleyerek ve değiştirerek grafik verilerini özelleştirebilirsiniz. Daha fazla ayrıntı için Aspose.Slides belgelerine bakın.

### Diğer grafik özelliklerini değiştirmek istersem ne olur?

Çeşitli grafik özelliklerine erişebilir ve bunları gereksinimlerinize göre özelleştirebilirsiniz. Grafik manipülasyonu hakkında kapsamlı bilgi için Aspose.Slides belgelerini inceleyin.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}