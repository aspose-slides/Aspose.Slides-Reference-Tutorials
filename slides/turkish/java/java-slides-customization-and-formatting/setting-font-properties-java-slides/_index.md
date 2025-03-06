---
title: Java Slaytlarında Yazı Tipi Özelliklerini Ayarlama
linktitle: Java Slaytlarında Yazı Tipi Özelliklerini Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java slaytlarında yazı tipi özelliklerini nasıl ayarlayacağınızı öğrenin. Bu adım adım kılavuz, kod örneklerini ve SSS'leri içerir.
weight: 15
url: /tr/java/customization-and-formatting/setting-font-properties-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java Slaytlarında Yazı Tipi Özelliklerini Ayarlamaya Giriş

Bu eğitimde Aspose.Slides for Java kullanarak Java slaytlarındaki metin için yazı tipi özelliklerinin nasıl ayarlanacağını keşfedeceğiz. Kalınlık ve yazı tipi boyutu gibi yazı tipi özellikleri, slaytlarınızın görünümünü geliştirmek için özelleştirilebilir.

## Önkoşullar

 Başlamadan önce Aspose.Slides for Java kütüphanesinin projenize eklendiğinden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## 1. Adım: Sunumu Başlatın

 Öncelikle mevcut bir PowerPoint dosyasını yükleyerek bir sunum nesnesini başlatmanız gerekir. Yer değiştirmek`"Your Document Directory"` belge dizininizin gerçek yolu ile.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 2. Adım: Grafik Ekleme

Bu örnekte ilk slayttaki bir grafikle çalışacağız. Slayt indeksini ihtiyaçlarınıza göre değiştirebilirsiniz. Kümelenmiş bir sütun grafiği ekleyeceğiz ve veri tablosunu etkinleştireceğiz.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.setDataTable(true);
```

## 3. Adım: Yazı Tipi Özelliklerini Özelleştirin

Şimdi grafik veri tablosunun yazı tipi özelliklerini özelleştirelim. Fontu kalın olarak ayarlayıp, font yüksekliğini (boyutunu) ayarlayacağız.

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
```

- `setFontBold(NullableBool.True)`: Bu satır yazı tipinin kalın olmasını ayarlar.
- `setFontHeight(20)`: Bu satır yazı yüksekliğini 20 punto olarak ayarlar. Bu değeri gerektiği gibi ayarlayabilirsiniz.

## 4. Adım: Sunuyu Kaydetme

Son olarak değiştirilen sunumu yeni bir dosyaya kaydedin. Çıktı formatını belirleyebilirsiniz; bu durumda onu bir PPTX dosyası olarak kaydediyoruz.

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

Bu eğitimde Aspose.Slides for Java kullanarak Java slaytlarındaki metinlerin yazı tipi özelliklerini nasıl ayarlayacağınızı öğrendiniz. PowerPoint sunumlarınızdaki metnin görünümünü geliştirmek için bu teknikleri uygulayabilirsiniz.

## SSS'ler

### Yazı tipi rengini nasıl değiştiririm?

 Yazı tipi rengini değiştirmek için`setFontColor` yöntemini seçin ve istediğiniz rengi belirtin. Örneğin:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontColor(Color.RED);
```

### Slaytlardaki diğer metinlerin yazı tipini değiştirebilir miyim?

Evet, slaytlardaki başlıklar ve etiketler gibi diğer metin öğelerinin yazı tipini değiştirebilirsiniz. Belirli metin öğelerinin yazı tipi özelliklerine erişmek ve bunları özelleştirmek için uygun nesneleri ve yöntemleri kullanın.

### İtalik yazı tipi stilini nasıl ayarlarım?

 Yazı tipi stilini italik olarak ayarlamak için`setFontItalic` yöntem:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontItalic(NullableBool.True);
```

 Ayarlayın`NullableBool.True` İtalik stili etkinleştirmek veya devre dışı bırakmak için gereken parametreyi kullanın.

### Bir grafikteki veri etiketlerinin yazı tipini nasıl değiştirebilirim?

Bir grafikteki veri etiketlerinin yazı tipini değiştirmek için uygun yöntemleri kullanarak veri etiketi metin biçimine erişmeniz gerekir. Örneğin:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0); // Dizini gerektiği gibi değiştirin
series.getLabels().getDefaultDataLabelFormat().getPortionFormat().setFontBold(NullableBool.True);
```

Bu kod, ilk serideki veri etiketlerinin yazı tipini kalın olarak ayarlar.

### Metnin belirli bir bölümünün yazı tipini nasıl değiştiririm?

 Bir metin öğesi içindeki metnin belirli bir bölümünün yazı tipini değiştirmek istiyorsanız,`PortionFormat` sınıf. Değiştirmek istediğiniz kısma erişin ve ardından istediğiniz yazı tipi özelliklerini ayarlayın.

```java
IAutoShape textShape = (IAutoShape)slide.getShapes().get_Item(0); // Dizini gerektiği gibi değiştirin
ITextFrame textFrame = textShape.getTextFrame();
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // Dizini gerektiği gibi değiştirin
IPortion portion = paragraph.getPortions().get_Item(0); // Dizini gerektiği gibi değiştirin

portion.getPortionFormat().setFontBold(NullableBool.True);
portion.getPortionFormat().setFontHeight(24);
```

Bu kod, şeklin içindeki metnin ilk bölümünün yazı tipini kalın olarak ayarlar ve yazı tipi yüksekliğini ayarlar.

### Bir sunumdaki tüm slaytlara yazı tipi değişikliklerini nasıl uygulayabilirim?

Yazı tipi değişikliklerini bir sunumdaki tüm slaytlara uygulamak için slaytlar arasında geçiş yapabilir ve yazı tipi özelliklerini gerektiği gibi ayarlayabilirsiniz. Her slayta ve bunların içindeki metin öğelerine erişmek için bir döngü kullanın, ardından yazı tipi özelliklerini özelleştirin.

```java
for (ISlide slide : pres.getSlides()) {
    // Metin öğelerinin yazı tipi özelliklerine buradan erişin ve özelleştirin
}
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
