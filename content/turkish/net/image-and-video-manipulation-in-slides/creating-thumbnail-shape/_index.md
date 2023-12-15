---
title: Aspose.Slides'ta Shape için Küçük Resim Oluşturma
linktitle: Aspose.Slides'ta Shape için Küçük Resim Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak PowerPoint sunumlarındaki şekiller için küçük resimler oluşturmayı öğrenin. Bu adım adım kılavuz, sunumların yüklenmesinden küçük resimlerin oluşturulmasına ve kaydedilmesine kadar pratik kod örnekleri sağlar.
type: docs
weight: 14
url: /tr/net/image-and-video-manipulation-in-slides/creating-thumbnail-shape/
---

## giriiş

Aspose.Slides for .NET, geliştiricilerin PowerPoint sunumlarıyla sorunsuz bir şekilde çalışmasına olanak tanıyan, zengin özelliklere sahip bir kitaplıktır. Yaygın gereksinimlerden biri, slaytlardaki belirli şekiller için küçük resimler oluşturmaktır. Bu, uygulamanızda bir şeklin hızlı bir önizlemesini veya temsilini sağlamak istediğinizde özellikle yararlı olabilir.

## Önkoşullar

Kodun ayrıntılarına girmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio veya başka herhangi bir uygun .NET geliştirme ortamı.
-  Aspose.Slides for .NET kitaplığı. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## Kurulum

1. Sağlanan bağlantıdan Aspose.Slides for .NET kitaplığını indirin.
2. İndirilen DLL dosyasına bir başvuru ekleyerek kitaplığı .NET projenize yükleyin.

## Sunum Yükleme

Aspose.Slides'ı kullanarak bir PowerPoint sunumu yükleyerek başlayalım. Aşağıdaki kod, bir sunumun bir dosyadan nasıl yükleneceğini gösterir:

```csharp
using Aspose.Slides;

// Sunuyu yükle
using var presentation = new Presentation("sample.pptx");
```

 Yer değiştirmek`"sample.pptx"` PowerPoint sunumunuzun gerçek yolu ile.

## Şekillere Erişim

Sunum yüklendikten sonra her slayttaki şekillere erişebilirsiniz. Bu örnekte, belirli bir slayttaki belirli bir şekil için küçük resim oluşturmaya odaklanacağız. Bir şekle şu şekilde erişebilirsiniz:

```csharp
// Bir slayta dizine göre erişme (0 tabanlı)
var slide = presentation.Slides[0];

// Bir şekle dizine göre erişme (0 tabanlı)
var shape = slide.Shapes[0];
```

Slayt ve şekil indekslerini sununuzun yapısına göre değiştirin.

## Küçük Resimler Oluşturma

Şimdi heyecan verici kısım geliyor; seçilen şekil için küçük resim oluşturma. Aspose.Slides bunu aşağıdaki özelliklerden yararlanarak başarmanıza olanak tanır:`GetThumbnail` yöntem. Bir şeklin küçük resmini şu şekilde oluşturabilirsiniz:

```csharp
// Küçük resim boyutlarını tanımlayın
int thumbnailWidth = 200;
int thumbnailHeight = 150;

// Şekil için küçük resim oluşturma
var thumbnail = shape.GetThumbnail(thumbnailWidth, thumbnailHeight);
```

 Ayarlayın`thumbnailWidth` Ve`thumbnailHeight` Küçük resminiz için istenen boyutları ayarlamak için değişkenler.

## Küçük Resimleri Kaydetme

Küçük resmi oluşturduktan sonra onu bir resim dosyası olarak kaydetmek isteyebilirsiniz. Küçük resmi PNG görüntüsü olarak şu şekilde kaydedebilirsiniz:

```csharp
// Küçük resmi resim olarak kaydedin
thumbnail.Save("shape_thumbnail.png", ImageFormat.Png);
```

Dosya adını ve biçimini gereksinimlerinize göre özelleştirin.

## Çözüm

Bu kılavuzda Aspose.Slides for .NET kullanarak PowerPoint sunumlarındaki şekiller için küçük resimlerin nasıl oluşturulacağını araştırdık. Bir sunuyu nasıl yükleyeceğinizi, şekillere nasıl erişeceğinizi, küçük resimler oluşturmayı ve bunları görüntü dosyaları olarak kaydetmeyi öğrendiniz. Bu işlevsellik, PowerPoint sunumları içeren uygulamalardaki kullanıcı deneyimini büyük ölçüde geliştirebilir.

## SSS'ler

### Farklı küçük resim boyutlarını nasıl belirtebilirim?

 Ayarlayabilirsiniz`thumbnailWidth` Ve`thumbnailHeight` Oluşturulan küçük resim için ihtiyacınız olan boyutları belirtmek için koddaki değişkenleri kullanın.

### Aynı anda birden çok şekil için küçük resimler oluşturabilir miyim?

Evet, bir slayttaki tüm şekilleri yineleyebilir ve bir döngü kullanarak her şekil için küçük resimler oluşturabilirsiniz.

### Aspose.Slides farklı PowerPoint formatlarıyla uyumlu mu?

Evet, Aspose.Slides, PPTX, PPT ve daha fazlası dahil olmak üzere çeşitli PowerPoint formatlarını destekler.

### Oluşturulan küçük resmin görünümünü özelleştirebilir miyim?

 iken`GetThumbnail` yöntemi, küçük resimler oluşturmanın hızlı bir yolunu sağlar; .NET'teki standart görüntü işleme kitaplıklarını kullanarak küçük resim görüntüsünü daha fazla değiştirebilirsiniz.

### Aspose.Slides PowerPoint ile ilgili diğer görevler için uygun mu?

Kesinlikle Aspose.Slides, PowerPoint sunumlarıyla çalışmak için slayt oluşturma, düzenleme, dönüştürme ve işleme dahil çok çeşitli özellikler sunar.