---
title: Aspose.Slides Kullanarak Sunum Slaytlarında Basit Dikdörtgen Şekil Oluşturma
linktitle: Aspose.Slides Kullanarak Sunum Slaytlarında Basit Dikdörtgen Şekil Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint slaytlarında basit bir dikdörtgen şeklinin nasıl oluşturulacağını öğrenin. Bu adım adım kılavuz, sunularınızı program aracılığıyla eklemek, özelleştirmek ve geliştirmek için kaynak kodu ve talimatlar sağlar.
type: docs
weight: 12
url: /tr/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

## Aspose.Slides for .NET'e Giriş

Aspose.Slides for .NET, geliştiricilerin PowerPoint sunumlarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir kitaplıktır. Slaytlar, şekiller, metinler, resimler ve daha fazlasını içeren sunum öğelerini oluşturmak, değiştirmek ve yönetmek için çok çeşitli özellikler sağlar. Bu kılavuzda Aspose.Slides for .NET'in özelliklerini kullanarak bir sunum slaytında basit bir dikdörtgen şekli oluşturmaya odaklanacağız.

## Geliştirme Ortamını Kurma

Kodlara dalmadan önce geliştirme ortamımızı ayarlayalım. Bu adımları takip et:

1.  Aspose.Slides for .NET'i indirin:[indirme sayfası](https://releases.aspose.com/slides/net/) ve projenizle uyumlu sürümü seçin.

2. Aspose.Slides'ı yükleyin: İndirdikten sonra, DLL referansını projenize ekleyerek Aspose.Slides'ı yükleyin.

3. Yeni Bir Proje Oluşturun: Tercih ettiğiniz geliştirme ortamını (örneğin, Visual Studio) kullanarak yeni bir .NET projesi oluşturun.

## Yeni Bir Sunu Oluşturma

Aspose.Slides for .NET'i kullanarak yeni bir PowerPoint sunumu oluşturarak başlayalım.

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // Yeni bir sunu oluşturma
        Presentation presentation = new Presentation();

        // Sunuya boş bir slayt ekleme
        Slide slide = presentation.Slides.AddEmptySlide();

        // Dikdörtgen şeklini ekleme kodunuz buraya gelecek

        // Sunuyu kaydet
        presentation.Save("RectangleShapePresentation.pptx", SaveFormat.Pptx);
    }
}
```

## Slayta Dikdörtgen Şekli Ekleme

Artık sunum slaytımız hazır olduğuna göre ona dikdörtgen şekli eklemeye geçelim.

```csharp
// Slayta dikdörtgen şekli ekleme
double x = 100; // Şeklin X koordinatı
double y = 100; // Şeklin Y koordinatı
double width = 200; // Şeklin genişliği
double height = 100; // Şeklin yüksekliği

slide.Shapes.AddRectangle(x, y, width, height);
```

## Dikdörtgen Şeklini Özelleştirme

Dikdörtgen şeklinin dolgu rengi, kenarlık stili ve daha fazlası gibi çeşitli yönlerini özelleştirebilirsiniz.

```csharp
// Eklenen şekli alın (dikdörtgen)
IShape rectangle = slide.Shapes[0];

// Dolgu rengini özelleştirin
rectangle.FillFormat.SolidFillColor.Color = Color.Blue;

// Kenarlığı özelleştir
rectangle.LineFormat.Width = 2; // Kenarlık genişliği
rectangle.LineFormat.DashStyle = LineDashStyle.DashDot; // Kenarlık stili
rectangle.LineFormat.FillFormat.SolidFillColor.Color = Color.Red; // Sınır rengi
```

## Sunumu Kaydetme

Dikdörtgen şeklini ekleyip özelleştirdikten sonra sunuyu kaydetme zamanı gelir.

```csharp
// Sunuyu kaydet
presentation.Save("RectangleShapePresentation.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu kılavuzda Aspose.Slides for .NET kullanarak bir sunum slaytında basit bir dikdörtgen şeklinin nasıl oluşturulacağını araştırdık. Geliştirme ortamını kurma, yeni bir sunum oluşturma, dikdörtgen şekli ekleme, görünümünü özelleştirme ve son sunumu kaydetme gibi temel adımları ele aldık. Aspose.Slides for .NET ile PowerPoint sunumlarınızı kolayca otomatikleştirip geliştirebilir, bir dinamizm ve etkileşim katmanı sağlayabilirsiniz.

## SSS'ler

### Aspose.Slides for .NET'i nasıl yüklerim?

Aspose.Slides for .NET'i yüklemek için şu adımları izleyin:

1.  Ziyaret edin[indirme sayfası](https://releases.aspose.com/slides/net/).
2. Projenizle uyumlu sürümü seçin.
3. Aspose.Slides DLL referansını .NET projenize ekleyin.

### Dikdörtgen şeklinin dolgu rengini özelleştirebilir miyim?

 Evet, dikdörtgen şeklinin dolgu rengini aşağıdaki düğmeyi kullanarak özelleştirebilirsiniz:`FillFormat` mülk. Sadece şekle erişin`FillFormat` ve istediğinizi ayarlayın`SolidFillColor`.

### Dikdörtgen şeklini ekledikten sonra sunumu nasıl kaydederim?

Sunuyu kullanarak kaydedebilirsiniz.`Save` yöntemi`Presentation` sınıf. İstediğiniz dosya adını ve istediğiniz kaydetme formatını (örneğin`SaveFormat.Pptx`).

### Aspose.Slides for .NET yalnızca dikdörtgen şekiller için uygun mudur?

Hayır, Aspose.Slides for .NET çok çeşitli şekilleri ve sunum öğelerini destekler. Dikdörtgenler, daireler, oklar ve daha fazlası gibi şekiller oluşturabilir ve değiştirebilirsiniz.

### Aspose.Slides for .NET hakkında daha fazla belgeyi nerede bulabilirim?

 Aspose.Slides for .NET'e ilişkin ayrıntılı belgeleri ve API referanslarını şu adreste bulabilirsiniz:[dokümantasyon sayfası](https://reference.aspose.com/slides/net/).