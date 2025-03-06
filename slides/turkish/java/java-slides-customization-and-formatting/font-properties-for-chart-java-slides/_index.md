---
title: Java Slaytlarındaki Grafik için Yazı Tipi Özellikleri
linktitle: Java Slaytlarındaki Grafik için Yazı Tipi Özellikleri
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java ile Java Slides'taki Grafik Yazı Tipi Özelliklerini geliştirin. Etkili sunumlar için yazı tipi boyutunu, stilini ve rengini özelleştirin.
weight: 11
url: /tr/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarındaki Grafik için Yazı Tipi Özellikleri


## Java Slaytlarındaki Grafik için Yazı Tipi Özelliklerine Giriş

Bu kılavuz, Aspose.Slides'ı kullanarak Java Slides'ta bir grafiğin yazı tipi özelliklerini ayarlama konusunda size yol gösterecektir. Sunumlarınızın görsel çekiciliğini artırmak için grafik metninin yazı tipi boyutunu ve görünümünü özelleştirebilirsiniz.

## Önkoşullar

 Başlamadan önce Aspose.Slides for Java API'nin projenize entegre olduğundan emin olun. Henüz yapmadıysanız adresinden indirebilirsiniz.[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/).

## 1. Adım: Bir Sunu Oluşturun

Öncelikle aşağıdaki kodu kullanarak yeni bir sunum oluşturun:

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. Adım: Grafik Ekleme

Şimdi sunumunuza kümelenmiş bir sütun grafiği ekleyelim:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Burada ilk slayta (100, 100) koordinatlarında 500 birim genişliğinde ve 400 birim yüksekliğinde kümelenmiş sütun grafiği ekliyoruz.

## 3. Adım: Yazı Tipi Özelliklerini Özelleştirin

Daha sonra grafiğin yazı tipi özelliklerini özelleştireceğiz. Bu örnekte, tüm grafik metinleri için yazı tipi boyutunu 20'ye ayarlıyoruz:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Bu kod, grafikteki tüm metinler için yazı tipi boyutunu 20 puntoya ayarlar.

## 4. Adım: Veri Etiketlerini Göster

Aşağıdaki kodu kullanarak grafikte veri etiketlerini de gösterebilirsiniz:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Bu kod satırı, grafikteki ilk seri için veri etiketlerini etkinleştirerek grafik sütunlarındaki değerleri görüntüler.

## Adım 5: Sunuyu Kaydetme

Son olarak sunuyu özelleştirilmiş grafik yazı tipi özelliklerinizle kaydedin:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Bu kod, sunuyu "FontPropertiesForChart.pptx" dosya adıyla belirtilen dizine kaydedecektir.

## Java Slaytlarındaki Grafik için Yazı Tipi Özellikleri İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
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

Bu eğitimde, Aspose.Slides for Java kullanarak Java Slides'ta bir grafiğin yazı tipi özelliklerini nasıl özelleştireceğinizi öğrendiniz. Grafiklerinizin ve sunumlarınızın görünümünü geliştirmek için bu teknikleri uygulayabilirsiniz. Daha fazla seçeneği keşfedin[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/).

## SSS'ler

### Yazı tipi rengini nasıl değiştirebilirim?

 Grafik metninin yazı tipi rengini değiştirmek için şunu kullanın:`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , değiştirilmesi`Color.RED` İstenilen renk ile.

### Yazı tipi stilini (kalın, italik vb.) değiştirebilir miyim?

 Evet, yazı tipi stilini değiştirebilirsiniz. Kullanmak`chart.getTextFormat().getPortionFormat().setFontBold(true);` Yazı tipini kalın yapmak için. Benzer şekilde şunları kullanabilirsiniz:`setFontItalic(true)` italik yapmak için.

### Belirli grafik öğeleri için yazı tipi özelliklerini nasıl özelleştiririm?

Eksen etiketleri veya açıklama metni gibi belirli grafik öğelerinin yazı tipi özelliklerini özelleştirmek için bu öğelere erişebilir ve yukarıda gösterilene benzer yöntemleri kullanarak yazı tipi özelliklerini ayarlayabilirsiniz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
