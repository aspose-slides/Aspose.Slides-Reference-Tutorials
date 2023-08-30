---
title: Slaytta Animasyonu Tekrarla
linktitle: Slaytta Animasyonu Tekrarla
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak bir slayttaki animasyonları nasıl tekrarlayacağınızı öğrenin. Bu adım adım kılavuz, PowerPoint sunumlarına program aracılığıyla büyüleyici animasyonlar eklemek için kaynak kodu ve net talimatlar sağlar.
type: docs
weight: 12
url: /tr/net/slide-animation-control/repeat-animation-on-slide/
---

## Aspose.Slides for .NET'e Giriş

Aspose.Slides for .NET, geliştiricilerin .NET çerçevesini kullanarak PowerPoint sunumları oluşturmasına, yönetmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır. Slaytlar, şekiller, metinler, resimler, animasyonlar ve daha fazlasıyla çalışmak için çok çeşitli özellikler sunar.

## Geliştirme Ortamınızı Kurma

Başlamadan önce geliştirme ortamınızı ayarlamanız gerekir. Bu adımları takip et:

1.  Visual Studio'yu şuradan indirip yükleyin:[Visual Studio İndirmeleri](https://visualstudio.microsoft.com/downloads/).
2. Visual Studio'da yeni bir .NET projesi (örneğin Konsol Uygulaması) oluşturun.

## PowerPoint Sunumu Yükleme

Başlamak için üzerinde çalışabileceğiniz bir PowerPoint sunumuna ihtiyacınız olacak. Bir PowerPoint dosyanızın hazır olduğundan emin olun.

```csharp
using Aspose.Slides;

// PowerPoint sunumunu yükleyin
using var presentation = new Presentation("presentation.pptx");
```

## Animasyonlara Erişim ve Değiştirme

Artık sunumuzu yüklediğimize göre, belirli bir slayttaki animasyonlara erişip bunları değiştirelim. Bu örnek için 2 numaralı slayttaki animasyonları tekrarlamak istediğimizi varsayalım.

```csharp
// Slayta dizine göre erişme (0 tabanlı)
var slideIndex = 1;
var slide = presentation.Slides[slideIndex];

// Slaydın animasyonlarına erişme
var animations = slide.Timeline.MainSequence;
```

## Slayt Üzerinde Animasyonların Tekrarlanması

Animasyonları tekrarlamak için animasyonları tekrar kopyalayıp slayda ekleyeceğiz. Bu döngüsel bir etki yaratacaktır. Bunu şu şekilde başarabilirsiniz:

```csharp
// Animasyonları klonlayın ve tekrar ekleyin
var clonedAnimations = animations.CloneSequence();
animations.AddSequence(clonedAnimations);
```

## Değiştirilen Sunumu Test Etme ve Dışa Aktarma

Animasyonları değiştirdikten sonra sunumu test etme ve dışa aktarma zamanı geldi. PPTX, PDF veya resimler gibi çeşitli formatlara aktarabilirsiniz.

```csharp
// Değiştirilen sunuyu kaydet
presentation.Save("modified_presentation.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu kılavuzda Aspose.Slides for .NET kullanarak bir slayttaki animasyonların nasıl tekrarlanacağını araştırdık. Kütüphaneyi tanıtarak ve geliştirme ortamını kurarak başladık. Daha sonra bir PowerPoint sunumu yükledik, animasyonlara erişip onları değiştirdik ve son olarak tekrar animasyon özelliğini uyguladık. Aspose.Slides for .NET, geliştiricilerin programlı olarak dinamik ve ilgi çekici sunumlar oluşturmasına olanak tanır.

## SSS'ler

### Aspose.Slides for .NET'i nasıl indirebilirim?

 Aspose.Slides for .NET'i sürümler sayfasından indirebilirsiniz:[Aspose.Slides for .NET'i indirin](https://releases.aspose.com/slides/net/)

### Bir slayttaki tüm animasyonlar yerine belirli animasyonları tekrarlayabilir miyim?

 Evet, belirli animasyonları, içindeki dizinlerini kullanarak hedefleyerek seçici olarak tekrarlayabilirsiniz.`MainSequence`.

### Aspose.Slides for .NET farklı PowerPoint formatlarıyla uyumlu mu?

Evet, Aspose.Slides for .NET, PPT, PPTX ve daha fazlası dahil olmak üzere çeşitli PowerPoint formatlarını destekler.

### Aspose.Slides for .NET'i kullanarak özel animasyonlar oluşturabilir miyim?

Kesinlikle! Aspose.Slides for .NET, gereksinimlerinize göre animasyonlar oluşturup özelleştirmeniz için kapsamlı API'ler sağlar.

### Aspose.Slides for .NET'in deneme sürümü mevcut mu?

Evet, web sitesinden ücretsiz deneme sürümünü indirerek Aspose.Slides for .NET'i deneyebilirsiniz.