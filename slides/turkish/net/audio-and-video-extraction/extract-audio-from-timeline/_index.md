---
title: PowerPoint Zaman Çizelgesinden Sesi Çıkarın
linktitle: Zaman Çizelgesinden Sesi Çıkar
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint sunumlarından nasıl ses çıkaracağınızı öğrenin. Multimedya içeriğinizi kolaylıkla geliştirin.
weight: 13
url: /tr/net/audio-and-video-extraction/extract-audio-from-timeline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint Zaman Çizelgesinden Sesi Çıkarın


Multimedya sunumları dünyasında ses, mesajınızı etkili bir şekilde iletmek için güçlü bir araç olabilir. Aspose.Slides for .NET, PowerPoint sunumlarından ses çıkarmak için kusursuz bir çözüm sunar. Bu adım adım kılavuzda, Aspose.Slides for .NET kullanarak bir PowerPoint sunumundan nasıl ses çıkaracağınızı göstereceğiz.

## Önkoşullar

PowerPoint sunumlarından ses çıkarmaya başlamadan önce aşağıdaki önkoşullara ihtiyacınız olacak:

1.  Aspose.Slides for .NET Library: Aspose.Slides for .NET kütüphanesinin kurulu olması gerekir. Henüz yüklemediyseniz adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/net/).

2. PowerPoint Sunumu: Sesi çıkarmak istediğiniz PowerPoint sunumunuza (PPTX) sahip olduğunuzdan emin olun. Sunum dosyasını seçtiğiniz bir dizine yerleştirin.

3. Temel C# Bilgisi: Bu eğitimde, C# programlama konusunda temel bir anlayışa sahip olduğunuz varsayılmaktadır.

Artık her şey hazır olduğuna göre adım adım kılavuza geçelim.

## 1. Adım: Ad Alanlarını İçe Aktarın

Başlamak için Aspose.Slides ile çalışmak ve dosya işlemlerini gerçekleştirmek için gerekli ad alanlarını içe aktarmanız gerekir. C# projenize aşağıdaki kodu ekleyin:

```csharp
using Aspose.Slides;
using System.IO;
```

## Adım 2: Sesi Zaman Çizelgesinden Çıkarın

Şimdi sağladığınız örneği birden fazla adıma ayıralım:

### Adım 2.1: Sunumu Yükleyin

```csharp
string pptxFile = Path.Combine("Your Document Directory", "AnimationAudio.pptx");

using (Presentation pres = new Presentation(pptxFile))
{
    // Kodunuz burada
}
```

Bu adımda belirtilen dosyadan PowerPoint sunumunu yüklüyoruz. Değiştirdiğinizden emin olun`"Your Document Directory"` sunum dosyanızın gerçek yolunu belirtin.

### Adım 2.2: Slayt ve Zaman Çizelgesine Erişin

```csharp
ISlide slide = pres.Slides[0];
```

Burada sunumdaki ilk slayda erişiyoruz. Gerekirse farklı bir slayta erişmek için dizini değiştirebilirsiniz.

### Adım 2.3: Efekt Sırasını Çıkarın

```csharp
ISequence effectsSequence = slide.Timeline.MainSequence;
```

`MainSequence` özelliği, seçilen slaydın efekt sırasına erişmenizi sağlar.

### Adım 2.4: Sesi Bayt Dizisi Olarak Çıkarın

```csharp
byte[] audio = effectsSequence[0].Sound.BinaryData;
```

Bu kod, sesi bir bayt dizisi olarak çıkarır. Bu örnekte, çıkarmak istediğiniz sesin efektler dizisinde ilk konumda (indeks 0) bulunduğunu varsayıyoruz. Ses farklı bir konumdaysa dizini değiştirebilirsiniz.

### Adım 2.5: Çıkarılan Sesi Kaydedin

```csharp
string outMediaPath = Path.Combine(RunExamples.OutPath, "MediaTimeline.mpg");
File.WriteAllBytes(outMediaPath, audio);
```

 Son olarak çıkarttığımız sesi medya dosyası olarak kaydediyoruz. Yukarıdaki kod onu kaydeder.`"MediaTimeline.mpg"` çıkış dizini içindeki dosya.

Bu kadar! Aspose.Slides for .NET'i kullanarak bir PowerPoint sunumundan sesi başarıyla çıkardınız.

## Çözüm

Aspose.Slides for .NET, PowerPoint sunumlarında multimedya öğeleriyle çalışmayı kolaylaştırır. Bu eğitimde, bir sunumdan adım adım ses çıkarmayı öğrendik. Doğru araçlar ve biraz C# bilgisiyle sunumlarınızı geliştirebilir ve ilgi çekici multimedya içeriği oluşturabilirsiniz.

 Herhangi bir sorunuz varsa veya daha fazla yardıma ihtiyacınız varsa, bizimle iletişime geçmekten çekinmeyin.[Aspose.Slides destek forumu](https://forum.aspose.com/).

## Sıkça Sorulan Sorular (SSS)

### 1. Bir PowerPoint sunumundaki belirli slaytlardan ses çıkarabilir miyim?

Evet, sağlanan koddaki dizini değiştirerek PowerPoint sunumundaki herhangi bir slayttan ses çıkarabilirsiniz.

### 2. Çıkarılan sesi Aspose.Slides for .NET kullanarak hangi formatlarda kaydedebilirim?

Aspose.Slides for .NET, çıkarılan sesi MP3, WAV veya desteklenen diğer ses formatları gibi çeşitli formatlarda kaydetmenize olanak tanır.

### 3. Aspose.Slides for .NET, PowerPoint'in en son sürümleriyle uyumlu mu?

Aspose.Slides for .NET, en yenileri de dahil olmak üzere çeşitli PowerPoint sürümleriyle uyumlu olacak şekilde tasarlanmıştır.

### 4. Çıkarılan sesi Aspose.Slides kullanarak değiştirebilir ve düzenleyebilir miyim?

Evet, Aspose.Slides, PowerPoint sunumundan çıkarıldıktan sonra ses işleme ve düzenleme için kapsamlı özellikler sunar.

### 5. Aspose.Slides for .NET'in kapsamlı belgelerini nerede bulabilirim?

 Aspose.Slides for .NET için ayrıntılı belgeler ve örnekler bulabilirsiniz.[Burada](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
