---
"description": "Java Slaytlarında grafikleri Aspose.Slides for Java kullanarak nasıl özelleştireceğinizi öğrenin. İkinci çizim seçeneklerini keşfedin ve sunumlarınızı geliştirin."
"linktitle": "Java Slaytlarında Grafikler için İkinci Grafik Seçenekleri"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Grafikler için İkinci Grafik Seçenekleri"
"url": "/tr/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Grafikler için İkinci Grafik Seçenekleri


## Java Slaytlarında Grafikler için İkinci Grafik Seçeneklerine Giriş

Bu eğitimde, Java için Aspose.Slides kullanarak grafiklere ikinci çizim seçeneklerinin nasıl ekleneceğini inceleyeceğiz. İkinci çizim seçenekleri, özellikle Pasta veya Pasta grafikleri gibi senaryolarda grafiklerin görünümünü ve davranışını özelleştirmenize olanak tanır. Bunu başarmak için adım adım talimatlar ve kaynak kodu örnekleri sağlayacağız. 

## Ön koşullar
Başlamadan önce, Java projenizde Aspose.Slides for Java'nın yüklü ve ayarlanmış olduğundan emin olun.

## Adım 1: Bir Sunum Oluşturun
Yeni bir sunum oluşturarak başlayalım:

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir Presentation sınıfı örneği oluşturun
Presentation presentation = new Presentation();
```

## Adım 2: Bir Slayda Grafik Ekleme
Sonra, bir slayta bir grafik ekleyeceğiz. Bu örnekte, bir Pasta Pastası grafiği oluşturacağız:

```java
// Slayta grafik ekle
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Adım 3: Grafik Özelliklerini Özelleştirin
Şimdi, ikinci çizim seçenekleri de dahil olmak üzere grafik için farklı özellikler ayarlayalım:

```java
// İlk seri için veri etiketlerini göster
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// İkinci pastanın boyutunu (yüzde olarak) ayarlayın
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Pastayı yüzdeye göre böl
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Bölmenin konumunu ayarlayın
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Adım 4: Sunumu Kaydedin
Son olarak sunumu grafik ve ikinci çizim seçenekleriyle kaydedin:

```java
// Sunumu diske yaz
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## İkinci Plot Seçenekleri İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir Presentation sınıfı örneği oluşturun
Presentation presentation = new Presentation();
// Slayta grafik ekle
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Farklı özellikler ayarlayın
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Sunumu diske yaz
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde, Java Slides'da Aspose.Slides for Java kullanarak grafiklere ikinci çizim seçeneklerinin nasıl ekleneceğini öğrendik. Grafiklerinizin görünümünü ve işlevselliğini geliştirmek için çeşitli özellikleri özelleştirebilir, sunumlarınızı daha bilgilendirici ve görsel olarak çekici hale getirebilirsiniz.

## SSS

### Pasta Pasta grafiğinde ikinci pastanın boyutunu nasıl değiştirebilirim?

Pasta Pasta grafiğindeki ikinci pastanın boyutunu değiştirmek için şunu kullanın: `setSecondPieSize` Yukarıdaki kod örneğinde gösterildiği gibi yöntem. Boyutu yüzde olarak belirtmek için değeri ayarlayın.

### Ne yapar? `PieSplitBy` Pasta grafiğinde kontrol nedir?

The `PieSplitBy` özellik, pasta grafiğinin nasıl bölüneceğini kontrol eder. Bunu şu şekilde ayarlayabilirsiniz: `PieSplitType.ByPercentage` veya `PieSplitType.ByValue` Tabloyu sırasıyla yüzdeye göre veya belirli bir değere göre bölmek için.

### Pasta Pasta grafiğinde bölünmenin konumunu nasıl ayarlarım?

Pasta grafiğindeki bölünmenin konumunu, `setPieSplitPosition` yöntem. İstenilen pozisyonu belirtmek için değeri ayarlayın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}