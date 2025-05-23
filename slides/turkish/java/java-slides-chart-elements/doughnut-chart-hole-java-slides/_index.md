---
"description": "Java Slaytlarında Aspose.Slides for Java kullanarak Özel Delik Boyutlarına Sahip Halka Grafikleri Oluşturun. Grafik özelleştirmesi için kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Çörek Grafiği Deliği"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Çörek Grafiği Deliği"
"url": "/tr/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Çörek Grafiği Deliği


## Java Slaytlarında Delikli Halka Grafiğine Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak delikli bir halka grafiği oluşturmanıza rehberlik edeceğiz. Bu adım adım kılavuz, kaynak kod örnekleriyle sizi süreçte yönlendirecektir.

## Ön koşullar

Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin yüklü ve ayarlanmış olduğundan emin olun. Bunu şuradan indirebilirsiniz: [Java belgeleri için Aspose.Slides](https://reference.aspose.com/slides/java/).

## Adım 1: Gerekli Kitaplıkları İçeri Aktarın

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Adım 2: Sunumu Başlatın

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";

// Bir Presentation sınıfı örneği oluşturun
Presentation presentation = new Presentation();
```

## Adım 3: Çörek Grafiğini Oluşturun

```java
try {
    // İlk slaytta bir halka grafiği oluşturun
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Halka grafiğindeki deliğin boyutunu ayarlayın (yüzde olarak)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Sunumu diske kaydet
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Sunum nesnesini elden çıkarın
    if (presentation != null) presentation.dispose();
}
```

## Adım 4: Kodu Çalıştırın

Belirtilen delik boyutuna sahip bir halka grafiği oluşturmak için Java kodunu IDE'nizde veya metin düzenleyicinizde çalıştırın. Değiştirdiğinizden emin olun `"Your Document Directory"` Sunumu kaydetmek istediğiniz gerçek yol ile.

## Java Slaytlarında Donut Grafik Deliği İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir Presentation sınıfı örneği oluşturun
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Sunumu diske yaz
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Bu eğitimde, Java için Aspose.Slides kullanarak delikli bir halka grafiği oluşturmayı öğrendiniz. Deliğin boyutunu, `setDoughnutHoleSize` yöntem parametresi.

## SSS

### Grafik segmentlerinin rengini nasıl değiştirebilirim?

Grafik bölümlerinin rengini değiştirmek için şunu kullanabilirsiniz: `setDataPointsInLegend` yöntem üzerinde `IChart` nesneyi seçin ve her veri noktası için istediğiniz rengi ayarlayın.

### Halka grafik segmentlerine etiket ekleyebilir miyim?

Evet, halka grafik bölümlerine etiket ekleyebilirsiniz. `setDataPointsLabelValue` yöntem üzerinde `IChart` nesne.

### Tabloya bir başlık eklemek mümkün mü?

Elbette! Grafiğe bir başlık ekleyebilirsiniz. `setTitle` yöntem üzerinde `IChart` nesne ve istenilen başlık metnini sağlamak.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}