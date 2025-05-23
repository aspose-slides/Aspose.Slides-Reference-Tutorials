---
"description": "Java PowerPoint sunumlarında Aspose.Slides for Java kullanarak otomatik dilim renkleriyle dinamik pasta grafiklerinin nasıl oluşturulacağını öğrenin. Kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Otomatik Pasta Grafiği Dilim Renklerini Ayarlama"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Otomatik Pasta Grafiği Dilim Renklerini Ayarlama"
"url": "/tr/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Otomatik Pasta Grafiği Dilim Renklerini Ayarlama


## Java Slaytlarında Otomatik Pasta Grafiği Dilim Renklerini Ayarlamaya Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumunda pasta grafiğinin nasıl oluşturulacağını ve grafik için otomatik dilim renklerinin nasıl ayarlanacağını inceleyeceğiz. Kaynak koduyla birlikte adım adım rehberlik sağlayacağız.

## Ön koşullar

Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin yüklü ve ayarlanmış olduğundan emin olun. Kütüphaneyi Aspose web sitesinden indirebilirsiniz: [Java için Aspose.Slides'ı indirin](https://releases.aspose.com/slides/java/).

## Adım 1: Gerekli Paketleri İçe Aktarın

Öncelikle Aspose.Slides for Java'dan gerekli paketleri import etmeniz gerekiyor:

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

## Adım 2: Bir PowerPoint Sunumu Oluşturun

Örneklemi oluştur `Presentation` Yeni bir PowerPoint sunumu oluşturmak için sınıf:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Adım 3: Slayt Ekle

Sunumun ilk slaydına erişin ve varsayılan verilerle bir grafik ekleyin:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Adım 4: Grafik Başlığını Ayarlayın

Tabloya bir başlık belirleyin:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Adım 5: Grafik Verilerini Yapılandırın

Grafiği ilk seri için değerleri gösterecek şekilde ayarlayın ve grafik verilerini yapılandırın:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Adım 6: Kategoriler ve Seriler Ekleyin

Tabloya yeni kategoriler ve seriler ekleyin:

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

## Adım 8: Çeşitli Dilim Renklerini Etkinleştir

Pasta grafiği için çeşitli dilim renklerini etkinleştirin:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Adım 9: Sunumu Kaydedin

Son olarak sunumu bir PowerPoint dosyasına kaydedin:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Otomatik Pasta Grafiği Dilim Renklerini Ayarlamak İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// PPTX dosyasını temsil eden Sunum sınıfını örneklendirin
Presentation presentation = new Presentation();
try
{
	// İlk slayda erişin
	ISlide slides = presentation.getSlides().get_Item(0);
	// Varsayılan verilerle grafik ekle
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Ayar çizelgesi Başlığı
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// İlk seriyi Değerleri Göster olarak ayarlayın
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Grafik veri sayfasının indeksini ayarlama
	int defaultWorksheetIndex = 0;
	// Grafik veri çalışma sayfasını alma
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Varsayılan olarak oluşturulan serileri ve kategorileri sil
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Yeni kategoriler ekleniyor
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Yeni seri ekleniyor
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

Aspose.Slides for Java kullanarak bir PowerPoint sunumunda pasta grafiğini başarıyla oluşturdunuz ve otomatik dilim renklerine sahip olacak şekilde yapılandırdınız. Bu adım adım kılavuz, bunu başarmanız için gereken kaynak kodunu sağlar. Grafiği ve sunumu gerektiği gibi daha da özelleştirebilirsiniz.

## SSS

### Pasta grafiğindeki her bir diliminin rengini nasıl özelleştirebilirim?

Pasta grafiğindeki tek tek dilimlerin renklerini özelleştirmek için şunu kullanabilirsiniz: `getAutomaticSeriesColors` varsayılan renk şemasını almak ve ardından renkleri gerektiği gibi değiştirmek için yöntem. İşte bir örnek:

```java
// Varsayılan renk şemasını alın
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Renkleri gerektiği gibi değiştirin
colors.get_Item(0).setColor(Color.RED); // İlk dilimin rengini kırmızıya ayarlayın
colors.get_Item(1).setColor(Color.BLUE); // İkinci dilimin rengini maviye ayarlayın
// Gerektiğinde daha fazla renk değişikliği ekleyin
```

### Pasta grafiğine nasıl lehçe ekleyebilirim?

Pasta grafiğine bir gösterge eklemek için şunu kullanabilirsiniz: `getLegend` yöntemini kullanın ve aşağıdaki gibi yapılandırın:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Efsane konumunu ayarlayın
legend.setOverlay(true); // Efsaneyi grafik üzerinde göster
```

### Başlık yazı tipini ve stilini değiştirebilir miyim?

Evet, başlık yazı tipini ve stilini değiştirebilirsiniz. Başlık yazı tipini ve stilini ayarlamak için aşağıdaki kodu kullanın:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Yazı tipi boyutunu ayarla
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Başlığı kalın yapın
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Başlığı italik yap
```

İhtiyacınıza göre yazı tipi boyutunu, kalınlığını ve italik stilini ayarlayabilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}