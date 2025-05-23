---
"description": "Aspose.Slides for Java kullanarak grafiklerde varsayılan işaretleyicilerle Java Slaytları oluşturmayı öğrenin. Kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarındaki Grafiklerde Varsayılan İşaretleyiciler"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarındaki Grafiklerde Varsayılan İşaretleyiciler"
"url": "/tr/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarındaki Grafiklerde Varsayılan İşaretleyiciler


## Java Slaytlarında Grafikteki Varsayılan İşaretleyicilere Giriş

Bu eğitimde, Java için Aspose.Slides kullanarak varsayılan işaretçilerle bir grafik oluşturmayı keşfedeceğiz. Varsayılan işaretçiler, bir grafikteki veri noktalarına vurgulamak için eklenen semboller veya şekillerdir. Verileri görselleştirmek için işaretçilerle bir çizgi grafiği oluşturacağız.

## Ön koşullar

Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin yüklü ve ayarlanmış olduğundan emin olun.

## Adım 1: Bir Sunum Oluşturun

Öncelikle bir sunum oluşturalım ve ona bir slayt ekleyelim. Daha sonra slayda bir grafik ekleyelim.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Adım 2: İşaretçilerle Çizgi Grafiği Ekleyin

Şimdi, slayda işaretçileri olan bir çizgi grafiği ekleyelim. Ayrıca grafikteki varsayılan verileri de temizleyeceğiz.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Adım 3: Grafik Verilerini Doldurun

Grafiği örnek verilerle dolduracağız. Bu örnekte, veri noktaları ve kategorilerle iki seri oluşturacağız.

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

// Seri verilerinin doldurulması
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Adım 4: Grafiği Özelleştirin

Grafiği daha da özelleştirebilirsiniz; örneğin, bir açıklama ekleyebilir ve görünümünü ayarlayabilirsiniz.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Adım 5: Sunumu Kaydedin

Son olarak sunumu grafikle birlikte istediğiniz yere kaydedin.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

İşte bu kadar! Java için Aspose.Slides'ı kullanarak varsayılan işaretçilerle bir çizgi grafiği oluşturdunuz.

## Java Slaytlarındaki Grafikteki Varsayılan İşaretleyiciler İçin Tam Kaynak Kodu

```java
        // Belgeler dizinine giden yol.
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

Bu kapsamlı eğitimde, Java için Aspose.Slides kullanarak grafiklerde varsayılan işaretçilerle Java Slaytları oluşturmayı öğrendiniz. Bir sunum hazırlamaktan grafiğin görünümünü özelleştirmeye ve sonucu kaydetmeye kadar tüm süreci ele aldık.

## SSS

### İşaretleyici sembollerini nasıl değiştirebilirim?

Her veri noktası için işaretçi stilini ayarlayarak işaretçi sembollerini özelleştirebilirsiniz. Kullan `IDataPoint.setMarkerStyle()` İşaretleyici sembolünü değiştirmek için.

### Tablonun renklerini nasıl ayarlarım?

Tablonun renklerini değiştirmek için şunu kullanabilirsiniz: `IChartSeriesFormat` Ve `IShapeFillFormat` dolgu ve çizgi özelliklerini ayarlamak için arayüzler.

### Veri noktalarına etiket ekleyebilir miyim?

Evet, veri noktalarına etiketler ekleyebilirsiniz. `IDataPoint.getLabel()` yöntemini kullanın ve ihtiyaç duyduğunuzda özelleştirin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}