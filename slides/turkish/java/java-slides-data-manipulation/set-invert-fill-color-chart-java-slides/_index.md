---
"description": "Aspose.Slides kullanarak Java Slayt grafikleri için ters dolgu renklerinin nasıl ayarlanacağını öğrenin. Bu adım adım kılavuz ve kaynak koduyla grafik görselleştirmelerinizi geliştirin."
"linktitle": "Java Slaytlarında Ters Doldurma Renk Tablosunu Ayarla"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Ters Doldurma Renk Tablosunu Ayarla"
"url": "/tr/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Ters Doldurma Renk Tablosunu Ayarla


## Java Slaytlarında Set Invert Fill Renk Tablosuna Giriş

Bu eğitimde, Java Slides'da Aspose.Slides for Java kullanarak bir grafik için ters dolgu renginin nasıl ayarlanacağını göstereceğiz. Ters dolgu rengi, bir grafikteki negatif değerleri belirli bir renkle vurgulamak istediğinizde kullanışlı bir özelliktir. Bunu başarmak için adım adım talimatlar ve kaynak kodu sağlayacağız.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. Java için Aspose.Slides kütüphanesi kuruldu.
2. Java geliştirme ortamı kuruldu.

## Adım 1: Bir Sunum Oluşturun

Öncelikle grafiğimizi eklemek için bir sunum oluşturmamız gerekiyor. Bir sunum oluşturmak için aşağıdaki kodu kullanabilirsiniz:

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Adım 2: Bir Grafik Ekleyin

Daha sonra sunuma kümelenmiş bir sütun grafiği ekleyeceğiz. Bunu nasıl yapabileceğinizi burada bulabilirsiniz:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Adım 3: Grafik Verilerini Ayarlayın

Şimdi seriler ve kategoriler dahil olmak üzere grafik verilerini ayarlayalım:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Yeni seriler ve kategoriler ekleniyor
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Adım 4: Seri Verilerini Doldurun

Şimdi, grafik için seri verilerini dolduralım:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Adım 5: Ters Dolgu Rengini Ayarla

Grafik serisinin dolgu rengini ters çevirmek için aşağıdaki kodu kullanabilirsiniz:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Yukarıdaki kodda, negatif değerler için diziyi ters dolgu rengine ayarlıyoruz ve ters dolgu için rengi belirtiyoruz.

## Adım 6: Sunumu Kaydedin

Son olarak sunumu grafikle birlikte kaydedin:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Set Invert Fill Renk Tablosu İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Yeni seriler ve kategoriler ekleniyor
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// İlk önce grafik serisini alalım ve seri verilerini dolduralım.
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

Bu eğitimde, Java Slides'da Aspose.Slides for Java kullanarak bir grafik için ters dolgu rengini nasıl ayarlayacağınızı gösterdik. Bu özellik, grafiklerinizdeki negatif değerleri belirli bir renkle vurgulamanıza olanak tanır ve verilerinizi görsel olarak daha bilgilendirici hale getirir.

## SSS

Bu bölümde, Java Slaytlar'da Aspose.Slides for Java kullanarak bir grafik için ters dolgu rengini ayarlamayla ilgili bazı genel soruları ele alacağız.

### Java için Aspose.Slides'ı nasıl yüklerim?

Java projenize Aspose.Slides JAR dosyalarını ekleyerek Aspose.Slides for Java'yı yükleyebilirsiniz. Kütüphaneyi şuradan indirebilirsiniz: [Aspose.Slides for Java indirme sayfası](https://releases.aspose.com/slides/java/). Belirli geliştirme ortamınıza ait belgelerde sağlanan kurulum talimatlarını izleyin.

### Grafik serisindeki ters dolgunun rengini özelleştirebilir miyim?

Evet, grafik serisindeki ters dolgunun rengini özelleştirebilirsiniz. Sağlanan kod örneğinde, `series.getInvertedSolidFillColor().setColor(Color.RED)` satır, ters dolgu için rengi kırmızıya ayarlar. Değiştirebilirsiniz `Color.RED` İstediğiniz herhangi bir renkle.

### Aspose.Slides for Java'da grafik türünü nasıl değiştirebilirim?

Grafik türünü değiştirerek değiştirebilirsiniz. `ChartType` bir grafik sunuma eklerken parametre. Kod örneğinde, `ChartType.ClusteredColumn`Uygun grafik türünü belirterek çizgi grafikleri, çubuk grafikleri, pasta grafikleri vb. gibi diğer grafik türlerini keşfedebilirsiniz. `ChartType` enum değeri.

### Bir grafiğe birden fazla veri serisi nasıl eklerim?

Bir grafiğe birden fazla veri serisi eklemek için şunu kullanabilirsiniz: `chart.getChartData().getSeries().add(...)` Eklemek istediğiniz her seri için yöntem. Grafiğinizi birden fazla seriyle doldurmak için her seri için uygun veri noktalarını ve etiketleri sağladığınızdan emin olun.

### Grafik görünümünün diğer yönlerini özelleştirmenin bir yolu var mı?

Evet, Aspose.Slides for Java kullanarak eksen etiketleri, başlıklar, açıklamalar ve daha fazlası dahil olmak üzere grafik görünümünün çeşitli yönlerini özelleştirebilirsiniz. Grafik öğelerini ve görünümünü özelleştirme hakkında ayrıntılı kılavuz için belgelere bakın.

### Tabloyu farklı formatlarda kaydedebilir miyim?

Evet, Java için Aspose.Slides'ı kullanarak grafiği farklı biçimlerde kaydedebilirsiniz. Sağlanan kod örneğinde, sunumu bir PPTX dosyası olarak kaydettik. Farklı kullanabilirsiniz `SaveFormat` İhtiyaçlarınıza bağlı olarak PDF, PNG veya SVG gibi diğer formatlarda kaydetme seçenekleri.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}