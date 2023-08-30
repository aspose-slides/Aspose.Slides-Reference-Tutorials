---
title: Aspose.Slides ile Sunum Slaytlarına Web Kaynağından Video Kareleri Ekleme
linktitle: Aspose.Slides ile Sunum Slaytlarına Web Kaynağından Video Kareleri Ekleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak web kaynaklarından video kareleri ekleyerek sunum slaytlarınızı nasıl geliştireceğinizi öğrenin. Adım adım talimatlar ve kaynak kodu örnekleriyle ilgi çekici multimedya sunumları oluşturun.
type: docs
weight: 20
url: /tr/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---

Günümüzün dinamik dünyasında sunumlar statik slaytların ötesine geçmiştir. Videolar gibi multimedya öğelerini sunumunuza entegre etmek, etkileşimi önemli ölçüde artırabilir ve bilgileri daha etkili bir şekilde iletebilir. Aspose.Slides for .NET, geliştiricilerin web kaynaklarından video karelerini sunum slaytlarına sorunsuz bir şekilde dahil etmelerini sağlar. Bu kılavuz süreç boyunca size adım adım yol göstererek Aspose.Slides'ın gücünü gösterir.

## Önkoşullar

Uygulamaya geçmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio veya yüklü herhangi bir uyumlu IDE
- Aspose.Slides for .NET kitaplığı
- C# programlamaya ilişkin temel bilgiler

## 1. Adım: Projenizi Kurma

Başlamak için tercih ettiğiniz IDE'de yeni bir proje oluşturun ve Aspose.Slides for .NET kütüphanesini ekleyin. Kitaplığı web sitesinden indirebilir veya NuGet Paket Yöneticisini kullanarak yükleyebilirsiniz.

## Adım 2: Slayta Video Çerçevesi Ekleme

1.  Yeni bir örneğini oluştur`Presentation` Aspose.Slides'ı kullanarak.
2.  kullanarak sunuya yeni bir slayt ekleyin.`Slides` Toplamak.
3. Slayttaki video çerçevesinin konumunu ve boyutlarını tanımlayın.
4.  Kullan`EmbedWebVideoFrame` Video çerçevesini slayda ekleme yöntemi.

```csharp
// Yeni bir Sunu oluştur
using (Presentation presentation = new Presentation())
{
    // Yeni bir slayt ekle
    ISlide slide = presentation.Slides.AddEmptySlide();

    // Video çerçevesinin konumunu ve boyutlarını tanımlayın
    int x = 100; // X koordinatı
    int y = 100; // Y koordinatı
    int width = 480; // Genişlik
    int height = 270; // Yükseklik

    // Slayta video çerçevesi ekleme
    slide.EmbedWebVideoFrame(x, y, width, height, new Uri("https://example.com/video.mp4"));
    
    // Sunuyu kaydet
    presentation.Save("output.pptx", SaveFormat.Pptx);
}
```

## 3. Adım: Video Oynatmayı Özelleştirme

Aspose.Slides, sunumunuzdaki video oynatma deneyimini özelleştirmeniz için çeşitli seçenekler sunar. Gömülü videonun otomatik oynatma, döngü ve sessize alma ayarları gibi özelliklerini kontrol edebilirsiniz.

```csharp
// Video karesini slayta alın
IVideoFrame videoFrame = (IVideoFrame)slide.Shapes[0];

//Otomatik oynatmayı etkinleştir
videoFrame.PlayMode = VideoPlayModePreset.Auto;

// Döngüyü etkinleştir
videoFrame.PlayLoopMode = VideoPlayLoopMode.Loop;

// Videonun sesini kapat
videoFrame.Volume = AudioVolumeMode.Mute;
```

## SSS

### Gömülü videonun kaynağını nasıl değiştirebilirim?

 Gömülü videonun kaynağını değiştirmek için, dosyada sağlanan URI'yi güncellemeniz yeterlidir.`EmbedWebVideoFrame` yeni web kaynağına işaret etme yöntemi.

### Video çerçevesinin görünümünü özelleştirebilir miyim?

Evet, konum, boyut ve şekil biçimlendirmesi gibi özellikleri kullanarak video çerçevesinin görünümünü özelleştirebilirsiniz.

### Videonun ne zaman oynatılmaya başlayacağını kontrol etmek mümkün mü?

 Kesinlikle! Oynatmanın başlama zamanını ayarlayarak kontrol edebilirsiniz.`videoFrame.StartTime` mülk.

### Yerleştirme için hangi video formatları destekleniyor?

Aspose.Slides, MP4, YouTube bağlantıları ve daha fazlası gibi popüler formatlar da dahil olmak üzere çeşitli web kaynaklarından video karelerinin yerleştirilmesini destekler.

### Gömülü videonun platformlar arası uyumluluğunu nasıl sağlayabilirim?

Gömülü video çerçeveleri, Microsoft PowerPoint'in ve diğer uyumlu sunum yazılımlarının modern sürümlerinde desteklenir.

## Çözüm

Aspose.Slides for .NET kullanarak web kaynaklarından video karelerini sunum slaytlarınıza dahil etmek, sunumlarınızı ilgi çekici multimedya deneyimlerine dönüştürebilir. Bu adım adım kılavuz, video karelerinin sorunsuz bir şekilde nasıl yerleştirileceğini, oynatmanın nasıl özelleştirileceğini ve sık sorulan soruların nasıl yanıtlanacağını göstermektedir. Sunumlarınızı dinamik video içeriğiyle geliştirin ve izleyicilerinizi daha önce hiç olmadığı kadar büyüleyin!