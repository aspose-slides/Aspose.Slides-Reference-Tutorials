---
"description": "Aspose.Slides kullanarak Java slaytları için düzen modlarının nasıl ayarlanacağını öğrenin. Kaynak koduyla bu adım adım kılavuzda grafik konumlandırma ve boyutlandırmayı özelleştirin."
"linktitle": "Java Slaytlarında Düzen Modunu Ayarlama"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Düzen Modunu Ayarlama"
"url": "/tr/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Düzen Modunu Ayarlama


## Java Slaytlarında Düzen Modunu Ayarlamaya Giriş

Bu eğitimde, Java slaytlarında Aspose.Slides for Java kullanarak bir grafik için düzen modunun nasıl ayarlanacağını öğreneceğiz. Düzen modu, grafiğin slayt içindeki konumunu ve boyutunu belirler.

## Ön koşullar

Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin yüklü ve ayarlanmış olduğundan emin olun. Kütüphaneyi şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Bir Sunum Oluşturun

Öncelikle yeni bir sunum oluşturmamız gerekiyor.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Adım 2: Slayt ve Grafik Ekleyin

Sonra, buna bir slayt ve bir grafik ekleyeceğiz. Bu örnekte, kümelenmiş bir sütun grafiği oluşturacağız.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Adım 3: Grafik Düzenini Ayarlayın

Şimdi, grafik için düzeni ayarlayalım. Slayt içindeki grafiğin konumunu ve boyutunu, `setX`, `setY`, `setWidth`, `setHeight` yöntemler. Ek olarak, şunu ayarlayacağız: `LayoutTargetType` düzen modunu belirlemek için.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

Bu örnekte, grafiğin düzen hedef türünü "İç" olarak ayarladık; bu, grafiğin slaydın iç alanına göre konumlandırılacağı ve boyutlandırılacağı anlamına gelir.

## Adım 4: Sunumu Kaydedin

Son olarak sunumu grafik düzeni ayarlarıyla kaydedelim.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Düzen Modu Ayarlamak İçin Tam Kaynak Kodu

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

Bu eğitimde, Java slaytlarında Aspose.Slides for Java kullanarak bir grafik için düzen modunun nasıl ayarlanacağını öğrendik. Grafiğin konumunu ve boyutunu, değerleri ayarlayarak özel gereksinimlerinize göre özelleştirebilirsiniz. `setX`, `setY`, `setWidth`, `setHeight`, Ve `setLayoutTargetType` yöntemler. Bu, slaytlarınızdaki grafiklerin yerleşimi üzerinde kontrol sahibi olmanızı sağlar.

## SSS

### Aspose.Slides for Java'da bir grafiğin düzen modunu nasıl değiştiririm?

Java için Aspose.Slides'ta bir grafiğin düzen modunu değiştirmek için şunu kullanabilirsiniz: `setLayoutTargetType` yöntemi grafiğin çizim alanında ayarlayabilirsiniz. Bunu şu şekilde ayarlayabilirsiniz: `LayoutTargetType.Inner` veya `LayoutTargetType.Outer` İstediğiniz düzene bağlı olarak.

### Slayt içindeki grafiğin konumunu ve boyutunu özelleştirebilir miyim?

Evet, slayt içindeki grafiğin konumunu ve boyutunu, `setX`, `setY`, `setWidth`, Ve `setHeight` grafik çizim alanındaki yöntemler. Bu değerleri, grafiği gereksinimlerinize göre konumlandırmak ve boyutlandırmak için ayarlayın.

### Aspose.Slides for Java hakkında daha fazla bilgiyi nerede bulabilirim?

Java için Aspose.Slides hakkında daha fazla bilgiyi şu adreste bulabilirsiniz: [belgeleme](https://reference.aspose.com/slides/java/)Java'da slaytlar ve grafiklerle etkili bir şekilde çalışmanıza yardımcı olacak ayrıntılı API referansları ve örnekler içerir.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}