---
title: Şekilleri Sunumdan SVG Formatına Aktarma
linktitle: Şekilleri Sunumdan SVG Formatına Aktarma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak şekilleri bir PowerPoint sunumundan SVG formatına nasıl aktaracağınızı öğrenin. Kaynak kodu içeren adım adım kılavuz. Çeşitli uygulamalar için şekilleri verimli bir şekilde çıkarın.
type: docs
weight: 16
url: /tr/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---
Bu kılavuz, Aspose.Slides for .NET kütüphanesini kullanarak şekilleri bir sunumdan SVG formatına aktarma sürecinde size yol gösterecektir. Aspose.Slides, Microsoft PowerPoint dosyalarıyla programlı olarak çalışmanıza olanak tanıyan güçlü bir API'dir. Bu eğitimde, C# kullanarak bir sunumdan şekilleri nasıl çıkaracağınızı ve bunları SVG formatında nasıl kaydedeceğinizi öğreneceksiniz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio yüklü
- C# programlamanın temel anlayışı
-  Aspose.Slides for .NET kitaplığı. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## Adım adım rehber

Bir sunumdan şekilleri SVG formatına aktarmak için şu adımları izleyin:

### 1. Yeni Bir Proje Oluşturun

Visual Studio'yu açın ve yeni bir C# projesi oluşturun.

### 2. Aspose.Slides'a Referans Ekleyin

Projenizde, Solution Explorer'da "Referanslar"a sağ tıklayın, ardından "Referans Ekle"ye tıklayın. İndirdiğiniz Aspose.Slides DLL dosyasına göz atın ve seçin.

### 3. Sunumu Yükleyin

```csharp
using Aspose.Slides;

// Sunuyu yükle
Presentation presentation = new Presentation("presentation.pptx");
```

### 4. Şekilleri Yineleyin

```csharp
foreach (IShape shape in presentation.Slides[0].Shapes)
{
    // Şeklin bir grup şekli olup olmadığını kontrol edin
    if (shape is IGroupShape groupShape)
    {
        foreach (IShape groupChildShape in groupShape.Shapes)
        {
            // Şekli SVG'ye aktar
            string svgFileName = $"shape_{groupChildShape.Id}.svg";
            groupChildShape.WriteAsSvg(svgFileName);
        }
    }
    else
    {
        // Şekli SVG'ye aktar
        string svgFileName = $"shape_{shape.Id}.svg";
        shape.WriteAsSvg(svgFileName);
    }
}
```

### 5. SVG Dosyalarını Kaydet

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx); // Sunudaki değişiklikleri kaydedin
```

## SSS

### Aspose.Slides for .NET'i nasıl kurabilirim?

 Aspose.Slides for .NET kütüphanesini şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/slides/net/). Belgelerde sağlanan kurulum talimatlarını izleyin.

### Aspose.Slides'ı kullanarak bir PowerPoint sunumunu nasıl yüklerim?

 kullanarak bir sunum yükleyebilirsiniz.`Presentation` sınıf yapıcısı. PowerPoint dosyasının yolunu parametre olarak belirtin.

### Bir şekli SVG formatına nasıl aktarırım?

 Şunu kullanabilirsiniz:`WriteAsSvg` bir yöntem`IShape` SVG formatına aktarmak için nesneyi seçin. SVG çıktısı için dosya adını belirtmeniz gerekir.

## Çözüm

Bu eğitimde Aspose.Slides for .NET kitaplığını kullanarak şekilleri bir PowerPoint sunumundan SVG formatına nasıl aktaracağınızı öğrendiniz. Bu, SVG grafiklerini destekleyen diğer uygulamalarda veya platformlarda kullanmak üzere ayrı ayrı şekiller çıkarmanız gerektiğinde yararlı olabilir. Aspose.Slides bunu programlı olarak gerçekleştirmenin basit ve etkili bir yolunu sunar.

 Daha fazla ayrıntı ve gelişmiş özellikler için bkz.[Aspose.Slides for .NET API Referansı](https://reference.aspose.com/slides/net/).