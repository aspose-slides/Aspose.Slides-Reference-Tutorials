---
"description": "Java için Aspose.Slides'ı kullanarak Java Slaytlarına Donut Açıklamaları Eklemeyi Öğrenin. Gelişmiş sunumlar için kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Donut Açıklaması Ekleme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Donut Açıklaması Ekleme"
"url": "/tr/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Donut Açıklaması Ekleme


## Java Slaytlarında Aspose.Slides for Java Kullanarak Donut Açıklaması Eklemeye Giriş

Bu eğitimde, Java'da Aspose.Slides for Java kullanarak bir slayda Doughnut Çağrısı ekleme sürecini adım adım anlatacağız. Doughnut Çağrısı, bir Doughnut grafiğindeki belirli veri noktalarını vurgulamak için kullanılabilen bir grafik öğesidir. Size kolaylık sağlamak için adım adım talimatlar ve eksiksiz kaynak kodu sağlayacağız.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. Java Geliştirme Ortamı
2. Java kütüphanesi için Aspose.Slides
3. Eclipse veya IntelliJ IDEA gibi Entegre Geliştirme Ortamı (IDE)
4. Donut Açıklamasını eklemek istediğiniz bir PowerPoint sunumu

## Adım 1: Java Projenizi Kurun

1. Seçtiğiniz IDE'de yeni bir Java projesi oluşturun.
2. Aspose.Slides for Java kütüphanesini projenize bağımlılık olarak ekleyin.

## Adım 2: Sunumu Başlatın

Başlamak için bir PowerPoint sunumu başlatmanız ve Donut Çağrısını eklemek istediğiniz bir slayt oluşturmanız gerekir. Bunu başarmak için kod şudur:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Değiştirdiğinizden emin olun `"Your Document Directory"` PowerPoint sunum dosyanızın gerçek yolunu belirtin.

## Adım 3: Bir Çörek Grafiği Oluşturun

Sonra, slaytta bir Donut grafiği oluşturacaksınız. Grafiğin konumunu ve boyutunu ihtiyaçlarınıza göre özelleştirebilirsiniz. İşte bir Donut grafiği eklemek için kod:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Adım 4: Donut Grafiğini Özelleştirin

Şimdi, Donut grafiğini özelleştirme zamanı. Efsaneyi kaldırma, delik boyutunu yapılandırma ve ilk dilim açısını ayarlama gibi çeşitli özellikler ayarlayacağız. İşte kod:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Bu kod parçacığı Donut grafiğinin özelliklerini ayarlar. Değerleri özel ihtiyaçlarınızı karşılayacak şekilde ayarlayabilirsiniz.

## Adım 5: Halka Grafiğine Veri Ekleme

Şimdi, Donut grafiğine veri ekleyelim. Ayrıca veri noktalarının görünümünü özelleştireceğiz. Bunu başarmak için kod şu şekilde:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Veri noktası görünümünü burada özelleştirin
        i++;
    }
    categoryIndex++;
}
```

Bu kodda, Donut grafiğine kategoriler ve veri noktaları ekliyoruz. Veri noktalarının görünümünü gerektiği gibi daha da özelleştirebilirsiniz.

## Adım 6: Sunumu Kaydedin

Son olarak, Donut Çağrısını ekledikten sonra sunumunuzu kaydetmeyi unutmayın. Sunumu kaydetmek için kod şu şekilde:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Değiştirdiğinizden emin olun `"chart.pptx"` İstediğiniz dosya adıyla.

Tebrikler! Java için Aspose.Slides kullanarak bir Doughnut Çağrısını bir Java slaydına başarıyla eklediniz. Artık Doughnut grafiği ve Çağrı ile PowerPoint sunumunu oluşturmak için Java uygulamanızı çalıştırabilirsiniz.

## Java Slaytlarında Donut Çağrısı Eklemek İçin Tam Kaynak Kodu

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
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde, Java için Aspose.Slides kullanarak bir Java slaydına Donut Çağrısı ekleme sürecini ele aldık. Donut grafiği oluşturmayı, görünümünü özelleştirmeyi ve veri noktaları eklemeyi öğrendiniz. Bu güçlü kütüphaneyle sunumlarınızı daha da geliştirmekten ve daha fazla grafik seçeneğini keşfetmekten çekinmeyin.

## SSS

### Donut Açıklamasının görünümünü nasıl değiştirebilirim?

Grafikteki veri noktalarının özelliklerini değiştirerek Donut Çağrısının görünümünü özelleştirebilirsiniz. Sağlanan kodda, veri noktalarının dolgu rengini, çizgi rengini, yazı tipi stilini ve diğer özniteliklerini nasıl ayarlayacağınızı görebilirsiniz.

### Çörek grafiğine daha fazla veri noktası ekleyebilir miyim?

Evet, Donut grafiğine ihtiyaç duyduğunuz kadar veri noktası ekleyebilirsiniz. Kategorilerin ve veri noktalarının eklendiği koddaki döngüleri basitçe genişletin ve uygun verileri ve biçimlendirmeyi sağlayın.

### Slayttaki Halka grafiğinin konumunu ve boyutunu nasıl ayarlayabilirim?

Çörek grafiğinin konumunu ve boyutunu, parametreleri değiştirerek değiştirebilirsiniz. `addChart` yöntem. Bu yöntemdeki dört sayı, grafiğin sol üst köşesinin X ve Y koordinatlarına ve sırasıyla genişliğine ve yüksekliğine karşılık gelir.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}