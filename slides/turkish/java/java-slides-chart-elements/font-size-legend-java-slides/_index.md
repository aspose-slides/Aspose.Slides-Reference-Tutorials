---
title: Java Slaytlarında Yazı Tipi Boyutu Açıklaması
linktitle: Java Slaytlarında Yazı Tipi Boyutu Açıklaması
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java ile PowerPoint sunumlarını geliştirin. Adım adım kılavuzumuzda açıklama yazı tipi boyutlarını ve daha fazlasını nasıl özelleştireceğinizi öğrenin.
weight: 13
url: /tr/java/chart-elements/font-size-legend-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java Slaytlarında Yazı Tipi Boyutu Göstergesine Giriş

Bu eğitimde, Aspose.Slides for Java'yı kullanarak bir PowerPoint slaydındaki açıklamanın yazı tipi boyutunu nasıl özelleştireceğinizi öğreneceksiniz. Bu görevi gerçekleştirmek için adım adım talimatlar ve kaynak kodu sağlayacağız.

## Önkoşullar

 Başlamadan önce Java projenizde Aspose.Slides for Java kitaplığının kurulu olduğundan ve kurulduğundan emin olun. Kütüphaneyi adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Sunumu Başlatın

Öncelikle gerekli sınıfları içe aktarın ve PowerPoint sunumunuzu başlatın.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Yer değiştirmek`"Your Document Directory"` PowerPoint dosyanızın gerçek yolunu belirtin.

## 2. Adım: Grafik Ekleme

Daha sonra slayta bir grafik ekleyeceğiz ve açıklamanın yazı tipi boyutunu ayarlayacağız.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 Bu kodda ilk slaytta kümelenmiş bir sütun grafiği oluşturuyoruz ve açıklama metninin yazı tipi boyutunu 20 punto olarak ayarlıyoruz. Ayarlayabilirsiniz`setFontHeight`Yazı tipi boyutunu gerektiği gibi değiştirmek için değer.

## Adım 3: Eksen Değerlerini Özelleştirin

Şimdi grafiğin dikey eksen değerlerini özelleştirelim.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Burada dikey eksen için minimum ve maksimum değerleri ayarlıyoruz. Değerleri veri gereksinimlerinize göre değiştirebilirsiniz.

## 4. Adım: Sunuyu Kaydetme

Son olarak değiştirilen sunumu yeni bir dosyaya kaydedin.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Bu kod, değiştirilen sunumu belirtilen dizine "output.pptx" olarak kaydeder.

## Java Slaytlarında Yazı Tipi Boyutu Açıklaması İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
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

Aspose.Slides for Java'yı kullanarak bir Java PowerPoint slaytındaki açıklamanın yazı tipi boyutunu başarıyla özelleştirdiniz. Etkileşimli ve görsel olarak çekici sunumlar oluşturmak için Aspose.Slides'ın yeteneklerini daha fazla keşfedebilirsiniz.

## SSS'ler

### Bir grafikteki açıklama metninin yazı tipi boyutunu nasıl değiştiririm?

Bir grafikteki açıklama metninin yazı tipi boyutunu değiştirmek için aşağıdaki kodu kullanabilirsiniz:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 Bu kodda bir grafik oluşturup lejant metninin yazı tipi boyutunu 20 punto olarak ayarlıyoruz. Ayarlayabilirsiniz`setFontHeight` Yazı tipi boyutunu değiştirmek için değer.

### Bir grafikteki göstergenin diğer özelliklerini özelleştirebilir miyim?

Evet, Aspose.Slides'ı kullanarak bir grafikteki açıklamanın çeşitli özelliklerini özelleştirebilirsiniz. Özelleştirebileceğiniz ortak özelliklerden bazıları metin biçimlendirmesi, konum, görünürlük ve daha fazlasını içerir. Örneğin efsanenin konumunu değiştirmek için şunları kullanabilirsiniz:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Bu kod, göstergenin grafiğin altında görünmesini ayarlar. Daha fazla özelleştirme seçeneği için Aspose.Slides belgelerini inceleyin.

### Bir grafikte dikey eksen için minimum ve maksimum değerleri nasıl ayarlarım?

Bir grafikte dikey eksenin minimum ve maksimum değerlerini ayarlamak için aşağıdaki kodu kullanabilirsiniz:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Burada otomatik eksen ölçeklendirmeyi devre dışı bırakıp dikey eksen için minimum ve maksimum değerleri belirliyoruz. Değerleri grafik verileriniz için gereken şekilde ayarlayın.

### Aspose.Slides için daha fazla bilgi ve belgeyi nerede bulabilirim?

 Aspose dokümantasyon web sitesinde Aspose.Slides for Java için kapsamlı dokümantasyon ve API referansları bulabilirsiniz. Ziyaret etmek[Burada](https://reference.aspose.com/slides/java/) Kütüphanenin kullanımına ilişkin detaylı bilgi için.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
