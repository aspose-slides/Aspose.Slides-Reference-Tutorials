---
title: Java Slaytlarındaki Grafik Veri Hücresi Formülleri
linktitle: Java Slaytlarındaki Grafik Veri Hücresi Formülleri
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak Java PowerPoint sunumlarında grafik veri hücresi formüllerini nasıl ayarlayacağınızı öğrenin. Formüllerle dinamik grafikler oluşturun.
weight: 11
url: /tr/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarındaki Grafik Veri Hücresi Formülleri


## Aspose.Slides for Java'da Grafik Veri Hücresi Formüllerine Giriş

Bu eğitimde Aspose.Slides for Java'yı kullanarak grafik veri hücresi formülleriyle nasıl çalışılacağını keşfedeceğiz. Aspose.Slides ile PowerPoint sunumlarında, veri hücreleri için formüllerin ayarlanması da dahil olmak üzere grafikler oluşturabilir ve değiştirebilirsiniz.

## Önkoşullar

 Başlamadan önce Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## 1. Adım: PowerPoint Sunusu Oluşturun

Öncelikle yeni bir PowerPoint sunusu oluşturalım ve ona bir grafik ekleyelim.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // İlk slayda grafik ekleme
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Grafik verileri için çalışma kitabını edinin
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Veri hücresi işlemlerine devam
    // ...
    
    // Sunuyu kaydet
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Adım 2: Veri Hücreleri İçin Formülleri Ayarlayın

Şimdi grafikteki belirli veri hücreleri için formüller ayarlayalım. Bu örnekte iki farklı hücre için formül ayarlayacağız.

### Hücre 1: A1 Gösterimini Kullanma

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

Yukarıdaki kodda A1 gösterimini kullanarak B2 hücresi için bir formül belirledik. Formül, F2'den H5'e kadar olan hücrelerin toplamını hesaplar ve sonuca 1 ekler.

### Hücre 2: R1C1 Gösterimini Kullanma

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Burada R1C1 gösterimini kullanarak C2 hücresi için bir formül belirledik. Formül, R2C6 ila R5C8 aralığındaki maksimum değeri hesaplar ve ardından bunu 3'e böler.

## Adım 3: Formülleri Hesaplayın

Formülleri ayarladıktan sonra aşağıdaki kodu kullanarak hesaplamanız önemlidir:

```java
workbook.calculateFormulas();
```

Bu adım, grafiğin formüllere göre güncellenen değerleri yansıtmasını sağlar.

## 4. Adım: Sunuyu Kaydetme

Son olarak değiştirilen sunumu bir dosyaya kaydedin.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Java Slaytlarındaki Grafik Veri Hücresi Formülleri İçin Tam Kaynak Kodu

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides for Java'da grafik veri hücresi formülleriyle nasıl çalışılacağını araştırdık. PowerPoint sunusu oluşturmayı, grafik eklemeyi, veri hücreleri için formüller ayarlamayı, formülleri hesaplamayı ve sunuyu kaydetmeyi ele aldık. Artık sunumlarınızda dinamik ve veriye dayalı grafikler oluşturmak için bu yeteneklerden yararlanabilirsiniz.

## SSS

### Belirli bir slayta nasıl grafik eklerim?

 Belirli bir slayda grafik eklemek için`getSlides().get_Item(slideIndex)` İstenilen slayta erişme yöntemini seçin ve ardından`addChart` Grafiği ekleme yöntemi.

### Veri hücrelerinde farklı türde formüller kullanabilir miyim?

Evet, veri hücresi formüllerinde matematiksel işlemler, işlevler ve diğer hücrelere yapılan başvurular da dahil olmak üzere çeşitli formül türlerini kullanabilirsiniz.

### Grafik türünü nasıl değiştiririm?

 Grafik türünü kullanarak değiştirebilirsiniz.`setChartType` konusundaki yöntem`IChart` nesne ve istenilenin belirtilmesi`ChartType`.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
