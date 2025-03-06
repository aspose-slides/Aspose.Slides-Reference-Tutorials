---
title: Java Slaytlarında Güneş Patlaması Grafiği
linktitle: Java Slaytlarında Güneş Patlaması Grafiği
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java Slaytlarında Çarpıcı Sunburst Grafikleri oluşturun. Adım Adım Grafik Oluşturmayı ve Veri İşlemeyi Öğrenin.
weight: 16
url: /tr/java/chart-elements/sunburst-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides ile Java Slaytlarında Sunburst Grafiğine Giriş

Bu eğitimde Aspose.Slides for Java API'sini kullanarak PowerPoint sunumunda Sunburst grafiğinin nasıl oluşturulacağını öğreneceksiniz. Sunburst grafiği, hiyerarşik verileri temsil etmek için kullanılan radyal bir grafiktir. Kaynak koduyla birlikte adım adım talimatlar sunacağız.

## Önkoşullar

 Başlamadan önce Java projenizde Aspose.Slides for Java kütüphanesinin kurulu ve yapılandırılmış olduğundan emin olun. Kütüphaneyi adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/java/).

## 1. Adım: Gerekli Kitaplıkları İçe Aktarın

Öncelikle Aspose.Slides ile çalışmak için gerekli kütüphaneleri içe aktarın ve Java uygulamanızda bir Sunburst grafiği oluşturun.

```java
import com.aspose.slides.*;
```

## Adım 2: Sunumu Başlatın

Bir PowerPoint sunumunu başlatın ve sunum dosyanızın kaydedileceği dizini belirtin.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Adım 3: Sunburst Grafiğini Oluşturun

Bir slaytta Sunburst grafiği oluşturun. Grafiğin konumunu (X, Y) ve boyutlarını (genişlik, yükseklik) belirliyoruz.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Adım 4: Grafik Verilerini Hazırlayın

Mevcut tüm kategorileri ve seri verilerini grafikten temizleyin ve grafik için bir veri çalışma kitabı oluşturun.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Adım 5: Grafik Hiyerarşisini Tanımlayın

Sunburst grafiğinin hiyerarşik yapısını tanımlayın. Dalları, gövdeleri ve yaprakları kategori olarak ekleyebilirsiniz.

```java
// Şube 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Şube 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Adım 6: Grafiğe Veri Ekleme

Sunburst grafik serisine veri noktaları ekleyin.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Adım 7: Sunuyu Kaydet

Son olarak sunburst grafiğiyle sunuyu kaydedin.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Java Slaytlarındaki Sunburst Grafiği İçin Tam Kaynak Kodu

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//şube 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//şube 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides for Java API'sini kullanarak PowerPoint sunumunda Sunburst grafiğinin nasıl oluşturulacağını öğrendiniz. Sunuyu nasıl başlatacağınızı, grafiği nasıl oluşturacağınızı, grafik hiyerarşisini nasıl tanımlayacağınızı, veri noktalarını nasıl ekleyeceğinizi ve sunumu nasıl kaydedeceğinizi gördünüz. Artık bu bilgiyi Java uygulamalarınızda etkileşimli ve bilgilendirici Sunburst grafikleri oluşturmak için kullanabilirsiniz.

## SSS'ler

### Sunburst grafiğinin görünümünü nasıl özelleştiririm?

Renkler, etiketler ve stiller gibi özellikleri değiştirerek Sunburst grafiğinin görünümünü özelleştirebilirsiniz. Ayrıntılı özelleştirme seçenekleri için Aspose.Slides belgelerine bakın.

### Grafiğe daha fazla veri noktası ekleyebilir miyim?

 Evet, kullanarak grafiğe daha fazla veri noktası ekleyebilirsiniz.`series.getDataPoints().addDataPointForSunburstSeries()` Eklemek istediğiniz her veri noktası için yöntem.

### Sunburst grafiğine nasıl araç ipuçları ekleyebilirim?

Sunburst grafiğine araç ipuçları eklemek için veri etiketi biçimini, grafik bölümlerinin üzerine geldiğinizde değerler veya açıklamalar gibi ek bilgileri görüntüleyecek şekilde ayarlayabilirsiniz.

### Köprülerle etkileşimli Sunburst grafikleri oluşturmak mümkün müdür?

Evet, belirli grafik öğelerine veya bölümlerine köprüler ekleyerek köprülerle etkileşimli Sunburst grafikleri oluşturabilirsiniz. Köprü eklemeyle ilgili ayrıntılar için Aspose.Slides belgelerine bakın.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
