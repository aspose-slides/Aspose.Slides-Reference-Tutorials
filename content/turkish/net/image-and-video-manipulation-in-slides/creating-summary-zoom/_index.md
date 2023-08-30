---
title: Aspose.Slides ile Sunum Slaytlarında Özet Yakınlaştırma Oluşturma
linktitle: Aspose.Slides ile Sunum Slaytlarında Özet Yakınlaştırma Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak özet yakınlaştırmayla büyüleyici sunum slaytları oluşturmayı öğrenin. Adım adım kılavuzumuz, etkileşimi geliştirmeye yönelik kaynak kodu ve özelleştirme ipuçları sağlar.
type: docs
weight: 16
url: /tr/net/image-and-video-manipulation-in-slides/creating-summary-zoom/
---

## Aspose.Slides for .NET'e Giriş

Aspose.Slides for .NET, geliştiricilerin .NET uygulamalarında PowerPoint sunumlarıyla çalışmasına olanak tanıyan kapsamlı bir kitaplıktır. Slaytlar, şekiller, metinler, resimler ve daha fazlasını oluşturma, düzenleme ve değiştirme dahil çok çeşitli özellikler sunar. Bu kılavuzda, sunum destelerinde özet yakınlaştırma slaytları oluşturmak için Aspose.Slides for .NET'i kullanmaya odaklanacağız.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio kuruldu.
- .NET Framework veya .NET Core yüklü.
-  Aspose.Slides for .NET kitaplığı. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## Geliştirme Ortamını Kurma

1. Visual Studio'da yeni bir .NET projesi oluşturun.
2. Projenize Aspose.Slides kütüphanesine bir referans ekleyin.

## Sunum Yükleme

Başlamak için mevcut bir PowerPoint sunumunu yükleyelim:

```csharp
using Aspose.Slides;

// Sunuyu yükle
using var presentation = new Presentation("path_to_your_presentation.pptx");
```

## Özet Yakınlaştırmaya Slaytlar Ekleme

Özet yakınlaştırma slaytları, tek bir slaytta birden çok slayda genel bakış sunmanıza olanak tanır. Özetlemek istediğimiz slaytları ekleyelim:

```csharp
// Özetlenecek slaytları ekleyin
var slideIndexes = new[] { 2, 3, 4 };
var summaryZoomSlide = presentation.Slides.AddSummaryZoomSlide(slideIndexes);
```

## Özet Yakınlaştırma Slaytları Oluşturma

Şimdi daha önce eklediğimiz slaytların genel görünümünü gösterecek gerçek özet yakınlaştırma slaydını oluşturalım:

```csharp
//Özet yakınlaştırma slaydı oluşturma
var summaryZoom = presentation.Slides.AddSummaryZoomSlide(new[] { summaryZoomSlide });
```

## Özet Yakınlaştırma Davranışını Özelleştirme

Özet yakınlaştırmanın düzen ve görünüm gibi davranışını özelleştirebilirsiniz:

```csharp
// Özet yakınlaştırma ayarlarını özelleştirin
var zoomFrame = summaryZoom.Shapes.OfType<ISmartArt>().FirstOrDefault();
if (zoomFrame != null)
{
    zoomFrame.Nodes[0].TextFrame.Text = "Summary Zoom";
    zoomFrame.Nodes[0].IsHidden = true; // Başlığı gizle
    zoomFrame.Nodes[1].IsHidden = true; // İçeriği gizle
}
```

## Referans için Kaynak Kodu Ekleme

Size kolaylık sağlamak için özet yakınlaştırma slaytları oluşturmaya yönelik kaynak kodun tamamı burada verilmiştir:

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        using var presentation = new Presentation("path_to_your_presentation.pptx");

        var slideIndexes = new[] { 2, 3, 4 };
        var summaryZoomSlide = presentation.Slides.AddSummaryZoomSlide(slideIndexes);

        var summaryZoom = presentation.Slides.AddSummaryZoomSlide(new[] { summaryZoomSlide });

        var zoomFrame = summaryZoom.Shapes.OfType<ISmartArt>().FirstOrDefault();
        if (zoomFrame != null)
        {
            zoomFrame.Nodes[0].TextFrame.Text = "Summary Zoom";
            zoomFrame.Nodes[0].IsHidden = true;
            zoomFrame.Nodes[1].IsHidden = true;
        }

        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Çözüm

Bu kılavuzda, sunum destelerinde özet yakınlaştırma slaytları oluşturmak için Aspose.Slides for .NET'in nasıl kullanılacağını araştırdık. Bu güçlü özellik, içeriğinize profesyonel bir dokunuş sağlayarak sunumlarınızın etkileşimini ve etkileşimini artırabilir.

## SSS'ler

### Aspose.Slides for .NET'i nasıl indirebilirim?

 Aspose.Slides for .NET'i şuradan indirebilirsiniz:[Aspose.Slides web sitesi](https://releases.aspose.com/slides/net/).

### Özet yakınlaştırma slaytlarının görünümünü özelleştirebilir miyim?

Evet, Aspose.Slides kütüphanesinin sağladığı çeşitli özellikleri kullanarak özet yakınlaştırma slaytlarının görünümünü özelleştirebilirsiniz.

### Aspose.Slides hem .NET Framework hem de .NET Core ile uyumlu mu?

Evet, Aspose.Slides hem .NET Framework hem de .NET Core'u destekleyerek geliştirme platformunuzu seçerken size esneklik sağlar.

### Belirli slayt aralıkları için özet yakınlaştırma slaytları oluşturabilir miyim?

Kesinlikle! Özet yakınlaştırmaya dahil etmek istediğiniz slaytları, slayt indekslerini kullanarak seçebilirsiniz.

### Özet yakınlaştırma slaytındaki başlığı ve içeriği nasıl gizleyebilirim?

 Şunu kullanabilirsiniz:`IsHidden` Özet yakınlaştırma slaytındaki başlığı ve içeriği gizlemek için SmartArt düğümlerinin özelliği.