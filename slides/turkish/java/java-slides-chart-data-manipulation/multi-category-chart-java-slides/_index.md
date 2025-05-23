---
"description": "Java için Aspose.Slides'ı kullanarak Java Slaytlarında Çok Kategorili Grafikler Oluşturun. Sunumlarda etkileyici veri görselleştirmesi için kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Çok Kategorili Tablo"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Çok Kategorili Tablo"
"url": "/tr/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Çok Kategorili Tablo


## Java Slaytlarında Aspose.Slides ile Çok Kategorili Tabloya Giriş

Bu eğitimde, Aspose.Slides for Java API'sini kullanarak Java slaytlarında çok kategorili bir grafik oluşturmayı öğreneceğiz. Bu kılavuz, birden fazla kategori ve seriye sahip kümelenmiş bir sütun grafiği oluşturmanıza yardımcı olmak için kaynak koduyla birlikte adım adım talimatlar sağlayacaktır.

## Ön koşullar
Başlamadan önce, Java geliştirme ortamınızda Aspose.Slides for Java kütüphanesinin yüklü ve ayarlanmış olduğundan emin olun.

## Adım 1: Ortamı Kurma
Öncelikle gerekli sınıfları içe aktaralım ve slaytlarla çalışmak için yeni bir Sunum nesnesi oluşturalım.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Adım 2: Slayt ve Grafik Ekleme
Daha sonra bir slayt oluşturun ve ona kümelenmiş sütun grafiği ekleyin.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Adım 3: Mevcut Verileri Temizleme
Grafikte mevcut olan tüm verileri temizleyin.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Adım 4: Veri Kategorilerini Ayarlama
Şimdi grafik için veri kategorileri ayarlayalım. Birden fazla kategori oluşturacağız ve bunları gruplayacağız.

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
Şimdi, veri noktalarıyla birlikte grafiğe bir seri ekleyelim.

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

İşte bu kadar! Aspose.Slides kullanarak bir Java slaydında çok kategorili bir grafik başarıyla oluşturdunuz. Bu grafiği özel gereksinimlerinize uyacak şekilde daha da özelleştirebilirsiniz.

## Java Slaytlarında Çok Kategorili Tablo İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
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
//            Seri Ekleme
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

Bu eğitimde, Java slaytlarında Aspose.Slides for Java API'sini kullanarak çok kategorili bir grafik oluşturmayı öğrendik. Birden fazla kategori ve seriye sahip kümelenmiş bir sütun grafiği oluşturmak için kaynak kodlu adım adım bir kılavuzdan geçtik.

## SSS

### Grafik görünümünü nasıl özelleştirebilirim?

Renkler, yazı tipleri ve stiller gibi özellikleri değiştirerek grafik görünümünü özelleştirebilirsiniz. Ayrıntılı özelleştirme seçenekleri için Aspose.Slides belgelerine bakın.

### Tabloya daha fazla seri ekleyebilir miyim?

Evet, 5. Adımda gösterilen benzer bir işlemi izleyerek grafiğe ek seriler ekleyebilirsiniz.

### Grafik türünü nasıl değiştirebilirim?

Grafik türünü değiştirmek için şunu değiştirin: `ChartType.ClusteredColumn` Adım 2'de grafik eklerken istenilen grafik türüyle.

### Tabloya nasıl başlık ekleyebilirim?

Grafiğe bir başlık eklemek için şunu kullanabilirsiniz: `ch.getChartTitle().getTextFrame().setText("Chart Title");` yöntem.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}