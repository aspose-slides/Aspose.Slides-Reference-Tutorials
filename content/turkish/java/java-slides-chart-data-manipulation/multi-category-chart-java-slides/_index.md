---
title: Java Slaytlarında Çok Kategorili Grafik
linktitle: Java Slaytlarında Çok Kategorili Grafik
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slaytlarında Çok Kategorili Grafikler oluşturun. Sunumlarda etkileyici veri görselleştirmesi için kaynak kodlu adım adım kılavuz.
type: docs
weight: 20
url: /tr/java/chart-data-manipulation/multi-category-chart-java-slides/
---

## Aspose.Slides ile Java Slaytlarında Çok Kategorili Grafiğe Giriş

Bu eğitimde Aspose.Slides for Java API'sini kullanarak Java slaytlarında çok kategorili bir grafiğin nasıl oluşturulacağını öğreneceğiz. Bu kılavuz, birden çok kategori ve seriden oluşan kümelenmiş bir sütun grafiği oluşturmanıza yardımcı olacak kaynak koduyla birlikte adım adım talimatlar sağlayacaktır.

## Önkoşullar
Başlamadan önce, Java geliştirme ortamınızda Aspose.Slides for Java kütüphanesinin kurulu olduğundan ve kurulduğundan emin olun.

## 1. Adım: Ortamı Ayarlama
Öncelikle gerekli sınıfları içe aktarın ve slaytlarla çalışmak için yeni bir Sunum nesnesi oluşturun.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Adım 2: Slayt ve Grafik Ekleme
Daha sonra bir slayt oluşturun ve buna kümelenmiş bir sütun grafiği ekleyin.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## 3. Adım: Mevcut Verileri Temizleme
Grafikteki mevcut verileri temizleyin.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Adım 4: Veri Kategorilerini Ayarlama
Şimdi grafik için veri kategorilerini ayarlayalım. Birden fazla kategori oluşturup bunları gruplandıracağız.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Kategoriler ekleyin ve gruplandırın
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Adım 5: Seri Ekleme
Şimdi grafiğe veri noktalarıyla birlikte bir seri ekleyelim.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Adım 6: Sunumu Kaydetme
Son olarak sunumu grafikle birlikte kaydedin.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Bu kadar! Aspose.Slides'ı kullanarak bir Java slaytında başarıyla çok kategorili bir grafik oluşturdunuz. Bu grafiği özel gereksinimlerinize uyacak şekilde daha da özelleştirebilirsiniz.

## Java Slaytlarında Çok Kategorili Grafik İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// Seri Ekleme
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Sunuyu grafikle kaydet
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde Aspose.Slides for Java API'sini kullanarak Java slaytlarında çok kategorili bir grafiğin nasıl oluşturulacağını öğrendik. Birden fazla kategori ve seriye sahip kümelenmiş bir sütun grafiği oluşturmak için kaynak kodlu adım adım kılavuzu inceledik.

## SSS'ler

### Grafiğin görünümünü nasıl özelleştirebilirim?

Renkler, yazı tipleri ve stiller gibi özellikleri değiştirerek grafiğin görünümünü özelleştirebilirsiniz. Ayrıntılı özelleştirme seçenekleri için Aspose.Slides belgelerine bakın.

### Grafiğe daha fazla seri ekleyebilir miyim?

Evet, 5. Adımda gösterilene benzer bir işlemi izleyerek grafiğe ek seriler ekleyebilirsiniz.

### Grafik türünü nasıl değiştiririm?

 Grafik türünü değiştirmek için değiştirin`ChartType.ClusteredColumn` 2. Adımda grafiği eklerken istediğiniz grafik türüyle.

### Grafiğe nasıl başlık ekleyebilirim?

 Kullanarak grafiğe bir başlık ekleyebilirsiniz.`ch.getChartTitle().getTextFrame().setText("Chart Title");` yöntem.