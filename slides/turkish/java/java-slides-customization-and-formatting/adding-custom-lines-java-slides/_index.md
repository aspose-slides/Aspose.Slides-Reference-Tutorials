---
title: Java Slaytlarına Özel Satır Ekleme
linktitle: Java Slaytlarına Özel Satır Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Java Slaytlarınızı Özel Çizgilerle Geliştirin. Aspose.Slides for Java'yı kullanan adım adım kılavuz. Etkili görseller için sunumlara satır eklemeyi ve satırları özelleştirmeyi öğrenin.
weight: 10
url: /tr/java/customization-and-formatting/adding-custom-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java Slaytlarına Özel Satır Eklemeye Giriş

Bu eğitimde Aspose.Slides for Java'yı kullanarak Java slaytlarınıza nasıl özel satırlar ekleyeceğinizi öğreneceksiniz. Slaytlarınızın görsel sunumunu geliştirmek ve belirli içeriği vurgulamak için özel çizgiler kullanılabilir. Bunu başarmak için size kaynak koduyla birlikte adım adım talimatlar sunacağız. Başlayalım!

## Önkoşullar

 Başlamadan önce Java projenizde Java için Aspose.Slides kütüphanesinin kurulu olduğundan emin olun. Kütüphaneyi web sitesinden indirebilirsiniz:[Aspose.Slides for Java](https://releases.aspose.com/slides/java/)

## Adım 1: Sunumu Başlatın

Öncelikle yeni bir sunum oluşturmanız gerekiyor. Bu örnekte boş bir sunum oluşturacağız.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. Adım: Grafik Ekleme

Daha sonra slayta bir grafik ekleyeceğiz. Bu örnekte kümelenmiş bir sütun grafiği ekliyoruz. İhtiyaçlarınıza uygun grafik türünü seçebilirsiniz.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## 3. Adım: Özel Bir Hat Ekleyin

 Şimdi grafiğe özel bir çizgi ekleyelim. Biz bir yaratacağız`IAutoShape` türün`ShapeType.Line` ve grafiğin içine yerleştirin.

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## Adım 4: Çizgiyi Özelleştirin

Özelliklerini ayarlayarak çizginin görünümünü özelleştirebilirsiniz. Bu örnekte çizgi rengini kırmızı olarak ayarlıyoruz.

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Adım 5: Sunuyu Kaydetme

Son olarak sunuyu istediğiniz konuma kaydedin.

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## Java Slaytlarına Özel Satır Eklemek İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
	shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
	shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
	pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Tebrikler! Aspose.Slides for Java'yı kullanarak Java slaydınıza başarıyla özel bir satır eklediniz. İstediğiniz görsel efektleri elde etmek için çizginin özelliklerini daha da özelleştirebilirsiniz.

## SSS'ler

### Çizgi rengini nasıl değiştiririm?

Çizgi rengini değiştirmek için aşağıdaki kodu kullanın:
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

 Yer değiştirmek`YOUR_COLOR` İstenilen renk ile.

### Diğer şekillere özel çizgiler ekleyebilir miyim?

 Evet, yalnızca grafiklere değil, çeşitli şekillere de özel çizgiler ekleyebilirsiniz. Basitçe bir`IAutoShape` ve ihtiyaçlarınıza göre özelleştirin.

### Çizgi kalınlığını nasıl değiştirebilirim?

 Çizgi kalınlığını ayarlayarak değiştirebilirsiniz.`Width` satır formatının özelliği. Örneğin:
```java
shape.getLineFormat().setWidth(2); // Çizgi kalınlığını 2 noktaya ayarla
```

### Bir slayta birden fazla satır eklemek mümkün mü?

Evet, bu eğitimde belirtilen adımları tekrarlayarak bir slayda birden fazla satır ekleyebilirsiniz. Her satır bağımsız olarak özelleştirilebilir.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
