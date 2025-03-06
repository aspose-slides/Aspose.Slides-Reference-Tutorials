---
title: Java Slaytlarında Veri Etiketi Bilgisini Ayarlama
linktitle: Java Slaytlarında Veri Etiketi Bilgisini Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'da Veri Etiketleri için Bilgilerin Nasıl Ayarlanacağını Öğrenin. Kaynak koduyla adım adım kılavuz.
weight: 25
url: /tr/java/data-manipulation/setting-callout-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Veri Etiketi Bilgisini Ayarlama


## Aspose.Slides for Java'da Veri Etiketi Bilgilerini Ayarlamaya Giriş

Bu eğitimde Aspose.Slides for Java kullanarak bir grafikteki veri etiketleri için açıklamaların nasıl ayarlanacağını göstereceğiz. Açıklamalar, grafiğinizdeki belirli veri noktalarını vurgulamak için yararlı olabilir. Kodu adım adım inceleyeceğiz ve gerekli kaynak kodunu sağlayacağız.

## Önkoşullar

- Aspose.Slides for Java'nın kurulu olması gerekir.
- Bir Java projesi oluşturun ve Aspose.Slides kütüphanesini projenize ekleyin.

## 1. Adım: Bir Sunum Oluşturun ve Grafik Ekleyin

 Öncelikle bir sunum oluşturmamız ve slayta bir grafik eklememiz gerekiyor. Değiştirdiğinizden emin olun`"Your Document Directory"` belge dizininizin gerçek yolu ile.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Adım 2: Grafiği Yapılandırın

Daha sonra gösterge, seri ve kategoriler gibi özellikleri ayarlayarak grafiği yapılandıracağız.

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

## 3. Adım: Veri Etiketlerini Özelleştirin

Şimdi, son seriye ilişkin açıklamaların ayarlanması da dahil olmak üzere veri etiketlerini özelleştireceğiz.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Veri noktası formatını özelleştirme (Dolgu, Çizgi vb.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //Etiket biçimlendirmesini özelleştirin (Yazı Tipi, Dolgu vb.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Ek bilgileri etkinleştir
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## 4. Adım: Sunuyu Kaydetme

Son olarak, sunuyu yapılandırılan grafikle kaydedin.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Artık Aspose.Slides for Java'yı kullanarak bir grafikteki veri etiketleri için açıklamaları başarıyla ayarladınız. Kodu özel grafiğinize ve veri gereksinimlerinize göre özelleştirin.

## Java Slaytlarında Veri Etiketine Yönelik Belirtmeyi Ayarlamak İçin Tam Kaynak Kodu

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

Bu eğitimde Aspose.Slides for Java kullanarak bir grafikteki veri etiketleri için açıklamaların nasıl ayarlanacağını araştırdık. Açıklamalar, grafiklerinizde ve sunumlarınızda belirli veri noktalarını vurgulamak için değerli araçlardır. Bu özelleştirmeyi gerçekleştirmenize yardımcı olmak için kaynak koduyla birlikte adım adım bir kılavuz sağladık.

## SSS'ler

### Veri etiketlerinin görünümünü nasıl özelleştiririm?

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

### Veri etiketleri için belirtme çizgilerini nasıl etkinleştirebilir veya devre dışı bırakabilirim?

 Veri etiketleri için belirtme çizgilerini etkinleştirmek veya devre dışı bırakmak için`setShowLabelAsDataCallout` yöntem. Şuna ayarla:`true` belirtme çizgilerini etkinleştirmek ve`false`bunları devre dışı bırakmak için.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Ek bilgileri etkinleştir
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Ek bilgileri devre dışı bırak
```

### Veri etiketleri için öncü çizgileri özelleştirebilir miyim?

Evet, çizgi stili, renk ve genişlik gibi özellikleri kullanarak veri etiketleri için öncü çizgileri özelleştirebilirsiniz. Örneğin:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Lider çizgileri etkinleştir
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Bunlar Aspose.Slides for Java'daki veri etiketleri ve belirtme çizgileri için bazı yaygın özelleştirme seçenekleridir. Görünümü özel ihtiyaçlarınıza göre daha da özelleştirebilirsiniz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
