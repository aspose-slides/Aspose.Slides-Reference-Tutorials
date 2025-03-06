---
title: Java Slaytlarında Otomatik Pasta Grafiği Dilim Renklerini Ayarlama
linktitle: Java Slaytlarında Otomatik Pasta Grafiği Dilim Renklerini Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak Java PowerPoint sunumlarında otomatik dilim renkleriyle dinamik pasta grafiklerinin nasıl oluşturulacağını öğrenin. Kaynak koduyla adım adım kılavuz.
weight: 24
url: /tr/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Otomatik Pasta Grafiği Dilim Renklerini Ayarlama


## Java Slaytlarında Otomatik Pasta Grafiği Dilim Renklerini Ayarlamaya Giriş

Bu derste, Aspose.Slides for Java kullanarak bir PowerPoint sunumunda pasta grafiğinin nasıl oluşturulacağını ve grafik için otomatik dilim renklerinin nasıl ayarlanacağını keşfedeceğiz. Kaynak koduyla birlikte adım adım rehberlik sağlayacağız.

## Önkoşullar

 Başlamadan önce Java projenizde Aspose.Slides for Java kitaplığının kurulu olduğundan ve kurulduğundan emin olun. Kütüphaneyi Aspose web sitesinden indirebilirsiniz:[Java için Aspose.Slides'ı indirin](https://releases.aspose.com/slides/java/).

## Adım 1: Gerekli Paketleri İçe Aktarın

Öncelikle gerekli paketleri Aspose.Slides for Java'dan içe aktarmanız gerekir:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## 2. Adım: PowerPoint Sunusu Oluşturun

 Örnekleyin`Presentation` yeni bir PowerPoint sunusu oluşturmak için sınıf:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 3. Adım: Slayt Ekleme

Sununun ilk slaydına erişin ve buna varsayılan verileri içeren bir grafik ekleyin:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Adım 4: Grafik Başlığını Ayarlayın

Grafik için bir başlık belirleyin:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Adım 5: Grafik Verilerini Yapılandırın

Grafiği, ilk serinin değerlerini gösterecek şekilde ayarlayın ve grafik verilerini yapılandırın:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Adım 6: Kategoriler ve Seriler Ekleme

Grafiğe yeni kategoriler ve seriler ekleyin:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Adım 7: Seri Verilerini Doldurun

Pasta grafiği için seri verilerini doldurun:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Adım 8: Çeşitli Dilim Renklerini Etkinleştirin

Pasta grafiği için çeşitli dilim renklerini etkinleştirin:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Adım 9: Sunuyu Kaydetme

Son olarak sunuyu bir PowerPoint dosyasına kaydedin:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Otomatik Pasta Grafiği Dilim Renklerini Ayarlamak İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// PPTX dosyasını temsil eden Sunum sınıfını somutlaştırın
Presentation presentation = new Presentation();
try
{
	// İlk slayda erişin
	ISlide slides = presentation.getSlides().get_Item(0);
	// Varsayılan verilerle grafik ekle
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Grafik başlığını ayarlama
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// İlk seriyi Değerleri Göster olarak ayarla
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Grafik veri sayfasının indeksini ayarlama
	int defaultWorksheetIndex = 0;
	// Grafik verileri çalışma sayfasını alma
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Varsayılan oluşturulan serileri ve kategorileri silin
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Yeni kategoriler ekleme
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Yeni seriler ekleniyor
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Şimdi seri verileri dolduruluyor
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Aspose.Slides for Java'yı kullanarak bir PowerPoint sunumunda başarılı bir şekilde pasta grafiği oluşturdunuz ve bunu otomatik dilim renklerine sahip olacak şekilde yapılandırdınız. Bu adım adım kılavuz, bunu başarmanız için size gerekli kaynak kodunu sağlar. Grafiği ve sunumu gerektiği gibi daha da özelleştirebilirsiniz.

## SSS'ler

### Pasta grafiğindeki tek tek dilimlerin renklerini nasıl özelleştirebilirim?

 Pasta grafiğindeki tek tek dilimlerin renklerini özelleştirmek için`getAutomaticSeriesColors` Varsayılan renk şemasını alma ve ardından renkleri gerektiği gibi değiştirme yöntemini kullanın. İşte bir örnek:

```java
//Varsayılan renk şemasını alın
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Renkleri gerektiği gibi değiştirin
colors.get_Item(0).setColor(Color.RED); // İlk dilimin rengini kırmızı olarak ayarlayın
colors.get_Item(1).setColor(Color.BLUE); // İkinci dilimin rengini mavi olarak ayarlayın
// Gerektiğinde daha fazla renk değişikliği ekleyin
```

### Pasta grafiğine nasıl gösterge ekleyebilirim?

 Pasta grafiğine bir açıklama eklemek için şunu kullanabilirsiniz:`getLegend` yöntemini seçin ve aşağıdaki gibi yapılandırın:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Gösterge konumunu ayarlayın
legend.setOverlay(true); // Göstergeyi grafiğin üzerinde görüntüleyin
```

### Başlık yazı tipini ve stilini değiştirebilir miyim?

Evet, başlık yazı tipini ve stilini değiştirebilirsiniz. Başlık yazı tipini ve stilini ayarlamak için aşağıdaki kodu kullanın:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Yazı tipi boyutunu ayarla
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Başlığı kalın yapın
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Başlığı italik yapın
```

Yazı tipi boyutunu, kalınlığını ve italik stilini gerektiği gibi ayarlayabilirsiniz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
