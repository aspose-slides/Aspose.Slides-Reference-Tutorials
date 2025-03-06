---
title: Java Slaytlarında Halka Grafik Deliği
linktitle: Java Slaytlarında Halka Grafik Deliği
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slaytlarında Özel Delik Boyutlarına sahip Halka Grafikleri oluşturun. Grafik özelleştirmesi için kaynak kodlu adım adım kılavuz.
weight: 11
url: /tr/java/chart-elements/doughnut-chart-hole-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java Slaytlarında Delikli Halka Grafiğine Giriş

Bu eğitimde Aspose.Slides for Java'yı kullanarak delikli bir halka grafiği oluşturma konusunda size rehberlik edeceğiz. Bu adım adım kılavuz, kaynak kodu örnekleriyle süreç boyunca size yol gösterecektir.

## Önkoşullar

 Başlamadan önce Java projenizde Aspose.Slides for Java kitaplığının kurulu olduğundan ve kurulduğundan emin olun. adresinden indirebilirsiniz.[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/).

## 1. Adım: Gerekli Kitaplıkları İçe Aktarın

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Adım 2: Sunumu Başlatın

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";

// Sunum sınıfının bir örneğini oluşturun
Presentation presentation = new Presentation();
```

## Adım 3: Halka Tablosunu Oluşturun

```java
try {
    // İlk slaytta halka grafiği oluşturun
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Halka grafiğindeki deliğin boyutunu ayarlayın (yüzde olarak)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Sunuyu diske kaydet
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Sunum nesnesini atın
    if (presentation != null) presentation.dispose();
}
```

## 4. Adım: Kodu Çalıştırın

 Belirtilen delik boyutuna sahip bir halka grafiği oluşturmak için IDE'nizde veya metin düzenleyicinizde Java kodunu çalıştırın. Değiştirdiğinizden emin olun`"Your Document Directory"` sunuyu kaydetmek istediğiniz asıl yolla.

## Java Slaytlarındaki Halka Grafik Deliği İçin Kaynak Kodunu Tamamlayın

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum sınıfının bir örneğini oluşturun
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

 Bu eğitimde Aspose.Slides for Java'yı kullanarak delikli bir halka grafiğinin nasıl oluşturulacağını öğrendiniz. Ayarlayarak deliğin boyutunu kişiselleştirebilirsiniz.`setDoughnutHoleSize` yöntem parametresi.

## SSS'ler

### Grafik bölümlerinin rengini nasıl değiştirebilirim?

 Grafik segmentlerinin rengini değiştirmek için`setDataPointsInLegend` konusundaki yöntem`IChart` nesneyi seçin ve her veri noktası için istediğiniz rengi ayarlayın.

### Halka grafik segmentlerine etiket ekleyebilir miyim?

 Evet, halka grafiği segmentlerine aşağıdaki düğmeyi kullanarak etiket ekleyebilirsiniz:`setDataPointsLabelValue` konusundaki yöntem`IChart` nesne.

### Grafiğe başlık eklemek mümkün mü?

 Kesinlikle! kullanarak grafiğe bir başlık ekleyebilirsiniz.`setTitle` konusundaki yöntem`IChart` nesne ve istenen başlık metninin sağlanması.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
