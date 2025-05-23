---
"description": "Java Slaytlarındaki Grafik Yazı Tipi Özelliklerini Aspose.Slides for Java ile geliştirin. Etkili sunumlar için yazı tipi boyutunu, stilini ve rengini özelleştirin."
"linktitle": "Java Slaytlarında Grafik İçin Yazı Tipi Özellikleri"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Grafik İçin Yazı Tipi Özellikleri"
"url": "/tr/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Grafik İçin Yazı Tipi Özellikleri


## Java Slaytlarında Grafik için Yazı Tipi Özelliklerine Giriş

Bu kılavuz, Aspose.Slides kullanarak Java Slides'da bir grafik için yazı tipi özelliklerini ayarlama konusunda size yol gösterecektir. Sunumlarınızın görsel çekiciliğini artırmak için grafik metninin yazı tipi boyutunu ve görünümünü özelleştirebilirsiniz.

## Ön koşullar

Başlamadan önce, projenize Aspose.Slides for Java API'nin entegre olduğundan emin olun. Henüz entegre etmediyseniz, şuradan indirebilirsiniz: [Java belgeleri için Aspose.Slides](https://reference.aspose.com/slides/java/).

## Adım 1: Bir Sunum Oluşturun

Öncelikle aşağıdaki kodu kullanarak yeni bir sunum oluşturun:

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Adım 2: Bir Grafik Ekleyin

Şimdi sununuza kümelenmiş sütun grafiği ekleyelim:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Burada, ilk slayda (100, 100) koordinatlarında genişliği 500 birim, yüksekliği 400 birim olan kümelenmiş bir sütun grafiği ekliyoruz.

## Adım 3: Yazı Tipi Özelliklerini Özelleştirin

Sonra, grafiğin yazı tipi özelliklerini özelleştireceğiz. Bu örnekte, tüm grafik metni için yazı tipi boyutunu 20 olarak ayarlıyoruz:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Bu kod, grafikteki tüm metinler için yazı tipi boyutunu 20 puntoya ayarlar.

## Adım 4: Veri Etiketlerini Göster

Aşağıdaki kodu kullanarak grafikte veri etiketlerini de gösterebilirsiniz:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Bu kod satırı, grafikteki ilk seri için veri etiketlerini etkinleştirir ve grafik sütunlarındaki değerleri görüntüler.

## Adım 5: Sunumu Kaydedin

Son olarak, sunuyu özelleştirilmiş grafik yazı tipi özellikleriyle kaydedin:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Bu kod sunumu belirtilen dizine "FontPropertiesForChart.pptx" dosya adıyla kaydedecektir.

## Java Slaytlarında Grafik İçin Yazı Tipi Özelliklerinin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Java Slides'da Aspose.Slides for Java kullanarak bir grafik için yazı tipi özelliklerini nasıl özelleştireceğinizi öğrendiniz. Grafiklerinizin ve sunumlarınızın görünümünü geliştirmek için bu teknikleri uygulayabilirsiniz. Daha fazla seçeneği keşfedin [Java belgeleri için Aspose.Slides](https://reference.aspose.com/slides/java/).

## SSS

### Yazı rengini nasıl değiştirebilirim?

Grafik metninin yazı tipi rengini değiştirmek için şunu kullanın: `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, yerine geçerek `Color.RED` İstenilen renkte.

### Yazı tipini (kalın, italik vb.) değiştirebilir miyim?

Evet, yazı tipini değiştirebilirsiniz. Kullan `chart.getTextFormat().getPortionFormat().setFontBold(true);` yazı tipini kalın yapmak için. Benzer şekilde, şunu kullanabilirsiniz `setFontItalic(true)` italik yapmak için.

### Belirli grafik öğeleri için yazı tipi özelliklerini nasıl özelleştirebilirim?

Eksen etiketleri veya gösterge metni gibi belirli grafik öğelerinin yazı tipi özelliklerini özelleştirmek için, bu öğelere erişebilir ve yukarıda gösterilen benzer yöntemleri kullanarak yazı tipi özelliklerini ayarlayabilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}