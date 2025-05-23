---
"description": "Aspose.Slides for Java'da Veri Etiketleri için Çağrıların Nasıl Ayarlanacağını Öğrenin. Kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Veri Etiketi İçin Çağrı Ayarlama"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Veri Etiketi İçin Çağrı Ayarlama"
"url": "/tr/java/data-manipulation/setting-callout-data-label-java-slides/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Veri Etiketi İçin Çağrı Ayarlama


## Java için Aspose.Slides'ta Veri Etiketi için Çağrı Ayarlamaya Giriş

Bu eğitimde, Java için Aspose.Slides kullanarak bir grafikteki veri etiketleri için açıklamaların nasıl ayarlanacağını göstereceğiz. Açıklamalar, grafiğinizdeki belirli veri noktalarını vurgulamak için yararlı olabilir. Kodu adım adım ele alacağız ve gerekli kaynak kodunu sağlayacağız.

## Ön koşullar

- Java için Aspose.Slides'ın yüklü olması gerekir.
- Bir Java projesi oluşturun ve Aspose.Slides kütüphanesini projenize ekleyin.

## Adım 1: Bir Sunum Oluşturun ve Bir Grafik Ekleyin

Öncelikle bir sunum oluşturmamız ve bir slayta grafik eklememiz gerekiyor. Değiştirdiğinizden emin olun `"Your Document Directory"` belge dizininize giden gerçek yol ile.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Adım 2: Grafiği Yapılandırın

Daha sonra, açıklama, seri ve kategori gibi özellikleri ayarlayarak grafiği yapılandıracağız.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Seri ve kategorileri yapılandırın (Seri ve kategori sayısını ayarlayabilirsiniz)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Veri noktalarını buraya ekleyin
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Adım 3: Veri Etiketlerini Özelleştirin

Şimdi, son seri için açıklama metinlerini ayarlamak da dahil olmak üzere veri etiketlerini özelleştireceğiz.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Veri noktası biçimlendirmesini özelleştirin (Dolgu, Çizgi, vb.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        // Etiket biçimlendirmesini özelleştirin (Yazı Tipi, Dolgu, vb.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Çağrıları etkinleştir
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Adım 4: Sunumu Kaydedin

Son olarak sunumu yapılandırılmış grafikle kaydedin.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Artık, Java için Aspose.Slides'ı kullanarak bir grafikteki veri etiketleri için çağrıları başarıyla ayarladınız. Kodu, belirli grafik ve veri gereksinimlerinize göre özelleştirin.

## Java Slaytlarında Veri Etiketi İçin Çağrı Ayarlamaya Yönelik Tam Kaynak Kodu

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save("chart.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde, Java için Aspose.Slides kullanarak bir grafikteki veri etiketleri için açıklamaların nasıl ayarlanacağını inceledik. Açıklamalar, grafiklerinizde ve sunumlarınızda belirli veri noktalarını vurgulamak için değerli araçlardır. Bu özelleştirmeyi başarmanıza yardımcı olmak için kaynak koduyla birlikte adım adım bir kılavuz sağladık.

## SSS

### Veri etiketlerinin görünümünü nasıl özelleştirebilirim?

Veri etiketlerinin görünümünü özelleştirmek için yazı tipi, dolgu ve çizgi stilleri gibi özellikleri değiştirebilirsiniz. Örneğin:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### Veri etiketleri için açıklamaları nasıl etkinleştirebilir veya devre dışı bırakabilirim?

Veri etiketleri için çağrıları etkinleştirmek veya devre dışı bırakmak için şunu kullanın: `setShowLabelAsDataCallout` yöntem. Bunu şu şekilde ayarlayın `true` çağrıları etkinleştirmek ve `false` onları etkisiz hale getirmek için.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Çağrıları etkinleştir
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Çağrıları devre dışı bırak
```

### Veri etiketleri için lider çizgilerini özelleştirebilir miyim?

Evet, çizgi stili, renk ve genişlik gibi özellikleri kullanarak veri etiketleri için lider çizgilerini özelleştirebilirsiniz. Örneğin:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Lider çizgilerini etkinleştir
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Bunlar, Aspose.Slides for Java'daki veri etiketleri ve açıklamalar için bazı genel özelleştirme seçenekleridir. Görünümü özel ihtiyaçlarınıza göre daha da özelleştirebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}