---
title: Notlardaki Slayttan Küçük Resim Oluştur
linktitle: Notlardaki Slayttan Küçük Resim Oluştur
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak notlar içeren slaytlardan küçük resimler oluşturun. Notları nasıl çıkaracağınızı, küçük resimler oluşturacağınızı ve PowerPoint düzenlemelerinizi nasıl geliştireceğinizi adım adım öğrenin.
type: docs
weight: 12
url: /tr/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

Günümüzün dijital çağında sunumlar, bilgi ve fikirlerin etkili bir şekilde aktarılmasında çok önemli bir rol oynamaktadır. Aspose.Slides for .NET gibi güçlü kitaplıkların ortaya çıkışıyla geliştiriciler, PowerPoint sunumlarındaki içeriği programlı olarak değiştirme ve çıkarma becerisini kazandılar. Yaygın gereksinimlerden biri, özellikle slaytlar önemli notlar içerdiğinde slaytlardan küçük resimler oluşturmaktır. Bu adım adım kılavuz, Aspose.Slides for .NET kullanarak notlar içeren slaytlardan küçük resimler oluşturma sürecinde size yol gösterecektir.

## Önkoşullar

Sürece dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Makinenizde Visual Studio yüklü.
- C# programlama ve .NET geliştirme konusunda temel bilgi.
-  Aspose.Slides for .NET kitaplığı. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## PowerPoint Sunumu Yükleme

İlk adım, Aspose.Slides for .NET kullanarak PowerPoint sunumunu yüklemeyi içerir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Slides;

// Sunuyu yükle
using (var presentation = new Presentation("your-presentation.pptx"))
{
    // Kodunuz burada
}
```

## Slaytları Notlarla Çıkarma

Slaytları notlarıyla birlikte çıkarmak için slaytlar arasında ilerlemeniz ve notlarına erişmeniz gerekir. Bunu şu şekilde başarabilirsiniz:

```csharp
// Slaytlar arasında yineleme
foreach (ISlide slide in presentation.Slides)
{
    // Slaytın notları olup olmadığını kontrol edin
    if (slide.NotesSlide != null)
    {
        // Notlara erişme
        string notes = slide.NotesSlide.NotesTextFrame.Text;
        
        // Kodunuz burada
    }
}
```

## Slaytlardan Küçük Resimler Oluşturma

Şimdi SlideUtil sınıfını kullanarak slaytlardan küçük resimler oluşturalım:

```csharp
using Aspose.Slides.Util;

// Slayt için küçük resim oluşturma
var thumbnail = SlideUtil.GetSlideThumbnail(slide, 1.0f);
```

## Küçük Resimleri Diske Kaydetme

Küçük resimleri oluşturduktan sonra bunları yerel diskinize kaydedebilirsiniz:

```csharp
// Küçük resmi diske kaydet
thumbnail.Save("slide-thumbnail.png", ImageFormat.Png);
```

## Çözüm

Bu eğitimde Aspose.Slides for .NET kullanarak notlar içeren slaytlardan küçük resimlerin nasıl oluşturulacağını araştırdık. Bir sunumu yüklemeyi, not içeren slaytları çıkarmayı, küçük resimler oluşturmayı ve bunları diske kaydetmeyi anlattık. Bu bilgiyle PowerPoint sunumunun işlenmesini içeren özellikler ekleyerek uygulamalarınızı geliştirebilirsiniz.

## SSS

### Aspose.Slides for .NET kütüphanesini nasıl edinebilirim?

 Aspose.Slides for .NET kütüphanesini şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/slides/net/).

### Yalnızca belirli slaytlar için küçük resimler oluşturabilir miyim?

Evet, ilgili slayt dizinini sunucuya sağlayarak belirli slaytlar için küçük resimler oluşturabilirsiniz.`SlideUtil.GetSlideThumbnail` yöntem.

### Aspose.Slides for .NET platformlar arası uygulamalara uygun mu?

Evet, Aspose.Slides for .NET, Windows ve Linux da dahil olmak üzere çeşitli platformlarla uyumludur ve bu da onu çapraz platform uygulamaları için uygun kılar.

### Oluşturulan küçük resimlerin görünümünü özelleştirebilir miyim?

Kesinlikle! Oluşturulan küçük resimlerin boyutunu, kalitesini ve diğer özelliklerini uygulamanızın gereksinimlerine uyacak şekilde ayarlayabilirsiniz.

### Aspose.Slides for .NET diğer PowerPoint düzenleme görevlerini destekliyor mu?

Evet, Aspose.Slides for .NET, PowerPoint sunumları oluşturma, düzenleme, dönüştürme ve işleme dahil çok çeşitli özellikler sunar.