---
title: Aspose.Slides .NET'te Veri Noktasında Grafik İşaretleyici Seçeneklerini Kullanma
linktitle: Veri Noktasındaki Grafik İşaretleyici Seçenekleri
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint grafiklerinizi nasıl geliştireceğinizi öğrenin. Veri noktası işaretçilerini görüntülerle özelleştirin. İlgi çekici sunumlar oluşturun.
weight: 11
url: /tr/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides .NET'te Veri Noktasında Grafik İşaretleyici Seçeneklerini Kullanma


Sunumlar ve veri görselleştirmeyle çalışırken Aspose.Slides for .NET, grafikleri oluşturmak, özelleştirmek ve değiştirmek için çok çeşitli güçlü özellikler sunar. Bu öğreticide grafik sunumlarınızı geliştirmek için veri noktalarında grafik işaretleyici seçeneklerinin nasıl kullanılacağını keşfedeceğiz. Bu adım adım kılavuz, önkoşullardan ve ad alanlarının içe aktarılmasından başlayarak her örneği birden çok adıma ayırmaya kadar süreç boyunca size yol gösterecektir.

## Önkoşullar

Veri noktalarında grafik işaretleyici seçeneklerini kullanmaya başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

-  Aspose.Slides for .NET: Aspose.Slides for .NET'in kurulu olduğundan emin olun. adresinden indirebilirsiniz.[İnternet sitesi](https://releases.aspose.com/slides/net/).

- Örnek Sunum: Bu eğitim için "Test.pptx" adlı örnek bir sunum kullanacağız. Bu sunumu belge dizininizde bulundurmalısınız.

Şimdi gerekli ad alanlarını içe aktararak başlayalım.

## Ad Alanlarını İçe Aktar

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Gerekli ad alanlarını içe aktardık ve sunumumuzu başlattık. Şimdi veri noktalarında grafik işaretleyici seçeneklerini kullanmaya devam edelim.

## Adım 1: Varsayılan Grafiğin Oluşturulması

```csharp

// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//Varsayılan grafiği oluşturma
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Slayt üzerinde belirtilen konumda ve boyutta "LineWithMarkers" türünde varsayılan bir grafik oluşturuyoruz.

## Adım 2: Varsayılan Grafik Verileri Çalışma Sayfası Dizinini Alma

```csharp
// Varsayılan grafik verileri çalışma sayfası dizinini alma
int defaultWorksheetIndex = 0;
```

Burada, varsayılan grafik verileri çalışma sayfasının indeksini elde ediyoruz.

## Adım 3: Grafik Verileri Çalışma Sayfasını Alma

```csharp
// Grafik verileri çalışma sayfasını alma
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Grafik verileriyle çalışmak için grafik verileri çalışma kitabını getiriyoruz.

## Adım 4: Grafik Serisini Değiştirme

```csharp
// Demo serisini sil
chart.ChartData.Series.Clear();

// Yeni seri ekle
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Bu adımda mevcut demo serilerini kaldırıyoruz ve grafiğe "Seri 1" adlı yeni bir seri ekliyoruz.

## Adım 5: Veri Noktaları için Resim Dolgusunu Ayarlama

```csharp
// İşaretçiler için resmi ayarlayın
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// İlk grafik serisini alın
IChartSeries series = chart.ChartData.Series[0];

// Resim dolgusu ile yeni veri noktaları ekleyin
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

Veri noktaları için resim işaretleyicileri ayarlayarak her bir veri noktasının grafikte nasıl görüneceğini özelleştirmenize olanak sağlıyoruz.

## Adım 6: Grafik Serisi İşaretleyici Boyutunun Değiştirilmesi

```csharp
// Grafik serisi işaretleyici boyutunu değiştirme
series.Marker.Size = 15;
```

Burada grafik serisi işaretçisinin boyutunu görsel olarak çekici hale getirecek şekilde ayarlıyoruz.

## Adım 7: Sunumu Kaydetme

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Son olarak sunumu yeni grafik ayarlarıyla kaydediyoruz.

## Çözüm

Aspose.Slides for .NET, çeşitli özelleştirme seçenekleriyle çarpıcı grafik sunumları oluşturmanıza olanak tanır. Bu öğreticide verilerinizin görsel temsilini geliştirmek için veri noktalarında grafik işaretleyici seçeneklerini kullanmaya odaklandık. Aspose.Slides for .NET ile sunumlarınızı bir sonraki aşamaya taşıyabilir, onları daha ilgi çekici ve bilgilendirici hale getirebilirsiniz.

Aspose.Slides for .NET ile ilgili herhangi bir sorunuz varsa veya yardıma ihtiyacınız varsa şu adresi ziyaret etmekten çekinmeyin:[Aspose.Slides belgeleri](https://reference.aspose.com/slides/net/) veya iletişime geçin[Topluluğu düşünün](https://forum.aspose.com/) destek için.

## Sıkça Sorulan Sorular (SSS)

### Aspose.Slides for .NET'te özel görüntüleri veri noktaları için işaretleyici olarak kullanabilir miyim?
Evet, bu eğitimde gösterildiği gibi Aspose.Slides for .NET'te özel görüntüleri veri noktaları için işaretleyici olarak kullanabilirsiniz.

### Aspose.Slides for .NET'te grafik türünü nasıl değiştirebilirim?
 Farklı bir grafik türü belirterek grafik türünü değiştirebilirsiniz.`ChartType` Grafiği oluştururken "Çubuk", "Pasta" veya "Alan" gibi.

### Aspose.Slides for .NET, PowerPoint'in en son sürümleriyle uyumlu mu?
Aspose.Slides for .NET, çeşitli PowerPoint formatlarıyla çalışacak şekilde tasarlanmıştır ve en son PowerPoint sürümleriyle uyumluluğu sürdürmek için düzenli olarak güncellenir.

### Aspose.Slides for .NET için daha fazla eğitim ve kaynağı nerede bulabilirim?
 Ek eğitimleri ve kaynakları şuradan keşfedebilirsiniz:[Aspose.Slides belgeleri](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET'in deneme sürümü mevcut mu?
 Evet, Aspose.Slides for .NET'i adresinden ücretsiz deneme sürümünü indirerek deneyebilirsiniz.[Burada](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
