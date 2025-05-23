---
"description": "Java Slaytlarında grafik veri etiketlerinin gerçek konumunu Aspose.Slides for Java kullanarak nasıl alacağınızı öğrenin. Kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Grafik Veri Etiketinin Gerçek Konumunu Alın"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Grafik Veri Etiketinin Gerçek Konumunu Alın"
"url": "/tr/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Grafik Veri Etiketinin Gerçek Konumunu Alın


## Java Slaytlarında Grafik Veri Etiketinin Gerçek Konumunu Almaya Giriş

Bu eğitimde, Java için Aspose.Slides kullanarak grafik veri etiketlerinin gerçek konumunu nasıl alacağınızı öğreneceksiniz. Grafik içeren bir PowerPoint sunumu oluşturan, veri etiketlerini özelleştiren ve ardından bu veri etiketlerinin konumlarını temsil eden şekiller ekleyen bir Java programı oluşturacağız.

## Ön koşullar

Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun.

## Adım 1: Bir PowerPoint Sunumu Oluşturun

Öncelikle yeni bir PowerPoint sunumu oluşturalım ve ona bir grafik ekleyelim. Grafiğin veri etiketlerini eğitimin ilerleyen kısımlarında özelleştireceğiz.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Adım 2: Veri Etiketlerini Özelleştirin
Şimdi, grafik serileri için veri etiketlerini özelleştirelim. Konumlarını ayarlayıp değerleri göstereceğiz.

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

## Adım 3: Veri Etiketlerinin Gerçek Pozisyonunu Alın
Bu adımda, grafik serisinin veri noktaları arasında yineleme yapacağız ve 4'ten büyük bir değere sahip veri etiketlerinin gerçek konumunu alacağız. Daha sonra bu konumları temsil etmek için elipsler ekleyeceğiz.

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

## Adım 4: Sunumu Kaydedin
Son olarak oluşturulan sunumu bir dosyaya kaydedin.

```java
try {
    // ... (önceki kod)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Java Slaytlarında Grafik Veri Etiketinin Gerçek Konumunu Almak İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//Yapılacaklar
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

Bu eğitimde, Java Slaytlarında grafik veri etiketlerinin gerçek konumunu Aspose.Slides for Java kullanarak nasıl alacağınızı öğrendiniz. Artık bu bilgiyi, PowerPoint sunumlarınızı özelleştirilmiş veri etiketleri ve konumlarının görsel gösterimleriyle geliştirmek için kullanabilirsiniz.

## SSS

### Bir grafikteki veri etiketlerini nasıl özelleştirebilirim?

Bir grafikteki veri etiketlerini özelleştirmek için şunu kullanabilirsiniz: `setDefaultDataLabelFormat` grafik serisindeki yöntemi ve konum ve görünürlük gibi özellikleri ayarlayın. Örneğin:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Veri etiketi konumlarını temsil etmek için şekilleri nasıl ekleyebilirim?

Bir grafik serisinin veri noktaları arasında yineleme yapabilir ve `getActualX`, `getActualY`, `getActualWidth`, Ve `getActualHeight` veri etiketinin konumunu almak için yöntemler. Daha sonra, kullanarak şekiller ekleyebilirsiniz `addAutoShape` yöntem. İşte bir örnek:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Oluşturulan sunumu nasıl kaydedebilirim?

Oluşturulan sunuyu kullanarak kaydedebilirsiniz. `save` yöntem. İstenilen dosya yolunu ve `SaveFormat` parametre olarak. Örneğin:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}