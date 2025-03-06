---
title: Java Slaytlarında Boşluk Genişliğini Ayarlama
linktitle: Java Slaytlarında Boşluk Genişliğini Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java ile Java Slides'ta Boşluk Genişliğini nasıl ayarlayacağınızı öğrenin. PowerPoint sunumlarınız için grafik görsellerini geliştirin.
weight: 21
url: /tr/java/data-manipulation/set-gap-width-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides for Java'da Boşluk Genişliğini Ayarlamaya Giriş

Bu eğitimde, Aspose.Slides for Java'yı kullanarak PowerPoint sunumundaki bir grafik için Boşluk Genişliğini ayarlama sürecinde size rehberlik edeceğiz. Boşluk Genişliği, bir grafikteki sütunlar veya çubuklar arasındaki boşluğu belirleyerek grafiğin görsel görünümünü kontrol etmenize olanak tanır.

## Önkoşullar

 Başlamadan önce Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun. Aspose web sitesinden indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## Adım adım rehber

Aspose.Slides for Java kullanarak bir grafikte Boşluk Genişliğini ayarlamak için şu adımları izleyin:

### 1. Boş Bir Sunum Oluşturun

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";

// Boş bir sunu oluşturma
Presentation presentation = new Presentation();
```

### 2. İlk Slayta Erişin

```java
// İlk slayda erişin
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Varsayılan Verilere Sahip Bir Grafik Ekleme

```java
// Varsayılan verileri içeren bir grafik ekleme
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Grafik Veri Sayfası Dizinini Ayarlayın

```java
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
```

### 5. Grafik Verileri Çalışma Kitabını Alın

```java
// Grafik verileri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Grafiğe Seri Ekleyin

```java
// Grafiğe seri ekle
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Grafiğe Kategoriler Ekleyin

```java
// Grafiğe kategori ekleme
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

### 10. Sunumu Kaydet

```java
// Sunuyu grafikle birlikte kaydedin
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Boşluk Genişliğini Ayarlamak İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Boş sunum oluşturma
Presentation presentation = new Presentation();
// İlk slayda erişin
ISlide slide = presentation.getSlides().get_Item(0);
// Varsayılan verilerle grafik ekle
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
// Grafik verileri çalışma sayfasını alma
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
// GapWidth değerini ayarlayın
series.getParentSeriesGroup().setGapWidth(50);
// Sunuyu grafikle kaydet
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint sunumundaki bir grafik için Boşluk Genişliğini nasıl ayarlayacağınızı öğrendiniz. Boşluk Genişliğini ayarlamak, grafiğinizdeki sütunlar veya çubuklar arasındaki boşluğu kontrol etmenize olanak tanıyarak verilerinizin görsel sunumunu geliştirir.

## SSS'ler

### Boşluk Genişliği değerini nasıl değiştiririm?

 Boşluk Genişliğini değiştirmek için`setGapWidth` konusundaki yöntem`ParentSeriesGroup`grafik serisi. Verilen örnekte Gap Width'i 50 olarak ayarladık ama siz bu değeri istediğiniz aralıklara göre ayarlayabilirsiniz.

### Diğer grafik özelliklerini özelleştirebilir miyim?

Evet, Aspose.Slides for Java, grafik özelleştirmesi için kapsamlı yetenekler sağlar. Renkler, etiketler, başlıklar ve daha fazlası gibi çeşitli grafik özelliklerini değiştirebilirsiniz. Grafik özelleştirme seçenekleri hakkında ayrıntılı bilgi için API Referansını kontrol edin.

### Daha fazla kaynak ve belgeyi nerede bulabilirim?

 Aspose.Slides for Java'da kapsamlı belgeler ve ek kaynaklar bulabilirsiniz.[Web sitesi](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
