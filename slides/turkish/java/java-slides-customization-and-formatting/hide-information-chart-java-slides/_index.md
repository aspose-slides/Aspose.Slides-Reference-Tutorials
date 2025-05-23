---
"description": "Java Slaytlarında grafik öğelerini Aspose.Slides for Java ile nasıl gizleyeceğinizi öğrenin. Adım adım rehberlik ve kaynak koduyla sunumları netlik ve estetik için özelleştirin."
"linktitle": "Java Slaytlarında Grafikten Bilgileri Gizle"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Grafikten Bilgileri Gizle"
"url": "/tr/java/customization-and-formatting/hide-information-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Grafikten Bilgileri Gizle


## Java Slaytlarında Grafikten Bilgi Gizlemeye Giriş

Bu eğitimde, Java Slaytlarında Aspose.Slides for Java API'sini kullanarak bir grafikten çeşitli öğeleri nasıl gizleyeceğinizi inceleyeceğiz. Bu kodu sunumlarınız için ihtiyaç duyduğunuz şekilde grafiklerinizi özelleştirmek için kullanabilirsiniz.

## Adım 1: Ortamı Kurma

Başlamadan önce, projenize Aspose.Slides for Java kütüphanesinin eklendiğinden emin olun. Bunu şuradan indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

## Adım 2: Yeni Bir Sunum Oluşturun

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Adım 3: Slayda Grafik Ekleme

Bir slayda işaretçiler içeren bir çizgi grafiği ekleyeceğiz ve ardından grafiğin çeşitli öğelerini gizleyeceğiz.

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

Değer eksenini (dikey eksen) gizlemek için aşağıdaki kodu kullanın:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Adım 6: Kategori Eksenini Gizle

Kategori eksenini (yatay eksen) gizlemek için şu kodu kullanın:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Adım 7: Efsaneyi Gizle

Tablonun açıklamasını şu şekilde gizleyebilirsiniz:

```java
chart.setLegend(false);
```

## Adım 8: Ana Izgara Çizgilerini Gizle

Yatay eksenin ana ızgara çizgilerini gizlemek için aşağıdaki kodu kullanabilirsiniz:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Adım 9: Seriyi Kaldır

Eğer grafikten tüm serileri kaldırmak istiyorsanız, aşağıdaki gibi bir döngü kullanabilirsiniz:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Adım 10: Grafik Serisini Özelleştirin

Grafik serisini gerektiği gibi özelleştirebilirsiniz. Bu örnekte, işaretçi stilini, veri etiketi konumunu, işaretçi boyutunu, çizgi rengini ve çizgi stilini değiştiriyoruz:

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

## Adım 11: Sunumu Kaydedin

Son olarak sunumu bir dosyaya kaydedin:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

İşte bu kadar! Java Slides'da Aspose.Slides for Java kullanarak bir grafikten çeşitli öğeleri başarıyla gizlediniz. Grafiklerinizi ve sunumlarınızı özel gereksinimleriniz için gerektiği gibi daha da özelleştirebilirsiniz.

## Java Slaytlarında Grafikten Bilgi Gizleme İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Grafik Başlığını Gizleme
	chart.setTitle(false);
	///Değerleri Gizleme ekseni
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Kategori Eksen görünürlüğü
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Efsaneyi Gizlemek
	chart.setLegend(false);
	//MajorGridLines'ı Gizleme
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
	//Seri çizgi renginin ayarlanması
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

Bu adım adım kılavuzda, Java Slaytlar'da Aspose.Slides for Java API'sini kullanarak bir grafikten çeşitli öğeleri nasıl gizleyeceğinizi inceledik. Bu, sunumlarınız için grafiklerinizi özelleştirmeniz ve bunları görsel olarak daha çekici hale getirmeniz veya özel ihtiyaçlarınıza göre uyarlamanız gerektiğinde inanılmaz derecede faydalı olabilir.

## SSS

### Grafik öğelerinin görünümünü nasıl daha fazla özelleştirebilirim?

Grafik serisinin, işaretçilerin, etiketlerin ve biçimin ilgili özelliklerine erişerek çizgi rengi, dolgu rengi, işaretçi stili ve daha fazlası gibi grafik öğelerinin çeşitli özelliklerini özelleştirebilirsiniz.

### Grafikte belirli veri noktalarını gizleyebilir miyim?

Evet, grafik serisindeki verileri düzenleyerek belirli veri noktalarını gizleyebilirsiniz. Veri noktalarını kaldırabilir veya değerlerini null olarak ayarlayarak gizleyebilirsiniz.

### Grafiğe ek serileri nasıl ekleyebilirim?

Grafiğe daha fazla seri eklemek için şunu kullanabilirsiniz: `IChartData.getSeries().add` Yöntem ve yeni seri için veri noktalarının belirlenmesi.

### Grafik türünü dinamik olarak değiştirmek mümkün müdür?

Evet, istediğiniz tipte yeni bir grafik oluşturarak ve eski grafikten yenisine veri kopyalayarak grafik tipini dinamik olarak değiştirebilirsiniz.

### Grafiğin başlığını ve eksen etiketlerini programlı olarak nasıl değiştirebilirim?

Grafik ve eksenlerin başlıklarını ve etiketlerini, ilgili özelliklerine erişip istediğiniz metni ve biçimlendirmeyi ayarlayarak ayarlayabilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}