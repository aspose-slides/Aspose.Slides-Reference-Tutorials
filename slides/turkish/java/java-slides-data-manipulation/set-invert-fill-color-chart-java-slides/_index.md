---
title: Java Slaytlarında Ters Çevirme Renk Tablosunu Ayarlama
linktitle: Java Slaytlarında Ters Çevirme Renk Tablosunu Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides'ı kullanarak Java Slides grafikleri için dolgu renklerini ters çevirmeyi nasıl ayarlayacağınızı öğrenin. Bu adım adım kılavuz ve kaynak koduyla grafik görselleştirmelerinizi geliştirin.
weight: 22
url: /tr/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java Slaytlarında Ters Çevirme Dolgu Renk Tablosunu Ayarlamaya Giriş

Bu eğitimde, Java Slides'da Aspose.Slides for Java kullanarak bir grafik için ters dolgu renginin nasıl ayarlanacağını göstereceğiz. Dolgu rengini ters çevirmek, bir grafikteki negatif değerleri belirli bir renkle vurgulamak istediğinizde kullanışlı bir özelliktir. Bunu başarmak için adım adım talimatlar ve kaynak kodu sağlayacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. Aspose.Slides for Java kütüphanesi kuruldu.
2. Java geliştirme ortamı kuruldu.

## 1. Adım: Bir Sunu Oluşturun

Öncelikle grafiğimizi ekleyeceğimiz bir sunum oluşturmamız gerekiyor. Sunum oluşturmak için aşağıdaki kodu kullanabilirsiniz:

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. Adım: Grafik Ekleme

Daha sonra sunuma kümelenmiş bir sütun grafiği ekleyeceğiz. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## 3. Adım: Grafik Verilerini Ayarlayın

Şimdi seriler ve kategoriler de dahil olmak üzere grafik verilerini ayarlayalım:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Yeni seri ve kategoriler ekleme
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Adım 4: Seri Verilerini Doldurun

Şimdi grafiğin seri verilerini dolduralım:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Adım 5: Ters Çevirme Dolgu Rengini Ayarlayın

Grafik serisinin ters çevir dolgu rengini ayarlamak için aşağıdaki kodu kullanabilirsiniz:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Yukarıdaki kodda seriyi negatif değerler için dolgu rengini ters çevirecek şekilde ayarladık ve ters çevrilmiş dolgunun rengini belirledik.

## Adım 6: Sunuyu Kaydetme

Son olarak sunumu grafikle birlikte kaydedin:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Ters Çevirme Dolgu Renk Tablosunu Ayarlamak İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Yeni seri ve kategoriler ekleme
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// İlk grafik serisini alın ve seri verilerini doldurun.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde size Aspose.Slides for Java kullanarak Java Slides'ta bir grafiğin ters dolgu rengini nasıl ayarlayacağınızı gösterdik. Bu özellik, grafiklerinizde negatif değerleri belirli bir renkle vurgulamanıza olanak tanıyarak verilerinizin görsel olarak daha bilgilendirici olmasını sağlar.

## SSS'ler

Bu bölümde Aspose.Slides for Java kullanarak Java Slides'ta bir grafik için ters dolgu rengini ayarlamayla ilgili bazı genel soruları ele alacağız.

### Aspose.Slides for Java'yı nasıl yüklerim?

 Aspose.Slides JAR dosyalarını Java projenize ekleyerek Aspose.Slides for Java'yı yükleyebilirsiniz. Kütüphaneyi adresinden indirebilirsiniz.[Aspose.Slides for Java indirme sayfası](https://releases.aspose.com/slides/java/). Özel geliştirme ortamınıza yönelik belgelerde sağlanan kurulum talimatlarını izleyin.

### Grafik serisindeki ters dolgunun rengini özelleştirebilir miyim?

Evet, grafik serisindeki ters dolgunun rengini özelleştirebilirsiniz. Sağlanan kod örneğinde,`series.getInvertedSolidFillColor().setColor(Color.RED)` çizgisi, ters dolgunun rengini kırmızıya ayarlar. Değiştirebilirsin`Color.RED` dilediğiniz diğer renk ile.

### Aspose.Slides for Java'da grafik türünü nasıl değiştirebilirim?

 Grafik türünü değiştirerek değiştirebilirsiniz.`ChartType` Sunuya bir grafik eklerken parametre. Kod örneğinde şunu kullandık:`ChartType.ClusteredColumn` . Uygun grafiği belirterek çizgi grafikler, çubuk grafikler, pasta grafikler vb. gibi diğer grafik türlerini keşfedebilirsiniz.`ChartType` numaralandırma değeri.

### Bir grafiğe birden fazla veri serisini nasıl eklerim?

 Bir grafiğe birden fazla veri serisi eklemek için`chart.getChartData().getSeries().add(...)` Eklemek istediğiniz her seri için yöntem. Grafiğinizi birden fazla seriyle doldurmak için her seriye uygun veri noktalarını ve etiketleri sağladığınızdan emin olun.

### Grafik görünümünün diğer yönlerini özelleştirmenin bir yolu var mı?

Evet, Aspose.Slides for Java'yı kullanarak eksen etiketleri, başlıklar, açıklamalar ve daha fazlası dahil olmak üzere grafik görünümünün çeşitli yönlerini özelleştirebilirsiniz. Grafik öğelerinin ve görünümün özelleştirilmesine ilişkin ayrıntılı rehberlik için belgelere bakın.

### Grafiği farklı formatlarda kaydedebilir miyim?

 Evet, Aspose.Slides for Java'yı kullanarak grafiği farklı formatlarda kaydedebilirsiniz. Verilen kod örneğinde sunumu PPTX dosyası olarak kaydettik. Farklı kullanabilirsiniz`SaveFormat` Gereksinimlerinize bağlı olarak PDF, PNG veya SVG gibi diğer formatlarda kaydetme seçenekleri.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
