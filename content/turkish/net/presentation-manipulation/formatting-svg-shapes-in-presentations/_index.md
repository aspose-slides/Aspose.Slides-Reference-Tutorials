---
title: Sunumlarda SVG Şekillerini Biçimlendirme
linktitle: Sunumlarda SVG Şekillerini Biçimlendirme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak sunumlarda SVG şekillerini nasıl formatlayacağınızı öğrenin. Kaynak koduyla adım adım kılavuz. Sunum tasarımınızı bugün yükseltin!
type: docs
weight: 13
url: /tr/net/presentation-manipulation/formatting-svg-shapes-in-presentations/
---

SVG (Ölçeklenebilir Vektör Grafikleri), iki boyutlu vektör grafiklerini temsil etmek için yaygın olarak kullanılan bir formattır. Aspose.Slides for .NET, geliştiricilerin sunumlarla programlı olarak çalışmasına olanak tanıyan güçlü bir kütüphanedir. Bu adım adım kılavuz, Aspose.Slides for .NET kullanılarak sunumlardaki SVG şekillerinin nasıl formatlanacağını gösterecektir.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. Visual Studio: Visual Studio'yu veya başka herhangi bir C# geliştirme ortamını yükleyin.
2.  Aspose.Slides for .NET: Aspose.Slides for .NET kitaplığını şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/slides/net/).

## Adım adım rehber

## 1. Yeni bir C# Projesi Oluşturun
Visual Studio'da yeni bir C# projesi oluşturun.

## 2. Aspose.Slides'a Referans Ekleyin
Projenize Aspose.Slides for .NET kitaplığına bir referans ekleyin.

## 3. Sunum Dosyasını Yükleyin
SVG şekillerini içeren PowerPoint sunum dosyasını yükleyin.

```csharp
using Aspose.Slides;

// Sunuyu yükle
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Kodunuz burada
}
```

## 4. Slayt ve SVG Şekline Erişim
Biçimlendirmek istediğiniz belirli slayda ve SVG şekline erişin.

```csharp
// Slayta erişme
ISlide slide = presentation.Slides[0]; // Uygun slayt indeksiyle değiştirin

// SVG şekline erişme
IShape svgShape = slide.Shapes[0]; // Uygun şekil indeksiyle değiştirin
```

## 5. SVG Şekline Biçimlendirme Uygulayın
 kullanarak SVG şekline biçimlendirme uygulayın.`ISvgShape` arayüz yöntemleri.

```csharp
// Şekli ISvgShape'e aktar
ISvgShape svg = svgShape as ISvgShape;

if (svg != null)
{
    // Biçimlendirmeyi uygula
    svg.FillFormat.SolidFillColor.Color = Color.Red;
    svg.LineFormat.Width = 2.0;
    svg.LineFormat.DashStyle = LineDashStyle.DashDot;
    
    // Diğer biçimlendirme seçenekleri
    //svg.LineFormat.FillFormat.SolidFillColor.Color = Color.Blue;
    // svg.LineFormat.Style = LineStyle.ThickBetweenThin;
}
```

## 6. Sunumu Kaydet
Değiştirilen sunuyu biçimlendirilmiş SVG şekliyle kaydedin.

```csharp
string outputPath = "output_path.pptx";
presentation.Save(outputPath, SaveFormat.Pptx);
```

## SSS

### Aspose.Slides for .NET'i nasıl kurabilirim?
 Aspose.Slides for .NET kütüphanesini sürümler sayfasından indirip kurabilirsiniz:[Aspose.Slides for .NET'i indirin](https://releases.aspose.com/slides/net/)

### Aspose.Slides'ı kullanarak mevcut bir sunumu nasıl yüklerim?
 kullanarak bir sunum yükleyebilirsiniz.`Presentation` sınıf. İşte bir örnek:
```csharp
using Aspose.Slides;

string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Kodunuz burada
}
```

### Biçimlendirmeyi bir SVG şekline nasıl uygularım?
 Bir SVG şeklini şunu kullanarak biçimlendirebilirsiniz:`ISvgShape` arayüz. Biçimlendirmeyi uygulamaya bir örnek:
```csharp
IShape svgShape = slide.Shapes[0]; // SVG şekline erişme
ISvgShape svg = svgShape as ISvgShape; // ISvgShape'e yayınla

if (svg != null)
{
    svg.FillFormat.SolidFillColor.Color = Color.Red; // Dolgu rengini ayarla
    svg.LineFormat.Width = 2.0; // Çizgi genişliğini ayarla
    svg.LineFormat.DashStyle = LineDashStyle.DashDot; // Çizgi çizgisi stilini ayarla
    // Diğer biçimlendirme seçenekleri
}
```

### Değiştirilen sunumu nasıl kaydederim?
 Değiştirilen sunumu kullanarak kaydedebilirsiniz.`Save` yöntem. İşte bir örnek:
```csharp
string outputPath = "output_path.pptx";
presentation.Save(outputPath, SaveFormat.Pptx);
```

 Daha ayrıntılı bilgi ve seçenekler için bkz.[Aspose.Slides for .NET API Referansı](https://reference.aspose.com/slides/net/).

## Çözüm
Bu kılavuzda Aspose.Slides for .NET kullanarak sunumlardaki SVG şekillerini nasıl formatlayacağınızı öğrendiniz. Sunumları yüklemeyi, SVG şekillerine erişmeyi, formatlamayı uygulamayı ve değiştirilen sunumu kaydetmeyi keşfettiniz. Aspose.Slides for .NET, sunumlarla programlı olarak çalışmak için kapsamlı bir araç seti sağlayarak slaytlarınızın her yönü üzerinde kontrol sahibi olmanızı sağlar.