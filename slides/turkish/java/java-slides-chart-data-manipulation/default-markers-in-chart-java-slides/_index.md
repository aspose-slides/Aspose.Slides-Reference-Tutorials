---
title: Java Slaytlarındaki Grafikteki Varsayılan İşaretçiler
linktitle: Java Slaytlarındaki Grafikteki Varsayılan İşaretçiler
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak grafiklerde varsayılan işaretleyicilerle Java Slaytları oluşturmayı öğrenin. Kaynak koduyla adım adım kılavuz.
type: docs
weight: 16
url: /tr/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

## Java Slaytlarındaki Grafikteki Varsayılan İşaretleyicilere Giriş

Bu eğitimde Aspose.Slides for Java'yı kullanarak varsayılan işaretleyicilerle nasıl grafik oluşturulacağını keşfedeceğiz. Varsayılan işaretçiler, bir grafikteki veri noktalarını vurgulamak için bunlara eklenen semboller veya şekillerdir. Verileri görselleştirmek için işaretçilerin bulunduğu bir çizgi grafiği oluşturacağız.

## Önkoşullar

Başlamadan önce Java projenizde Aspose.Slides for Java kitaplığının kurulu olduğundan ve kurulduğundan emin olun.

## 1. Adım: Bir Sunu Oluşturun

Öncelikle bir sunum oluşturalım ve ona bir slayt ekleyelim. Daha sonra slayda bir grafik ekleyeceğiz.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Adım 2: İşaretçilerle Çizgi Grafiği Ekleme

Şimdi slayta işaretleyicilerin bulunduğu bir çizgi grafiği ekleyelim. Ayrıca grafikteki tüm varsayılan verileri de temizleyeceğiz.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## 3. Adım: Grafik Verilerini Doldurun

Grafiği örnek verilerle dolduracağız. Bu örnekte veri noktaları ve kategorileri olan iki seri oluşturacağız.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Seri 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Seri 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Seri verilerini doldurma
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## 4. Adım: Grafiği Özelleştirin

Gösterge eklemek ve görünümünü ayarlamak gibi yöntemlerle grafiği daha da özelleştirebilirsiniz.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Adım 5: Sunuyu Kaydetme

Son olarak, sunumu grafikle birlikte istediğiniz konuma kaydedin.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Bu kadar! Aspose.Slides for Java'yı kullanarak varsayılan işaretleyicilere sahip bir çizgi grafik oluşturdunuz.

## Java Slaytlarındaki Grafikteki Varsayılan İşaretleyiciler İçin Kaynak Kodunu Tamamlayın

```java
        // Belgeler dizininin yolu.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //İkinci grafik serisini alın
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Şimdi seri verileri dolduruluyor
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Çözüm

Bu kapsamlı eğitimde Aspose.Slides for Java'yı kullanarak grafiklerde varsayılan işaretçilerle Java Slaytları oluşturmayı öğrendiniz. Bir sunumun hazırlanmasından grafiğin görünümünün özelleştirilmesine ve sonucun kaydedilmesine kadar tüm süreci ele aldık.

## SSS'ler

### İşaretçi sembollerini nasıl değiştirebilirim?

Her veri noktası için işaretçi stilini ayarlayarak işaretçi sembollerini özelleştirebilirsiniz. Kullanmak`IDataPoint.setMarkerStyle()` İşaretçi sembolünü değiştirmek için.

### Grafiğin renklerini nasıl ayarlarım?

 Grafiğin renklerini değiştirmek için`IChartSeriesFormat` Ve`IShapeFillFormat` Dolgu ve çizgi özelliklerini ayarlamak için arayüzler.

### Veri noktalarına etiket ekleyebilir miyim?

 Evet, kullanarak veri noktalarına etiket ekleyebilirsiniz.`IDataPoint.getLabel()` yöntemini kullanın ve bunları gerektiği gibi özelleştirin.