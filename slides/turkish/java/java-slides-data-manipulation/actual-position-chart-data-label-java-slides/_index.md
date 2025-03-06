---
title: Java Slaytlarında Grafik Veri Etiketinin Gerçek Konumunu Alın
linktitle: Java Slaytlarında Grafik Veri Etiketinin Gerçek Konumunu Alın
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slides'ta grafik veri etiketlerinin gerçek konumunu nasıl alacağınızı öğrenin. Kaynak koduyla adım adım kılavuz.
weight: 18
url: /tr/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java Slaytlarında Grafik Veri Etiketinin Gerçek Konumunu Almaya Giriş

Bu eğitimde Aspose.Slides for Java'yı kullanarak grafik veri etiketlerinin gerçek konumunu nasıl alacağınızı öğreneceksiniz. Grafik içeren bir PowerPoint sunumu oluşturan, veri etiketlerini özelleştiren ve ardından bu veri etiketlerinin konumlarını temsil eden şekiller ekleyen bir Java programı oluşturacağız.

## Önkoşullar

Başlamadan önce Java projenizde Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun.

## 1. Adım: PowerPoint Sunusu Oluşturun

Öncelikle yeni bir PowerPoint sunusu oluşturalım ve ona bir grafik ekleyelim. Grafiğin veri etiketlerini öğreticinin ilerleyen kısımlarında özelleştireceğiz.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## 2. Adım: Veri Etiketlerini Özelleştirin
Şimdi grafik serisi için veri etiketlerini özelleştirelim. Konumlarını belirleyip değerlerini göstereceğiz.

```java
try {
    // ... (önceki kod)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (kalan kod)
} finally {
    if (pres != null) pres.dispose();
}
```

## 3. Adım: Veri Etiketlerinin Gerçek Konumunu Alın
Bu adımda grafik serisinin veri noktalarını yineleyeceğiz ve değeri 4'ten büyük olan veri etiketlerinin gerçek konumunu alacağız. Daha sonra bu konumları temsil etmek için elipsler ekleyeceğiz.

```java
try {
    // ... (önceki kod)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (kalan kod)
} finally {
    if (pres != null) pres.dispose();
}
```

## 4. Adım: Sunuyu Kaydetme
Son olarak oluşturulan sunumu bir dosyaya kaydedin.

```java
try {
    // ... (önceki kod)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Java Slaytlarında Grafik Veri Etiketinin Gerçek Konumunu Almak için Kaynak Kodunu Tamamlayın

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//YAPMAK
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java'yı kullanarak Java Slides'daki grafik veri etiketlerinin gerçek konumunu nasıl alacağınızı öğrendiniz. Artık bu bilgiyi PowerPoint sunumlarınızı özelleştirilmiş veri etiketleri ve konumlarının görsel temsilleriyle geliştirmek için kullanabilirsiniz.

## SSS'ler

### Bir grafikteki veri etiketlerini nasıl özelleştirebilirim?

 Bir grafikteki veri etiketlerini özelleştirmek için`setDefaultDataLabelFormat` Grafik serisindeki yöntemi kullanın ve konum ve görünürlük gibi özellikleri ayarlayın. Örneğin:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Veri etiketi konumlarını temsil edecek şekilleri nasıl ekleyebilirim?

 Bir grafik serisinin veri noktalarını yineleyebilir ve`getActualX`, `getActualY`, `getActualWidth` , Ve`getActualHeight`Konumunu almak için veri etiketinin yöntemleri. Daha sonra, kullanarak şekiller ekleyebilirsiniz.`addAutoShape` yöntem. İşte bir örnek:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Oluşturulan sunumu nasıl kaydedebilirim?

 Oluşturulan sunumu kullanarak kaydedebilirsiniz.`save` yöntem. İstediğiniz dosya yolunu ve`SaveFormat` parametreler olarak. Örneğin:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
