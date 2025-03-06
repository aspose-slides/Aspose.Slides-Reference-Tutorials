---
title: Java Slaytlarında Konum Eksenini Ayarlama
linktitle: Java Slaytlarında Konum Eksenini Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java ile Grafiklerinizi Geliştirin. Java slaytlarında konum eksenini nasıl ayarlayacağınızı, çarpıcı sunumlar oluşturmayı ve grafik düzenlerini kolaylıkla nasıl özelleştireceğinizi öğrenin.
weight: 16
url: /tr/java/customization-and-formatting/setting-position-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Konum Eksenini Ayarlama


## Aspose.Slides for Java'da Konum Eksenini Ayarlamaya Giriş

Bu eğitimde Aspose.Slides for Java kullanarak bir grafikte konum eksenini nasıl ayarlayacağımızı öğreneceğiz. Grafiğinizin görünümünü ve düzenini özelleştirmek istediğinizde ekseni konumlandırmak faydalı olabilir. Kümelenmiş bir sütun grafiği oluşturacağız ve yatay eksenin kategoriler arasındaki konumunu ayarlayacağız.

## Önkoşullar

 Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin kurulu ve kurulu olduğundan emin olun. Kütüphaneyi adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Sunum Oluşturma

Öncelikle üzerinde çalışacağımız yeni bir sunum oluşturalım:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 Değiştirdiğinizden emin olun`"Your Document Directory"` belge dizininizin gerçek yolu ile.

## Adım 2: Grafik Ekleme

Daha sonra slayta kümelenmiş bir sütun grafiği ekleyeceğiz. Grafiğin grafik türünü, konumunu (x, y koordinatları) ve boyutlarını (genişlik ve yükseklik) belirtiriz:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Burada (50, 50) konumuna genişliği 450, yüksekliği 300 olan kümelenmiş sütun grafiği ekledik. Bu değerleri ihtiyacınıza göre ayarlayabilirsiniz.

## Adım 3: Konum Ekseninin Ayarlanması

Kategoriler arasındaki konum eksenini ayarlamak için aşağıdaki kodu kullanabilirsiniz:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Bu kod, belirli grafik düzenleri için yararlı olabilecek kategoriler arasında görüntülenecek yatay ekseni ayarlar.

## Adım 4: Sunumu Kaydetme

Son olarak sunumu grafikle birlikte kaydedelim:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 Yer değiştirmek`"AsposeClusteredColumnChart.pptx"` İstediğiniz dosya adı ile.

Bu kadar! Aspose.Slides for Java'yı kullanarak başarıyla kümelenmiş bir sütun grafiği oluşturdunuz ve kategoriler arasındaki konum eksenini ayarladınız.

## Kaynak Kodunu Tamamlayın
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides for Java kullanarak bir grafikte konum ekseninin nasıl ayarlanacağını araştırdık. Bu kılavuzda özetlenen adımları izleyerek, kümelenmiş bir sütun grafiğinin nasıl oluşturulacağını ve yatay ekseni kategoriler arasına konumlandırarak görünümünü nasıl özelleştireceğinizi öğrendiniz. Aspose.Slides for Java, grafikler ve sunumlarla çalışmak için güçlü özellikler sunarak onu Java geliştiricileri için değerli bir araç haline getiriyor.

## SSS'ler

### Grafiği nasıl daha da özelleştirebilirim?

Veri serileri, grafik başlığı, göstergeler ve daha fazlası dahil olmak üzere grafiğin çeşitli yönlerini özelleştirebilirsiniz. Bakın[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/) ayrıntılı talimatlar ve örnekler için.

### Grafik türünü değiştirebilir miyim?

 Evet, grafik türünü değiştirerek değiştirebilirsiniz.`ChartType` Grafiği eklerken parametre. Aspose.Slides for Java, çubuk grafikler, çizgi grafikler ve daha fazlası gibi çeşitli grafik türlerini destekler.

### Daha fazla örnek ve belgeyi nerede bulabilirim?

 Kapsamlı belgeler ve daha fazla örnek bulabilirsiniz.[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/) sayfa.

Sistem kaynaklarını serbest bırakmak için sunum nesnesini işiniz bittiğinde elden çıkarmayı unutmayın:

```java
if (pres != null) pres.dispose();
```

Bu eğitimde bu kadar. Aspose.Slides for Java'yı kullanarak bir grafikte konum eksenini nasıl ayarlayacağınızı öğrendiniz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
