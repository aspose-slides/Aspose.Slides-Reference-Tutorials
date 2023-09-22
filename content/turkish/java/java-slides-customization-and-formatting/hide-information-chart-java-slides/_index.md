---
title: Java Slaytlarındaki Grafikteki Bilgileri Gizle
linktitle: Java Slaytlarındaki Grafikteki Bilgileri Gizle
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java ile Java Slides'ta grafik öğelerini nasıl gizleyeceğinizi öğrenin. Adım adım rehberlik ve kaynak koduyla sunumlarınızı netlik ve estetik açısından özelleştirin.
type: docs
weight: 13
url: /tr/java/customization-and-formatting/hide-information-chart-java-slides/
---

## Java Slaytlarında Bilgileri Grafikten Gizlemeye Giriş

Bu derste, Aspose.Slides for Java API'sini kullanarak Java Slides'daki bir grafikteki çeşitli öğelerin nasıl gizleneceğini inceleyeceğiz. Sunumlarınız için grafiklerinizi gerektiği gibi özelleştirmek amacıyla bu kodu kullanabilirsiniz.

## 1. Adım: Ortamı Ayarlama

 Başlamadan önce Aspose.Slides for Java kütüphanesinin projenize eklendiğinden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## Adım 2: Yeni Bir Sunu Oluşturun

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 3. Adım: Slayta Grafik Ekleme

Bir slayda işaretleyicilerin bulunduğu bir çizgi grafiği ekleyeceğiz ve ardından grafiğin çeşitli öğelerini gizlemeye devam edeceğiz.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Adım 4: Grafik Başlığını Gizle

Grafik başlığını aşağıdaki şekilde gizleyebilirsiniz:

```java
chart.setTitle(false);
```

## Adım 5: Değer Eksenini Gizle

Değerler eksenini (dikey eksen) gizlemek için aşağıdaki kodu kullanın:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Adım 6: Kategori Eksenini Gizle

Kategori eksenini (yatay eksen) gizlemek için şu kodu kullanın:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Adım 7: Göstergeyi Gizle

Grafiğin açıklamasını şu şekilde gizleyebilirsiniz:

```java
chart.setLegend(false);
```

## Adım 8: Ana Izgara Çizgilerini Gizleyin

Yatay eksenin ana ızgara çizgilerini gizlemek için aşağıdaki kodu kullanabilirsiniz:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Adım 9: Seriyi Kaldır

Tüm serileri grafikten kaldırmak istiyorsanız şunun gibi bir döngü kullanabilirsiniz:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Adım 10: Grafik Serisini Özelleştirin

Grafik serisini gerektiği gibi özelleştirebilirsiniz. Bu örnekte işaretçi stilini, veri etiketi konumunu, işaretçi boyutunu, çizgi rengini ve çizgi stilini değiştiriyoruz:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## Adım 11: Sunuyu Kaydetme

Son olarak sunuyu bir dosyaya kaydedin:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

Bu kadar! Aspose.Slides for Java'yı kullanarak Java Slides'daki bir grafikteki çeşitli öğeleri başarıyla gizlediniz. Grafiklerinizi ve sunumlarınızı özel gereksinimlerinize göre daha da özelleştirebilirsiniz.

## Java Slaytlarındaki Grafikten Bilgileri Gizlemek İçin Kaynak Kodunu Tamamlayın

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Grafik Başlığını gizleme
	chart.setTitle(false);
	///Değerler eksenini gizleme
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Kategori Eksen görünürlüğü
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Efsaneyi Gizleme
	chart.setLegend(false);
	//MajorGridLines'ı gizleme
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//Seri çizgi rengini ayarlama
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## Çözüm

Bu adım adım kılavuzda, Aspose.Slides for Java API'sini kullanarak Java Slides'daki bir grafikteki çeşitli öğelerin nasıl gizleneceğini araştırdık. Grafiklerinizi sunumlar için özelleştirmeniz ve onları görsel olarak daha çekici veya özel ihtiyaçlarınıza göre uyarlamanız gerektiğinde bu son derece yararlı olabilir.

## SSS'ler

### Grafik öğelerinin görünümünü nasıl daha da özelleştirebilirim?

Grafik serisinin, işaretçilerin, etiketlerin ve formatın ilgili özelliklerine erişerek grafik öğelerinin çizgi rengi, dolgu rengi, işaretçi stili ve daha fazlası gibi çeşitli özelliklerini özelleştirebilirsiniz.

### Grafikteki belirli veri noktalarını gizleyebilir miyim?

Evet, grafik serisindeki verileri değiştirerek belirli veri noktalarını gizleyebilirsiniz. Veri noktalarını kaldırabilir veya gizlemek için değerlerini null olarak ayarlayabilirsiniz.

### Grafiğe nasıl ek seri ekleyebilirim?

 Kullanarak grafiğe daha fazla seri ekleyebilirsiniz.`IChartData.getSeries().add` yöntemi ve yeni seri için veri noktalarının belirlenmesi.

### Grafik türünü dinamik olarak değiştirmek mümkün mü?

Evet, istediğiniz türde yeni bir grafik oluşturup verileri eski grafikten yenisine kopyalayarak grafik türünü dinamik olarak değiştirebilirsiniz.

### Grafiğin başlığını ve eksen etiketlerini programlı olarak nasıl değiştirebilirim?

Grafiğin ve eksenlerin başlığını ve etiketlerini, ilgili özelliklerine erişerek ve istediğiniz metni ve formatı ayarlayarak ayarlayabilirsiniz.