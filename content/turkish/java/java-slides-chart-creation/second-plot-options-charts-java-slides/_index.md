---
title: Java Slaytlarındaki Grafikler için İkinci Grafik Seçenekleri
linktitle: Java Slaytlarındaki Grafikler için İkinci Grafik Seçenekleri
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slides'taki grafikleri nasıl özelleştireceğinizi öğrenin. İkinci senaryo seçeneklerini keşfedin ve sunumlarınızı geliştirin.
type: docs
weight: 12
url: /tr/java/chart-creation/second-plot-options-charts-java-slides/
---

## Java Slaytlarındaki Grafikler için İkinci Grafik Seçeneklerine Giriş

Bu eğitimde Aspose.Slides for Java kullanarak grafiklere ikinci çizim seçeneklerinin nasıl ekleneceğini inceleyeceğiz. İkinci çizim seçenekleri, özellikle Pie of Pie grafikleri gibi senaryolarda grafiklerin görünümünü ve davranışını özelleştirmenize olanak tanır. Bunu başarmak için adım adım talimatlar ve kaynak kodu örnekleri sunacağız. 

## Önkoşullar
Başlamadan önce Java projenizde Aspose.Slides for Java'nın kurulu ve kurulu olduğundan emin olun.

## 1. Adım: Bir Sunu Oluşturun
Yeni bir sunum oluşturarak başlayalım:

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum sınıfının bir örneğini oluşturun
Presentation presentation = new Presentation();
```

## Adım 2: Slayta Grafik Ekleme
Daha sonra slayta bir grafik ekleyeceğiz. Bu örnekte bir Pasta Pastası grafiği oluşturacağız:

```java
// Slayta grafik ekleme
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## 3. Adım: Grafik Özelliklerini Özelleştirin
Şimdi ikinci çizim seçenekleri de dahil olmak üzere grafik için farklı özellikler ayarlayalım:

```java
// İlk serinin veri etiketlerini göster
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// İkinci pastanın boyutunu ayarlayın (yüzde olarak)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Pastayı yüzdeye göre böl
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Bölmenin konumunu ayarlayın
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## 4. Adım: Sunuyu Kaydetme
Son olarak sunumu grafik ve ikinci çizim seçenekleriyle kaydedin:

```java
// Sunumu diske yaz
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## İkinci Grafik Seçenekleri İçin Kaynak Kodunu Tamamlayın

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum sınıfının bir örneğini oluşturun
Presentation presentation = new Presentation();
// Slayta grafik ekleme
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Farklı özellikleri ayarlayın
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Sunumu diske yaz
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java kullanarak Java Slides'daki grafiklere ikinci çizim seçeneklerini nasıl ekleyeceğimizi öğrendik. Grafiklerinizin görünümünü ve işlevselliğini geliştirmek, sunumlarınızı daha bilgilendirici ve görsel olarak çekici hale getirmek için çeşitli özellikleri özelleştirebilirsiniz.

## SSS'ler

### Pie of Pie grafiğindeki ikinci pastanın boyutunu nasıl değiştirebilirim?

 Pasta Pastası grafiğindeki ikinci pastanın boyutunu değiştirmek için`setSecondPieSize` Yukarıdaki kod örneğinde gösterildiği gibi yöntem. Boyutu yüzde cinsinden belirtmek için değeri ayarlayın.

###  Nedir`PieSplitBy` control in a Pie of Pie chart?

`PieSplitBy` özellik pasta grafiğinin nasıl bölündüğünü kontrol eder. İkisinden birine ayarlayabilirsiniz`PieSplitType.ByPercentage` veya`PieSplitType.ByValue` Grafiği sırasıyla yüzdeye veya belirli bir değere göre bölmek için.

### Pie of Pie grafiğinde bölünmenin konumunu nasıl ayarlarım?

Bölmenin konumunu Pie of Pie grafiğinde ayarlayabilirsiniz.`setPieSplitPosition` yöntem. İstenilen konumu belirtmek için değeri ayarlayın.