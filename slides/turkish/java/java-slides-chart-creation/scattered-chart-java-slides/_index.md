---
"description": "Aspose.Slides kullanarak Java'da Dağılım Grafikleri oluşturmayı öğrenin. Sunumlarda veri görselleştirme için Java kaynak koduyla adım adım kılavuz."
"linktitle": "Java Slaytlarında Dağınık Grafik"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Dağınık Grafik"
"url": "/tr/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Dağınık Grafik


## Java için Aspose.Slides'da Dağınık Grafiklere Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir Dağılım Grafiği oluşturma sürecinde size rehberlik edeceğiz. Dağılım grafikleri, veri noktalarını iki boyutlu bir düzlemde görselleştirmek için kullanışlıdır. Adım adım talimatlar sağlayacağız ve kolaylık olması için Java kaynak kodunu ekleyeceğiz.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. [Java için Aspose.Slides](https://products.aspose.com/slides/java) kuruldu.
2. Java geliştirme ortamı kuruldu.

## Adım 1: Sunumu Başlatın

Öncelikle gerekli kütüphaneleri import edip yeni bir sunum oluşturalım.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";

// Eğer mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Yeni bir sunum oluştur
Presentation pres = new Presentation();
```

## Adım 2: Bir Slayt Ekleyin ve Dağılım Grafiğini Oluşturun

Sonra bir slayt ekleyin ve üzerinde dağılım grafiğini oluşturun. `ScatterWithSmoothLines` Bu örnekte grafik türü.

```java
// İlk slaydı alın
ISlide slide = pres.getSlides().get_Item(0);

// Dağılım grafiğinin oluşturulması
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Adım 3: Grafik Verilerini Hazırlayın

Şimdi, dağılım grafiğimiz için verileri hazırlayalım. Her biri birden fazla veri noktasına sahip iki seri ekleyeceğiz.

```java
// Varsayılan grafik veri çalışma sayfası dizinini alma
int defaultWorksheetIndex = 0;

// Grafik veri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Demo serisini sil
chart.getChartData().getSeries().clear();

// İlk seriyi ekle
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// İlk grafik serisini ele alalım
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// İlk seriye veri noktaları ekleyin
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Serinin türünü düzenle
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // İşaretleyici boyutunu değiştir
series.getMarker().setSymbol(MarkerStyleType.Star); // İşaretleyici sembolünü değiştir

// İkinci grafik serisini ele alalım
series = chart.getChartData().getSeries().get_Item(1);

// İkinci seriye veri noktaları ekleyin
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// İkinci seri için işaretleyici stilini değiştirin
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Adım 4: Sunumu Kaydedin

Son olarak sunumu dağılım grafiğiyle birlikte PPTX dosyasına kaydedin.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

İşte bu kadar! Aspose.Slides for Java kullanarak bir Dağılım Grafiği başarıyla oluşturdunuz. Artık bu örneği, belirli veri ve tasarım gereksinimlerinize uyacak şekilde daha da özelleştirebilirsiniz.

## Java Slaytlarında Dağınık Grafik İçin Tam Kaynak Kodu
```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Eğer mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Varsayılan grafiği oluşturma
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Varsayılan grafik veri çalışma sayfası dizinini alma
int defaultWorksheetIndex = 0;
// Grafik veri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Demo serisini sil
chart.getChartData().getSeries().clear();
// Yeni seri ekle
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// İlk grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Oraya yeni bir nokta (1:3) ekleyin.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Yeni nokta ekle (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Serinin türünü düzenle
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Grafik serisi işaretleyicisini değiştirme
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// İkinci grafik serisini alın
series = chart.getChartData().getSeries().get_Item(1);
// Oraya yeni bir madde (5:2) ekleyin.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Yeni nokta ekle (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Yeni nokta ekle (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Yeni nokta ekle (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Grafik serisi işaretleyicisini değiştirme
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java kullanarak Dağılım Grafiği oluşturma sürecini adım adım anlattık. Dağılım grafikleri, veri noktalarını iki boyutlu bir alanda görselleştirmek için güçlü araçlardır ve karmaşık veri ilişkilerini analiz etmeyi ve anlamayı kolaylaştırır.

## SSS

### Grafik türünü nasıl değiştirebilirim?

Grafik türünü değiştirmek için şunu kullanın: `setType` grafik serisindeki yöntemi kullanın ve istediğiniz grafik türünü sağlayın. Örneğin, `series.setType(ChartType.Line)` seriyi çizgi grafiğine çevirirdi.

### İşaretleyicinin boyutunu ve stilini nasıl özelleştirebilirim?

İşaretleyici boyutunu ve stilini değiştirmek için şunu kullanabilirsiniz: `getMarker` seri üzerindeki yöntemi ve ardından boyut ve sembol özelliklerini ayarlayın. Örneğin:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Aspose.Slides for Java belgelerinde daha fazla özelleştirme seçeneğini keşfetmekten çekinmeyin.

Değiştirmeyi unutmayın `"Your Document Directory"` Sunumu kaydetmek istediğiniz gerçek yol ile.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}