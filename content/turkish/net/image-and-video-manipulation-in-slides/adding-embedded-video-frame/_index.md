---
title: Aspose.Slides kullanarak Sunum Slaytlarına Gömülü Video Çerçevesi Ekleme
linktitle: Aspose.Slides kullanarak Sunum Slaytlarına Gömülü Video Çerçevesi Ekleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak gömülü video çerçeveleri ekleyerek sunum slaytlarınızı nasıl geliştireceğinizi öğrenin. Videoları sorunsuz bir şekilde entegre etmek, oynatmayı özelleştirmek ve büyüleyici sunumlar oluşturmak için eksiksiz kaynak kodunu içeren bu adım adım kılavuzu izleyin.
type: docs
weight: 19
url: /tr/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

## Aspose.Slides for .NET'e Giriş

Aspose.Slides for .NET, geliştiricilerin PowerPoint sunumlarıyla programlı olarak çalışmasını sağlayan çok yönlü ve zengin özelliklere sahip bir kitaplıktır. Sunum oluşturma, düzenleme, dönüştürme ve değiştirme dahil çok çeşitli işlevler sağlar. Bu kılavuzda video karelerini sunum slaytlarına yerleştirme sürecine odaklanacağız.

## Önkoşullar

Uygulamaya geçmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio (veya başka herhangi bir .NET geliştirme ortamı)
- C# programlama dili hakkında temel bilgi
- Aspose.Slides for .NET kitaplığı

## Aspose.Slides for .NET'i Yükleme

Başlamak için Aspose.Slides for .NET kitaplığını yüklemeniz gerekir. Kütüphaneyi web sitesinden indirebilir veya NuGet gibi bir paket yöneticisi kullanabilirsiniz. NuGet'i kullanarak şu şekilde yükleyebilirsiniz:

```csharp
Install-Package Aspose.Slides
```

## Yeni Bir Sunu Oluşturma

Aspose.Slides'ı kullanarak yeni bir PowerPoint sunumu oluşturarak başlayalım. Sunum oluşturmak için temel kod pasajını burada bulabilirsiniz:

```csharp
using Aspose.Slides;

// Yeni bir sunu oluşturma
Presentation presentation = new Presentation();
```

## Slayt Ekleme

Daha sonra sunuma yeni bir slayt ekleyeceğiz. Slaytlar sıfırdan başlayarak dizine eklenir. Nasıl slayt ekleyebileceğiniz aşağıda açıklanmıştır:

```csharp
// Sunuya yeni bir slayt ekleme
ISlide slide = presentation.Slides.AddEmptySlide(SlideLayout.Blank);
```

## Video Yerleştirme

Şimdi işin heyecan verici kısmı geliyor; slayta video yerleştirme. Devam etmek için video dosyası yoluna veya URL'ye sahip olmanız gerekir. Slayda bir videoyu nasıl gömebileceğiniz aşağıda açıklanmıştır:

```csharp
// Video dosyasının yolu
string videoPath = "path_to_your_video.mp4";

// Videoyu slayta ekleyin
IVideoFrame videoFrame = slide.Shapes.AddVideoFrame(100, 100, 480, 270, videoPath);
```

## Video Çerçevesini Özelleştirme

Video karesinin boyutu, konumu ve oynatma seçenekleri gibi çeşitli yönlerini özelleştirebilirsiniz. Oynatma modunun otomatik olarak başlayacak şekilde nasıl ayarlanacağına dair bir örnek:

```csharp
// Video oynatma modunu otomatik olarak başlayacak şekilde ayarlayın
videoFrame.PlayMode = VideoPlayMode.Auto;
```

## Sunumu Kaydetme ve Dışa Aktarma

Video çerçevesini ekleyip beğeninize göre özelleştirdikten sonra sunuyu kaydetme zamanı gelir. PPTX veya PDF gibi çeşitli formatlarda kaydedebilirsiniz. Bunu PPTX dosyası olarak nasıl kaydedeceğiniz aşağıda açıklanmıştır:

```csharp
// Sunuyu kaydet
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu kılavuzda Aspose.Slides for .NET kullanarak gömülü video kareleri ekleyerek sunum slaytlarınızı nasıl geliştirebileceğinizi araştırdık. Bu güçlü kitaplık, hedef kitleniz üzerinde kalıcı bir etki bırakacak dinamik ve ilgi çekici sunumlar oluşturmanıza olanak tanır. Bu kılavuzda özetlenen adımları izleyerek multimedya içeriğini slaytlarınıza sorunsuz bir şekilde entegre edebilir ve büyüleyici sunumlar oluşturabilirsiniz.

## SSS'ler

### Aspose.Slides for .NET'i nasıl yüklerim?

 Aspose.Slides for .NET'i NuGet paket yöneticisini kullanarak yükleyebilirsiniz. NuGet Paket Yöneticisi Konsolunuzda aşağıdaki komutu çalıştırmanız yeterlidir:`Install-Package Aspose.Slides`

### Video çerçevesinin görünümünü özelleştirebilir miyim?

Evet, Aspose.Slides kütüphanesinin sağladığı özellikleri kullanarak video karesinin boyutunu, konumunu ve oynatma seçeneklerini özelleştirebilirsiniz.

### Yerleştirme için hangi video formatları destekleniyor?

Aspose.Slides, MP4, AVI ve WMV dahil olmak üzere çeşitli formatlardaki videoların yerleştirilmesini destekler.

### Videonun ne zaman oynatılmaya başlayacağını kontrol edebilir miyim?

Kesinlikle! Tercihlerinize bağlı olarak video karesinin oynatma modunu otomatik veya manuel olarak başlayacak şekilde ayarlayabilirsiniz.

### Aspose.Slides yalnızca video eklemek için mi kullanılıyor?

Hayır, Aspose.Slides video eklemenin ötesinde geniş bir işlevsellik yelpazesi sunuyor. PowerPoint sunumlarını programlı olarak oluşturmanıza, düzenlemenize, dönüştürmenize ve değiştirmenize olanak tanır.