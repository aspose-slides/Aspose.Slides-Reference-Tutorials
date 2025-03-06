---
title: Java Slaytlarındaki Ağaç Haritası Grafiği
linktitle: Java Slaytlarındaki Ağaç Haritası Grafiği
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slaytlarında Ağaç Haritası Grafikleri oluşturun. Hiyerarşik verileri görselleştirmek için kaynak kodlu adım adım kılavuz.
type: docs
weight: 13
url: /tr/java/chart-creation/tree-map-chart-java-slides/
---

## Java Slaytlarında Ağaç Haritası Grafiğine Giriş

Bu eğitimde Aspose.Slides for Java kütüphanesini kullanarak bir PowerPoint sunumunda Ağaç Haritası grafiğinin nasıl oluşturulacağını göstereceğiz. Ağaç Haritası grafikleri hiyerarşik verileri görselleştirmenin etkili bir yoludur.

## Önkoşullar

Başlamadan önce Java projenizde Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun.

## 1. Adım: Gerekli Kitaplıkları İçe Aktarın

```java
import com.aspose.slides.*;
```

## 2. Adım: Sunuyu Yükleyin

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Adım 3: Ağaç Haritası Grafiği Oluşturun

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);

    // Şube 1'i oluştur
    IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch1");

    chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

    // Şube 2'yi oluştur
    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem4");

    chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));

    // Veri noktaları ekleyin
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
    series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);

    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));

    series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);

    // Sunuyu Ağaç Haritası grafiğiyle kaydedin
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Java Slaytlarındaki Ağaç Haritası Grafiği İçin Tam Kaynak Kodu
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//şube 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//şube 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));
	series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);
	pres.save("Treemap.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides for Java kütüphanesini kullanarak PowerPoint sunumunda Ağaç Haritası grafiğinin nasıl oluşturulacağını öğrendiniz. Ağaç Haritası grafikleri hiyerarşik verileri görselleştirmek ve sunumlarınızı daha bilgilendirici ve ilgi çekici hale getirmek için değerli bir araçtır.

## SSS'ler

### Ağaç Haritası grafiğine nasıl veri eklerim?

 Ağaç Haritası grafiğine veri eklemek için`series.getDataPoints().addDataPointForTreemapSeries()` Veri değerlerini parametre olarak geçirme yöntemi.

### Ağaç Haritası grafiğinin görünümünü nasıl özelleştirebilirim?

 Ağaç Haritası grafiğinin çeşitli özelliklerini değiştirerek görünümünü özelleştirebilirsiniz.`chart` Ve`series`renkler, etiketler ve düzenler gibi nesneler.

### Tek bir sunumda birden fazla Ağaç Haritası grafiği oluşturabilir miyim?

Evet, aynı adımları izleyerek ve farklı slayt konumları belirterek tek bir sunumda birden fazla Ağaç Haritası grafiği oluşturabilirsiniz.

### Sunuyu Ağaç Haritası grafiğiyle nasıl kaydederim?

 Kullan`pres.save()` Sunumu Ağaç Haritası grafiğiyle istenen formatta (örneğin, PPTX) kaydetme yöntemini kullanın.