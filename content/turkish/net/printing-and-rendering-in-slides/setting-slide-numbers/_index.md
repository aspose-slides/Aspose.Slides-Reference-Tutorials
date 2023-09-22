---
title: Aspose.Slides kullanarak Sunumlar için Slayt Numaralarını Ayarlama
linktitle: Aspose.Slides kullanarak Sunumlar için Slayt Numaralarını Ayarlama
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint sunumlarına slayt numaralarını nasıl ekleyeceğinizi ve özelleştireceğinizi öğrenin. Bu adım adım kılavuz, projeyi ayarlamak, bir sunumu yüklemek, slayt numaraları eklemek, formatlarını özelleştirmek ve yerleşimlerini ayarlamak için kaynak kodu örnekleri sağlar.
type: docs
weight: 16
url: /tr/net/printing-and-rendering-in-slides/setting-slide-numbers/
---

## Aspose.Slides for .NET'e Giriş

Aspose.Slides for .NET, .NET geliştiricilerinin PowerPoint sunumlarını programlı olarak oluşturmasına, değiştirmesine ve işlemesine olanak tanıyan çok yönlü bir kitaplıktır. Slaytlar, şekiller, metinler, resimler ve daha fazlası dahil olmak üzere çeşitli sunum öğeleriyle etkileşim kurmak için geniş bir özellik yelpazesi sunar. Bu kılavuzda Aspose.Slides for .NET'i kullanarak slayt numaraları eklemeye ve özelleştirmeye odaklanacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio (veya başka herhangi bir .NET geliştirme ortamı)
-  Aspose.Slides for .NET kitaplığı (Şuradan indirin:[Burada](https://releases.aspose.com/slides/net/)

## Projenin Kurulumu

1. Yeni bir Visual Studio projesi oluşturun (örneğin, Konsol Uygulaması).
2. Aspose.Slides for .NET kitaplığına bir referans ekleyin.

## Sunum Yükleme

Başlamak için mevcut bir PowerPoint sunumunu yükleyelim:

```csharp
using Aspose.Slides;

// Sunuyu yükle
using Presentation presentation = new Presentation("your-presentation.pptx");
```

## Slayt Numaraları Ekleme

Daha sonra sunumdaki her slayta slayt numaraları ekleyelim:

```csharp
// Slayt numaralarını etkinleştir
foreach (ISlide slide in presentation.Slides)
{
    // Slayt numarası şekli ekleme
    IAutoShape slideNumberShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 10, 10, 50, 20);
    slideNumberShape.TextFrame.Text = (slide.SlideNumber).ToString();
}
```

## Slayt Numarası Formatını Özelleştirme

Yazı tipini, rengini, boyutunu ve daha fazlasını ayarlayarak slayt numaralarının görünümünü özelleştirebilirsiniz:

```csharp
foreach (IAutoShape shape in presentation.Slides[0].Shapes.OfType<IAutoShape>())
{
    // Yazı tipini ve rengini özelleştirin
    ITextFrame textFrame = shape.TextFrame;
    IParagraph paragraph = textFrame.Paragraphs[0];
    IPortion portion = paragraph.Portions[0];
    
    portion.PortionFormat.FontHeight = 12;
    portion.PortionFormat.FillFormat.SolidFillColor.Color = Color.Black;
}
```

## Slayt Numarası Yerleşimini Güncelleme

Ayrıca her slayttaki slayt numaralarının konumunu da ayarlayabilirsiniz:

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IAutoShape shape in slide.Shapes.OfType<IAutoShape>())
    {
        shape.Left = slide.SlideSize.Size.Width - shape.Width - 10;
        shape.Top = slide.SlideSize.Size.Height - shape.Height - 10;
    }
}
```

## Değiştirilen Sunumu Kaydetme

Slayt numaralarını ekleyip özelleştirdikten sonra değiştirilen sunuyu kaydedin:

```csharp
presentation.Save("output-presentation.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu kılavuzda Aspose.Slides for .NET kullanarak slayt numaraları ekleyip özelleştirerek sunumlarınızı nasıl geliştirebileceğinizi araştırdık. Verilen adımları ve kod örneklerini takip ederek slayt numaraları ekleme işlemini otomatikleştirebilir ve profesyonel görünümlü sunumlar oluşturabilirsiniz.

## SSS'ler

### Aspose.Slides for .NET'i nasıl yüklerim?

 Aspose.Slides for .NET kütüphanesini şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/slides/net/). İndirdikten sonra .NET projenizdeki kitaplığa bir referans ekleyin.

### Slayt numaralarının görünümünü özelleştirebilir miyim?

Evet, sağlanan kod örneklerini kullanarak slayt numaralarının yazı tipini, rengini, boyutunu ve diğer özelliklerini özelleştirebilirsiniz.

### Her slayttaki slayt numaralarının konumunu nasıl ayarlayabilirim?

Kod örneklerinde gösterildiği gibi slayt numarası şekillerinin koordinatlarını değiştirerek slayt numaralarının konumunu ayarlayabilirsiniz.

### Aspose.Slides for .NET yalnızca slayt numaralarını eklemek için mi kullanılır?

Hayır, Aspose.Slides for .NET slayt numaraları eklemenin ötesinde çok çeşitli özellikler sunar. PowerPoint sunumlarının çeşitli öğelerini programlı olarak oluşturmanıza, değiştirmenize ve yönetmenize olanak tanır.

### Daha sonra slayt numaralarını kaldırmak istersem değişiklikler geri alınabilir mi?

Evet, Aspose.Slides kütüphanesini kullanarak ilgili şekilleri slaytlardan kaldırarak slayt numaralarını kolayca kaldırabilirsiniz.