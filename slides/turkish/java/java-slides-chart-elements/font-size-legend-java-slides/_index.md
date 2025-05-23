---
"description": "PowerPoint sunumlarınızı Aspose.Slides for Java ile geliştirin. Adım adım kılavuzumuzda efsane yazı tiplerini ve daha fazlasını nasıl özelleştireceğinizi öğrenin."
"linktitle": "Java Slaytlarında Yazı Tipi Boyutu Efsanesi"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Yazı Tipi Boyutu Efsanesi"
"url": "/tr/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Yazı Tipi Boyutu Efsanesi


## Java Slaytlarında Yazı Tipi Boyutu Efsanesine Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint slaydındaki efsanenin yazı tipi boyutunu nasıl özelleştireceğinizi öğreneceksiniz. Bu görevi başarmak için adım adım talimatlar ve kaynak kodu sağlayacağız.

## Ön koşullar

Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin yüklü ve ayarlanmış olduğundan emin olun. Kütüphaneyi şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Sunumu Başlatın

Öncelikle gerekli sınıfları içe aktarın ve PowerPoint sunumunuzu başlatın.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Yer değiştirmek `"Your Document Directory"` PowerPoint dosyanızın gerçek yolunu belirtin.

## Adım 2: Bir Grafik Ekleyin

Daha sonra slayda bir grafik ekleyeceğiz ve açıklamanın yazı boyutunu ayarlayacağız.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

Bu kodda, ilk slaytta kümelenmiş bir sütun grafiği oluşturuyoruz ve efsane metninin yazı tipi boyutunu 20 punto olarak ayarlıyoruz. `setFontHeight` İhtiyaç halinde yazı tipi boyutunu değiştirmek için değer.

## Adım 3: Eksen Değerlerini Özelleştirin

Şimdi grafiğin dikey eksen değerlerini özelleştirelim.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Burada, dikey eksen için minimum ve maksimum değerleri ayarlıyoruz. Değerleri veri gereksinimlerinize göre değiştirebilirsiniz.

## Adım 4: Sunumu Kaydedin

Son olarak, değiştirilen sunumu yeni bir dosyaya kaydedin.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Bu kod, değiştirilen sunumu belirtilen dizine "output.pptx" olarak kaydeder.

## Java Slaytlarında Yazı Tipi Boyutu Efsanesi İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Java PowerPoint slaydındaki efsanenin yazı tipi boyutunu Aspose.Slides for Java kullanarak başarıyla özelleştirdiniz. Etkileşimli ve görsel olarak çekici sunumlar oluşturmak için Aspose.Slides'ın yeteneklerini daha fazla keşfedebilirsiniz.

## SSS

### Bir grafikteki açıklama metninin yazı tipi boyutunu nasıl değiştirebilirim?

Bir grafikteki efsane metninin yazı tipi boyutunu değiştirmek için aşağıdaki kodu kullanabilirsiniz:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

Bu kodda bir grafik oluşturuyoruz ve efsane metninin yazı tipi boyutunu 20 punto olarak ayarlıyoruz. `setFontHeight` yazı tipi boyutunu değiştirmek için değer.

### Bir grafikteki efsanenin diğer özelliklerini özelleştirebilir miyim?

Evet, Aspose.Slides kullanarak bir grafikteki efsanenin çeşitli özelliklerini özelleştirebilirsiniz. Özelleştirebileceğiniz bazı genel özellikler arasında metin biçimlendirme, konum, görünürlük ve daha fazlası bulunur. Örneğin, efsanenin konumunu değiştirmek için şunları kullanabilirsiniz:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Bu kod, efsanenin grafiğin alt kısmında görünmesini sağlar. Daha fazla özelleştirme seçeneği için Aspose.Slides belgelerini inceleyin.

### Bir grafikte dikey eksen için minimum ve maksimum değerleri nasıl ayarlarım?

Bir grafikteki dikey eksen için minimum ve maksimum değerleri ayarlamak için aşağıdaki kodu kullanabilirsiniz:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Burada, otomatik eksen ölçeklemesini devre dışı bırakıyoruz ve dikey eksen için minimum ve maksimum değerleri belirliyoruz. Değerleri grafik verileriniz için gerektiği gibi ayarlayın.

### Aspose.Slides hakkında daha fazla bilgi ve belgeyi nerede bulabilirim?

Aspose.Slides for Java için kapsamlı dokümanları ve API referanslarını Aspose dokümantasyon web sitesinde bulabilirsiniz. Ziyaret edin [Burada](https://reference.aspose.com/slides/java/) Kütüphanenin kullanımı hakkında detaylı bilgi için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}