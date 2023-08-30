---
title: Slayttan Video Çıkart
linktitle: Slayttan Video Çıkart
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint slaytlarından video çıkarma konusunda uzmanlaşın. Kod örnekleri içeren kılavuzumuzu takip edin.
type: docs
weight: 14
url: /tr/net/audio-and-video-extraction/extract-video/
---

## giriiş

Günümüzün dijital dünyasında multimedya sunumları iletişimin önemli bir parçası haline geldi. PowerPoint sunumları genellikle bilgiyi etkili bir şekilde iletmek için metin, resim ve videoların bir karışımını içerir. Ancak arşivleme, paylaşma veya daha fazla düzenleme gibi çeşitli amaçlarla slayttan video çıkarmanız gerekebileceği zamanlar olabilir. Aspose.Slides for .NET'in devreye girdiği yer burasıdır.

## Önkoşullar

Adım adım kılavuza geçmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- C# ve .NET çerçevesi hakkında temel bilgi
- Visual Studio yüklü
-  Aspose.Slides for .NET kitaplığı (şu adresten indirin:[Burada](https://releases.aspose.com/slides/net)

## Adım adım rehber

Aspose.Slides for .NET kullanarak bir slayttan video çıkarma sürecini inceleyelim:

### Adım 1: Kurulum

1. Visual Studio'yu açın ve yeni bir C# projesi oluşturun.
2. Solution Explorer'da projenize sağ tıklayın ve "NuGet Paketlerini Yönet"i seçin.
3. "Aspose.Slides"ı arayın ve en son sürümü yükleyin.

### Adım 2: Sunumu Yükleyin

```csharp
using Aspose.Slides;

// Sunuyu yükle
using var presentation = new Presentation("your-presentation.pptx");
```

 Yer değiştirmek`"your-presentation.pptx"` PowerPoint sunum dosyanızın gerçek yolunu belirtin.

### 3. Adım: Videoyu Çıkarın

```csharp
// İlk slaydı alın
var slide = presentation.Slides[0];

// Slayt şekillerini yineleyin
foreach (var shape in slide.Shapes)
{
    if (shape is IVideoFrame videoFrame)
    {
        // Videoyu video çerçevesinden çıkarın
        var video = videoFrame.EmbeddedVideo;
        // Video nesnesi ile daha fazla işlem yapılabilir
    }
}
```

### 4. Adım: Videoyu Kaydet

```csharp
// Çıkarılan videoyu kaydedin
video.WriteToFile("extracted-video.mp4");
```

 Yer değiştirmek`"extracted-video.mp4"` çıkarılan video dosyası için istenen ad ve yolla.

## Çözüm

Aspose.Slides for .NET, PowerPoint sunumlarından video çıkarma görevini basitleştirir. Yalnızca birkaç satır kodla slaytların içine yerleştirilmiş videoları alabilir ve bunları ayrı video dosyaları olarak kaydedebilirsiniz. İster içeriği yeniden kullanmak ister derlemeler oluşturmak istiyor olun, bu kitaplık kusursuz bir çözüm sunar.

## SSS'ler

### Aspose.Slides belgelerine nasıl erişebilirim?

 Aspose.Slides for .NET belgelerine şu adresten ulaşabilirsiniz:[Burada](https://reference.aspose.com/slides/net/).

### Aspose.Slides diğer programlama dilleri için de mevcut mu?

Evet, Aspose.Slides, Java dahil birden fazla programlama dili için mevcuttur. Uygun kütüphaneleri Aspose web sitesinde bulabilirsiniz.

### Aynı yaklaşımı kullanarak ses çıkarabilir miyim?

Hayır, verilen örnek özellikle videoların çıkarılması içindir. Sesi çıkarmak için kodu ses çerçeveleriyle çalışacak şekilde değiştirmeniz gerekir.

### Aspose.Slides'ı kullanmak için herhangi bir lisans ücreti var mı?

Evet, Aspose.Slides ticari bir üründür. Aspose web sitesinde lisanslama ve fiyatlandırma hakkında detaylı bilgiye ulaşabilirsiniz.

### Çıkarılan videonun özelliklerine nasıl erişebilirim?

`EmbeddedVideo` elde edilen nesne`IVideoFrame` videonun süre, çözünürlük ve daha fazlası gibi çeşitli özelliklerine erişim sağlar.