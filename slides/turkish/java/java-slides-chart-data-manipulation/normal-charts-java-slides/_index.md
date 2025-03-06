---
title: Java Slaytlarındaki Normal Grafikler
linktitle: Java Slaytlarındaki Normal Grafikler
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java ile Java Slaytlarında Normal Grafikler oluşturun. PowerPoint sunumlarında grafik oluşturmaya, özelleştirmeye ve kaydetmeye yönelik adım adım kılavuz ve kaynak kodu.
weight: 21
url: /tr/java/chart-data-manipulation/normal-charts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java Slaytlarındaki Normal Grafiklere Giriş

Bu eğitimde Aspose.Slides for Java API'sini kullanarak Java Slides'ta normal grafikler oluşturma sürecini anlatacağız. PowerPoint sunumunda kümelenmiş sütun grafiğinin nasıl oluşturulacağını göstermek için kaynak koduyla birlikte adım adım talimatlar kullanacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. Aspose.Slides for Java API kuruldu.
2. Bir Java geliştirme ortamı kuruldu.
3. Java programlamanın temel bilgisi.

## Adım 1: Projeyi Kurma

Projeniz için bir dizininizin olduğundan emin olun. Kodda belirtildiği gibi buna "Belge Dizininiz" adını verelim. Bunu proje dizininizin gerçek yoluyla değiştirebilirsiniz.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Henüz mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Adım 2: Sunum Oluşturma

Şimdi bir PowerPoint sunumu oluşturalım ve ilk slaydına erişelim.

```java
// PPTX dosyasını temsil eden Sunum sınıfını somutlaştırın
Presentation pres = new Presentation();
// İlk slayda erişin
ISlide sld = pres.getSlides().get_Item(0);
```

## 3. Adım: Grafik Ekleme

Slayta kümelenmiş bir sütun grafiği ekleyeceğiz ve başlığını belirleyeceğiz.

```java
// Varsayılan verilerle grafik ekle
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Grafik başlığını ayarlama
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Adım 4: Grafik Verilerini Ayarlama

Daha sonra seri ve kategorileri tanımlayarak grafik verilerini ayarlayacağız.

```java
// İlk seriyi Değerleri Göster olarak ayarla
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;

// Grafik verileri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Varsayılan oluşturulan serileri ve kategorileri silin
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Yeni seriler ekleniyor
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Yeni kategoriler ekleme
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Adım 5: Seri Verilerini Doldurma

Şimdi grafik için seri veri noktalarını dolduralım.

```java
// İlk grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Seri verilerini doldurma
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Seri için dolgu rengini ayarlama
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// İkinci grafik serisini alın
series = chart.getChartData().getSeries().get_Item(1);

// Seri verilerini doldurma
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Seri için dolgu rengini ayarlama
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Adım 6: Etiketleri Özelleştirme

Grafik serisi için veri etiketlerini özelleştirelim.

```java
// İlk etikette Kategori adı gösterilecektir
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Seri adı ve ayırıcıyla birlikte üçüncü etiketin değerini göster
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Adım 7: Sunumu Kaydetme

Son olarak, sunumu grafikle birlikte proje dizininize kaydedin.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Bu kadar! Aspose.Slides for Java'yı kullanarak bir PowerPoint sunumunda başarıyla kümelenmiş bir sütun grafiği oluşturdunuz. Bu grafiği gereksinimlerinize göre daha da özelleştirebilirsiniz.

## Java Slaytlarındaki Normal Grafikler İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Henüz mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// PPTX dosyasını temsil eden Sunum sınıfını somutlaştırın
Presentation pres = new Presentation();
// İlk slayda erişin
ISlide sld = pres.getSlides().get_Item(0);
// Varsayılan verilerle grafik ekle
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Grafik başlığını ayarlama
// Chart.getChartTitle().getTextFrameForOverriding().setText("Örnek Başlık");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// İlk seriyi Değerleri Göster olarak ayarla
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
// Grafik verileri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Varsayılan oluşturulan serileri ve kategorileri silin
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Yeni seriler ekleniyor
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Yeni kategoriler ekleme
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// İlk grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Şimdi seri verileri dolduruluyor
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Seri için dolgu rengini ayarlama
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// İkinci grafik serisini alın
series = chart.getChartData().getSeries().get_Item(1);
// Şimdi seri verileri dolduruluyor
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Seri için dolgu rengini ayarlama
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// İlk etikette Kategori adı gösterilecektir
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Üçüncü etiketin değerini göster
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Sunuyu grafikle kaydet
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Çözüm

Bu eğitimde Aspose.Slides for Java API'sini kullanarak Java Slides'ta normal grafiklerin nasıl oluşturulacağını öğrendik. Bir PowerPoint sunumunda kümelenmiş sütun grafiği oluşturmak için kaynak kodunu içeren adım adım kılavuzu inceledik.

## SSS'ler

### Grafik türünü nasıl değiştirebilirim?

 Grafik türünü değiştirmek için`ChartType`kullanarak grafiği eklerken parametre`sld.getShapes().addChart()`. Aspose.Slides'ta bulunan çeşitli grafik türleri arasından seçim yapabilirsiniz.

### Grafik serisinin renklerini değiştirebilir miyim?

 Evet, kullanarak her serinin dolgu rengini ayarlayarak grafik serisinin renklerini değiştirebilirsiniz.`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Grafiğe nasıl daha fazla kategori veya seri eklerim?

 Kullanarak yeni veri noktaları ve etiketler ekleyerek grafiğe daha fazla kategori veya seri ekleyebilirsiniz.`chart.getChartData().getCategories().add()` Ve`chart.getChartData().getSeries().add()` yöntemler.

### Grafik başlığını nasıl daha da özelleştirebilirim?

 Özelliklerini değiştirerek grafik başlığını daha da özelleştirebilirsiniz.`chart.getChartTitle()` metin hizalaması, yazı tipi boyutu ve rengi gibi.

### Grafiği farklı bir dosya biçiminde nasıl kaydederim?

 Grafiği farklı bir dosya biçiminde kaydetmek için`SaveFormat` parametresi`pres.save()` yöntemi istenen formata (örneğin, PDF, PNG, JPEG) dönüştürebilirsiniz.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
