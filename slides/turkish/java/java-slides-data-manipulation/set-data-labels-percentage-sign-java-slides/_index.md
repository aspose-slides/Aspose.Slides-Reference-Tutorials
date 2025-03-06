---
title: Veri Etiketlerini Ayarlama Yüzdesi Java Slaytlarında Oturum Açma
linktitle: Veri Etiketlerini Ayarlama Yüzdesi Java Slaytlarında Oturum Açma
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak PowerPoint sunumlarında yüzde işaretleriyle veri etiketlerini nasıl ayarlayacağınızı öğrenin. Adım adım rehberlik ve kaynak koduyla ilgi çekici grafikler oluşturun.
type: docs
weight: 17
url: /tr/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## Veri Etiketlerini Ayarlama Yüzdesine Giriş Aspose.Slides for Java'da Oturum Açın

Bu kılavuzda, Aspose.Slides for Java'yı kullanarak veri etiketlerini yüzde işaretiyle ayarlama sürecinde size yol göstereceğiz. Yığılmış sütun grafiğiyle bir PowerPoint sunumu oluşturacağız ve veri etiketlerini yüzdeleri gösterecek şekilde yapılandıracağız.

## Önkoşullar

 Başlamadan önce Aspose.Slides for Java kütüphanesinin projenize eklendiğinden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## 1. Adım: Yeni Bir Sunu Oluşturun

Öncelikle Aspose.Slides'ı kullanarak yeni bir PowerPoint sunumu oluşturuyoruz.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum sınıfının bir örneğini oluşturun
Presentation presentation = new Presentation();
```

## 2. Adım: Slayt ve Grafik Ekleme

Daha sonra sunuma bir slayt ve yığılmış sütun grafiği ekliyoruz.

```java
// Slaytın referansını alın
ISlide slide = presentation.getSlides().get_Item(0);

// Slayta YüzdelerYığın Sütun grafiği ekleme
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## 3. Adım: Eksen Numarası Formatını Yapılandırın

Yüzdeleri görüntülemek için grafiğin dikey eksenine ilişkin sayı biçimini yapılandırmamız gerekir.

```java
// NumberFormatLinkedToSource'u false olarak ayarlayın
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Adım 4: Grafik Verilerini Ekleyin

Seriler ve veri noktaları oluşturarak grafiğe veri ekliyoruz. Bu örnekte, ilgili veri noktalarıyla birlikte iki seri ekliyoruz.

```java
// Grafik verileri çalışma sayfasını alma
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

## 5. Adım: Veri Etiketlerini Özelleştirin

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

## Adım 6: Sunuyu Kaydetme

Son olarak sunumu PowerPoint dosyasına kaydediyoruz.

```java
// Sunumu diske yaz
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Bu kadar! Aspose.Slides for Java'yı kullanarak, yığılmış sütun grafiği ve veri etiketlerini yüzdeleri gösterecek şekilde yapılandırdığınız bir PowerPoint sunumunu başarıyla oluşturdunuz.

## Java Slaytlarında Veri Etiketlerini Ayarlama Yüzdesi Oturum Açma İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum sınıfının bir örneğini oluşturun
Presentation presentation = new Presentation();
// Slaytın referansını alın
ISlide slide = presentation.getSlides().get_Item(0);
// Slayta YüzdelerYığın Sütun grafiği ekleme
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// NumberFormatLinkedToSource'u false olarak ayarlayın
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Grafik verileri çalışma sayfasını alma
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
// Dolgu türünü ve rengini ayarlama
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

Bu kılavuzu takip ederek, iş raporlarında, eğitim materyallerinde ve daha fazlasında bilgilerin etkili bir şekilde iletilmesinde özellikle yararlı olabilecek yüzdeye dayalı veri etiketleriyle ilgi çekici sunumların nasıl oluşturulacağını öğrendiniz.

## SSS'ler

### Grafik serisinin renklerini nasıl değiştirebilirim?

 Grafik serisinin dolgu rengini aşağıdaki düğmeyi kullanarak değiştirebilirsiniz:`setFill` örnekte gösterildiği gibi yöntem.

### Veri etiketlerinin yazı tipi boyutunu özelleştirebilir miyim?

Evet, veri etiketlerinin yazı tipi boyutunu ayarlayarak özelleştirebilirsiniz.`setFontHeight` özellik kodda gösterildiği gibidir.

### Grafiğe nasıl daha fazla seri ekleyebilirim?

 Kullanarak grafiğe ek seriler ekleyebilirsiniz.`add` konusundaki yöntem`IChartSeriesCollection` nesne.
