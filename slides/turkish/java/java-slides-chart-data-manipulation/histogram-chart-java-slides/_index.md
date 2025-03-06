---
title: Java Slaytlarındaki Histogram Grafiği
linktitle: Java Slaytlarındaki Histogram Grafiği
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarında Histogram Grafiklerini nasıl oluşturacağınızı öğrenin. Veri görselleştirmesi için kaynak kodu içeren adım adım kılavuz.
weight: 19
url: /tr/java/chart-data-manipulation/histogram-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarındaki Histogram Grafiği


## Aspose.Slides kullanarak Java Slaytlarında Histogram Grafiğine Giriş

Bu eğitimde, Aspose.Slides for Java API'sini kullanarak PowerPoint sunumunda Histogram Grafiği oluşturma sürecinde size rehberlik edeceğiz. Histogram Grafiği, verilerin sürekli bir aralıktaki dağılımını temsil etmek için kullanılır.

## Önkoşullar

 Başlamadan önce Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Web sitesi](https://releases.aspose.com/slides/java/).

## 1. Adım: Projenizi Başlatın

Bir Java projesi oluşturun ve Aspose.Slides kütüphanesini projenizin bağımlılıklarına ekleyin.

## Adım 2: Gerekli Kitaplıkları İçe Aktarın

```java
import com.aspose.slides.*;
```

## 3. Adım: Mevcut Bir Sunumu Yükleyin

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Değiştirdiğinizden emin olun`"Your Document Directory"` PowerPoint belgenizin gerçek yolunu belirtin.

## Adım 4: Histogram Grafiği Oluşturun

Şimdi sunumdaki bir slayt üzerinde Histogram Grafiği oluşturalım.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Seriye veri noktaları ekleme
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Yatay eksen toplama türünü Otomatik olarak ayarlayın
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Sunuyu kaydet
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 Bu kodda öncelikle mevcut kategorileri ve serileri grafikten temizliyoruz. Daha sonra seriye veri noktalarını kullanarak ekliyoruz.`getDataPoints().addDataPointForHistogramSeries` yöntem. Son olarak yatay eksen toplama tipini Otomatik olarak ayarlayıp sunumu kaydediyoruz.

## Java Slaytlarındaki Histogram Grafiği İçin Tam Kaynak Kodu

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides for Java API'sini kullanarak PowerPoint sunumunda Histogram Grafiğinin nasıl oluşturulacağını araştırdık. Histogram Grafikleri, verilerin sürekli bir aralıktaki dağılımını görselleştirmek için değerli araçlardır ve özellikle istatistiksel veya analitik içerikle uğraşırken sunumlarınıza güçlü bir katkı sağlayabilirler.

## SSS'ler

### Aspose.Slides for Java'yı nasıl yüklerim?

 Aspose.Slides for Java kütüphanesini şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/slides/java/). Web sitelerinde verilen kurulum talimatlarını izleyin.

### Histogram Grafiği ne için kullanılır?

Histogram Grafiği, verilerin sürekli bir aralıktaki dağılımını görselleştirmek için kullanılır. İstatistiklerde sıklık dağılımlarını temsil etmek için yaygın olarak kullanılır.

### Histogram Grafiğinin görünümünü özelleştirebilir miyim?

Evet, Aspose.Slides API'sini kullanarak grafiğin görünümünü renkler, etiketler ve eksenler dahil olmak üzere özelleştirebilirsiniz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
