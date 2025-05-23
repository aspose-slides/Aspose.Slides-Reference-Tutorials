---
"description": "Java için Aspose.Slides kullanarak Java Slaytlarında Ağaç Haritası Grafikleri Oluşturun. Hiyerarşik verileri görselleştirmek için kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Ağaç Haritası Grafiği"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Ağaç Haritası Grafiği"
"url": "/tr/java/chart-creation/tree-map-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Ağaç Haritası Grafiği


## Java Slaytlarında Ağaç Harita Grafiğine Giriş

Bu eğitimde, Aspose.Slides for Java kütüphanesini kullanarak bir PowerPoint sunumunda Ağaç Haritası grafiğinin nasıl oluşturulacağını göstereceğiz. Ağaç Haritası grafikleri, hiyerarşik verileri görselleştirmenin etkili bir yoludur.

## Ön koşullar

Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun.

## Adım 1: Gerekli Kitaplıkları İçe Aktarın

```java
import com.aspose.slides.*;
```

## Adım 2: Sunumu Yükleyin

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Adım 3: Bir Ağaç Haritası Grafiği Oluşturun

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);

    // 1. dalı oluştur
    IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch1");

    chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

    // 2. dalı oluştur
    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem4");

    chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));

    // Veri noktaları ekle
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

    // Sunumu Ağaç Haritası çizelgesiyle kaydedin
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Java Slaytlarında Ağaç Harita Grafiği İçin Tam Kaynak Kodu
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

Bu eğitimde, Aspose.Slides for Java kütüphanesini kullanarak bir PowerPoint sunumunda Ağaç Haritası grafiğinin nasıl oluşturulacağını öğrendiniz. Ağaç Haritası grafikleri, hiyerarşik verileri görselleştirmek, sunumlarınızı daha bilgilendirici ve ilgi çekici hale getirmek için değerli bir araçtır.

## SSS

### Ağaç Haritası grafiğine nasıl veri eklerim?

Ağaç Haritası grafiğine veri eklemek için şunu kullanın: `series.getDataPoints().addDataPointForTreemapSeries()` yöntem, veri değerlerini parametre olarak geçirmektir.

### Ağaç Haritası grafiğinin görünümünü nasıl özelleştirebilirim?

Ağaç Haritası grafiğinin görünümünü, çeşitli özelliklerini değiştirerek özelleştirebilirsiniz. `chart` Ve `series` renkler, etiketler ve düzenler gibi nesneler.

### Tek bir sunumda birden fazla Ağaç Haritası grafiği oluşturabilir miyim?

Evet, aynı adımları izleyerek ve farklı slayt konumlarını belirleyerek tek bir sunumda birden fazla Ağaç Haritası grafiği oluşturabilirsiniz.

### Ağaç Haritası grafiğiyle sunumu nasıl kaydederim?

Kullanın `pres.save()` Ağaç Haritası grafiğini içeren sunumu istenilen formatta (örneğin PPTX) kaydetme yöntemi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}