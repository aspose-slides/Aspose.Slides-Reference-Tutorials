---
"description": "Aspose.Slides ile Java sunumlarında Kutu Grafikleri oluşturmayı öğrenin. Etkili veri görselleştirmesi için adım adım kılavuz ve kaynak kodu dahildir."
"linktitle": "Java Slaytlarında Kutu Grafiği"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Kutu Grafiği"
"url": "/tr/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Kutu Grafiği


## Java için Aspose.Slides'da Kutu Grafiğine Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir Kutu Grafiği oluşturma sürecinde size yol göstereceğiz. Kutu grafikleri, çeşitli çeyrekler ve aykırı değerler içeren istatistiksel verileri görselleştirmek için kullanışlıdır. Başlamanıza yardımcı olmak için kaynak koduyla birlikte adım adım talimatlar sağlayacağız.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Java kütüphanesi için Aspose.Slides kuruldu ve yapılandırıldı.
- Java geliştirme ortamı kuruldu.

## Adım 1: Sunumu Başlatın

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Bu adımda, mevcut bir PowerPoint dosyasının (bu örnekte "test.pptx") yolunu kullanarak bir sunum nesnesi başlatıyoruz.

## Adım 2: Kutu Grafiğini Oluşturun

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Bu adımda, sunumun ilk slaydında bir Kutu Tablosu şekli oluşturuyoruz. Ayrıca tablodan mevcut kategorileri ve serileri temizliyoruz.

## Adım 3: Kategorileri Tanımlayın

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

Bu adımda, Kutu Tablosu için kategorileri tanımlıyoruz. `IChartDataWorkbook` kategoriler eklemek ve bunları uygun şekilde etiketlemek.

## Adım 4: Seriyi Oluşturun

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Burada, grafik için bir BoxAndWhisker serisi oluşturuyoruz ve çeyreklik yöntemi, ortalama çizgisi, ortalama işaretleyicileri, iç noktalar ve aykırı değer noktaları gibi çeşitli seçenekleri yapılandırıyoruz.

## Adım 5: Veri Noktalarını Ekleyin

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

Bu adımda, BoxAndWhisker serisine veri noktaları ekliyoruz. Bu veri noktaları, grafik için istatistiksel verileri temsil eder.

## Adım 6: Sunumu Kaydedin

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Son olarak sunumu Kutu Grafiği ile birlikte "BoxAndWhisker.pptx" adlı yeni bir PowerPoint dosyasına kaydediyoruz.

Tebrikler! Java için Aspose.Slides kullanarak bir Kutu Grafiği başarıyla oluşturdunuz. Çeşitli özellikleri ayarlayarak ve ihtiyaç duyduğunuzda daha fazla veri noktası ekleyerek grafiği daha da özelleştirebilirsiniz.

## Java Slaytlarında Kutu Grafiği İçin Tam Kaynak Kodu

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Java için Aspose.Slides kullanarak bir Kutu Grafiği oluşturmayı öğrendik. Kutu Grafikleri, dörtlükler ve aykırı değerler dahil olmak üzere istatistiksel verileri görselleştirmek için değerli araçlardır. Java uygulamalarınızda Kutu Grafikleri oluşturmaya başlamanıza yardımcı olmak için kaynak koduyla birlikte adım adım bir kılavuz sağladık.

## SSS

### Kutu Grafiğinin görünümünü nasıl değiştirebilirim?

Çizgi stilleri, renkler ve yazı tipleri gibi özellikleri değiştirerek Kutu Grafiğinin görünümünü özelleştirebilirsiniz. Grafik özelleştirmeyle ilgili ayrıntılar için Aspose.Slides for Java belgelerine bakın.

### Kutu Grafiğine ek veri serileri ekleyebilir miyim?

Evet, ek veri serileri oluşturarak Kutu Grafiğine birden fazla veri serisi ekleyebilirsiniz. `IChartSeries` nesneleri ve onlara veri noktaları eklemeyi içerir.

### QuartileMethodType.Exclusive ne anlama geliyor?

The `QuartileMethodType.Exclusive` ayar, çeyrek hesaplamalarının münhasır yöntem kullanılarak yapılması gerektiğini belirtir. Verilerinize ve gereksinimlerinize bağlı olarak farklı çeyrek hesaplama yöntemleri seçebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}