---
title: Grafiğe Özel Hata Çubukları Ekleme
linktitle: Grafiğe Özel Hata Çubukları Ekleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak grafiklere nasıl özel hata çubukları ekleyeceğinizi öğrenin. Doğru veri görselleştirmesi için hata çubukları oluşturun, stillendirin ve özelleştirin.
type: docs
weight: 13
url: /tr/net/licensing-and-formatting/add-custom-error/
---

## Özel Hata Çubuklarına Giriş

Hata çubukları, bir grafikteki veri noktalarının değişkenliğini veya belirsizliğini belirtmek için kullanılan grafiksel gösterimlerdir. Veri noktasının gerçek değerinin düşebileceği aralığın belirlenmesine yardımcı olabilirler. Özel hata çubukları, her veri noktası için belirli hata değerleri tanımlamanıza olanak tanıyarak belirsizliğin grafiğinizde nasıl görüntülendiği konusunda daha fazla kontrol sağlar.

## Geliştirme Ortamını Kurma

 Başlamadan önce Aspose.Slides for .NET kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net). Belgelerde sağlanan kurulum talimatlarını izleyin.

## Örnek Grafik Oluşturma

Aspose.Slides for .NET'i kullanarak örnek bir grafik oluşturarak başlayalım. Gösterim amacıyla temel bir çubuk grafik oluşturacağız. Projenizde kütüphaneye referans verdiğinizden emin olun.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

// Sunum nesnesini somutlaştır
using Presentation presentation = new Presentation();

// Slayt ekle
ISlide slide = presentation.Slides.AddSlide(0, presentation.SlideSize.Size);

// Grafik ekle
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredBar, 100, 100, 500, 300);

// Örnek veriler ekleyin
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;
IChartSeries series = chart.ChartData.Series.Add(workbook.GetCell(0, "A1"), chart.Type);
series.Values.Add(workbook.GetCell(0, "B1"));
series.Values.Add(workbook.GetCell(0, "B2"));

// Kategori etiketlerini ayarlayın
chart.ChartData.Categories.Add(workbook.GetCell(0, "A2"));
chart.ChartData.Categories.Add(workbook.GetCell(0, "A3"));

// Grafik başlığını ayarla
chart.ChartTitle.AddTextFrameForOverriding("Sample Chart");
chart.ChartTitle.TextFrameForOverriding.Text = "Sample Chart";

// Sunuyu kaydet
presentation.Save("SampleChart.pptx", SaveFormat.Pptx);
```

Bu kod, örnek çubuk grafiği içeren bir PowerPoint sunusu oluşturur.

## Grafiğe Hata Çubukları Ekleme

Şimdi grafiğe hata çubukları ekleyelim. Bir serideki belirli veri noktalarına hata çubukları eklenir. Örnek grafiğimizdeki ilk veri noktasına hata çubukları ekleyeceğiz.

```csharp
// İlk seriye erişin
IChartSeries firstSeries = chart.ChartData.Series[0];

// Hata çubukları ekleyin
IErrorBarsFormat errorBarsFormat = firstSeries.ErrorBarsFormat.Add();
errorBarsFormat.Type = ErrorBarType.FixedValue;

// Hata çubuğu değerini ayarla
errorBarsFormat.Value = 5; // Verilerinize göre değeri ayarlayabilirsiniz

// Güncellenen sunuyu kaydet
presentation.Save("ChartWithErrorBars.pptx", SaveFormat.Pptx);
```

Bu kod, grafiğin ilk veri noktasına sabit değerli hata çubukları ekler.

## Hata Çubuğu Değerlerini Özelleştirme

Her veri noktası için hata çubuğu değerlerini ayrı ayrı özelleştirebilirsiniz. Her veri noktası için farklı hata değerleri ayarlamak üzere kodu değiştirelim.

```csharp
// Her nokta için özel hata değerleri ayarlayın
double[] errorValues = { 3, 6 }; // İki veri noktası için hata değerleri

for (int i = 0; i < firstSeries.DataPoints.Count; i++)
{
    firstSeries.ErrorBarsFormat[i].Value = errorValues[i];
}

// Güncellenen sunuyu kaydet
presentation.Save("CustomErrorValuesChart.pptx", SaveFormat.Pptx);
```

Bu kod, serideki her veri noktası için özel hata değerlerini ayarlar.

## Hata Çubuklarını Şekillendirme

Görünürlüğünü artırmak ve grafiğinizin estetiğine uyum sağlamak için hata çubuklarına stil verebilirsiniz. Hata çubuklarının görünümünü özelleştirelim.

```csharp
// Hata çubuğu görünümünü özelleştirme
errorBarsFormat.LineFormat.Width = 2; // Çizgi genişliğini ayarla
errorBarsFormat.LineFormat.SolidFillColor.Color = Color.Red; //Çizgi rengini ayarla

