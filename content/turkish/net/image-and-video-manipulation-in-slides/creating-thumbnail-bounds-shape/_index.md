---
title: Aspose.Slides'ta Şekil Sınırlarıyla Küçük Resim Oluşturma
linktitle: Aspose.Slides'ta Şekil Sınırlarıyla Küçük Resim Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak PowerPoint sunumlarındaki şekiller için özel küçük resimler oluşturmayı öğrenin. Bu adım adım kılavuz, kaynak kodu örnekleri sağlar ve sunumların yüklenmesini, şekillere erişmeyi, küçük resim sınırlarını tanımlamayı, oluşturmayı, kaydetmeyi ve daha fazlasını kapsar.
type: docs
weight: 10
url: /tr/net/image-and-video-manipulation-in-slides/creating-thumbnail-bounds-shape/
---

## Şekil Sınırlarıyla Küçük Resim Oluşturmaya Giriş

Sunumlarla çalışmak söz konusu olduğunda Aspose.Slides for .NET, geliştiricilerin slaytların, şekillerin ve içeriğin çeşitli yönlerini değiştirmesine olanak tanıyan güçlü bir araç seti sağlar. Yaygın görevlerden biri, slaytlardaki şekiller için belirli sınırlara sahip küçük resimler oluşturmaktır. Bu adım adım kılavuz, Aspose.Slides for .NET'i kullanarak bunu başarma sürecinde size yol gösterecektir. Hadi dalalım!

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio veya herhangi bir uyumlu IDE
- Aspose.Slides for .NET kitaplığı
- Temel C# ve .NET bilgisi

## Projenin Kurulumu

1. IDE'nizde yeni bir C# projesi oluşturun.
2.  Aspose.Slides for .NET kitaplığını şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/slides/net/).
3. Projenizdeki Aspose.Slides DLL'lerine referanslar ekleyin.

## Sunum Yükleme

Başlamak için, küçük resmini oluşturmak istediğiniz şeklin bulunduğu slaydı içeren PowerPoint sunumunu yüklemeniz gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Slides;

// Sunuyu yükle
using Presentation presentation = new Presentation("your-presentation.pptx");
```

## Şekillere Erişim

Sunum yüklendikten sonra küçük resmini oluşturmak istediğiniz şekle erişmeniz gerekir. Bunu slaytlar ve şekiller arasında yineleyerek yapabilirsiniz:

```csharp
// İlk slaydı alın
ISlide slide = presentation.Slides[0];

// Şekli indeksine göre alın (0 tabanlı)
IShape shape = slide.Shapes[0];
```

## Sınırlarla Küçük Resimler Oluşturma

Şimdi şeklin belirli sınırlara sahip küçük resmini oluşturacağınız kısım geliyor. Bu birkaç adımı içerir:

1. İstediğiniz boyutlara sahip bir Bitmap oluşturun.
2.  kullanarak şekli Bitmap'e aktarın.`RenderToGraphics` yöntem.

İşte nasıl yapıldığı:

```csharp
using System.Drawing;

// Küçük resmin sınırlarını tanımlayın
Rectangle bounds = new Rectangle(0, 0, 200, 150);

// Belirtilen sınırlara sahip bir Bitmap oluşturun
using Bitmap thumbnailBitmap = new Bitmap(bounds.Width, bounds.Height);

// Şekli Bitmap'e aktarın
using Graphics graphics = Graphics.FromImage(thumbnailBitmap);
shape.RenderToGraphics(graphics, bounds);
```

## Çıktıyı Kaydetme

Küçük resmi oluşturduktan sonra onu bir dosyaya kaydetmek isteyebilirsiniz. Bunu aşağıdaki kodu kullanarak yapabilirsiniz:

```csharp
// Küçük resmi bir dosyaya kaydedin
thumbnailBitmap.Save("thumbnail.png", ImageFormat.Png);
```

## Çözüm

Bu kılavuzda, Aspose.Slides for .NET'i kullanarak PowerPoint sunumundaki bir şekil için belirli sınırlara sahip küçük resim oluşturma sürecini anlattık. Bu kitaplık, sunumları programlı olarak yönetmek ve iş akışınızı kolaylaştıran görevleri gerçekleştirmek için kusursuz bir yol sağlar.

## SSS'ler

### Aspose.Slides for .NET'i nasıl kurabilirim?

 Aspose.Slides for .NET'i kurmak için kütüphaneyi sürümler sayfasından indirebilirsiniz:[Burada](https://releases.aspose.com/slides/net/).

### Birden çok şekil için küçük resimler oluşturabilir miyim?

Evet, bir slayttaki şekilleri yineleyebilir ve küçük resim oluşturma işlemini her şekil için ayrı ayrı tekrarlayabilirsiniz.

### Küçük resimleri kaydetmek için hangi görüntü formatları desteklenir?

Aspose.Slides for .NET, küçük resimlerin kaydedilmesi için PNG, JPEG, GIF ve BMP dahil olmak üzere çeşitli görüntü formatlarını destekler.

### Aspose.Slides hem masaüstü hem de web uygulamaları için uygun mu?

Evet, Aspose.Slides for .NET çok yönlüdür ve PowerPoint sunumlarıyla programlı olarak çalışmak için hem masaüstü hem de web uygulamalarında kullanılabilir.

### Aspose.Slides for .NET hakkında nasıl daha fazla bilgi edinebilirim?

Daha ayrıntılı bilgi, eğitimler ve belgeler için şu adresi ziyaret edebilirsiniz:[.NET referansı için Aspose.Slides](https://reference.aspose.com/slides/net/).