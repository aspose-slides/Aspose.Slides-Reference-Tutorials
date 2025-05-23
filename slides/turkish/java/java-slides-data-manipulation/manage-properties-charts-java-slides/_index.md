---
"description": "Aspose.Slides ile Java slaytlarında çarpıcı grafikler oluşturmayı ve özellikleri yönetmeyi öğrenin. Güçlü sunumlar için kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Özellik Grafiklerini Yönetin"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Özellik Grafiklerini Yönetin"
"url": "/tr/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Özellik Grafiklerini Yönetin


## Aspose.Slides kullanarak Java Slaytlarında Özellikleri ve Grafikleri Yönetmeye Giriş

Bu eğitimde, Aspose.Slides kullanarak Java slaytlarında özelliklerin nasıl yönetileceğini ve grafiklerin nasıl oluşturulacağını inceleyeceğiz. Aspose.Slides, PowerPoint sunumlarıyla çalışmak için güçlü bir Java API'sidir. Kaynak kod örnekleri de dahil olmak üzere adım adım süreci ele alacağız.

## Ön koşullar

Başlamadan önce, projenizde Java için Aspose.Slides kütüphanesinin yüklü ve ayarlanmış olduğundan emin olun. Bunu şuradan indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

## Bir Slayda Grafik Ekleme

Bir slayda grafik eklemek için şu adımları izleyin:

1. Gerekli sınıfları içe aktarın ve Presentation sınıfının bir örneğini oluşturun.

```java
// Bir Presentation sınıfı örneği oluşturun
Presentation presentation = new Presentation();
```

2. Grafiği eklemek istediğiniz slayda erişin. Bu örnekte, ilk slayda erişiyoruz.

```java
// İlk slayda erişin
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Varsayılan verilerle bir grafik ekleyin. Bu durumda, bir StackedColumn3D grafiği ekliyoruz.

```java
// Varsayılan verilerle grafik ekle
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Grafik Verilerini Ayarlama

Grafik verilerini ayarlamak için bir grafik veri çalışma kitabı oluşturmamız ve seriler ve kategoriler eklememiz gerekir. Şu adımları izleyin:

4. Grafik veri sayfasının indeksini ayarlayın.

```java
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
```

5. Grafik veri çalışma kitabını alın.

```java
// Grafik veri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Grafiğe seri ekleyin. Bu örnekte, "Seri 1" ve "Seri 2" adlı iki seri ekliyoruz.

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Tabloya kategoriler ekleyin. Burada üç kategori ekliyoruz.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 3B Döndürme Özelliklerini Ayarlama

Şimdi grafik için 3D dönüş özelliklerini ayarlayalım:

8. Dik açı eksenlerini ayarlayın.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. X ve Y eksenleri için dönüş açılarını ayarlayın. Bu örnekte, X'i 40 derece ve Y'yi 270 derece döndürüyoruz.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Derinlik yüzdesini 150 olarak ayarlayın.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Seri Verilerinin Doldurulması

11. İkinci grafik serisini alın ve veri noktalarıyla doldurun.

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

## Çakışmayı Ayarlama

12. Seri için örtüşme değerini ayarlayın. Örneğin, örtüşme olmaması için 100 olarak ayarlayabilirsiniz.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Sunumu Kaydetme

Son olarak sunumu diske kaydedin.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

İşte bu kadar! Java'da Aspose.Slides kullanarak özel özelliklere sahip bir 3B yığılmış sütun grafiği başarıyla oluşturdunuz.

## Java Slaytlarında Özellikleri Yönetme Grafikleri İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir Presentation sınıfı örneği oluşturun
Presentation presentation = new Presentation();
// İlk slayda erişin
ISlide slide = presentation.getSlides().get_Item(0);
// Varsayılan verilerle grafik ekle
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
// Grafik veri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Seri ekle
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Kategori Ekle
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Rotation3D özelliklerini ayarlayın
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

Bu eğitimde, Aspose.Slides kullanarak Java slaytlarında özellikleri yönetme ve grafikler oluşturma dünyasına daldık. Aspose.Slides, geliştiricilerin PowerPoint sunumlarıyla verimli bir şekilde çalışmasını sağlayan sağlam bir Java API'sidir. Temel adımları ele aldık ve sizi süreçte yönlendirmek için kaynak kodu örnekleri sağladık.

## SSS

### Grafik türünü nasıl değiştirebilirim?

Grafik türünü değiştirerek değiştirebilirsiniz. `ChartType` Grafik eklerken parametre. Kullanılabilir grafik türleri için Aspose.Slides belgelerine bakın.

### Grafik renklerini özelleştirebilir miyim?

Evet, seri veri noktalarının veya kategorilerin dolgu özelliklerini ayarlayarak grafik renklerini özelleştirebilirsiniz.

### Bir seriye nasıl daha fazla veri noktası eklerim?

Bir seriye daha fazla veri noktası eklemek için şunu kullanabilirsiniz: `series.getDataPoints().addDataPointForBarSeries()` yöntemi ve veri değerini içeren hücreyi belirterek.

### Farklı bir dönüş açısı nasıl ayarlayabilirim?

X ve Y eksenleri için farklı bir dönüş açısı ayarlamak için şunu kullanın: `chart.getRotation3D().setRotationX()` Ve `chart.getRotation3D().setRotationY()` istenilen açı değerleri ile.

### Başka hangi 3B özelliklerini özelleştirebilirim?

Aspose.Slides belgelerine başvurarak grafiğin derinlik, perspektif ve aydınlatma gibi diğer 3B özelliklerini inceleyebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}