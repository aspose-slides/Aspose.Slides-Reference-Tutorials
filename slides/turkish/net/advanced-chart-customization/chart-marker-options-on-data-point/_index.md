---
"description": "Aspose.Slides for .NET kullanarak PowerPoint grafiklerinizi nasıl geliştireceğinizi öğrenin. Veri noktası işaretleyicilerini görsellerle özelleştirin. İlgi çekici sunumlar oluşturun."
"linktitle": "Veri Noktasında Grafik İşaretleyici Seçenekleri"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides .NET'te Veri Noktasında Grafik İşaretleyici Seçeneklerini Kullanma"
"url": "/tr/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides .NET'te Veri Noktasında Grafik İşaretleyici Seçeneklerini Kullanma


Sunumlar ve veri görselleştirmeyle çalışırken, Aspose.Slides for .NET, grafikler oluşturmak, özelleştirmek ve düzenlemek için çok çeşitli güçlü özellikler sunar. Bu eğitimde, grafik sunumlarınızı geliştirmek için veri noktalarında grafik işaretleyici seçeneklerinin nasıl kullanılacağını inceleyeceğiz. Bu adım adım kılavuz, ön koşullardan ve ad alanlarını içe aktarmaktan başlayarak her örneği birden fazla adıma ayırmaya kadar süreci adım adım anlatacaktır.

## Ön koşullar

Veri noktalarında grafik işaretleyici seçeneklerini kullanmaya başlamadan önce, aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Aspose.Slides for .NET: Aspose.Slides for .NET'in yüklü olduğundan emin olun. Bunu şuradan indirebilirsiniz: [web sitesi](https://releases.aspose.com/slides/net/).

- Örnek Sunum: Bu eğitim için "Test.pptx" adlı örnek bir sunum kullanacağız. Bu sunum belge dizininizde bulunmalıdır.

Şimdi gerekli namespace'leri import ederek başlayalım.

## Ad Alanlarını İçe Aktar

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Gerekli ad alanlarını içe aktardık ve sunumumuzu başlattık. Şimdi, veri noktalarında grafik işaretleyici seçeneklerini kullanmaya devam edelim.

## Adım 1: Varsayılan Grafiği Oluşturma

```csharp

// Belgeler dizinine giden yol.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Varsayılan grafiği oluşturma
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Slaytta belirtilen konum ve boyutta "LineWithMarkers" türünde varsayılan bir grafik oluşturuyoruz.

## Adım 2: Varsayılan Grafik Veri Çalışma Sayfası Dizinini Alma

```csharp
// Varsayılan grafik veri çalışma sayfası dizinini alma
int defaultWorksheetIndex = 0;
```

Burada varsayılan grafik veri çalışma sayfasının dizinini elde ediyoruz.

## Adım 3: Grafik Veri Çalışma Sayfasını Alma

```csharp
// Grafik veri çalışma sayfasını alma
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Grafik verileriyle çalışmak için grafik veri çalışma kitabını getiriyoruz.

## Adım 4: Grafik Serisini Değiştirme

```csharp
// Demo serisini sil
chart.ChartData.Series.Clear();

// Yeni seri ekle
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Bu adımda mevcut demo serilerini kaldırıp grafiğe "Seri 1" adında yeni bir seri ekliyoruz.

## Adım 5: Veri Noktaları için Resim Dolgusunu Ayarlama

```csharp
// Resmi işaretçilere ayarlayın
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// İlk grafik serisini ele alalım
IChartSeries series = chart.ChartData.Series[0];

// Resim dolgulu yeni veri noktaları ekleyin
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Veri noktaları için resim işaretçileri ayarlıyoruz, böylece her bir veri noktasının grafikte nasıl görüneceğini özelleştirebiliyorsunuz.

## Adım 6: Grafik Serisi İşaretçi Boyutunu Değiştirme

```csharp
// Grafik serisi işaretleyici boyutunu değiştirme
series.Marker.Size = 15;
```

Burada, grafik serisi işaretçisinin boyutunu görsel olarak çekici hale getirmek için ayarlıyoruz.

## Adım 7: Sunumu Kaydetme

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Son olarak sunumu yeni grafik ayarlarıyla kaydediyoruz.

## Çözüm

Aspose.Slides for .NET, çeşitli özelleştirme seçenekleriyle çarpıcı grafik sunumları oluşturmanızı sağlar. Bu eğitimde, verilerinizin görsel temsilini geliştirmek için veri noktalarında grafik işaretleyici seçeneklerini kullanmaya odaklandık. Aspose.Slides for .NET ile sunumlarınızı bir üst seviyeye taşıyabilir, onları daha ilgi çekici ve bilgilendirici hale getirebilirsiniz.

Aspose.Slides for .NET ile ilgili herhangi bir sorunuz varsa veya yardıma ihtiyacınız varsa, şu adresi ziyaret etmekten çekinmeyin: [Aspose.Slides belgeleri](https://reference.aspose.com/slides/net/) veya ulaşın [Aspose topluluğu](https://forum.aspose.com/) destek için.

## Sıkça Sorulan Sorular (SSS)

### Aspose.Slides for .NET'te veri noktaları için işaretçi olarak özel görseller kullanabilir miyim?
Evet, bu eğitimde gösterildiği gibi, Aspose.Slides for .NET'te veri noktaları için işaretçi olarak özel görseller kullanabilirsiniz.

### Aspose.Slides for .NET'te grafik türünü nasıl değiştirebilirim?
Farklı bir tür belirterek grafik türünü değiştirebilirsiniz. `ChartType` Grafik oluştururken "Çubuk", "Pasta" veya "Alan" gibi.

### Aspose.Slides for .NET, PowerPoint'in en son sürümleriyle uyumlu mudur?
Aspose.Slides for .NET, çeşitli PowerPoint formatlarıyla çalışacak şekilde tasarlanmıştır ve en son PowerPoint sürümleriyle uyumluluğun sürdürülmesi için düzenli olarak güncellenmektedir.

### Aspose.Slides for .NET için daha fazla öğretici ve kaynağı nerede bulabilirim?
Ek öğreticileri ve kaynakları şu adreste keşfedebilirsiniz: [Aspose.Slides belgeleri](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET'in deneme sürümü mevcut mu?
Evet, Aspose.Slides for .NET'i ücretsiz deneme sürümünü indirerek deneyebilirsiniz. [Burada](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}