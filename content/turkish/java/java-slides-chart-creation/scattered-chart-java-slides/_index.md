---
title: Java Slaytlarında Dağınık Grafik
linktitle: Java Slaytlarında Dağınık Grafik
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides'ı kullanarak Java'da Dağılım Grafikleri oluşturmayı öğrenin. Sunumlarda veri görselleştirmesi için Java kaynak kodunu içeren adım adım kılavuz.
type: docs
weight: 11
url: /tr/java/chart-creation/scattered-chart-java-slides/
---

## Aspose.Slides for Java'da Dağınık Grafiğe Giriş

Bu eğitimde Aspose.Slides for Java'yı kullanarak Dağılım Grafiği oluşturma sürecinde size rehberlik edeceğiz. Dağılım grafikleri, veri noktalarını iki boyutlu bir düzlemde görselleştirmek için kullanışlıdır. Size kolaylık sağlamak için adım adım talimatlar sunacağız ve Java kaynak kodunu ekleyeceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. [Java için Aspose.Slides](https://products.aspose.com/slides/java) Kurulmuş.
2. Bir Java geliştirme ortamı kuruldu.

## Adım 1: Sunumu Başlatın

Öncelikle gerekli kütüphaneleri içe aktarın ve yeni bir sunum oluşturun.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";

// Henüz mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Yeni bir sunu oluşturma
Presentation pres = new Presentation();
```

## Adım 2: Slayt Ekleyin ve Dağılım Grafiği Oluşturun

 Daha sonra bir slayt ekleyin ve üzerinde dağılım grafiğini oluşturun. biz kullanacağız`ScatterWithSmoothLines` Bu örnekte grafik türü.

```java
// İlk slaydı alın
ISlide slide = pres.getSlides().get_Item(0);

// Dağılım grafiğini oluşturma
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Adım 3: Grafik Verilerini Hazırlayın

Şimdi dağılım grafiğimiz için verileri hazırlayalım. Her biri birden fazla veri noktasına sahip iki seri ekleyeceğiz.

```java
// Varsayılan grafik verileri çalışma sayfası dizinini alma
int defaultWorksheetIndex = 0;

//Grafik verileri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Demo serisini sil
chart.getChartData().getSeries().clear();

// İlk seriyi ekle
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// İlk grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// İlk seriye veri noktaları ekleyin
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Serinin türünü düzenleyin
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // İşaretçi boyutunu değiştir
series.getMarker().setSymbol(MarkerStyleType.Star); // İşaretçi sembolünü değiştir

// İkinci grafik serisini alın
series = chart.getChartData().getSeries().get_Item(1);

// İkinci seriye veri noktaları ekleyin
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// İkinci serinin işaret stilini değiştirme
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## 4. Adım: Sunuyu Kaydetme

Son olarak, dağılım grafiğini içeren sunumu bir PPTX dosyasına kaydedin.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Bu kadar! Aspose.Slides for Java'yı kullanarak başarıyla bir Dağılım Grafiği oluşturdunuz. Artık bu örneği özel verilerinize ve tasarım gereksinimlerinize uyacak şekilde daha da özelleştirebilirsiniz.

## Java Slaytlarındaki Dağınık Grafik İçin Tam Kaynak Kodu
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Henüz mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Varsayılan grafiği oluşturma
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Varsayılan grafik verileri çalışma sayfası dizinini alma
int defaultWorksheetIndex = 0;
//Grafik verileri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Demo serisini sil
chart.getChartData().getSeries().clear();
// Yeni seri ekle
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// İlk grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Buraya yeni noktayı (1:3) ekleyin.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Yeni nokta ekle (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Serinin türünü düzenleyin
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Grafik serisi işaretçisini değiştirme
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// İkinci grafik serisini alın
series = chart.getChartData().getSeries().get_Item(1);
// Buraya yeni noktayı (5:2) ekleyin.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Yeni nokta ekle (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
//Yeni nokta ekle (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Yeni nokta ekle (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Grafik serisi işaretçisini değiştirme
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde size Aspose.Slides for Java'yı kullanarak Dağılım Grafiği oluşturma sürecini anlattık. Dağılım grafikleri, iki boyutlu bir uzaydaki veri noktalarını görselleştirmeye yönelik güçlü araçlardır ve karmaşık veri ilişkilerini analiz etmeyi ve anlamayı kolaylaştırır.

## SSS'ler

### Grafik türünü nasıl değiştirebilirim?

 Grafik türünü değiştirmek için`setType` Grafik serisindeki yöntemi seçin ve istenen grafik türünü sağlayın. Örneğin,`series.setType(ChartType.Line)` seriyi çizgi grafiğine dönüştürür.

### İşaretçi boyutunu ve stilini nasıl özelleştiririm?

 İşaretçi boyutunu ve stilini kullanarak değiştirebilirsiniz.`getMarker` serideki yöntemi seçin ve ardından boyut ve sembol özelliklerini ayarlayın. Örneğin:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Aspose.Slides for Java belgelerinde daha fazla özelleştirme seçeneğini keşfetmekten çekinmeyin.

 Değiştirmeyi unutmayın`"Your Document Directory"` sunuyu kaydetmek istediğiniz asıl yolla.