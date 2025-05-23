---
"description": "Java için Aspose.Slides'ı kullanarak Java slaytlarındaki veri noktalarına nasıl renk ekleneceğini öğrenin."
"linktitle": "Java Slaytlarında Veri Noktalarına Renk Ekleme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Veri Noktalarına Renk Ekleme"
"url": "/tr/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Veri Noktalarına Renk Ekleme


## Java Slaytlarında Veri Noktalarına Renk Eklemeye Giriş

Bu eğitimde, Java slaytlarındaki veri noktalarına Aspose.Slides for Java kullanarak nasıl renk ekleneceğini göstereceğiz. Bu adım adım kılavuz, bu görevi başarmanıza yardımcı olacak kaynak kod örneklerini içerir.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Java Geliştirme Ortamı
- Java kütüphanesi için Aspose.Slides

## Adım 1: Yeni Bir Sunum Oluşturun

İlk olarak, Java için Aspose.Slides kullanarak yeni bir sunum oluşturacağız. Bu sunum, grafiğimiz için kapsayıcı görevi görecek.

```java
Presentation pres = new Presentation();
```

## Adım 2: Bir Sunburst Grafiği Ekleyin

Şimdi, sunuma bir Sunburst grafiği ekleyelim. Grafik türünü, konumunu ve boyutunu belirtelim.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Adım 3: Veri Noktalarına Erişim

Grafikteki veri noktalarını değiştirmek için, şuraya erişmemiz gerekir: `IChartDataPointCollection` nesne.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Adım 4: Veri Noktalarını Özelleştirin

Bu adımda, belirli veri noktalarını özelleştireceğiz. Burada, veri noktalarının rengini değiştiriyoruz ve etiket ayarlarını yapılandırıyoruz.

```java
// Veri noktası 0'ı özelleştir
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Veri noktası 9'u özelleştir
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Adım 5: Sunumu Kaydedin

Son olarak sunumu özelleştirilmiş grafikle kaydedin.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

İşte bu kadar! Aspose.Slides for Java kullanarak bir Java slaydındaki belirli veri noktalarına başarıyla renk eklediniz.

## Java Slaytlarında Veri Noktalarına Renk Eklemek İçin Tam Kaynak Kodu

```java
Presentation pres = new Presentation();
try
{
	// Belgeler dizinine giden yol.
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
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//Yapılacaklar
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Java slaytlarındaki veri noktalarına Aspose.Slides for Java kullanarak nasıl renk ekleyeceğinizi öğrendiniz. Grafiklerinizi ve sunumlarınızı özel gereksinimlerinize göre daha da özelleştirebilirsiniz.

## SSS

### Diğer veri noktalarının rengini nasıl değiştirebilirim?

Diğer veri noktalarının rengini değiştirmek için 4. Adımda gösterilene benzer bir yaklaşımı izleyebilirsiniz. Özelleştirmek istediğiniz veri noktasına erişin ve renk ve etiket ayarlarını değiştirin.

### Tablonun diğer yönlerini özelleştirebilir miyim?

Evet, yazı tipleri, etiketler, başlıklar ve daha fazlası dahil olmak üzere grafiğin çeşitli yönlerini özelleştirebilirsiniz. [Java belgeleri için Aspose.Slides](https://reference.aspose.com/slides/java/) Detaylı özelleştirme seçenekleri için.

### Daha fazla örnek ve dokümanı nerede bulabilirim?

Java için Aspose.Slides'ı kullanma hakkında daha fazla örnek ve ayrıntılı belgeler bulabilirsiniz [Aspose.Slides belgeleri](https://reference.aspose.com/slides/java/) Web sitesi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}