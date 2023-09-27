---
title: Aspose.Slides ile Sunum Slaytlarında Grup Şekilleri Oluşturma
linktitle: Aspose.Slides ile Sunum Slaytlarında Grup Şekilleri Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak grup şekilleriyle büyüleyici sunum slaytları oluşturmayı öğrenin. Şekilleri kolayca eklemek, gruplamak ve dönüştürmek ve sunumlarınızı geliştirmek için adım adım kılavuzumuzu ve kaynak kodu örneğimizi takip edin.
type: docs
weight: 11
url: /tr/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

## Aspose.Slides for .NET'e Giriş

Aspose.Slides for .NET, geliştiricilerin PowerPoint sunumlarını programlı olarak değiştirmelerine olanak tanıyan kapsamlı ve zengin özelliklere sahip bir kitaplıktır. Sunum dosyalarını oluşturmak, değiştirmek veya dönüştürmek istiyorsanız Aspose.Slides, süreci basitleştirmek için çok çeşitli araçlar ve işlevler sunar.

## Önkoşullar

Aspose.Slides for .NET ile çalışmaya başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio: Visual Studio'yu makinenize yükleyin.
-  Aspose.Slides Kütüphanesi: Projenizde Aspose.Slides kütüphanesini indirin ve referans alın. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## Aspose.Slides'ı Projenize Ekleme

1. Verilen bağlantıdan Aspose.Slides kütüphanesini indirin.
2. Visual Studio'da yeni bir proje oluşturun veya mevcut bir projeyi açın.
3. Çözüm Gezgini'nde projenize sağ tıklayın ve "NuGet Paketlerini Yönet"i seçin.
4. "Gözat" sekmesini seçin ve "Aspose.Slides"ı arayın.
5. Aspose.Slides paketini projenize yükleyin.

## Yeni Bir Sunu Oluşturma

Aspose.Slides'ı kullanarak yeni bir PowerPoint sunumu oluşturarak başlayalım:

```csharp
using Aspose.Slides;

// Yeni bir sunu oluşturma
Presentation presentation = new Presentation();
```

## Slayta Şekiller Ekleme

Daha sonra slayta bazı şekiller ekleyelim. Bu örnekte iki dikdörtgen ekleyeceğiz:

```csharp
// İlk slayda erişin
ISlide slide = presentation.Slides[0];

// Slayta dikdörtgenler ekleme
IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);
```

## Şekilleri Birlikte Gruplandırma

Şimdi şekilleri toplu olarak yönetmek için birlikte gruplayalım:

```csharp
// Grup şekilleri
IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });
```

## Gruplandırılmış Şekillere Dönüşümler Uygulama

Gruplandırılmış şekillere çeşitli dönüşümler uygulayabilirsiniz. Örneğin gruplandırılmış şekilleri 45 derece döndürelim:

```csharp
// Grubu 45 derece döndürün
groupShape.Rotation = 45;
```

## Kaynak Kodu Örneği

Aspose.Slides'ı kullanarak grup şekilleri oluşturmanın tam kaynak kodu örneğini burada bulabilirsiniz:

```csharp
using Aspose.Slides;

namespace GroupShapesExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Yeni bir sunu oluşturma
            Presentation presentation = new Presentation();

            // İlk slayda erişin
            ISlide slide = presentation.Slides[0];

            // Slayta dikdörtgenler ekleme
            IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
            IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);

            // Grup şekilleri
            IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });

            // Grubu 45 derece döndürün
            groupShape.Rotation = 45;

            // Sunuyu kaydet
            presentation.Save("GroupShapesExample.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Çözüm

Bu eğitimde Aspose.Slides for .NET kullanarak sunum slaytlarında grup şekillerinin nasıl oluşturulacağını öğrendiniz. Kitaplık, sunumlarınızı dinamik olarak geliştirmek için şekiller eklemek, bunları bir arada gruplamak ve dönüşümler uygulamak için basit bir yol sağlar.

## SSS'ler

### Aspose.Slides for .NET'i nasıl yüklerim?

 Aspose.Slides kütüphanesini sağlanan bağlantıdan indirebilirsiniz:[Burada](https://releases.aspose.com/slides/net/). İndirdikten sonra NuGet paketlerini kullanarak projenize ekleyebilirsiniz.

### Gruplandırılmış şekillere farklı dönüşümler uygulayabilir miyim?

Evet, gruplandırılmış şekillere döndürme, ölçekleme ve konumlandırma gibi çeşitli dönüşümler uygulayarak slaytlarınızın görsel görünümünü özelleştirebilirsiniz.

### Aspose.Slides sunum oluşturmaya ve değiştirmeye uygun mu?

Kesinlikle! Aspose.Slides for .NET, sunum dosyalarının oluşturulmasını, değiştirilmesini ve dönüştürülmesini destekleyen çok yönlü bir kitaplıktır. Farklı ihtiyaçlara cevap verecek geniş bir özellik yelpazesi sunar.

### Farklı türdeki şekilleri bir arada gruplayabilir miyim?

 Evet, dikdörtgenler, daireler ve metin kutuları gibi farklı türdeki şekilleri birlikte gruplandırabilirsiniz.`GroupShapes` yöntem. Bu, bunları toplu olarak yönetmenize ve manipüle etmenize olanak tanır.

### Aspose.Slides yalnızca .NET uygulamalarına uygun mudur?

Evet, Aspose.Slides özellikle .NET uygulamaları için tasarlanmıştır. Ancak Java gibi diğer programlama dilleri için de versiyonlar mevcuttur.