---
"description": "Aspose.Slides for Java API'sini kullanarak Java PowerPoint sunumlarında Radar Grafiklerinin nasıl oluşturulacağını öğrenin."
"linktitle": "Java Slaytlarında Radar Grafiği Oluşturma"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Radar Grafiği Oluşturma"
"url": "/tr/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Radar Grafiği Oluşturma


## Java Slaytlarında Radar Grafiği Oluşturmaya Giriş

Bu eğitimde, Aspose.Slides for Java API'sini kullanarak bir Radar Grafiği oluşturma sürecinde size rehberlik edeceğiz. Radar grafikleri, verileri dairesel bir desende görselleştirmek için kullanışlıdır ve birden fazla veri serisini karşılaştırmayı kolaylaştırır. Java kaynak koduyla birlikte adım adım talimatlar sağlayacağız.

## Ön koşullar

Başlamadan önce, projenize Aspose.Slides for Java kütüphanesinin entegre olduğundan emin olun. Kütüphaneyi şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Sunumu Ayarlama

Yeni bir PowerPoint sunumu hazırlayıp, ona bir slayt ekleyerek başlayalım.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Adım 2: Radar Grafiği Ekleme

Daha sonra slayda bir radar grafiği ekleyeceğiz. Grafiğin konumunu ve boyutlarını belirteceğiz.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Adım 3: Grafik Verilerini Ayarlama

Şimdi grafik verilerini ayarlayacağız. Bu, bir veri çalışma kitabı oluşturmayı, kategoriler eklemeyi ve seriler eklemeyi içerir.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Grafik başlığını ayarla
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Varsayılan olarak oluşturulan serileri ve kategorileri sil
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Yeni kategoriler ekleniyor
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Yeni seri ekleniyor
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Adım 4: Seri Verilerini Doldurma

Şimdi radar grafiğimiz için seri verilerini dolduracağız.

```java
// Seri 1 için seri verilerini doldurun
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Seri rengini ayarla
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Seri 2 için seri verilerini doldurun
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Seri rengini ayarla
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Adım 5: Eksen ve Efsaneleri Özelleştirme

Radar grafiğimizin eksenlerini ve göstergelerini özelleştirelim.

```java
// Efsane konumunu ayarla
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Kategori Eksen Metin Özelliklerini Ayarlama
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Efsanelerin Metin Özelliklerini Ayarlama
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Değer Eksen Metin Özelliklerini Ayarlama
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Değer ekseni sayı biçimini ayarlama
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Grafik ana birim değerini ayarlama
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Adım 6: Sunumu Kaydetme

Son olarak, oluşturulan sunumu radar grafiğiyle kaydedin

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

İşte bu kadar! Aspose.Slides for Java kullanarak bir PowerPoint sunumunda bir radar grafiğini başarıyla oluşturdunuz. Şimdi bu örneği özel ihtiyaçlarınıza uyacak şekilde daha da özelleştirebilirsiniz.

## Java Slaytlarında Radar Grafiği Oluşturmak İçin Tam Kaynak Kodu

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// İlk slayda erişin
	ISlide sld = pres.getSlides().get_Item(0);
	// Radar grafiği ekle
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Grafik veri sayfasının indeksini ayarlama
	int defaultWorksheetIndex = 0;
	// Grafik verilerini alma Çalışma Sayfası
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Grafik başlığını ayarla
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Varsayılan olarak oluşturulan serileri ve kategorileri sil
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Yeni kategoriler ekleniyor
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Yeni seri ekleniyor
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Şimdi seri verileri dolduruluyor
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Seri rengini ayarla
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Şimdi başka bir seri verisi dolduruluyor
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Seri rengini ayarla
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Efsane konumunu ayarla
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Kategori Eksen Metin Özelliklerini Ayarlama
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Efsanelerin Metin Özelliklerini Ayarlama
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Değer Eksen Metin Özelliklerini Ayarlama
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Değer ekseni sayı biçimini ayarlama
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Grafik ana birim değerini ayarlama
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Oluşturulan sunumu kaydet
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumunda bir radar grafiğinin nasıl oluşturulacağını öğrendiniz. Bu kavramları, verilerinizi Java uygulamalarınızda etkili bir şekilde görselleştirmek ve sunmak için uygulayabilirsiniz.

## SSS

### Grafik başlığını nasıl değiştirebilirim?

Grafik başlığını değiştirmek için aşağıdaki satırı değiştirin:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Radar grafiğine daha fazla veri serisi ekleyebilir miyim?

Evet, dahil etmek istediğiniz her ek seri için "Adım 3" ve "Adım 4"teki adımları izleyerek daha fazla veri serisi ekleyebilirsiniz.

### Grafik renklerini nasıl özelleştirebilirim?

Seri renklerini, çizgileri ayarlayan çizgileri değiştirerek özelleştirebilirsiniz. `SolidFillColor` her seri için özellik. Örneğin:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Eksen etiketlerini ve biçimlendirmesini nasıl değiştirebilirim?

Yazı tipi boyutu ve rengi dahil olmak üzere eksen etiketlerini ve biçimlendirmesini özelleştirmek için "Adım 5"e bakın.

### Tabloyu farklı bir dosya biçiminde nasıl kaydedebilirim?

Dosya uzantısını değiştirerek çıktı biçimini değiştirebilirsiniz. `outPath` değişken ve uygun olanı kullanarak `SaveFormat`Örneğin, PDF olarak kaydetmek için şunu kullanın: `SaveFormat.Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}