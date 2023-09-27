---
title: Java Slaytlarında Formülleri Hesaplama
linktitle: Java Slaytlarında Formülleri Hesaplama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak Java Slides'ta formülleri nasıl hesaplayacağınızı öğrenin. Dinamik PowerPoint sunumları için kaynak kodunu içeren adım adım kılavuz.
type: docs
weight: 10
url: /tr/java/data-manipulation/calculate-formulas-java-slides/
---

## Aspose.Slides Kullanarak Java Slaytlarında Formül Hesaplamaya Giriş

Bu kılavuzda, Aspose.Slides for Java API'sini kullanarak Java Slides'taki formüllerin nasıl hesaplanacağını göstereceğiz. Aspose.Slides, PowerPoint sunumlarıyla çalışmak için güçlü bir kütüphanedir ve slaytlarda grafikleri yönetmek ve formül hesaplamaları yapmak için özellikler sağlar.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Java Geliştirme Ortamı
-  Aspose.Slides for Java kütüphanesi (Şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/slides/java/)
- Java programlamayla ilgili temel bilgiler

## 1. Adım: Yeni Bir Sunu Oluşturun

Öncelikle yeni bir PowerPoint sunumu oluşturalım ve ona bir slayt ekleyelim. Bu örnekte tek slaytla çalışacağız.

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## Adım 2: Slayta Grafik Ekleme

Şimdi slayta kümelenmiş bir sütun grafiği ekleyelim. Bu grafiği formül hesaplamalarını göstermek için kullanacağız.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## 3. Adım: Formülleri ve Değerleri Ayarlayın

Daha sonra Aspose.Slides API'sini kullanarak grafik veri hücreleri için formüller ve değerler ayarlayacağız. Bu hücrelerin formüllerini hesaplayacağız.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// A1 hücresinin formülünü ayarla
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// A2 hücresi için değeri ayarla
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// B2 hücresinin formülünü ayarla
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// C2 hücresinin formülünü ayarla
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// A1 hücresinin formülünü tekrar ayarla
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## 4. Adım: Sunuyu Kaydetme

Son olarak hesaplanan formüllerle değiştirilen sunumu kaydedelim.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## Java Slaytlarındaki Formülleri Hesaplamak İçin Tam Kaynak Kodu

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Bu kılavuzda Aspose.Slides for Java kullanarak Java Slides'taki formüllerin nasıl hesaplanacağını öğrendik. Yeni bir sunum oluşturduk, ona grafik ekledik, grafik veri hücreleri için formüller ve değerler belirledik, hesaplanan formüllerle sunumu kaydettik.

## SSS'ler

### Grafik veri hücreleri için formülleri nasıl ayarlarım?

 Grafik veri hücreleri için formülleri aşağıdakileri kullanarak ayarlayabilirsiniz:`setFormula` yöntemi`IChartDataCell` Aspose.Slides'ta.

### Grafik veri hücreleri için değerleri nasıl ayarlarım?

 Grafik veri hücreleri için değerleri aşağıdakileri kullanarak ayarlayabilirsiniz:`setValue` yöntemi`IChartDataCell` Aspose.Slides'ta.

### Çalışma kitabındaki formülleri nasıl hesaplarım?

 Bir çalışma kitabındaki formülleri aşağıdakileri kullanarak hesaplayabilirsiniz:`calculateFormulas` yöntemi`IChartDataWorkbook` Aspose.Slides'ta.
