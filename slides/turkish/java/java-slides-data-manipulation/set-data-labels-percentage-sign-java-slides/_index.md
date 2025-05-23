---
"description": "Aspose.Slides for Java kullanarak PowerPoint sunumlarında yüzde işaretleriyle veri etiketlerinin nasıl ayarlanacağını öğrenin. Adım adım rehberlik ve kaynak koduyla ilgi çekici grafikler oluşturun."
"linktitle": "Veri Etiketlerini Ayarla Yüzde Oturum Açma Java Slaytları"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Veri Etiketlerini Ayarla Yüzde Oturum Açma Java Slaytları"
"url": "/tr/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Veri Etiketlerini Ayarla Yüzde Oturum Açma Java Slaytları


## Aspose.Slides for Java'da Veri Etiketlerini Ayarlama Yüzde İşaretine Giriş

Bu kılavuzda, Aspose.Slides for Java kullanarak yüzde işaretiyle veri etiketleri ayarlama sürecinde size yol göstereceğiz. Yığılmış sütun grafiği içeren bir PowerPoint sunumu oluşturacağız ve veri etiketlerini yüzdeleri gösterecek şekilde yapılandıracağız.

## Ön koşullar

Başlamadan önce, projenize Aspose.Slides for Java kütüphanesinin eklendiğinden emin olun. Bunu şuradan indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Yeni Bir Sunum Oluşturun

Öncelikle Aspose.Slides kullanarak yeni bir PowerPoint sunumu oluşturuyoruz.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir Presentation sınıfı örneği oluşturun
Presentation presentation = new Presentation();
```

## Adım 2: Slayt ve Grafik Ekleyin

Daha sonra sunumumuza bir slayt ve yığılmış sütun grafiği ekliyoruz.

```java
// Slaytın referansını alın
ISlide slide = presentation.getSlides().get_Item(0);

// Bir slaytta PercentsStackedColumn grafiği ekleyin
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Adım 3: Eksen Numarası Biçimini Yapılandırın

Yüzdeleri görüntülemek için, grafiğin dikey ekseni için sayı biçimini yapılandırmamız gerekir.

```java
// NumberFormatLinkedToSource'u false olarak ayarlayın
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Adım 4: Grafik Verilerini Ekleyin

Seriler ve veri noktaları oluşturarak grafiğe veri ekliyoruz. Bu örnekte, ilgili veri noktalarıyla iki seri ekliyoruz.

```java
// Grafik veri çalışma sayfasını alma
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Yeni seri ekle
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Yeni seri ekle
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Adım 5: Veri Etiketlerini Özelleştirin

Şimdi veri etiketlerinin görünümünü özelleştirelim.

```java
// LabelFormat özelliklerini ayarlama
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Adım 6: Sunumu Kaydedin

Son olarak sunumu bir PowerPoint dosyasına kaydediyoruz.

```java
// Sunumu diske yaz
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

İşte bu kadar! Aspose.Slides for Java kullanarak yığılmış sütun grafiği içeren bir PowerPoint sunumu oluşturdunuz ve veri etiketlerini yüzdeleri görüntüleyecek şekilde yapılandırdınız.

## Set Veri Etiketleri Yüzdesi İçin Tam Kaynak Kodu Java Slaytlarında Oturum Açın

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir Presentation sınıfı örneği oluşturun
Presentation presentation = new Presentation();
// Slaytın referansını alın
ISlide slide = presentation.getSlides().get_Item(0);
// Bir slaytta PercentsStackedColumn grafiği ekleyin
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// NumberFormatLinkedToSource'u false olarak ayarlayın
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Grafik veri çalışma sayfasını alma
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Yeni seri ekle
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Serinin dolgu rengini ayarlama
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// LabelFormat özelliklerini ayarlama
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Yeni seri ekle
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Dolgu türü ve rengini ayarlama
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Sunumu diske yaz
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu kılavuzu takip ederek, özellikle iş raporlarında, eğitim materyallerinde ve daha fazlasında bilgileri etkili bir şekilde iletmek için yararlı olabilecek, yüzdeye dayalı veri etiketleriyle ilgi çekici sunumlar oluşturmayı öğrendiniz.

## SSS

### Grafik serisinin renklerini nasıl değiştirebilirim?

Grafik serisinin dolgu rengini, şunu kullanarak değiştirebilirsiniz: `setFill` Örnekte gösterildiği gibi bir yöntem.

### Veri etiketlerinin yazı tipi boyutunu özelleştirebilir miyim?

Evet, veri etiketlerinin yazı tipi boyutunu, `setFontHeight` kodda gösterildiği gibi özellik.

### Grafiğe daha fazla seri nasıl ekleyebilirim?

Grafiğe ek seriler eklemek için şunu kullanabilirsiniz: `add` yöntem üzerinde `IChartSeriesCollection` nesne.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}