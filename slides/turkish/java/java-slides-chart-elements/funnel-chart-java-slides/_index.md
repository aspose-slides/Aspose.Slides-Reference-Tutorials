---
title: Java Slaytlarındaki Huni Grafiği
linktitle: Java Slaytlarındaki Huni Grafiği
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Adım adım eğitimlerle Aspose.Slides for Java'yı keşfedin. Çarpıcı huni grafikleri ve daha fazlasını oluşturun.
weight: 14
url: /tr/java/chart-elements/funnel-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarındaki Huni Grafiği


## Java Slaytlarındaki Huni Grafiğine Giriş

Bu eğitimde Aspose.Slides for Java kullanarak huni grafiğinin nasıl oluşturulacağını göstereceğiz. Huni grafikleri, satış dönüşümleri veya müşteri edinme gibi giderek daraltılan aşamalara sahip sıralı bir süreci görselleştirmek için kullanışlıdır.

## Önkoşullar

 Başlamadan önce Aspose.Slides kütüphanesinin Java projenize eklendiğinden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## 1. Adım: Sunumu Başlatın

Öncelikle bir sunum başlatalım ve huni grafiğimizi yerleştireceğimiz yere bir slayt ekleyelim.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Değiştirdiğinizden emin olun`"Your Document Directory"` proje dizininizin gerçek yolu ile.

## 2. Adım: Huni Grafiğini Oluşturun

Şimdi huni grafiğini oluşturalım ve boyutlarını slaytta ayarlayalım.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Yukarıdaki kodda ilk slayta (50, 50) koordinatlarında 500 genişliğinde ve 400 piksel yüksekliğinde bir huni grafiği ekliyoruz.

## 3. Adım: Grafik Verilerini Tanımlayın

Daha sonra huni grafiğimiz için verileri tanımlayacağız. Grafiğin kategorilerini ve serilerini belirleyeceğiz.

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
```

Burada mevcut tüm verileri temizliyoruz, kategoriler ekliyoruz (bu durumda dönüşüm hunisinin aşamaları) ve etiketlerini ayarlıyoruz.

## 4. Adım: Veri Noktalarını Ekleyin

Şimdi huni grafiği serimize veri noktaları ekleyelim.

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

Bu adımda huni grafiğimiz için bir seri oluşturuyoruz ve huninin her aşamasındaki değerleri temsil eden veri noktalarını ekliyoruz.

## Adım 5: Sunuyu Kaydetme

Son olarak huni grafiğinin bulunduğu sunumu bir PowerPoint dosyasına kaydediyoruz.

```java
    pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 Değiştirdiğinizden emin olun`"Your Document Directory"` İstediğiniz kaydetme konumuyla.

## Java Slaytlarındaki Huni Grafiği İçin Tam Kaynak Kodu

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
	pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde size Aspose.Slides for Java kullanarak Java Slides'ta nasıl huni grafiği oluşturulacağını gösterdik. Renkleri, etiketleri ve diğer özellikleri özel ihtiyaçlarınıza uyacak şekilde ayarlayarak grafiği daha da özelleştirebilirsiniz.

## SSS'ler

### Huni grafiğinin görünümünü nasıl özelleştirebilirim?

Grafiğin, serilerin ve veri noktalarının özelliklerini değiştirerek huni grafiğinin görünümünü özelleştirebilirsiniz. Ayrıntılı özelleştirme seçenekleri için Aspose.Slides belgelerine bakın.

### Huni grafiğine daha fazla kategori veya veri noktası ekleyebilir miyim?

Evet, 3. Adım ve 4. Adımdaki kodu uygun şekilde genişleterek huni grafiğine daha fazla kategori ve veri noktası ekleyebilirsiniz.

### Grafik türünü huni dışında bir şeyle değiştirmek mümkün mü?

 Evet, Aspose.Slides çeşitli grafik türlerini destekler. Grafik türünü değiştirerek değiştirebilirsiniz.`ChartType.Funnel` 2. Adımda istenen grafik türüyle.

### Aspose.Slides ile çalışırken hataları veya istisnaları nasıl ele alacağım?

Standart Java istisna işleme mekanizmalarını kullanarak hataları ve istisnaları yönetebilirsiniz. Beklenmedik durumların başarıyla üstesinden gelmek için kodunuzda doğru hata işleme özelliğinin bulunduğundan emin olun.

### Aspose.Slides for Java için daha fazla örneği ve belgeyi nerede bulabilirim?

 Aspose.Slides for Java kullanımına ilişkin daha fazla örnek ve ayrıntılı belgeyi şu adreste bulabilirsiniz:[dokümantasyon](https://docs.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
