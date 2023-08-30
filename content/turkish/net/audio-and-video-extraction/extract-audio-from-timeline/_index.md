---
title: Zaman Çizelgesinden Sesi Çıkar
linktitle: Zaman Çizelgesinden Sesi Çıkar
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint zaman çizelgelerinden nasıl ses çıkaracağınızı öğrenin. Kod örnekleri içeren adım adım kılavuz.
type: docs
weight: 13
url: /tr/net/audio-and-video-extraction/extract-audio-from-timeline/
---

## Aspose.Slides for .NET'e Giriş

Aspose.Slides for .NET, geliştiricilerin Microsoft Office'in kurulmasına gerek kalmadan PowerPoint sunumları oluşturmasına, düzenlemesine, dönüştürmesine ve değiştirmesine olanak tanıyan kapsamlı bir kitaplıktır. Slaytlar, şekiller, metinler, resimler ve hatta ses gibi sunum öğelerine erişim de dahil olmak üzere çok çeşitli özellikleri destekler. Bu kılavuzda bir sunumun zaman çizelgesinden ses çıkarmaya odaklanacağız.

## PowerPoint Sunumlarında Zaman Çizelgesini Anlamak

PowerPoint sunumundaki zaman çizelgesi olayların, animasyonların ve multimedya öğelerinin sırasını temsil eder. Buna slaytlarla senkronize edilen ses parçaları da dahildir. Aspose.Slides bu ses parçalarına programlı olarak erişmenizi ve çıkarmanızı sağlar.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya herhangi bir uyumlu .NET geliştirme ortamı
-  Aspose.Slides kütüphanesi. Şuradan indirebilirsiniz[Burada](https://downloads.aspose.com/slides/net)

## Adım 1: Aspose.Slides Kitaplığını Yükleme

1. Verilen bağlantıdan Aspose.Slides kütüphanesini indirin.
2. Referansı Aspose.Slides derlemesine ekleyerek kitaplığı .NET projenize yükleyin.

## Adım 2: Sunumu Yükleme

Bir sunumdan ses çıkarmak için önce PowerPoint dosyasını yüklemeniz gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Slides;

// Sunuyu yükle
using var presentation = new Presentation("presentation.pptx");
```

## 3. Adım: Zaman Çizelgesine Erişim

Sunuyu yükledikten sonra zaman çizelgesine ve ilgili ses parçalarına erişebilirsiniz:

```csharp
// İlk slayda erişin
var slide = presentation.Slides[0];

//Slaydın zaman çizelgesine erişin
var timeline = slide.Timeline;
```

## Adım 4: Sesi Zaman Çizelgesinden Çıkarma

Artık zaman çizelgesine erişiminiz olduğuna göre sesi çıkarabilirsiniz:

```csharp
foreach (var timeLineShape in timeline.Shapes)
{
    if (timeLineShape.MediaType == MediaType.Audio)
    {
        var audio = (IAudioFrame)timeLineShape;
        // Ses işleme kodunu buraya çıkarın
    }
}
```

## Adım 5: Çıkarılan Sesi Kaydetme

Sesi çıkardıktan sonra istediğiniz formatta kaydedebilirsiniz:

```csharp
audio.AudioData.WriteToFile("extracted_audio.mp3");
```

## Çözüm

Bu eğitimde Aspose.Slides for .NET kullanarak bir PowerPoint sunumunun zaman çizelgesinden nasıl ses çıkarılacağını araştırdık. Sunumun yüklenmesinden zaman çizelgesine erişmeye ve son olarak sesin çıkarılmasına kadar olan adımları ele aldık. Aspose.Slides bu süreci basitleştirerek PowerPoint sunumlarındaki çeşitli multimedya öğeleriyle programlı olarak çalışmayı kolaylaştırır.

## SSS'ler

### Aspose.Slides kütüphanesini nasıl kurabilirim?

 Aspose.Slides kütüphanesini şu adresten indirebilirsiniz:[Burada](https://downloads.aspose.com/slides/net). İndirdikten sonra .NET projenizdeki Aspose.Slides derlemesine bir referans ekleyin.

### Sunumdaki herhangi bir slayttan ses çıkarabilir miyim?


Evet, Aspose.Slides for .NET'i kullanarak sunumdaki herhangi bir slaydın zaman çizelgesinden ses çıkartabilirsiniz.

### Çıkarılan sesi hangi formatlarda kaydedebilirim?

Aspose.Slides, çıkarılan sesi MP3, WAV ve daha fazlası gibi çeşitli formatlarda kaydetmenize olanak tanır.

### Aspose.Slides'ı kullanabilmek için Microsoft Office'in yüklü olması gerekiyor mu?

Hayır, Microsoft Office'in kurulu olmasına gerek yok. Aspose.Slides for .NET, PowerPoint sunumlarıyla programlı olarak çalışmak için gerekli tüm işlevleri sağlar.

### Aspose.Slides ticari projeler için uygun mudur?

Evet, Aspose.Slides hem kişisel hem de ticari projeler için uygundur. PowerPoint sunumlarını programlı olarak yönetmek için çok çeşitli özellikler sunar.