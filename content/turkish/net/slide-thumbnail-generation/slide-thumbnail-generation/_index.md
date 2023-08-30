---
title: Aspose.Slides'ta Slayt Küçük Resmi Oluşturma
linktitle: Aspose.Slides'ta Slayt Küçük Resmi Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Adım adım kılavuz ve kod örnekleriyle Aspose.Slides for .NET'te slayt küçük resimleri oluşturun. Görünümü özelleştirin ve küçük resimleri kaydedin. Sunum önizlemelerini geliştirin.
type: docs
weight: 10
url: /tr/net/slide-thumbnail-generation/slide-thumbnail-generation/
---

Sunum manipülasyonu alanında Aspose.Slides, geliştiricilerin PowerPoint sunumlarını programlı olarak oluşturmasına, değiştirmesine ve yönetmesine olanak tanıyan güçlü bir araç olarak duruyor. Sunduğu temel özelliklerden biri slayt küçük resmi oluşturmadır. Bu makale, Aspose.Slides for .NET kullanarak slayt küçük resimleri oluşturma sürecini ayrıntılı olarak ele alıyor ve geliştiricilere bu işlevselliği sorunsuz bir şekilde uygulama becerisi kazandıracak adım adım kılavuz ve kod örnekleri sağlıyor.

## Önkoşullar

Uygulamaya geçmeden önce aşağıdakilerin mevcut olduğundan emin olun:

- .NET Framework yüklü Visual Studio.
-  Aspose.Slides for .NET kitaplığı. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## Slayt Küçük Resmi Oluşturmaya Giriş

Slayt küçük resimleri sunumlarda çok önemli bir rol oynar ve her slaydın içeriğinin hızlı bir önizlemesini sunar. Aspose.Slides, bu küçük resimleri programlı olarak oluşturmak için basit bir mekanizma sağlayarak bu süreci basitleştirir.

## Projenin Kurulumu

1. Visual Studio'da yeni bir proje oluşturun.
2. Gerekli Aspose.Slides derlemelerine referanslar ekleyin.

## Sunum Yükleme

Aşağıdaki kodu kullanarak PowerPoint sunumunu yükleyin:

```csharp
using Aspose.Slides;

// Sunuyu yükle
Presentation presentation = new Presentation("path_to_presentation.pptx");
```

## Slayt Küçük Resimleri Oluşturma

Sunumdaki tüm slaytlar için küçük resimler oluşturun:

```csharp
// Küçük Resim Seçeneklerini Başlat
ThumbnailOptions thumbnailOptions = new ThumbnailOptions();

// Tüm slaytlar için küçük resimler oluşturun
foreach (ISlide slide in presentation.Slides)
{
    using (MemoryStream thumbnailStream = new MemoryStream())
    {
        slide.GetThumbnail(thumbnailStream, thumbnailOptions);
        // Küçük resmi gerektiği gibi işleyin veya kaydedin
    }
}
```

## Küçük Resim Görünümünü Özelleştirme

 Küçük resim görünümünü değiştirerek özelleştirebilirsiniz.`thumbnailOptions`. Örneğin boyutları, arka plan rengini ve daha fazlasını ayarlayabilirsiniz.

```csharp
thumbnailOptions.SlideSize = SlideSizeType.Screen;
thumbnailOptions.BackgroundColor = Color.White;
```

## Küçük Resimleri Kaydetme

Oluşturulan küçük resimleri diske kaydedin:

```csharp
using (FileStream fileStream = new FileStream("slide_thumbnail.png", FileMode.Create))
{
    thumbnailStream.Seek(0, SeekOrigin.Begin);
    thumbnailStream.CopyTo(fileStream);
}
```

## Çözüm

Aspose.Slides for .NET, geliştiricilerin zahmetsizce slayt küçük resimleri oluşturmasına olanak tanıyarak sunum önizleme deneyimini geliştirir. Bu makalede özetlenen adımları izleyerek, slayt küçük resmi oluşturmayı uygulamalarınıza dahil etme bilgisine sahip oldunuz.

## SSS

### Oluşturulan küçük resimlerin boyutlarını nasıl özelleştirebilirim?

 Oluşturulan küçük resimlerin boyutlarını özelleştirmek için`thumbnailOptions.SlideSize` mülk. Gibi önceden tanımlanmış çeşitli boyutlar arasından seçim yapabilirsiniz.`SlideSizeType.Screen`, `SlideSizeType.A4Paper`, vesaire.

### Küçük resimlerin arka plan rengini değiştirebilir miyim?

 Kesinlikle! Ayarlayın`thumbnailOptions.BackgroundColor` oluşturulan küçük resimler için istenen arka plan rengini ayarlama özelliği.

### Yalnızca belirli slaytlar için küçük resimler oluşturmak mümkün mü?

Evet, sunumdaki tüm slaytlar yerine istediğiniz slaytları yineleyerek belirli slaytlar için küçük resimler oluşturabilirsiniz.

### Oluşturulan küçük resimler yüksek kalitede mi?

 Varsayılan olarak oluşturulan küçük resimler iyi kalitededir ve önizleme amaçlarına uygundur. gibi parametreleri ayarlayabilirsiniz.`thumbnailOptions.Quality`küçük resimlerin kalitesini daha da kontrol etmek için.

### Slayt küçük resmi oluşturma performansı nasıl etkiler?

Slayt küçük resmi oluşturma, performans için optimize edilmiştir. Ancak çok sayıda slayt için küçük resimler oluşturmak veya yüksek kaliteli ayarları kullanmak işlem süresini etkileyebilir.

Aspose.Slides'ı kullanarak slayt küçük resmi oluşturmayı uygulamak, sunumla ilgili uygulamalarınızı geliştirmeniz için bir olasılıklar dünyasının kapılarını açar. İster hızlı önizlemeler ister özelleştirilmiş ekranlar olsun, bu özellik geliştiricilerin etkili bir şekilde yararlanabileceği değerli işlevler sağlar. Öyleyse devam edin, slayt küçük resmi oluşturmayı projelerinize entegre edin ve sunum uygulamalarınızın kullanıcı deneyimini yükseltin!