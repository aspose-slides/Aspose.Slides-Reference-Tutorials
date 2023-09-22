---
title: Slaytta Animasyonu Geri Sarma
linktitle: Slaytta Animasyonu Geri Sarma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak PowerPoint slaytlarındaki animasyonları nasıl geri saracağınızı öğrenin. Sunumlarınızı dinamik olarak geliştirmek için eksiksiz kaynak kodu örnekleri içeren bu adım adım kılavuzu izleyin.
type: docs
weight: 13
url: /tr/net/slide-animation-control/rewind-animation-on-slide/
---

## Aspose.Slides ile Animasyonlara Giriş

Animasyonlar sunumlarınıza hayat vererek onları daha ilgi çekici ve görsel olarak çekici hale getirebilir. Aspose.Slides for .NET, geliştiricilerin animasyon ekleme, değiştirme ve yönetme dahil olmak üzere PowerPoint sunumlarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir kitaplıktır.

## Önkoşullar

Başlamadan önce aşağıdakilerin yerinde olduğundan emin olun:

- Visual Studio: Visual Studio'yu veya başka herhangi bir .NET geliştirme ortamını yükleyin.
-  Aspose.Slides: Aspose.Slides for .NET kitaplığını şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/slides/net/).

## Adım 1: Sunum Dosyasını Yükleme

Öncelikle animasyonların bulunduğu slaydı içeren PowerPoint sunum dosyasını yükleyerek başlayalım. İşte bunu başarmak için kod pasajı:

```csharp
using Aspose.Slides;

// Sunuyu yükle
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Kodunuz burada
}
```

## Adım 2: Slayt ve Animasyona Erişim

Daha sonra, belirli slayda ve animasyonlarına erişmemiz gerekiyor. Bu adımda geri sarmak istediğiniz animasyonu içeren slaydı hedefleyeceğiz. İşte nasıl:

```csharp
// Slayt indeksinin 0 olduğunu varsayalım (ilk slayt)
ISlide slide = presentation.Slides[0];

// Slayt animasyonlarına erişim
ISlideAnimation slideAnimation = slide.SlideShowTransition;
```

## 3. Adım: Animasyonları Geri Sarma

Şimdi heyecan verici kısım geliyor: animasyonları geri sarmak. Aspose.Slides, bir slayttaki animasyonları sıfırlayarak slaydı etkili bir şekilde başlangıç durumuna geri getirmenizi sağlar. İşte bunu başarmak için kod pasajı:

```csharp
// Slayttaki animasyonları geri sarma
slideAnimation.StopAfterRepeats = 0; // Tekrar sayısını 0 olarak ayarlayın
```

## Adım 4: Değiştirilen Sunumu Kaydetme

Animasyonları geri sardıktan sonra sıra değiştirilen sunumu kaydetmeye gelir. Yeni bir adla kaydedebilir veya mevcut dosyanın üzerine yazabilirsiniz. Sunuyu şu şekilde kaydedebilirsiniz:

```csharp
// Değiştirilen sunuyu kaydet
string outputPath = "path_to_save_modified_presentation.pptx";
presentation.Save(outputPath, SaveFormat.Pptx);
```

## Çözüm

Tebrikler! Aspose.Slides for .NET'i kullanarak bir slayttaki animasyonları nasıl geri saracağınızı başarıyla öğrendiniz. Bu güçlü kitaplık, PowerPoint sunumlarınızı programlı olarak düzenlemeniz ve geliştirmeniz için gereken araçları sağlar.

## SSS'ler

### Aspose.Slides for .NET'i nasıl yüklerim?

 Aspose.Slides for .NET kütüphanesini şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/slides/net/). Belgelerde sağlanan kurulum talimatlarını takip ettiğinizden emin olun.

### Bir slayttaki belirli nesnelere ilişkin animasyonları geri sarabilir miyim?

Evet, Aspose.Slides bir slaytta belirli nesneleri ve bunların animasyonlarını hedeflemenize olanak tanır. Animasyonları nesne düzeyinde de değiştirebilirsiniz.

### Aspose.Slides farklı PowerPoint formatlarıyla uyumlu mu?

Evet, Aspose.Slides, PPTX, PPT, PPSX ve daha fazlası dahil olmak üzere çeşitli PowerPoint formatlarını destekler. Desteklenen biçimlerin tam listesi için belgelere göz atmayı unutmayın.

### Animasyonların geri sarma davranışını özelleştirebilir miyim?

Kesinlikle! Aspose.Slides, animasyon davranışını özelleştirmek için bir dizi özellik ve yöntem sağlar. Animasyonların hızını, yönünü ve diğer yönlerini kontrol edebilirsiniz.

### Daha fazla kaynak ve belgeyi nerede bulabilirim?

 Kapsamlı belgeler, eğitimler ve kod örnekleri için bkz.[Aspose.Slides for .NET belgeleri](https://reference.aspose.com/slides/net/).