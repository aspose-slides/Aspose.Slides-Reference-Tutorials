---
"description": "Aspose.Slides for Java kullanarak PowerPoint sunumlarında otomatik seri renklendirmeli dinamik grafiklerin nasıl oluşturulacağını öğrenin. Veri görselleştirmelerinizi zahmetsizce geliştirin."
"linktitle": "Java Slaytlarında Otomatik Grafik Serisi Rengi"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Otomatik Grafik Serisi Rengi"
"url": "/tr/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Otomatik Grafik Serisi Rengi


## Aspose.Slides for Java'da Otomatik Grafik Serisi Rengine Giriş

Bu eğitimde, Java için Aspose.Slides kullanarak bir grafik içeren bir PowerPoint sunumunun nasıl oluşturulacağını ve grafik serileri için otomatik dolgu renklerinin nasıl ayarlanacağını inceleyeceğiz. Otomatik dolgu renkleri, grafiklerinizi görsel olarak daha çekici hale getirebilir ve kütüphanenin sizin için renkleri seçmesine izin vererek size zaman kazandırabilir.

## Ön koşullar

Başlamadan önce projenizde Aspose.Slides for Java kütüphanesinin yüklü olduğundan emin olun. Bunu şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Yeni Bir Sunum Oluşturun

Öncelikle yeni bir PowerPoint sunumu oluşturup içine bir slayt ekleyelim.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir Presentation sınıfı örneği oluşturun
Presentation presentation = new Presentation();
```

## Adım 2: Slayda Bir Grafik Ekleyin

Sonra, slayda kümelenmiş bir sütun grafiği ekleyeceğiz. Ayrıca ilk seriyi değerleri gösterecek şekilde ayarlayacağız.

```java
// İlk slayda erişin
ISlide slide = presentation.getSlides().get_Item(0);
// Varsayılan verilerle grafik ekle
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// İlk seriyi Değerleri Göster olarak ayarlayın
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Adım 3: Grafik Verilerini Doldurun

Şimdi, grafiği verilerle dolduracağız. Varsayılan olarak oluşturulan serileri ve kategorileri silerek başlayacağız ve ardından yeni seriler ve kategoriler ekleyeceğiz.

```java
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

## Adım 5: Seri için Otomatik Doldurma Rengini Ayarlayın

Şimdi, grafik serileri için otomatik dolgu renklerini ayarlayalım. Bu, kütüphanenin bizim için renkleri seçmesini sağlayacaktır.

```java
// Seri için otomatik dolgu rengi ayarlama
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Adım 6: Sunumu Kaydedin

Son olarak sunumu grafikle birlikte bir PowerPoint dosyasına kaydedeceğiz.

```java
// Sunuyu grafikle kaydet
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Otomatik Grafik Serisi Rengi İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir Presentation sınıfı örneği oluşturun
Presentation presentation = new Presentation();
try
{
	// İlk slayda erişin
	ISlide slide = presentation.getSlides().get_Item(0);
	// Varsayılan verilerle grafik ekle
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
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
	// Seri için otomatik dolgu rengi ayarlama
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// İkinci grafik serisini alın
	series = chart.getChartData().getSeries().get_Item(1);
	// Şimdi seri verileri dolduruluyor
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Seri için dolgu renginin ayarlanması
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

Bu eğitimde, Java için Aspose.Slides kullanarak bir grafikle PowerPoint sunumu oluşturmayı ve grafik serileri için otomatik dolgu renklerini ayarlamayı öğrendik. Otomatik renkler, grafiklerinizin görsel çekiciliğini artırabilir ve sunumlarınızı daha ilgi çekici hale getirebilir. Grafiği, özel gereksinimleriniz için gerektiği gibi daha da özelleştirebilirsiniz.

## SSS

### Aspose.Slides for Java'da grafik serileri için otomatik dolgu renklerini nasıl ayarlarım?

Aspose.Slides for Java'da grafik serileri için otomatik doldurma renklerini ayarlamak için aşağıdaki kodu kullanın:

```java
// Seri için otomatik dolgu rengi ayarlama
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Bu kod kütüphanenin grafik serileri için renkleri otomatik olarak seçmesini sağlayacaktır.

### Gerekirse grafik renklerini özelleştirebilir miyim?

Evet, grafik renklerini gerektiği gibi özelleştirebilirsiniz. Sağlanan örnekte, otomatik dolgu renkleri kullandık, ancak belirli renkleri değiştirerek ayarlayabilirsiniz. `FillType` Ve `SolidFillColor` Dizi formatının özellikleri.

### Tabloya ek seriler veya kategoriler nasıl ekleyebilirim?

Grafiğe ek seriler veya kategoriler eklemek için şunu kullanın: `getSeries()` Ve `getCategories()` grafik yöntemleri `ChartData` nesne. Verilerini ve etiketlerini belirterek yeni seriler ve kategoriler ekleyebilirsiniz.

### Tablo ve etiketleri daha ileri bir şekilde biçimlendirmek mümkün müdür?

Evet, grafik, seri ve etiketleri gerektiği gibi daha fazla biçimlendirebilirsiniz. Java için Aspose.Slides, yazı tipleri, renkler, stiller ve daha fazlası dahil olmak üzere grafikler için kapsamlı biçimlendirme seçenekleri sunar. Biçimlendirme seçenekleri hakkında daha fazla ayrıntı için belgeleri inceleyebilirsiniz.

### Aspose.Slides for Java ile çalışma hakkında daha fazla bilgiyi nerede bulabilirim?

Java için Aspose.Slides hakkında daha fazla bilgi ve ayrıntılı belgeler için referans belgelerini ziyaret edebilirsiniz [Burada](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}