---
title: Java Slaytlarındaki Grafik Trend Çizgileri
linktitle: Java Slaytlarındaki Grafik Trend Çizgileri
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slides'a çeşitli trend çizgilerini nasıl ekleyeceğinizi öğrenin. Etkili veri görselleştirmesi için kod örnekleri içeren adım adım kılavuz.
weight: 15
url: /tr/java/data-manipulation/chart-trend-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarındaki Grafik Trend Çizgileri


## Java Slaytlarındaki Grafik Trend Çizgilerine Giriş: Adım Adım Kılavuz

Bu kapsamlı kılavuzda, Aspose.Slides for Java kullanarak Java Slides'ta grafik trend çizgilerinin nasıl oluşturulacağını keşfedeceğiz. Grafik trend çizgileri, veri trendlerini etkili bir şekilde görselleştirmenize ve analiz etmenize yardımcı olarak sunumlarınıza değerli bir katkı olabilir. Açık açıklamalar ve kod örnekleriyle süreç boyunca size yol göstereceğiz.

## Önkoşullar

Grafik trend çizgileri oluşturmaya başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Java Geliştirme Ortamı
- Aspose.Slides for Java Kütüphanesi
- Seçtiğiniz Bir Kod Düzenleyici

## 1. Adım: Başlarken

Gerekli ortamı kurup yeni bir sunum oluşturarak başlayalım:

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Henüz mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Boş sunum oluşturma
Presentation pres = new Presentation();
```

Sunumumuzu başlattık ve artık kümelenmiş bir sütun grafiği eklemeye hazırız:

```java
// Kümelenmiş sütun grafiği oluşturma
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Adım 2: Üstel Trend Çizgisi Ekleme

Grafik serimize üstel bir trend çizgisi ekleyerek başlayalım:

```java
// Grafik serisi 1 için üstel trend çizgisi ekleme
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Adım 3: Doğrusal Trend Çizgisi Ekleme

Daha sonra grafik serimize doğrusal bir trend çizgisi ekleyeceğiz:

```java
// Grafik serisi 1 için doğrusal trend çizgisi ekleme
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Adım 4: Logaritmik Trend Çizgisi Ekleme

Şimdi farklı bir grafik serisine logaritmik bir trend çizgisi ekleyelim:

```java
// Grafik serisi 2 için logaritmik eğilim çizgisi ekleme
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Adım 5: Hareketli Ortalama Trend Çizgisini Ekleme

Ayrıca hareketli ortalama trend çizgisi de ekleyebiliriz:

```java
// Grafik serisi 2 için hareketli ortalama trend çizgisi ekleniyor
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Adım 6: Polinom Trend Çizgisini Ekleme

Polinom eğilim çizgisi ekleme:

```java
// Grafik serisi 3 için polinom eğilim çizgisi ekleme
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Adım 7: Güç Trend Çizgisini Ekleme

Son olarak bir güç trend çizgisi ekleyelim:

```java
// Grafik serisi 3 için güç trend çizgisi ekleniyor
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Adım 8: Sunumu Kaydetme

Artık grafiğimize çeşitli trend çizgileri eklediğimize göre sunumu kaydedelim:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Tebrikler! Aspose.Slides for Java'yı kullanarak Java Slides'ta farklı türde trend çizgileri içeren bir sunumu başarıyla oluşturdunuz.

## Java Slaytlarındaki Grafik Trend Çizgileri İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Henüz mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Boş sunum oluşturma
Presentation pres = new Presentation();
// Kümelenmiş sütun grafiği oluşturma
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Grafik serisi 1 için potansiyel trend çizgisi ekleme
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Grafik serisi 1 için Doğrusal trend çizgisi ekleme
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Grafik serisi 2 için Logaritmik trend çizgisi ekleme
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Grafik serisi 2 için MovingAverage trend çizgisi ekleniyor
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Grafik serisi 3 için Polinom eğilim çizgisi ekleme
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Grafik serisi 3 için Güç eğilim çizgisi ekleniyor
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Sunum kaydediliyor
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java kütüphanesini kullanarak Java Slides'daki grafiklere farklı türde trend çizgilerinin nasıl ekleneceğini öğrendik. İster veri analizi üzerinde çalışıyor olun ister bilgilendirici sunumlar oluşturuyor olun, trendleri görselleştirme yeteneği güçlü bir araç olabilir.

## SSS'ler

### Aspose.Slides for Java'da trend çizgisinin rengini nasıl değiştiririm?

 Bir trend çizgisinin rengini değiştirmek için`getSolidFillColor().setColor(Color)` Doğrusal bir trend çizgisi ekleme örneğinde gösterildiği gibi yöntem.

### Tek bir grafik serisine birden fazla trend çizgisi ekleyebilir miyim?

Evet, tek bir grafik serisine birden fazla trend çizgisi ekleyebilirsiniz. Sadece aramanız yeterli`getTrendLines().add()` Eklemek istediğiniz her trend çizgisi için yöntemi seçin.

### Aspose.Slides for Java'daki bir grafikten trend çizgisini nasıl kaldırırım?

 Bir grafikten trend çizgisini kaldırmak için`removeAt(int index)` kaldırmak istediğiniz trend çizgisinin indeksini belirterek yöntemini seçin.

### Trend çizgisi denklemi görünümünü özelleştirmek mümkün mü?

 Evet, trend çizgisi denklemi görünümünü kullanarak özelleştirebilirsiniz.`setDisplayEquation(boolean)` Örnekte gösterildiği gibi yöntem.

### Aspose.Slides for Java için daha fazla kaynağa ve örneğe nasıl erişebilirim?

 Aspose.Slides for Java ile ilgili ek kaynaklara, belgelere ve örneklere şu adresten erişebilirsiniz:[Web sitesi](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
