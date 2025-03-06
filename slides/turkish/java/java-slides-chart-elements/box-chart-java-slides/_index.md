---
title: Java Slaytlarındaki Kutu Grafiği
linktitle: Java Slaytlarındaki Kutu Grafiği
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java sunumlarında Kutu Grafikleri oluşturmayı öğrenin. Etkili veri görselleştirmesi için adım adım kılavuz ve kaynak kodu dahildir.
weight: 10
url: /tr/java/chart-elements/box-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarındaki Kutu Grafiği


## Aspose.Slides for Java'da Kutu Grafiğine Giriş

Bu eğitimde Aspose.Slides for Java'yı kullanarak Kutu Grafiği oluşturma sürecinde size yol göstereceğiz. Kutu grafikleri, çeşitli çeyreklere ve aykırı değerlere sahip istatistiksel verileri görselleştirmek için kullanışlıdır. Başlamanıza yardımcı olmak için kaynak koduyla birlikte adım adım talimatlar sağlayacağız.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.Slides for Java kütüphanesi yüklendi ve yapılandırıldı.
- Bir Java geliştirme ortamı kuruldu.

## Adım 1: Sunumu Başlatın

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Bu adımda, mevcut bir PowerPoint dosyasının yolunu (bu örnekte "test.pptx") kullanarak bir sunum nesnesini başlatıyoruz.

## Adım 2: Kutu Grafiği Oluşturun

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Bu adımda sunumun ilk slaytında Kutu Grafiği şekli oluşturuyoruz. Ayrıca mevcut kategorileri ve serileri de grafikten temizliyoruz.

## 3. Adım: Kategorileri Tanımlayın

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

 Bu adımda Kutu Grafiği için kategorileri tanımlıyoruz. biz kullanıyoruz`IChartDataWorkbook` Kategoriler eklemek ve bunları buna göre etiketlemek için.

## Adım 4: Seriyi Oluşturun

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Burada grafik için bir BoxAndWhisker serisi oluşturuyoruz ve çeyrek yöntemi, ortalama çizgi, ortalama işaretleyiciler, iç noktalar ve aykırı noktalar gibi çeşitli seçenekleri yapılandırıyoruz.

## 5. Adım: Veri Noktalarını Ekleyin

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

Bu adımda BoxAndWhisker serisine veri noktaları ekliyoruz. Bu veri noktaları grafiğin istatistiksel verilerini temsil eder.

## Adım 6: Sunuyu Kaydetme

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Son olarak Kutu Grafiğinin bulunduğu sunumu "BoxAndWhisker.pptx" isimli yeni bir PowerPoint dosyasına kaydediyoruz.

Tebrikler! Aspose.Slides for Java'yı kullanarak başarıyla bir Kutu Grafiği oluşturdunuz. Çeşitli özellikleri ayarlayarak ve gerektiğinde daha fazla veri noktası ekleyerek grafiği daha da özelleştirebilirsiniz.

## Java Slaytlarındaki Kutu Grafiği İçin Kaynak Kodunu Tamamlayın

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

Bu eğitimde Aspose.Slides for Java'yı kullanarak Kutu Grafiğinin nasıl oluşturulacağını öğrendik. Kutu Grafikleri, çeyrekler ve aykırı değerler de dahil olmak üzere istatistiksel verileri görselleştirmek için değerli araçlardır. Java uygulamalarınızda Kutu Grafikleri oluşturmaya başlamanıza yardımcı olmak için kaynak koduyla birlikte adım adım bir kılavuz sağladık.

## SSS'ler

### Kutu Grafiğinin görünümünü nasıl değiştirebilirim?

Çizgi stilleri, renkler ve yazı tipleri gibi özellikleri değiştirerek Kutu Grafiğinin görünümünü özelleştirebilirsiniz. Grafik özelleştirmeyle ilgili ayrıntılar için Aspose.Slides for Java belgelerine bakın.

### Kutu Grafiğine ek veri serileri ekleyebilir miyim?

 Evet, ek veriler oluşturarak Kutu Grafiğine birden fazla veri serisi ekleyebilirsiniz.`IChartSeries` nesneler ve bunlara veri noktaları ekleme.

### QuartileMethodType.Exclusive ne anlama geliyor?

`QuartileMethodType.Exclusive` ayarı, çeyrek hesaplamalarının özel yöntem kullanılarak yapılması gerektiğini belirtir. Verilerinize ve gereksinimlerinize bağlı olarak farklı çeyrek hesaplama yöntemlerini seçebilirsiniz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
