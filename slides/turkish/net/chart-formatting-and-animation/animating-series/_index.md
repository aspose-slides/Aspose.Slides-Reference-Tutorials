---
title: Aspose.Slides for .NET ile Grafik Serisini Canlandırın
linktitle: Grafikteki Animasyon Serisi
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET ile grafik serilerini nasıl canlandıracağınızı öğrenin. Dinamik sunumlarla izleyicilerinizin ilgisini çekin. Şimdi başla!
weight: 12
url: /tr/net/chart-formatting-and-animation/animating-series/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Animasyonlu grafiklerle sunumlarınıza biraz heyecan katmak mı istiyorsunuz? Aspose.Slides for .NET grafiklerinizi hayata geçirmek için burada. Bu adım adım kılavuzda, Aspose.Slides for .NET kullanarak bir grafikteki serilerin nasıl canlandırılacağını size göstereceğiz. Ancak aksiyona dalmadan önce önkoşulları ele alalım.

## Önkoşullar

Aspose.Slides for .NET kullanarak bir grafikteki serileri başarılı bir şekilde canlandırmak için aşağıdakilere ihtiyacınız olacak:

### 1. Aspose.Slides for .NET Kitaplığı

 Aspose.Slides for .NET kitaplığının kurulu olduğundan emin olun. Henüz yapmadıysanız adresinden indirebilirsiniz.[Aspose.Slides for .NET web sitesi](https://releases.aspose.com/slides/net/).

### 2. Grafikli Mevcut Sunum

Canlandırmak istediğiniz mevcut bir grafikle bir PowerPoint sunusu (PPTX) hazırlayın.

Artık önkoşulları ele aldığımıza göre, grafik serisini canlandırmak için süreci bir dizi adıma ayıralım.


## 1. Adım: Gerekli Ad Alanlarını İçe Aktarın

Aspose.Slides for .NET ile çalışmak için gerekli ad alanlarını C# kodunuza aktarmanız gerekir:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Adım 2: Mevcut Sunumu Yükleyin

Bu adımda, canlandırmak istediğiniz grafiği içeren mevcut PowerPoint sunumunuzu (PPTX) yükleyin.

```csharp
// Belge dizinine giden yol
string dataDir = "Your Document Directory";

// Bir sunum dosyasını temsil eden Sunum sınıfını somutlaştırın
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Kodunuz buraya gelecek
}
```

## Adım 3: Grafik Nesnesinin Referansını Alın

Sununuzdaki grafikle çalışmak için grafik nesnesine bir referans almanız gerekir:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Adım 4: Seriyi Canlandırın

Artık grafik serinize animasyon efektleri eklemenin zamanı geldi. Grafiğin tamamına bir solma efekti ekleyeceğiz ve her serinin tek tek görünmesini sağlayacağız.

```csharp
// Grafiği canlandırın
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Her seriye animasyon ekleyin
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Adım 5: Değiştirilen Sunuyu Kaydetme

Animasyon efektlerini grafiğinize ekledikten sonra değiştirilen sunumu diske kaydedin.

```csharp
//Değiştirilen sunuyu kaydet
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

Bu kadar! Aspose.Slides for .NET'i kullanarak bir grafikteki serileri başarıyla canlandırdınız.

## Çözüm

Bu eğitimde, Aspose.Slides for .NET'i kullanarak bir grafikteki serileri canlandırma sürecinde size yol gösterdik. Bu güçlü kütüphaneyle izleyicilerinizi büyüleyen ilgi çekici ve dinamik sunumlar oluşturabilirsiniz.

 Herhangi bir sorunuz varsa veya daha fazla yardıma ihtiyacınız varsa Aspose.Slides topluluğuna kendi adreslerinden ulaşmaktan çekinmeyin.[destek Forumu](https://forum.aspose.com/).

## SSS

### Aspose.Slides for .NET'i kullanarak serilerin yanı sıra diğer grafik öğelerini de canlandırabilir miyim?
Evet, Aspose.Slides for .NET'i kullanarak veri noktaları, eksenler ve göstergeler dahil olmak üzere çeşitli grafik öğelerine animasyon uygulayabilirsiniz.

### Aspose.Slides for .NET, PowerPoint'in en son sürümleriyle uyumlu mu?
Aspose.Slides for .NET, PowerPoint 2007 ve sonrası da dahil olmak üzere çeşitli PowerPoint sürümlerini destekleyerek en yeni sürümlerle uyumluluk sağlar.

### Animasyon efektlerini her grafik serisi için ayrı ayrı özelleştirebilir miyim?
Evet, benzersiz ve ilgi çekici sunumlar oluşturmak için her grafik serisine yönelik animasyon efektlerini uyarlayabilirsiniz.

### Aspose.Slides for .NET'in deneme sürümü mevcut mu?
 Evet, kütüphaneyi ücretsiz deneme sürümüyle deneyebilirsiniz.[Aspose.Slides for .NET web sitesi](https://releases.aspose.com/).

### Aspose.Slides for .NET lisansını nereden satın alabilirim?
 Aspose.Slides for .NET lisansını satın alma sayfasından alabilirsiniz.[Burada](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
