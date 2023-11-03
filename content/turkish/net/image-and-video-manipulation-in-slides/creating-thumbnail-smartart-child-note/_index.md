---
title: Aspose.Slides'ta SmartArt Alt Notu için Küçük Resim Oluşturma
linktitle: Aspose.Slides'ta SmartArt Alt Notu için Küçük Resim Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak SmartArt alt notları için küçük resimler oluşturmayı öğrenin. Tam kaynak kodunu içeren adım adım kılavuz.
type: docs
weight: 15
url: /tr/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

## SmartArt Çocuk Notu için Küçük Resim Oluşturmaya Giriş

Bu eğitimde, .NET'teki Aspose.Slides kütüphanesini kullanarak SmartArt alt notu için küçük resim oluşturma sürecini anlatacağız. Aspose.Slides, geliştiricilerin PowerPoint sunumlarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir API'dir. Kodu göstererek ve sürecin her bölümünü açıklayarak adım adım ilerleyeceğiz.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio (veya herhangi bir başka .NET geliştirme ortamı) yüklü.
-  Aspose.Slides for .NET kitaplığı. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## Projenin Kurulumu

1. Visual Studio'da yeni bir C# projesi oluşturun.
2. Aspose.Slides for .NET kitaplığına bir referans ekleyin.

## Sunumu Yükleme

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // Sunuyu yükle
        using (Presentation presentation = new Presentation("presentation.pptx"))
        {
            // Kodunuz burada
        }
    }
}
```

## SmartArt Şekillerine Erişim

```csharp
// İlk slaytta bir SmartArt şeklimiz olduğunu varsayarsak
ISlide slide = presentation.Slides[0];
ISmartArt smartArt = (ISmartArt)slide.Shapes[0];

// Alt düğümlere erişme
ISmartArtNodeCollection nodes = smartArt.AllNodes;
```

## Alt Not için Küçük Resim Oluşturma

```csharp
foreach (ISmartArtNode node in nodes)
{
    // Düğümün alt düğümleri olduğunu varsayarsak
    ISmartArtNodeCollection childNodes = node.ChildNodes;

    // Küçük resim oluşturma
    using (Bitmap thumbnail = childNodes.GenerateThumbnail(new Size(200, 150)))
    {
        //Küçük resmi kaydedin veya diğer işlemleri gerçekleştirin
        thumbnail.Save($"thumbnail_{node.Text}.png");
    }
}
```

## Sunumu Küçük Resimlerle Kaydetme

```csharp
// Sunuyu küçük resimlerle kaydedin
presentation.Save("presentation_with_thumbnails.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde Aspose.Slides for .NET kullanarak SmartArt alt notları için küçük resimlerin nasıl oluşturulacağını öğrendik. Bir sunumun yüklenmesinden SmartArt şekillerine erişmeye, küçük resimler oluşturmaya ve sunumu küçük resimlerle kaydetmeye kadar tüm süreci ele aldık.

## SSS'ler

### Aspose.Slides for .NET'i nasıl kurabilirim?

 Aspose.Slides for .NET'i web sitelerinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/net/).

### Diğer şekiller için de küçük resimler oluşturabilir miyim?

Evet, Aspose.Slides; resimler, grafikler ve daha fazlası dahil olmak üzere farklı şekil türleri için küçük resimler oluşturmak için çeşitli yöntemler sunar.

### Aspose.Slides hem kişisel hem de ticari projeler için uygun mu?

Evet, Aspose.Slides hem kişisel hem de ticari projelerde kullanılabilir. Ancak dağıtımdan önce lisans koşullarını gözden geçirdiğinizden emin olun.

### Oluşturulan küçük resimlerin görünümünü özelleştirebilir miyim?

Kesinlikle! Aspose.Slides, oluşturulan küçük resimlerin boyutunu, kalitesini ve diğer özelliklerini gereksinimlerinize uyacak şekilde özelleştirmenize olanak tanır.

### Aspose.Slides .NET dışında diğer programlama dillerini destekliyor mu?

Evet, Aspose.Slides; Java, Python ve daha fazlası dahil olmak üzere birden fazla programlama dili için mevcut olduğundan, çeşitli geliştirme ortamları için çok yönlüdür.