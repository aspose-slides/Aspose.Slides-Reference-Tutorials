---
title: Java Slaytlarında Özellikler Grafiklerini Yönetme
linktitle: Java Slaytlarında Özellikler Grafiklerini Yönetme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile çarpıcı grafikler oluşturmayı ve Java slaytlarındaki özellikleri yönetmeyi öğrenin. Güçlü sunumlar için kaynak kodlu adım adım kılavuz.
weight: 13
url: /tr/java/data-manipulation/manage-properties-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Özellikler Grafiklerini Yönetme


## Aspose.Slides kullanarak Java Slaytlarında Özellikleri ve Grafikleri Yönetmeye Giriş

Bu eğitimde Aspose.Slides kullanarak Java slaytlarında özelliklerin nasıl yönetileceğini ve grafiklerin nasıl oluşturulacağını keşfedeceğiz. Aspose.Slides, PowerPoint sunumlarıyla çalışmak için güçlü bir Java API'sidir. Kaynak kodu örnekleri de dahil olmak üzere süreci adım adım inceleyeceğiz.

## Önkoşullar

Başlamadan önce projenizde Java için Aspose.Slides kütüphanesinin kurulu ve kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## Slayta Grafik Ekleme

Slayta grafik eklemek için şu adımları izleyin:

1. Gerekli sınıfları içe aktarın ve Sunum sınıfının bir örneğini oluşturun.

```java
// Sunum sınıfının bir örneğini oluşturun
Presentation presentation = new Presentation();
```

2. Grafiği eklemek istediğiniz slayda erişin. Bu örnekte ilk slayda erişiyoruz.

```java
// İlk slayda erişin
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Varsayılan verileri içeren bir grafik ekleyin. Bu durumda StackedColumn3D grafiği ekliyoruz.

```java
// Varsayılan verilerle grafik ekle
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Grafik Verilerini Ayarlama

Grafik verilerini ayarlamak için grafik verileri çalışma kitabı oluşturup seri ve kategori eklememiz gerekiyor. Bu adımları takip et:

4. Grafik veri sayfasının indeksini ayarlayın.

```java
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
```

5. Grafik verileri çalışma kitabını edinin.

```java
// Grafik verileri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Grafiğe seri ekleyin. Bu örnekte "Seri 1" ve "Seri 2" adında iki seri ekliyoruz.

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Grafiğe kategoriler ekleyin. Burada üç kategori ekliyoruz.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 3D Döndürme Özelliklerini Ayarlama

Şimdi grafiğin 3B döndürme özelliklerini ayarlayalım:

8. Doğru açılı eksenleri ayarlayın.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. X ve Y eksenleri için dönüş açılarını ayarlayın. Bu örnekte X'i 40 derece, Y'yi ise 270 derece döndürüyoruz.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Derinlik yüzdesini 150 olarak ayarlayın.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Seri Verilerini Doldurma

11. İkinci grafik serisini alın ve onu veri noktalarıyla doldurun.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Seri verilerini doldur
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Örtüşmeyi Ayarlama

12. Seriler için örtüşme değerini ayarlayın. Örneğin, çakışma olmaması için bunu 100'e ayarlayabilirsiniz.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Sunumu Kaydetme

Son olarak sunumu diske kaydedin.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Bu kadar! Java'da Aspose.Slides'ı kullanarak özel özelliklere sahip bir 3B yığın sütun grafiğini başarıyla oluşturdunuz.

## Java Slaytlarındaki Özellikler Grafiklerini Yönetmek İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum sınıfının bir örneğini oluşturun
Presentation presentation = new Presentation();
// İlk slayda erişin
ISlide slide = presentation.getSlides().get_Item(0);
// Varsayılan verilerle grafik ekle
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
// Grafik verileri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Seri ekle
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Kategori Ekle
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Rotation3D özelliklerini ayarlama
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// İkinci grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Şimdi seri verileri dolduruluyor
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// OverLap değerini ayarla
series.getParentSeriesGroup().setOverlap((byte) 100);
// Sunumu diske yaz
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde Aspose.Slides'ı kullanarak Java slaytlarında özellikleri yönetme ve grafikler oluşturma dünyasını derinlemesine inceledik. Aspose.Slides, geliştiricilerin PowerPoint sunumlarıyla verimli bir şekilde çalışmasını sağlayan güçlü bir Java API'sidir. Temel adımları ele aldık ve süreç boyunca size yol gösterecek kaynak kodu örnekleri sağladık.

## SSS'ler

### Grafik türünü nasıl değiştirebilirim?

 Grafik türünü değiştirerek değiştirebilirsiniz.`ChartType` Grafiği eklerken parametre. Mevcut grafik türleri için Aspose.Slides belgelerine bakın.

### Grafik renklerini özelleştirebilir miyim?

Evet, seri veri noktalarının veya kategorilerinin dolgu özelliklerini ayarlayarak grafik renklerini özelleştirebilirsiniz.

### Bir seriye nasıl daha fazla veri noktası eklerim?

 kullanarak bir seriye daha fazla veri noktası ekleyebilirsiniz.`series.getDataPoints().addDataPointForBarSeries()` yöntemi ve veri değerini içeren hücrenin belirtilmesi.

### Farklı bir dönüş açısını nasıl ayarlayabilirim?

 X ve Y eksenleri için farklı bir dönüş açısı ayarlamak için şunu kullanın:`chart.getRotation3D().setRotationX()` Ve`chart.getRotation3D().setRotationY()` İstenilen açı değerlerinde.

### Başka hangi 3B özelliklerini özelleştirebilirim?

Aspose.Slides belgelerine başvurarak grafiğin derinlik, perspektif ve aydınlatma gibi diğer 3B özelliklerini keşfedebilirsiniz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
