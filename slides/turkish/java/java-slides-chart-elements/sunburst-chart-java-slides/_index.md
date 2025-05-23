---
"description": "Aspose.Slides ile Java Slaytlarında Çarpıcı Sunburst Grafikleri Oluşturun. Adım Adım Grafik Oluşturma ve Veri İşlemeyi Öğrenin."
"linktitle": "Java Slaytlarında Sunburst Grafiği"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Sunburst Grafiği"
"url": "/tr/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Sunburst Grafiği


## Java Slaytlarında Aspose.Slides ile Sunburst Grafiğine Giriş

Bu eğitimde, Aspose.Slides for Java API'sini kullanarak bir PowerPoint sunumunda Sunburst grafiğinin nasıl oluşturulacağını öğreneceksiniz. Sunburst grafiği, hiyerarşik verileri temsil etmek için kullanılan bir radyal grafiktir. Kaynak koduyla birlikte adım adım talimatlar sağlayacağız.

## Ön koşullar

Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin yüklü ve yapılandırılmış olduğundan emin olun. Kütüphaneyi şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Gerekli Kitaplıkları İçe Aktarın

Öncelikle Aspose.Slides ile çalışmak için gerekli kütüphaneleri içeri aktarın ve Java uygulamanızda bir Sunburst grafiği oluşturun.

```java
import com.aspose.slides.*;
```

## Adım 2: Sunumu Başlatın

Bir PowerPoint sunumu başlatın ve sunum dosyanızın kaydedileceği dizini belirtin.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Adım 3: Sunburst Grafiğini Oluşturun

Bir slaytta Sunburst grafiği oluşturun. Grafiğin konumunu (X, Y) ve boyutlarını (genişlik, yükseklik) belirtiyoruz.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Adım 4: Grafik Verilerini Hazırlayın

Grafikteki mevcut kategorileri ve seri verilerini temizleyin ve grafik için bir veri çalışma kitabı oluşturun.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Adım 5: Grafik Hiyerarşisini Tanımlayın

Sunburst grafiğinin hiyerarşik yapısını tanımlayın. Kategoriler olarak dallar, gövdeler ve yapraklar ekleyebilirsiniz.

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

## Adım 7: Sunumu Kaydedin

Son olarak sunuyu Sunburst grafiğiyle kaydedin.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Sunburst Grafiği İçin Tam Kaynak Kodu

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

Bu eğitimde, Aspose.Slides for Java API'sini kullanarak bir PowerPoint sunumunda Sunburst grafiğinin nasıl oluşturulacağını öğrendiniz. Sunumu nasıl başlatacağınızı, grafiği nasıl oluşturacağınızı, grafik hiyerarşisini nasıl tanımlayacağınızı, veri noktaları nasıl ekleyeceğinizi ve sunumu nasıl kaydedeceğinizi gördünüz. Artık bu bilgiyi kullanarak Java uygulamalarınızda etkileşimli ve bilgilendirici Sunburst grafikleri oluşturabilirsiniz.

## SSS

### Sunburst grafiğinin görünümünü nasıl özelleştirebilirim?

Renkler, etiketler ve stiller gibi özellikleri değiştirerek Sunburst grafiğinin görünümünü özelleştirebilirsiniz. Ayrıntılı özelleştirme seçenekleri için Aspose.Slides belgelerine bakın.

### Grafiğe daha fazla veri noktası ekleyebilir miyim?

Evet, grafiğe daha fazla veri noktası eklemek için şunu kullanabilirsiniz: `series.getDataPoints().addDataPointForSunburstSeries()` Dahil etmek istediğiniz her veri noktası için bir yöntem.

### Sunburst grafiğine araç ipuçlarını nasıl ekleyebilirim?

Sunburst grafiğine araç ipuçları eklemek için, grafik segmentlerinin üzerine gelindiğinde değerler veya açıklamalar gibi ek bilgilerin görüntülenmesini sağlayacak şekilde veri etiketi biçimini ayarlayabilirsiniz.

### Bağlantılı etkileşimli Sunburst grafikleri oluşturmak mümkün müdür?

Evet, belirli grafik öğelerine veya segmentlerine köprüler ekleyerek köprülerle etkileşimli Sunburst grafikleri oluşturabilirsiniz. Köprüler ekleme hakkında ayrıntılar için Aspose.Slides belgelerine bakın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}