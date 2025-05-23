---
"description": "Java Slaytlarında Aspose.Slides for Java ile Boşluk Genişliğini nasıl ayarlayacağınızı öğrenin. PowerPoint sunumlarınız için grafik görsellerini geliştirin."
"linktitle": "Java Slaytlarında Boşluk Genişliğini Ayarlama"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Boşluk Genişliğini Ayarlama"
"url": "/tr/java/data-manipulation/set-gap-width-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Boşluk Genişliğini Ayarlama


## Java için Aspose.Slides'ta Boşluk Genişliğini Ayarlamaya Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumunda bir grafik için Boşluk Genişliğini ayarlama sürecinde size rehberlik edeceğiz. Boşluk Genişliği, bir grafikteki sütunlar veya çubuklar arasındaki boşluğu belirler ve grafiğin görsel görünümünü kontrol etmenizi sağlar.

## Ön koşullar

Başlamadan önce, Aspose.Slides for Java kütüphanesinin yüklü olduğundan emin olun. Bunu Aspose web sitesinden indirebilirsiniz [Burada](https://releases.aspose.com/slides/java/).

## Adım Adım Kılavuz

Java için Aspose.Slides'ı kullanarak bir grafikte Boşluk Genişliğini ayarlamak için şu adımları izleyin:

### 1. Boş Bir Sunum Oluşturun

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";

// Boş bir sunum oluşturma 
Presentation presentation = new Presentation();
```

### 2. İlk Slayda Erişim

```java
// İlk slayda erişin
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Varsayılan Verilerle Bir Grafik Ekleyin

```java
// Varsayılan verilerle bir grafik ekleyin
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Grafik Veri Sayfasının İndeksini Ayarlayın

```java
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
```

### 5. Grafik Veri Çalışma Kitabını edinin

```java
// Grafik veri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Grafiğe Seri Ekleme

```java
// Seriyi grafiğe ekle
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Tabloya Kategoriler Ekleyin

```java
// Tabloya kategoriler ekleyin
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Seri Verilerini Doldurun

```java
// Seri verilerini doldur
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Seri veri noktalarını doldurma
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Boşluk Genişliğini Ayarlayın

```java
// Boşluk Genişliği değerini ayarlayın
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Sunumu Kaydedin

```java
// Sunumu grafikle birlikte kaydedin
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Set Gap Genişliği İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Boş sunum oluşturma 
Presentation presentation = new Presentation();
// İlk slayda erişin
ISlide slide = presentation.getSlides().get_Item(0);
// Varsayılan verilerle grafik ekle
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
// Grafik veri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Seri ekle
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Kategori Ekle
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// İkinci grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Şimdi seri verileri dolduruluyor
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// GapWidth değerini ayarla
series.getParentSeriesGroup().setGapWidth(50);
// Sunuyu grafikle kaydet
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumunda bir grafik için Boşluk Genişliğini nasıl ayarlayacağınızı öğrendiniz. Boşluk Genişliğini ayarlamak, grafiğinizdeki sütunlar veya çubuklar arasındaki boşluğu kontrol etmenizi sağlayarak verilerinizin görsel temsilini geliştirmenize olanak tanır.

## SSS

### Boşluk Genişliği değerini nasıl değiştirebilirim?

Boşluk Genişliğini değiştirmek için şunu kullanın: `setGapWidth` yöntem üzerinde `ParentSeriesGroup` grafik serisinin. Verilen örnekte, Boşluk Genişliğini 50 olarak ayarladık, ancak bu değeri istediğiniz aralığa ayarlayabilirsiniz.

### Diğer grafik özelliklerini özelleştirebilir miyim?

Evet, Java için Aspose.Slides grafik özelleştirmesi için kapsamlı yetenekler sunar. Renkler, etiketler, başlıklar ve daha fazlası gibi çeşitli grafik özelliklerini değiştirebilirsiniz. Grafik özelleştirme seçenekleri hakkında ayrıntılı bilgi için API Referansını kontrol edin.

### Daha fazla kaynak ve belgeyi nerede bulabilirim?

Java için Aspose.Slides hakkında kapsamlı belgeler ve ek kaynaklar bulabilirsiniz [Aspose web sitesi](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}