---
"description": "Aspose.Slides for Java ile Java Slaytlarında Normal Grafikler Oluşturun. PowerPoint sunumlarında grafikleri oluşturmak, özelleştirmek ve kaydetmek için adım adım kılavuz ve kaynak kodu."
"linktitle": "Java Slaytlarında Normal Grafikler"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Normal Grafikler"
"url": "/tr/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Normal Grafikler


## Java Slaytlarında Normal Grafiklere Giriş

Bu eğitimde, Aspose.Slides for Java API'sini kullanarak Java Slides'ta normal grafikler oluşturma sürecini ele alacağız. PowerPoint sunumunda kümelenmiş sütun grafiğinin nasıl oluşturulacağını göstermek için kaynak kodla birlikte adım adım talimatlar kullanacağız.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. Aspose.Slides for Java API'si kuruldu.
2. Java geliştirme ortamı kuruldu.
3. Temel Java programlama bilgisi.

## Adım 1: Projenin Kurulumu

Projeniz için bir dizininiz olduğundan emin olun. Kodda belirtildiği gibi buna "Belge Dizininiz" diyelim. Bunu proje dizininize giden gerçek yolla değiştirebilirsiniz.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Eğer mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Adım 2: Bir Sunum Oluşturma

Şimdi bir PowerPoint sunumu oluşturalım ve ilk slaydına erişelim.

```java
// PPTX dosyasını temsil eden Sunum sınıfını örneklendirin
Presentation pres = new Presentation();
// İlk slayda erişin
ISlide sld = pres.getSlides().get_Item(0);
```

## Adım 3: Grafik Ekleme

Slayda kümelenmiş sütun grafiği ekleyeceğiz ve başlığını belirleyeceğiz.

```java
// Varsayılan verilerle grafik ekle
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Ayar çizelgesi Başlığı
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Adım 4: Grafik Verilerini Ayarlama

Daha sonra serileri ve kategorileri tanımlayarak grafik verilerini ayarlayacağız.

```java
// İlk seriyi Değerleri Göster olarak ayarlayın
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;

// Grafik veri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Varsayılan olarak oluşturulan serileri ve kategorileri sil
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Yeni seri ekleniyor
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Yeni kategoriler ekleniyor
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Adım 5: Seri Verilerini Doldurma

Şimdi, grafik için seri veri noktalarını dolduralım.

```java
// İlk grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Seri verilerinin doldurulması
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Seri için dolgu renginin ayarlanması
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// İkinci grafik serisini alın
series = chart.getChartData().getSeries().get_Item(1);

// Seri verilerinin doldurulması
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Seri için dolgu renginin ayarlanması
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Adım 6: Etiketleri Özelleştirme

Grafik serileri için veri etiketlerini özelleştirelim.

```java
// İlk etiket Kategori adını gösterecektir
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Üçüncü etiket için seri adı ve ayırıcıyla değeri göster
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Adım 7: Sunumu Kaydetme

Son olarak sunumu grafikle birlikte proje dizininize kaydedin.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

İşte bu kadar! Aspose.Slides for Java kullanarak bir PowerPoint sunumunda kümelenmiş bir sütun grafiğini başarıyla oluşturdunuz. Bu grafiği gereksinimlerinize göre daha da özelleştirebilirsiniz.

## Java Slaytlarında Normal Grafikler İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Eğer mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// PPTX dosyasını temsil eden Sunum sınıfını örneklendirin
Presentation pres = new Presentation();
// İlk slayda erişin
ISlide sld = pres.getSlides().get_Item(0);
// Varsayılan verilerle grafik ekle
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Ayar çizelgesi Başlığı
// Grafik.getChartTitle().getTextFrameForOverriding().setText("Örnek Başlık");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// İlk seriyi Değerleri Göster olarak ayarlayın
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
// Grafik veri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Varsayılan olarak oluşturulan serileri ve kategorileri sil
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Yeni seri ekleniyor
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Yeni kategoriler ekleniyor
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// İlk grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Şimdi seri verileri dolduruluyor
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Seri için dolgu renginin ayarlanması
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// İkinci grafik serisini alın
series = chart.getChartData().getSeries().get_Item(1);
// Şimdi seri verileri dolduruluyor
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Seri için dolgu renginin ayarlanması
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// İlk etiket Kategori adını gösterecek
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Üçüncü etiket için değeri göster
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Sunuyu grafikle kaydet
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Çözüm

Bu eğitimde, Aspose.Slides for Java API'sini kullanarak Java Slides'ta normal grafiklerin nasıl oluşturulacağını öğrendik. Bir PowerPoint sunumunda kümelenmiş sütun grafiği oluşturmak için kaynak kodlu adım adım bir kılavuzda yürüdük.

## SSS

### Grafik türünü nasıl değiştirebilirim?

Grafik türünü değiştirmek için, `ChartType` grafik eklerken parametreyi kullanarak `sld.getShapes().addChart()`Aspose.Slides'da bulunan çeşitli grafik türlerinden seçim yapabilirsiniz.

### Grafik serisinin renklerini değiştirebilir miyim?

Evet, her seri için dolgu rengini ayarlayarak grafik serisinin renklerini değiştirebilirsiniz. `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Grafiğe daha fazla kategori veya seri nasıl eklerim?

Yeni veri noktaları ve etiketler ekleyerek grafiğe daha fazla kategori veya seri ekleyebilirsiniz. `chart.getChartData().getCategories().add()` Ve `chart.getChartData().getSeries().add()` Yöntemler.

### Grafik başlığını daha fazla nasıl özelleştirebilirim?

Grafik başlığını, özelliklerini değiştirerek daha da özelleştirebilirsiniz. `chart.getChartTitle()` metin hizalaması, yazı tipi boyutu ve rengi gibi.

### Tabloyu farklı bir dosya biçiminde nasıl kaydedebilirim?

Tabloyu farklı bir dosya biçiminde kaydetmek için, `SaveFormat` parametre içinde `pres.save()` İstenilen formata (örneğin PDF, PNG, JPEG) dönüştürme yöntemi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}