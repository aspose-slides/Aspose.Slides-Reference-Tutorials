---
title: Aspose.Slides kullanarak Sunum Slaytlarına Video Çerçeveleri Ekleme
linktitle: Aspose.Slides kullanarak Sunum Slaytlarına Video Çerçeveleri Ekleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak video kareleri ekleyerek sunumlarınızı nasıl geliştireceğinizi öğrenin. Sorunsuz bir şekilde ilgi çekici ve etkileşimli içerik oluşturun.
type: docs
weight: 19
url: /tr/net/shape-effects-and-manipulation-in-slides/adding-video-frames/
---

## Aspose.Slides ve Video Entegrasyonuna Giriş

Aspose.Slides, geliştiricilerin PowerPoint sunumlarını programlı bir şekilde oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan kapsamlı bir kitaplıktır. Video çerçevelerini slaytlarınıza entegre ederek sunumlarınızı geliştirebilir, daha dinamik ve ilgi çekici hale getirebilirsiniz.

## Videoları Birleştirmenin Önkoşulları

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya tercih edilen herhangi bir .NET geliştirme ortamı
- Aspose.Slides for .NET kütüphanesi kuruldu
- Video kareleri eklemek istediğiniz bir PowerPoint sunumu (PPTX)

## Geliştirme Ortamınızı Kurma

1. Visual Studio'yu açın ve yeni bir .NET projesi oluşturun.
2.  Aspose.Slides NuGet paketini yükleyin:`Install-Package Aspose.Slides`.

## Sunum Yükleme ve Slaytlara Erişme

Başlamak için Aspose.Slides'ı kullanarak PowerPoint sunumunuzu yükleyin:

```csharp
using Aspose.Slides;

// Sunuyu yükle
using Presentation presentation = new Presentation("your-presentation.pptx");

// Slaytlara erişme
ISlideCollection slides = presentation.Slides;
```

## Sunuma Video Dosyaları Ekleme

1. Video dosyalarınızı projenizdeki bir klasöre yerleştirin.
2. Kodunuza bu dosyalara referanslar ekleyin:

```csharp
// Video dosyalarını ekleyin
string videoPath = "path-to-your-videos-folder";
string[] videoFiles = Directory.GetFiles(videoPath, "*.mp4");
```

## Video Çerçevelerini Slaytlara Yerleştirme

Slaytları yineleyin ve video kareleri ekleyin:

```csharp
foreach (ISlide slide in slides)
{
    foreach (string videoFile in videoFiles)
    {
        IVideoFrame videoFrame = slide.Shapes.AddVideoFrame(100, 100, 320, 240, videoFile);
    }
}
```

## Video Çerçevesi Özelliklerini Özelleştirme

Konum, boyut ve stil gibi video karesi özelliklerini özelleştirebilirsiniz:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.X = 200;
    videoFrame.Y = 150;
    videoFrame.Width = 480;
    videoFrame.Height = 360;
}
```

## Oynatma Seçeneklerinin Kullanımı

 kullanarak video oynatmayı kontrol edin.`VideoPlayModePreset` numaralandırma:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.PlayMode = VideoPlayModePreset.Auto;
}
```

## Değiştirilen Sunumu Kaydetme ve Dışa Aktarma

Video karelerini ekledikten sonra sununuzu kaydedin:

```csharp
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

## Çözüm

Aspose.Slides kullanarak sunum slaytlarınıza video çerçeveleri eklemek, içeriğinizin görsel etkisini artırır. Videoları sorunsuz bir şekilde nasıl entegre edeceğinizi, video karesi özelliklerini nasıl özelleştireceğinizi ve oynatma seçeneklerini nasıl kontrol edeceğinizi öğrendiniz. Hedef kitlenizin ilgisini çekecek dinamik ve ilgi çekici sunumlar oluşturmaya başlayın.

## SSS

### Tek bir slayda birden fazla videoyu nasıl eklerim?

Video dosyalarınızı yineleyin ve sağlanan kodu kullanarak istediğiniz slayda video kareleri ekleyin.

### Video oynatma ayarlarını kontrol edebilir miyim?

 Evet, kullanabilirsiniz`VideoPlayModePreset` Otomatik oynatma gibi oynatma seçeneklerini ayarlamak için numaralandırma.

### Hangi video formatları destekleniyor?

Aspose.Slides, MP4, AVI, WMV ve daha fazlası dahil olmak üzere çeşitli video formatlarını destekler.

### C#'ta programlı olarak video eklemek mümkün mü?

Kesinlikle Aspose.Slides for .NET, C# kullanarak programlı olarak slaytlara video eklemek için kullanıcı dostu bir API sağlar.

### Video çerçevesinin görünümünü değiştirebilir miyim?

Evet, video karesinin konumunu, boyutunu ve diğer görsel özelliklerini gereksinimlerinize göre özelleştirebilirsiniz.