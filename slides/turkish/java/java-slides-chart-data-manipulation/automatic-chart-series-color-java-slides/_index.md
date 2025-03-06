---
title: Java Slaytlarında Otomatik Grafik Serisi Rengi
linktitle: Java Slaytlarında Otomatik Grafik Serisi Rengi
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak PowerPoint sunumlarında otomatik seri renkleriyle dinamik grafikler oluşturmayı öğrenin. Veri görselleştirmelerinizi zahmetsizce geliştirin.
type: docs
weight: 14
url: /tr/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## Aspose.Slides for Java'da Otomatik Grafik Serisi Rengine Giriş

Bu eğitimde Aspose.Slides for Java kullanarak grafikli bir PowerPoint sunumunun nasıl oluşturulacağını ve grafik serileri için otomatik dolgu renklerinin nasıl ayarlanacağını keşfedeceğiz. Otomatik dolgu renkleri, grafiklerinizi görsel olarak daha çekici hale getirebilir ve kitaplığın renkleri sizin için seçmesine izin vererek size zaman kazandırabilir.

## Önkoşullar

 Başlamadan önce projenizde Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## 1. Adım: Yeni Bir Sunu Oluşturun

Öncelikle yeni bir PowerPoint sunusu oluşturup ona bir slayt ekleyeceğiz.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum sınıfının bir örneğini oluşturun
Presentation presentation = new Presentation();
```

## Adım 2: Slayta Grafik Ekleme

Daha sonra slayta kümelenmiş bir sütun grafiği ekleyeceğiz. Ayrıca ilk seriyi değerleri gösterecek şekilde ayarlayacağız.

```java
// İlk slayda erişin
ISlide slide = presentation.getSlides().get_Item(0);
// Varsayılan verilerle grafik ekle
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// İlk seriyi Değerleri Göster olarak ayarla
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## 3. Adım: Grafik Verilerini Doldurun

Şimdi grafiği verilerle dolduracağız. Varsayılan olarak oluşturulan serileri ve kategorileri silerek başlayacağız ve ardından yeni seriler ve kategoriler ekleyeceğiz.

```java
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

## Adım 4: Seri Verilerini Doldurun

Hem Seri 1 hem de Seri 2 için seri verilerini dolduracağız.

```java
// İlk grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Şimdi seri verileri dolduruluyor
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// İkinci grafik serisini alın
series = chart.getChartData().getSeries().get_Item(1);
// Şimdi seri verileri dolduruluyor
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Adım 5: Seriler için Otomatik Dolgu Rengini Ayarlayın

Şimdi grafik serisi için otomatik dolgu renklerini ayarlayalım. Bu, kütüphanenin bizim için renkleri seçmesini sağlayacaktır.

```java
// Seriler için otomatik dolgu rengini ayarlama
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Adım 6: Sunuyu Kaydetme

Son olarak, grafiğin bulunduğu sunumu bir PowerPoint dosyasına kaydedeceğiz.

```java
// Sunuyu grafikle kaydet
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Otomatik Grafik Serisi Rengi İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum sınıfının bir örneğini oluşturun
Presentation presentation = new Presentation();
try
{
	// İlk slayda erişin
	ISlide slide = presentation.getSlides().get_Item(0);
	// Varsayılan verilerle grafik ekle
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
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
	// Seriler için otomatik dolgu rengini ayarlama
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// İkinci grafik serisini alın
	series = chart.getChartData().getSeries().get_Item(1);
	// Şimdi seri verileri dolduruluyor
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Seri için dolgu rengini ayarlama
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Sunuyu grafikle kaydet
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides for Java kullanarak grafik içeren bir PowerPoint sunumunun nasıl oluşturulacağını ve grafik serileri için otomatik dolgu renklerinin nasıl ayarlanacağını öğrendik. Otomatik renkler, grafiklerinizin görsel çekiciliğini artırabilir ve sunumlarınızı daha ilgi çekici hale getirebilir. Grafiği özel gereksinimlerinize göre daha da özelleştirebilirsiniz.

## SSS'ler

### Aspose.Slides for Java'da grafik serileri için otomatik dolgu renklerini nasıl ayarlarım?

Aspose.Slides for Java'da grafik serileri için otomatik dolgu renklerini ayarlamak için aşağıdaki kodu kullanın:

```java
// Seriler için otomatik dolgu rengini ayarlama
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Bu kod, kütüphanenin grafik serisi için renkleri otomatik olarak seçmesine olanak tanır.

### Gerekirse grafik renklerini özelleştirebilir miyim?

 Evet, grafik renklerini gerektiği gibi özelleştirebilirsiniz. Verilen örnekte otomatik dolgu renkleri kullandık ancak siz,`FillType` Ve`SolidFillColor` serinin formatının özellikleri.

### Grafiğe nasıl ek seri veya kategori ekleyebilirim?

 Grafiğe ek seriler veya kategoriler eklemek için`getSeries()` Ve`getCategories()` grafiğin yöntemleri`ChartData` nesne. Verilerini ve etiketlerini belirterek yeni seri ve kategoriler ekleyebilirsiniz.

### Grafiği ve etiketleri daha da biçimlendirmek mümkün mü?

Evet, grafiği, serileri ve etiketleri gerektiği gibi daha da biçimlendirebilirsiniz. Aspose.Slides for Java, grafikler için yazı tipleri, renkler, stiller ve daha fazlasını içeren kapsamlı formatlama seçenekleri sunar. Biçimlendirme seçenekleri hakkında daha fazla ayrıntı için belgeleri inceleyebilirsiniz.

### Aspose.Slides for Java ile çalışmaya ilişkin daha fazla bilgiyi nerede bulabilirim?

 Aspose.Slides for Java hakkında daha fazla bilgi ve ayrıntılı dokümantasyon için referans dokümantasyonu ziyaret edebilirsiniz.[Burada](https://reference.aspose.com/slides/java/).