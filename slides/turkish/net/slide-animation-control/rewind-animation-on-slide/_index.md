---
title: Aspose.Slides ile Sunumlarda Geri Sarma Animasyonlarında Uzmanlaşma
linktitle: Slaytta Animasyonu Geri Sarma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak PowerPoint slaytlarındaki animasyonları nasıl geri saracağınızı öğrenin. Tam kaynak kodu örneklerinin yer aldığı bu adım adım kılavuzu izleyin.
type: docs
weight: 13
url: /tr/net/slide-animation-control/rewind-animation-on-slide/
---
## giriiş
Sunumların dinamik dünyasında büyüleyici animasyonların kullanılması katılımı önemli ölçüde artırabilir. Aspose.Slides for .NET, sunumlarınıza hayat katacak güçlü bir araç seti sağlar. İlgi çekici özelliklerden biri, slaytlardaki animasyonları geri sarma yeteneğidir. Bu kapsamlı kılavuzda, süreç boyunca size adım adım yol göstererek Aspose.Slides for .NET'i kullanarak animasyon geri sarmanın tüm potansiyelinden yararlanmanıza olanak sağlayacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
-  Aspose.Slides for .NET: Kütüphanenin kurulu olduğundan emin olun. Değilse, şuradan indirin:[Aspose.Slides for .NET Belgeleri](https://reference.aspose.com/slides/net/).
- .NET Geliştirme Ortamı: Çalışan bir .NET geliştirme ortamı kurduğunuzdan emin olun.
- Temel C# Bilgisi: C# programlama dilinin temellerine aşina olun.
## Ad Alanlarını İçe Aktar
Aspose.Slides for .NET tarafından sağlanan işlevsellikten yararlanmak için C# kodunuzda gerekli ad alanlarını içe aktarmanız gerekecektir. İşte size yol gösterecek bir pasaj:
```csharp
using System;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## 1. Adım: Projenizi Kurun
Tercih ettiğiniz .NET geliştirme ortamında yeni bir proje oluşturun. Eğer mevcut değilse, belgeleriniz için bir dizin oluşturun.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Adım: Sunuyu Yükleyin
 Örnekleyin`Presentation` sunum dosyanızı temsil edecek sınıf.
```csharp
using (Presentation presentation = new Presentation(dataDir + "AnimationRewind.pptx"))
{
    // Sonraki adımlara ilişkin kodunuz buraya gelecek
}
```
## Adım 3: Efekt Sırasına Erişim
İlk slaydın efekt sırasını alın.
```csharp
ISequence effectsSequence = presentation.Slides[0].Timeline.MainSequence;
```
## 4. Adım: Efekt Zamanlamasını Değiştirin
Ana dizinin ilk efektine erişin ve geri sarmayı etkinleştirmek için zamanlamasını değiştirin.
```csharp
IEffect effect = effectsSequence[0];
Console.WriteLine("\nEffect Timing/Rewind in source presentation is {0}", effect.Timing.Rewind);
effect.Timing.Rewind = true;
```
## Adım 5: Sunuyu Kaydetme
Değiştirilen sunuyu kaydedin.
```csharp
presentation.Save(RunExamples.OutPath + "AnimationRewind-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
## Adım 6: Hedef Sunumunda Geri Sarma Efektini Kontrol Edin
Değiştirilen sunumu yükleyin ve geri sarma efektinin uygulanıp uygulanmadığını kontrol edin.
```csharp
using (Presentation pres = new Presentation(RunExamples.OutPath + "AnimationRewind-out.pptx"))
{
    effectsSequence = pres.Slides[0].Timeline.MainSequence;
    effect = effectsSequence[0];
    Console.WriteLine("Effect Timing/Rewind in destination presentation is {0}\n", effect.Timing.Rewind);
}
```
Ek slaytlar için bu adımları tekrarlayın veya süreci sununuzun yapısına göre özelleştirin.
## Çözüm
Unlocking the rewind animation feature in Aspose.Slides for .NET opens up exciting possibilities for creating dynamic and engaging presentations. By following this step-by-step guide, you can seamlessly integrate animation rewind into your projects, enhancing the visual appeal of your slides.
---
## SSS
### Aspose.Slides for .NET en son .NET framework sürümüyle uyumlu mu?
 Aspose.Slides for .NET, en yeni .NET framework sürümleriyle uyumluluğun sağlanması amacıyla düzenli olarak güncellenmektedir. Kontrol edin[dokümantasyon](https://reference.aspose.com/slides/net/) uyumluluk ayrıntıları için.
### Bir slayttaki belirli nesnelere geri sarma animasyonu uygulayabilir miyim?
Evet, geri sarma animasyonunu bir slayttaki belirli nesnelere veya öğelere seçici olarak uygulamak için kodu özelleştirebilirsiniz.
### Aspose.Slides for .NET'in deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü edinerek özellikleri keşfedebilirsiniz.[Burada](https://releases.aspose.com/).
### Aspose.Slides for .NET için nasıl destek alabilirim?
 Ziyaret edin[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) yardım istemek ve toplulukla etkileşime geçmek.
### Aspose.Slides for .NET için geçici bir lisans satın alabilir miyim?
 Evet, adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).