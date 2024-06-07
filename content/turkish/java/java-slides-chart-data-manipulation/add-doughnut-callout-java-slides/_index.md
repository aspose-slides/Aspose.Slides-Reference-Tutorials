---
title: Java Slaytlarına Donut Belirtme Çizgisi Ekleme
linktitle: Java Slaytlarına Donut Belirtme Çizgisi Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slaytlarına Donut Açıklamaları Eklemeyi öğrenin. Gelişmiş sunumlar için kaynak kodlu adım adım kılavuz.
type: docs
weight: 12
url: /tr/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

## Aspose.Slides for Java kullanarak Java Slaytlarına Donut Açıklamaları Eklemeye Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak Java'da bir slayda Donut Açıklamaları ekleme sürecinde size yol göstereceğiz. Halka Belirtme Çizgisi, Halka grafiğindeki belirli veri noktalarını vurgulamak için kullanılabilen bir grafik öğesidir. Size kolaylık sağlamak için adım adım talimatlar ve eksiksiz kaynak kodu sağlayacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. Java Geliştirme Ortamı
2. Aspose.Slides for Java kütüphanesi
3. Eclipse veya IntelliJ IDEA gibi Entegre Geliştirme Ortamı (IDE)
4. Donut Açıklamasını eklemek istediğiniz bir PowerPoint sunumu

## 1. Adım: Java Projenizi ayarlayın

1. Seçtiğiniz IDE'de yeni bir Java projesi oluşturun.
2. Aspose.Slides for Java kütüphanesini projenize bağımlılık olarak ekleyin.

## Adım 2: Sunumu Başlatın

Başlamak için bir PowerPoint sunumu başlatmanız ve Donut Açıklamasını eklemek istediğiniz yere bir slayt oluşturmanız gerekir. İşte bunu başarmak için kod:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 Değiştirdiğinizden emin olun`"Your Document Directory"` PowerPoint sunum dosyanızın gerçek yolunu belirtin.

## 3. Adım: Halka Grafiği Oluşturun

Daha sonra slaytta bir Halka grafiği oluşturacaksınız. Grafiğin konumunu ve boyutunu gereksinimlerinize göre özelleştirebilirsiniz. İşte Donut grafiği ekleme kodu:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Adım 4: Halka Tablosunu Özelleştirin

Şimdi Halka grafiğini özelleştirmenin zamanı geldi. Göstergeyi kaldırmak, delik boyutunu yapılandırmak ve ilk dilim açısını ayarlamak gibi çeşitli özellikleri ayarlayacağız. İşte kod:

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

Bu kod parçacığı, Halka grafiğinin özelliklerini ayarlar. Değerleri özel ihtiyaçlarınızı karşılayacak şekilde ayarlayabilirsiniz.

## Adım 5: Halka Grafiğine Veri Ekleme

Şimdi Donut grafiğine veri ekleyelim. Ayrıca veri noktalarının görünümünü de özelleştireceğiz. İşte bunu başarmak için kod:

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

Bu kodda Donut grafiğine kategoriler ve veri noktaları ekliyoruz. Gerektiğinde veri noktalarının görünümünü daha da özelleştirebilirsiniz.

## Adım 6: Sunuyu Kaydetme

Son olarak Donut Callout'u ekledikten sonra sunumunuzu kaydetmeyi unutmayın. Sunuyu kaydetme kodu:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 Değiştirdiğinizden emin olun`"chart.pptx"` İstediğiniz dosya adı ile.

Tebrikler! Aspose.Slides for Java'yı kullanarak Java slaydına başarıyla Donut Açıklamaları eklediniz. Artık Donut grafiği ve Belirtme çizgisiyle PowerPoint sunumu oluşturmak için Java uygulamanızı çalıştırabilirsiniz.

## Java Slaytlarına Donut Belirtme Çizgisi Eklemek İçin Kaynak Kodunu Tamamlayın

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

Bu eğitimde Aspose.Slides for Java'yı kullanarak bir Java slaytına Donut Callout ekleme işlemini ele aldık. Halka grafiği oluşturmayı, görünümünü özelleştirmeyi ve veri noktaları eklemeyi öğrendiniz. Bu güçlü kitaplıkla sunumlarınızı daha da geliştirmekten çekinmeyin ve daha fazla grafik seçeneğini keşfedin.

## SSS'ler

### Donut Açıklamalarının görünümünü nasıl değiştirebilirim?

Grafikteki veri noktalarının özelliklerini değiştirerek Halka Belirtinin görünümünü özelleştirebilirsiniz. Sağlanan kodda dolgu rengini, çizgi rengini, yazı tipi stilini ve veri noktalarının diğer niteliklerini nasıl ayarlayacağınızı görebilirsiniz.

### Donut grafiğine daha fazla veri noktası ekleyebilir miyim?

Evet, Donut grafiğine gerektiği kadar veri noktası ekleyebilirsiniz. Kategorilerin ve veri noktalarının eklendiği koddaki döngüleri genişletmeniz ve uygun verileri ve biçimlendirmeyi sağlamanız yeterlidir.

### Slayttaki Halka grafiğinin konumunu ve boyutunu nasıl ayarlayabilirim?

Aşağıdaki parametreleri değiştirerek Halka grafiğinin konumunu ve boyutunu değiştirebilirsiniz.`addChart` yöntem. Bu yöntemdeki dört sayı, sırasıyla grafiğin sol üst köşesinin X ve Y koordinatlarına ve genişliğine ve yüksekliğine karşılık gelir.