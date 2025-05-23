---
"description": "Aspose.Slides for Java kullanarak PowerPoint sunumlarında Histogram Grafikleri oluşturmayı öğrenin. Veri görselleştirme için kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Histogram Grafiği"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Histogram Grafiği"
"url": "/tr/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Histogram Grafiği


## Aspose.Slides kullanarak Java Slaytlarında Histogram Grafiğine Giriş

Bu eğitimde, Aspose.Slides for Java API'sini kullanarak bir PowerPoint sunumunda Histogram Grafiği oluşturma sürecinde size rehberlik edeceğiz. Histogram Grafiği, verilerin sürekli bir aralıktaki dağılımını temsil etmek için kullanılır.

## Ön koşullar

Başlamadan önce, Aspose.Slides for Java kütüphanesinin yüklü olduğundan emin olun. Bunu şuradan indirebilirsiniz: [Aspose web sitesi](https://releases.aspose.com/slides/java/).

## Adım 1: Projenizi Başlatın

Bir Java projesi oluşturun ve Aspose.Slides kütüphanesini projenizin bağımlılıklarına ekleyin.

## Adım 2: Gerekli Kitaplıkları İçe Aktarın

```java
import com.aspose.slides.*;
```

## Adım 3: Mevcut Bir Sunumu Yükleyin

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Değiştirdiğinizden emin olun `"Your Document Directory"` PowerPoint belgenizin gerçek yolunu belirtin.

## Adım 4: Bir Histogram Grafiği Oluşturun

Şimdi sunumdaki bir slaytta Histogram Grafiği oluşturalım.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Seriye veri noktaları ekleyin
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Yatay eksen toplama türünü Otomatik olarak ayarlayın
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Sunumu kaydet
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Bu kodda, önce grafikten mevcut kategorileri ve serileri temizliyoruz. Ardından, seriye veri noktalarını şu şekilde ekliyoruz: `getDataPoints().addDataPointForHistogramSeries` yöntem. Son olarak yatay eksen toplama türünü Otomatik olarak ayarlıyoruz ve sunumu kaydediyoruz.

## Java Slaytlarında Histogram Grafiği İçin Tam Kaynak Kodu

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java API'sini kullanarak bir PowerPoint sunumunda Histogram Grafiğinin nasıl oluşturulacağını inceledik. Histogram Grafikleri, verilerin sürekli bir aralıktaki dağılımını görselleştirmek için değerli araçlardır ve özellikle istatistiksel veya analitik içerikle uğraşırken sunumlarınıza güçlü bir katkı sağlayabilirler.

## SSS

### Java için Aspose.Slides'ı nasıl yüklerim?

Aspose.Slides for Java kütüphanesini şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/). Web sitelerinde verilen kurulum talimatlarını izleyin.

### Histogram Grafiği ne için kullanılır?

Histogram Grafiği, verilerin sürekli bir aralıktaki dağılımını görselleştirmek için kullanılır. İstatistikte sıklıkla frekans dağılımlarını temsil etmek için kullanılır.

### Histogram Grafiğinin görünümünü özelleştirebilir miyim?

Evet, Aspose.Slides API'sini kullanarak grafiğin renkleri, etiketleri ve eksenleri dahil görünümünü özelleştirebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}