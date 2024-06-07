---
title: Java Slaytlarındaki Veri Noktalarına Renk Ekleme
linktitle: Java Slaytlarındaki Veri Noktalarına Renk Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java slaytlarındaki veri noktalarına nasıl renk ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/java/chart-data-manipulation/add-color-data-points-java-slides/
---

## Java Slaytlarında Veri Noktalarına Renk Eklemeye Giriş

Bu eğitimde Aspose.Slides for Java kullanarak Java slaytlarındaki veri noktalarına nasıl renk ekleyeceğimizi göstereceğiz. Bu adım adım kılavuz, bu görevi gerçekleştirmenize yardımcı olacak kaynak kodu örneklerini içerir.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Java Geliştirme Ortamı
- Aspose.Slides for Java kütüphanesi

## 1. Adım: Yeni Bir Sunu Oluşturun

Öncelikle Aspose.Slides for Java'yı kullanarak yeni bir sunum oluşturacağız. Bu sunum grafiğimiz için kapsayıcı görevi görecek.

```java
Presentation pres = new Presentation();
```

## Adım 2: Sunburst Grafiği Ekleyin

Şimdi sunuma Sunburst grafiği ekleyelim. Grafiğin türünü, konumunu ve boyutunu belirleriz.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## 3. Adım: Veri Noktalarına Erişin

 Grafikteki veri noktalarını değiştirmek için`IChartDataPointCollection` nesne.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## 4. Adım: Veri Noktalarını Özelleştirin

Bu adımda belirli veri noktalarını özelleştireceğiz. Burada veri noktalarının rengini değiştiriyoruz ve etiket ayarlarını yapıyoruz.

```java
//Veri noktası 0'ı özelleştirin
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Veri noktası 9'u özelleştirme
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Adım 5: Sunuyu Kaydetme

Son olarak sunuyu özelleştirilmiş grafikle kaydedin.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Bu kadar! Aspose.Slides for Java'yı kullanarak bir Java slaytındaki belirli veri noktalarına başarıyla renk eklediniz.

## Java Slaytlarındaki Veri Noktalarına Renk Eklemek İçin Tam Kaynak Kodu

```java
Presentation pres = new Presentation();
try
{
	// Belgeler dizininin yolu.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//YAPMAK
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides for Java kullanarak Java slaytlarındaki veri noktalarına nasıl renk ekleyeceğinizi öğrendiniz. Grafiklerinizi ve sunumlarınızı özel gereksinimlerinize göre daha da özelleştirebilirsiniz.

## SSS'ler

### Diğer veri noktalarının rengini nasıl değiştirebilirim?

Diğer veri noktalarının rengini değiştirmek için 4. Adımda gösterilene benzer bir yaklaşım izleyebilirsiniz. Özelleştirmek istediğiniz veri noktasına erişin ve renk ve etiket ayarlarını değiştirin.

### Grafiğin diğer yönlerini özelleştirebilir miyim?

 Evet, yazı tipleri, etiketler, başlıklar ve daha fazlası dahil olmak üzere grafiğin çeşitli yönlerini özelleştirebilirsiniz. Bakın[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/) ayrıntılı özelleştirme seçenekleri için.

### Daha fazla örnek ve belgeyi nerede bulabilirim?

Aspose.Slides for Java kullanımına ilişkin daha fazla örnek ve ayrıntılı belgeyi şu adreste bulabilirsiniz:[Aspose.Slides belgeleri](https://reference.aspose.com/slides/java/) İnternet sitesi.