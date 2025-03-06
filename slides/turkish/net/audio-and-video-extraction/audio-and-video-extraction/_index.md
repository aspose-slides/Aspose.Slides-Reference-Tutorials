---
title: Aspose.Slides for .NET ile Ses ve Video Çıkarmada Uzmanlaşmak
linktitle: Aspose.Slides kullanarak Slaytlardan Ses ve Video Çıkarma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint slaytlarından nasıl ses ve video çıkaracağınızı öğrenin. Zahmetsiz multimedya çıkarma.
weight: 10
url: /tr/net/audio-and-video-extraction/audio-and-video-extraction/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## giriiş

Dijital çağda multimedya sunumları iletişim, eğitim ve eğlencenin ayrılmaz bir parçası haline geldi. PowerPoint slaytları sıklıkla bilgi aktarmak için kullanılır ve sıklıkla ses ve video gibi temel unsurları içerir. Bu öğelerin çıkarılması, sunumların arşivlenmesinden içeriğin yeniden kullanılmasına kadar çeşitli nedenlerle çok önemli olabilir.

Bu adım adım kılavuzda Aspose.Slides for .NET kullanarak PowerPoint slaytlarından nasıl ses ve video çıkarılacağını keşfedeceğiz. Aspose.Slides, .NET geliştiricilerinin PowerPoint sunumlarıyla programlı olarak çalışmasına olanak tanıyan, multimedya çıkarma gibi görevleri her zamankinden daha erişilebilir hale getiren güçlü bir kütüphanedir.

## Önkoşullar

PowerPoint slaytlarından ses ve video çıkarmanın ayrıntılarına dalmadan önce, yerine getirmeniz gereken birkaç önkoşul vardır:

1. Visual Studio: .NET geliştirme için makinenizde Visual Studio'nun kurulu olduğundan emin olun.

2.  Aspose.Slides for .NET: Aspose.Slides for .NET'i indirip yükleyin. Kütüphaneyi ve belgeleri şu adreste bulabilirsiniz:[Aspose.Slides for .NET web sitesi](https://releases.aspose.com/slides/net/).

3. PowerPoint Sunumu: Çıkarma alıştırması yapmak için ses ve video öğeleri içeren bir PowerPoint sunumu hazırlayın.

Şimdi PowerPoint slaytlarından ses ve video çıkarma sürecini takip edilmesi kolay birden fazla adıma ayıralım.

## Slayttan Sesi Çıkarma

### 1. Adım: Projenizi Kurun

Visual Studio'da yeni bir proje oluşturarak ve gerekli Aspose.Slides ad alanlarını içe aktararak başlayın:

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideShow;
```

### 2. Adım: Sunuyu Yükleyin

Çıkarmak istediğiniz sesi içeren PowerPoint sunumunu yükleyin:

```csharp
string dataDir = "Your Document Directory";
string presName = dataDir + "AudioSlide.ppt";
Presentation pres = new Presentation(presName);
```

### 3. Adım: İstediğiniz Slayta Erişin

 Belirli bir slayta erişmek için`ISlide` arayüz:

```csharp
ISlide slide = pres.Slides[0];
```

### Adım 4: Sesi Çıkarın

Slaydın geçiş efektlerinden ses verilerini alın:

```csharp
ISlideShowTransition transition = slide.SlideShowTransition;
byte[] audio = transition.Sound.BinaryData;
System.Console.WriteLine("Length: " + audio.Length);
```

## Slayttan Video Çıkarma

### 1. Adım: Projenizi Kurun

Tıpkı ses çıkarma örneğinde olduğu gibi, yeni bir proje oluşturup gerekli Aspose.Slides ad alanlarını içe aktararak başlayın.

### 2. Adım: Sunuyu Yükleyin

Çıkarmak istediğiniz videoyu içeren PowerPoint sunumunu yükleyin:

```csharp
string dataDir = "Your Document Directory";
string presName = dataDir + "Video.pptx";
Presentation pres = new Presentation(presName);
```

### 3. Adım: Slaytlar ve Şekiller Üzerinde Yineleme Yapın

Video karelerini tanımlamak için slaytlar ve şekiller arasında dolaşın:

```csharp
foreach (ISlide slide in pres.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
        if (shape is VideoFrame)
        {
            // Video karesi bilgilerini çıkarın
            IVideoFrame vf = shape as IVideoFrame;
            String type = vf.EmbeddedVideo.ContentType;
            int ss = type.LastIndexOf('/');
            type = type.Remove(0, type.LastIndexOf('/') + 1);
            
            // Bayt dizisi olarak video verilerini alın
            Byte[] buffer = vf.EmbeddedVideo.BinaryData;
            
            // Videoyu bir dosyaya kaydedin
            using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
            {
                stream.Write(buffer, 0, buffer.Length);
            }
        }
    }
}
```

## Çözüm

Aspose.Slides for .NET, PowerPoint sunumlarından ses ve video çıkarma işlemini basitleştirir. İster multimedya içeriğini arşivlemek, başka bir amaca uygun hale getirmek veya analiz etmek üzerinde çalışıyor olun, bu kitaplık görevi kolaylaştırır.

Bu kılavuzda özetlenen adımları izleyerek PowerPoint sunumlarınızdan kolayca ses ve video çıkarabilir ve bu öğelerden çeşitli şekillerde yararlanabilirsiniz.

Aspose.Slides for .NET ile etkili multimedya çıkarımının doğru araçlara, kütüphaneye ve multimedya öğeleri içeren bir PowerPoint sunumuna bağlı olduğunu unutmayın.

## SSS

### Aspose.Slides for .NET en son PowerPoint formatlarıyla uyumlu mu?
Evet, Aspose.Slides for .NET, PPTX dahil en yeni PowerPoint formatlarını destekler.

### Aynı anda birden fazla slayttan ses ve video çıkarabilir miyim?
Evet, birden fazla slaytta ilerlemek ve her birinden multimedya çıkarmak için kodu değiştirebilirsiniz.

### Aspose.Slides for .NET için herhangi bir lisanslama seçeneği var mı?
Aspose, ücretsiz denemeler ve geçici lisanslar dahil olmak üzere çeşitli lisanslama seçenekleri sunar. Bu seçenekleri kendi sitelerinde keşfedebilirsiniz.[İnternet sitesi](https://purchase.aspose.com/buy).

### Aspose.Slides for .NET için nasıl destek alabilirim?
 Teknik destek ve topluluk tartışmaları için Aspose.Slides'ı ziyaret edebilirsiniz.[forum](https://forum.aspose.com/).

### Aspose.Slides for .NET ile başka hangi görevleri gerçekleştirebilirim?
 Aspose.Slides for .NET, PowerPoint sunumları oluşturma, değiştirme ve dönüştürme dahil çok çeşitli özellikler sunar. Daha fazla ayrıntı için belgeleri inceleyebilirsiniz:[Aspose.Slides for .NET Belgeleri](https://reference.aspose.com/slides/net/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
