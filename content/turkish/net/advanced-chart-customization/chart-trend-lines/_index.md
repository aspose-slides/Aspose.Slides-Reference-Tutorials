---
title: Aspose.Slides for .NET'te Grafik Trend Çizgilerini Keşfetme
linktitle: Grafik Trend Çizgileri
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Bu adım adım kılavuzdan Aspose.Slides for .NET'i kullanarak grafiklere çeşitli trend çizgilerini nasıl ekleyeceğinizi öğrenin. Veri görselleştirme becerilerinizi kolaylıkla geliştirin!
type: docs
weight: 12
url: /tr/net/advanced-chart-customization/chart-trend-lines/
---

Veri görselleştirme ve sunum dünyasında grafikleri birleştirmek, bilgiyi etkili bir şekilde iletmenin güçlü bir yolu olabilir. Aspose.Slides for .NET, grafiklerinizle çalışmak için grafiklerinize trend çizgileri ekleme yeteneği de dahil olmak üzere zengin özelliklere sahip araçlar sunar. Bu derste Aspose.Slides for .NET'i kullanarak adım adım bir grafiğe trend çizgileri ekleme sürecini inceleyeceğiz. 

## Önkoşullar

Aspose.Slides for .NET ile çalışmaya başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olmanız gerekir:

1.  Aspose.Slides for .NET: Kütüphaneye erişmek ve onu kullanmak için Aspose.Slides for .NET'in kurulu olması gerekir. Kütüphaneyi adresinden temin edebilirsiniz.[indirme sayfası](https://releases.aspose.com/slides/net/).

2. Geliştirme Ortamı: Tercihen Visual Studio gibi bir .NET entegre geliştirme ortamı kullanan bir geliştirme ortamı kurmalısınız.

3. Temel C# Bilgisi: Aspose.Slides for .NET ile çalışmak için C# kullanacağımız için C# programlamaya dair temel bir anlayış faydalıdır.

Artık önkoşulları ele aldığımıza göre, adım adım bir grafiğe trend çizgileri ekleme sürecini inceleyelim.

## Ad Alanlarını İçe Aktarma

Öncelikle gerekli ad alanlarını C# projenize aktardığınızdan emin olun. Bu ad alanları Aspose.Slides for .NET ile çalışmak için gereklidir.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## 1. Adım: Bir Sunu Oluşturun

Bu adımda üzerinde çalışacağımız boş bir sunum oluşturuyoruz.

```csharp
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";

// Henüz mevcut değilse dizin oluşturun.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Boş sunum oluşturma
Presentation pres = new Presentation();
```

## Adım 2: Slayta Grafik Ekleme

Daha sonra slayta kümelenmiş bir sütun grafiği ekliyoruz.

```csharp
// Kümelenmiş sütun grafiği oluşturma
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## 3. Adım: Grafiğe Trend Çizgileri Ekleyin

Şimdi grafik serisine çeşitli türde trend çizgileri ekliyoruz.

### Üstel Trend Çizgisi Ekleme

```csharp
// Grafik serisi 1 için üstel trend çizgisi ekleme
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Doğrusal Trend Çizgisi Ekleme

```csharp
// Grafik serisi 1 için doğrusal trend çizgisi ekleme
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Logaritmik Trend Çizgisi Ekleme

```csharp
// Grafik serisi 2 için logaritmik eğilim çizgisi ekleme
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Hareketli Ortalama Trend Çizgisi Ekleme

```csharp
// Grafik serisi 2 için hareketli ortalama trend çizgisi ekleniyor
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Polinom Trend Çizgisi Ekleme

```csharp
// Grafik serisi 3 için polinom eğilim çizgisi ekleme
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Güç Trend Çizgisi Ekleme

```csharp
// Grafik serisi 3 için güç trend çizgisi ekleniyor
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## 4. Adım: Sunuyu Kaydetme

Grafiğe trend çizgileri ekledikten sonra sunumu kaydedin.

```csharp
// Sunum kaydediliyor
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Bu kadar! Aspose.Slides for .NET'i kullanarak grafiğinize çeşitli trend çizgilerini başarıyla eklediniz.

## Çözüm

Aspose.Slides for .NET, grafikleri kolaylıkla oluşturmanıza ve değiştirmenize olanak tanıyan çok yönlü bir kitaplıktır. Bu adım adım kılavuzu izleyerek grafiklerinize farklı türde eğilim çizgileri ekleyerek verilerinizin görsel sunumunu geliştirebilirsiniz.

### SSS

### Aspose.Slides for .NET belgelerini nerede bulabilirim?
 Dokümantasyona ulaşabilirsiniz[Burada](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET'i nasıl indirebilirim?
 Aspose.Slides for .NET'i indirme sayfasından indirebilirsiniz.[Burada](https://releases.aspose.com/slides/net/).

### Aspose.Slides for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, adresini ziyaret ederek Aspose.Slides for .NET'i ücretsiz deneyebilirsiniz.[bu bağlantı](https://releases.aspose.com/).

### Aspose.Slides for .NET'i nereden satın alabilirim?
 Aspose.Slides for .NET'i satın almak için satın alma sayfasını ziyaret edin[Burada](https://purchase.aspose.com/buy).

### Aspose.Slides for .NET için geçici bir lisansa ihtiyacım var mı?
 Aspose.Slides for .NET için geçici lisansı şu adresten edinebilirsiniz:[bu bağlantı](https://purchase.aspose.com/temporary-license/).