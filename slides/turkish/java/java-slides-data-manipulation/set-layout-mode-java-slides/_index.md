---
title: Java Slaytlarında Düzen Modunu Ayarlama
linktitle: Java Slaytlarında Düzen Modunu Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides'ı kullanarak Java slaytları için düzen modlarını nasıl ayarlayacağınızı öğrenin. Kaynak kodlu bu adım adım kılavuzda grafik konumlandırmasını ve boyutlandırmasını özelleştirin.
type: docs
weight: 23
url: /tr/java/data-manipulation/set-layout-mode-java-slides/
---

## Java Slaytlarında Düzen Modunu Ayarlamaya Giriş

Bu eğitimde Aspose.Slides for Java kullanarak Java slaytlarındaki bir grafiğin düzen modunu nasıl ayarlayacağımızı öğreneceğiz. Düzen modu, grafiğin slayt içindeki konumunu ve boyutlarını belirler.

## Önkoşullar

 Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin kurulu ve kurulu olduğundan emin olun. Kütüphaneyi adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/java/).

## 1. Adım: Bir Sunu Oluşturun

Öncelikle yeni bir sunum oluşturmamız gerekiyor.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 2. Adım: Slayt ve Grafik Ekleme

Daha sonra buna bir slayt ve grafik ekleyeceğiz. Bu örnekte kümelenmiş bir sütun grafiği oluşturacağız.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## 3. Adım: Grafik Düzenini Ayarlayın

 Şimdi grafiğin düzenini ayarlayalım. Grafiğin slayt içindeki konumunu ve boyutunu aşağıdaki düğmeyi kullanarak ayarlayacağız:`setX`, `setY`, `setWidth`, `setHeight` yöntemler. Ek olarak, ayarlayacağız`LayoutTargetType` Düzen modunu belirlemek için.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

Bu örnekte grafiği, düzen hedef türü "İç" olacak şekilde ayarladık; bu, slaydın iç alanına göre konumlandırılacağı ve boyutlandırılacağı anlamına gelir.

## 4. Adım: Sunuyu Kaydetme

Son olarak sunumu grafik düzeni ayarlarıyla kaydedelim.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Düzen Modunu Ayarlamak İçin Kaynak Kodunu Tamamlayın

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

 Bu eğitimde, Aspose.Slides for Java'yı kullanarak Java slaytlarındaki bir grafiğin düzen modunu nasıl ayarlayacağımızı öğrendik. Tablodaki değerleri ayarlayarak grafiğin konumunu ve boyutunu özel gereksinimlerinize göre özelleştirebilirsiniz.`setX`, `setY`, `setWidth`, `setHeight` , Ve`setLayoutTargetType`yöntemler. Bu, slaytlarınızın içindeki grafiklerin yerleşimi üzerinde kontrol sahibi olmanızı sağlar.

## SSS'ler

### Aspose.Slides for Java'da bir grafiğin düzen modunu nasıl değiştiririm?

 Aspose.Slides for Java'da bir grafiğin düzen modunu değiştirmek için`setLayoutTargetType` Grafiğin çizim alanındaki yöntem. İkisinden birine ayarlayabilirsiniz`LayoutTargetType.Inner` veya`LayoutTargetType.Outer` İstediğiniz düzene bağlı olarak.

### Slayttaki grafiğin konumunu ve boyutunu özelleştirebilir miyim?

 Evet, slayt içindeki grafiğin konumunu ve boyutunu özelleştirebilirsiniz.`setX`, `setY`, `setWidth` , Ve`setHeight` Grafiğin çizim alanındaki yöntemler. Grafiği gereksinimlerinize göre konumlandırmak ve boyutlandırmak için bu değerleri ayarlayın.

### Aspose.Slides for Java hakkında daha fazla bilgiyi nerede bulabilirim?

 Aspose.Slides for Java hakkında daha fazla bilgiyi şurada bulabilirsiniz:[dokümantasyon](https://reference.aspose.com/slides/java/). Java'da slaytlar ve grafiklerle etkili bir şekilde çalışmanıza yardımcı olacak ayrıntılı API referansları ve örnekleri içerir.