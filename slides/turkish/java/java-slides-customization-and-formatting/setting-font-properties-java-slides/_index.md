---
"description": "Java slaytlarında Aspose.Slides for Java kullanarak yazı tipi özelliklerinin nasıl ayarlanacağını öğrenin. Bu adım adım kılavuz, kod örnekleri ve SSS içerir."
"linktitle": "Java Slaytlarında Yazı Tipi Özelliklerini Ayarlama"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Yazı Tipi Özelliklerini Ayarlama"
"url": "/tr/java/customization-and-formatting/setting-font-properties-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Yazı Tipi Özelliklerini Ayarlama


## Java Slaytlarında Yazı Tipi Özelliklerini Ayarlamaya Giriş

Bu eğitimde, Java slaytlarındaki metinler için Aspose.Slides for Java kullanarak yazı tipi özelliklerinin nasıl ayarlanacağını inceleyeceğiz. Kalınlık ve yazı tipi boyutu gibi yazı tipi özellikleri, slaytlarınızın görünümünü geliştirmek için özelleştirilebilir.

## Ön koşullar

Başlamadan önce projenize Aspose.Slides for Java kütüphanesinin eklendiğinden emin olun. Bunu şuradan indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Sunumu Başlatın

Öncelikle, mevcut bir PowerPoint dosyasını yükleyerek bir sunum nesnesini başlatmanız gerekir. Değiştir `"Your Document Directory"` belge dizininize giden gerçek yol ile.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Adım 2: Bir Grafik Ekleyin

Bu örnekte, ilk slayttaki bir grafikle çalışacağız. Slayt dizinini ihtiyaçlarınıza göre değiştirebilirsiniz. Kümelenmiş bir sütun grafiği ekleyeceğiz ve veri tablosunu etkinleştireceğiz.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.setDataTable(true);
```

## Adım 3: Yazı Tipi Özelliklerini Özelleştirin

Şimdi, grafik veri tablosunun yazı tipi özelliklerini özelleştirelim. Yazı tipini kalın olarak ayarlayacağız ve yazı tipi yüksekliğini (boyutunu) ayarlayacağız.

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
```

- `setFontBold(NullableBool.True)`Bu satır yazı tipini kalın olarak ayarlar.
- `setFontHeight(20)`: Bu satır yazı tipi yüksekliğini 20 puana ayarlar. Bu değeri ihtiyacınıza göre ayarlayabilirsiniz.

## Adım 4: Sunumu Kaydedin

Son olarak, değiştirilen sunumu yeni bir dosyaya kaydedin. Çıktı biçimini belirtebilirsiniz; bu durumda, bunu bir PPTX dosyası olarak kaydediyoruz.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Yazı Tipi Özelliklerini Ayarlamak İçin Tam Kaynak Kodu

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.setDataTable(true);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Java slaytlarındaki metinler için Aspose.Slides for Java kullanarak yazı tipi özelliklerinin nasıl ayarlanacağını öğrendiniz. Bu teknikleri, PowerPoint sunumlarınızdaki metnin görünümünü geliştirmek için uygulayabilirsiniz.

## SSS

### Yazı rengini nasıl değiştirebilirim?

Yazı tipi rengini değiştirmek için şunu kullanın: `setFontColor` yöntemini seçin ve istediğiniz rengi belirtin. Örneğin:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontColor(Color.RED);
```

### Slaytlardaki diğer metinlerin yazı tipini değiştirebilir miyim?

Evet, slaytlardaki başlıklar ve etiketler gibi diğer metin öğelerinin yazı tipini değiştirebilirsiniz. Belirli metin öğeleri için yazı tipi özelliklerine erişmek ve bunları özelleştirmek için uygun nesneleri ve yöntemleri kullanın.

### İtalik yazı stilini nasıl ayarlarım?

Yazı tipini italik olarak ayarlamak için şunu kullanın: `setFontItalic` yöntem:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontItalic(NullableBool.True);
```

Ayarla `NullableBool.True` İtalik stili etkinleştirmek veya devre dışı bırakmak için gerektiği gibi parametreyi ayarlayın.

### Bir grafikteki veri etiketlerinin yazı tipini nasıl değiştirebilirim?

Bir grafikteki veri etiketlerinin yazı tipini değiştirmek için, uygun yöntemleri kullanarak veri etiketi metin biçimine erişmeniz gerekir. Örneğin:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0); // Gerektiğinde dizini değiştirin
series.getLabels().getDefaultDataLabelFormat().getPortionFormat().setFontBold(NullableBool.True);
```

Bu kod, ilk serideki veri etiketlerinin yazı tipini kalın olarak ayarlar.

### Metnin belirli bir bölümünün yazı tipini nasıl değiştiririm?

Bir metin öğesi içindeki metnin belirli bir bölümünün yazı tipini değiştirmek istiyorsanız, şunu kullanabilirsiniz: `PortionFormat` Sınıf. Değiştirmek istediğiniz bölüme erişin ve ardından istediğiniz yazı tipi özelliklerini ayarlayın.

```java
IAutoShape textShape = (IAutoShape)slide.getShapes().get_Item(0); // Gerektiğinde dizini değiştirin
ITextFrame textFrame = textShape.getTextFrame();
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // Gerektiğinde dizini değiştirin
IPortion portion = paragraph.getPortions().get_Item(0); // Gerektiğinde dizini değiştirin

portion.getPortionFormat().setFontBold(NullableBool.True);
portion.getPortionFormat().setFontHeight(24);
```

Bu kod, bir şeklin içindeki metnin ilk kısmının yazı tipini kalın yapar ve yazı tipi yüksekliğini ayarlar.

### Bir sunumdaki tüm slaytlara yazı tipi değişikliklerini nasıl uygulayabilirim?

Bir sunumdaki tüm slaytlara yazı tipi değişiklikleri uygulamak için slaytlar arasında yineleme yapabilir ve yazı tipi özelliklerini gerektiği gibi ayarlayabilirsiniz. Her bir slayta ve içindeki metin öğelerine erişmek için bir döngü kullanın, ardından yazı tipi özelliklerini özelleştirin.

```java
for (ISlide slide : pres.getSlides()) {
    // Metin öğelerinin yazı tipi özelliklerine buradan erişin ve özelleştirin
}
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}