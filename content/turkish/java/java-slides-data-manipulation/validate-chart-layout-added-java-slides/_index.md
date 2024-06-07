---
title: Java Slaytlarına Eklenen Grafik Düzenini Doğrulayın
linktitle: Java Slaytlarına Eklenen Grafik Düzenini Doğrulayın
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java ile PowerPoint'te ana grafik düzeni doğrulaması. Çarpıcı sunumlar için grafikleri programlı bir şekilde değiştirmeyi öğrenin.
type: docs
weight: 10
url: /tr/java/data-manipulation/validate-chart-layout-added-java-slides/
---

## Aspose.Slides for Java'da Grafik Düzenini Doğrulamaya Giriş

Bu eğitimde Aspose.Slides for Java kullanarak bir PowerPoint sunumunda grafik düzeninin nasıl doğrulanacağını inceleyeceğiz. Bu kitaplık, PowerPoint sunumlarıyla programlı olarak çalışmanıza olanak tanır ve grafikler de dahil olmak üzere çeşitli öğeleri yönetmenizi ve doğrulamanızı kolaylaştırır.

## Adım 1: Sunumu Başlatma

 Öncelikle bir sunum nesnesini başlatmamız ve mevcut bir PowerPoint sunumunu yüklememiz gerekiyor. Yer değiştirmek`"Your Document Directory"` sunum dosyanızın gerçek yolunu içeren (`test.pptx` bu örnekte).

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Adım 2: Grafik Ekleme

 Daha sonra sunuma bir grafik ekleyeceğiz. Bu örnekte, kümelenmiş bir sütun grafiği ekliyoruz ancak siz bunu değiştirebilirsiniz.`ChartType` ihyaç olduğu gibi.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## 3. Adım: Grafik Düzenini Doğrulama

 Şimdi grafik düzenini aşağıdaki komutu kullanarak doğrulayacağız:`validateChartLayout()` yöntem. Bu, grafiğin slaytta düzgün şekilde yerleştirilmesini sağlar.

```java
chart.validateChartLayout();
```

## Adım 4: Grafik Konumunu ve Boyutunu Alma

Grafik düzenini doğruladıktan sonra konumu ve boyutu hakkında bilgi almak isteyebilirsiniz. Gerçek X ve Y koordinatlarının yanı sıra grafiğin çizim alanının genişliğini ve yüksekliğini de alabiliriz.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## Adım 5: Sunumu Kaydetme

 Son olarak değiştirilen sunumu kaydetmeyi unutmayın. Bu örnekte, onu şu şekilde kaydediyoruz:`Result.pptx`, ancak gerekirse farklı bir dosya adı belirtebilirsiniz.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Java Slaytlarına Eklenen Grafik Düzenini Doğrulamak İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
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

Bu eğitimde Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarında grafiklerle çalışma dünyasını derinlemesine inceledik. Grafik düzenini doğrulamak, konumunu ve boyutunu almak ve değiştirilen sunumu kaydetmek için gerekli adımları ele aldık. İşte kısa bir özet:

## SSS'ler

### Grafik türünü nasıl değiştiririm?

 Grafik türünü değiştirmek için basitçe değiştirin`ChartType.ClusteredColumn`İstenilen grafik türü ile`addChart()` yöntem.

### Grafik verilerini özelleştirebilir miyim?

Evet, veri serileri, kategoriler ve değerler ekleyip değiştirerek grafik verilerini özelleştirebilirsiniz. Daha fazla ayrıntı için Aspose.Slides belgelerine bakın.

### Diğer grafik özelliklerini değiştirmek istersem ne olur?

Çeşitli grafik özelliklerine erişebilir ve bunları ihtiyaçlarınıza göre özelleştirebilirsiniz. Grafik manipülasyonu hakkında kapsamlı bilgi için Aspose.Slides belgelerini inceleyin.