// Güncellenen sunuyu kaydet
presentation.Save("StyledErrorBarsChart.pptx", SaveFormat.Pptx);
```

Bu kod hata çubuklarının çizgi genişliğini ve rengini ayarlar.

## Grafik Verilerini Güncelleme

Grafik verilerini güncellemeniz gerekiyorsa bunu Aspose.Slides for .NET'i kullanarak kolayca yapabilirsiniz. Verileri yeni değerlerle değiştirelim.

```csharp
// Grafik verilerini güncelle
series.Values[0].Value = 15;
series.Values[1].Value = 20;

// Güncellenen sunuyu kaydet
presentation.Save("UpdatedChartData.pptx", SaveFormat.Pptx);
```

Bu kod, grafik verilerinin değerlerini günceller.

## Çoklu Seriler için Hata Çubukları

Bir grafikteki birden fazla seriye hata çubukları ekleyebilirsiniz. Örnek grafiğimizdeki ikinci seriye hata çubuklarını ekleyelim.

```csharp
// İkinci seriye erişin
IChartSeries secondSeries = chart.ChartData.Series[1];

// İkinci seriye hata çubukları ekleyin
IErrorBarsFormat secondSeriesErrorBars = secondSeries.ErrorBarsFormat.Add();
secondSeriesErrorBars.Type = ErrorBarType.Percent;

// İkinci seri için hata çubuğu değerini ayarlayın
secondSeriesErrorBars.Value = 10; // Değeri ayarlayabilirsiniz

// Güncellenen sunuyu kaydet
presentation.Save("MultiSeriesChartWithErrorBars.pptx", SaveFormat.Pptx);
```

Bu kod, grafikteki ikinci seriye hata çubukları ekler.

## Negatif ve Pozitif Hataların Ele Alınması

Hata çubukları hem pozitif hem de negatif hataları temsil edebilir. Her iki hata çubuğu türünü de eklemek için kodu değiştirelim.

```csharp
// Pozitif ve negatif hata çubukları ekleyin
errorBarsFormat.Type = ErrorBarType.Custom;
errorBarsFormat.PlusValue = 4; // Pozitif hata değeri
errorBarsFormat.MinusValue = 2; // Negatif hata değeri

// Güncellenen sunuyu kaydet
presentation.Save("PositiveNegativeErrorBars.pptx", SaveFormat.Pptx);
```

Bu kod, grafiğe özel pozitif ve negatif hata çubukları ekler.

## Grafiği Kaydetme ve Dışa Aktarma

Hata çubuklarını ekledikten ve grafiğinizi özelleştirdikten sonra, daha sonra kullanmak üzere kaydedebilir ve dışa aktarabilirsiniz.

```csharp
// Son grafiği kaydet
presentation.Save("FinalChart.pptx", SaveFormat.Pptx);
```

Bu kod, hata çubuklarıyla birlikte son grafiği kaydeder.

## Çözüm

Bu eğitimde Aspose.Slides for .NET kullanarak bir grafiğe özel hata çubuklarının nasıl ekleneceğini araştırdık. Örnek bir grafik oluşturmayı, hata çubukları eklemeyi, hata değerlerini özelleştirmeyi, hata çubuklarını şekillendirmeyi, grafik verilerini güncellemeyi, birden fazla seriye hata çubukları eklemeyi ve pozitif ve negatif hataları ele almayı ele aldık. Aspose.Slides for .NET ile verilerinizin değişkenliğini etkili bir şekilde ileten özel hata çubuklarıyla bilgilendirici ve görsel olarak çekici grafikler oluşturma esnekliğine sahip olursunuz.

## SSS'ler

### Hata çubuklarının kalınlığını nasıl ayarlayabilirim?

 Hata çubuklarının kalınlığını değiştirerek ayarlayabilirsiniz.`LineFormat.Width` mülkiyeti`ErrorBarsFormat`.

### Her veri noktası için farklı hata değerleri kullanabilir miyim?

Evet, bir döngü kullanarak her veri noktası için özel hata değerlerini ayrı ayrı ayarlayabilirsiniz.`Value` mülkiyet`ErrorBarsFormat`.

### Tek bir grafikte birden fazla seriye hata çubukları eklemek mümkün müdür?

Kesinlikle aynı grafikteki birden fazla seriye hata çubukları ekleyebilirsiniz. İstediğiniz seriye erişin ve makalede gösterildiği gibi hata çubuklarını uygulayın.

### Hata çubuklarını ekledikten sonra kaldırabilir miyim?

 Evet, hata çubuklarını arayarak kaldırabilirsiniz.`Clear` konusundaki yöntem`ErrorBarsFormat` nesne.

### Aspose.Slides for .NET hakkında daha fazla bilgiyi nerede bulabilirim?

 Aspose.Slides for .NET ile ilgili ayrıntılı belgeleri ve örnekleri şu adreste bulabilirsiniz:[Aspose dokümantasyon web sitesi](https://reference.aspose.com/slides/net/).