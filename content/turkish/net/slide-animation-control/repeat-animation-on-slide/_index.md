---
title: Aspose.Slides .NET ile PowerPoint Animasyonlarında Uzmanlaşmak
linktitle: Slaytta Animasyonu Tekrarla
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint sunumlarını geliştirin. Animasyonları zahmetsizce kontrol edin, izleyicilerinizi büyüleyin ve kalıcı bir izlenim bırakın.
type: docs
weight: 12
url: /tr/net/slide-animation-control/repeat-animation-on-slide/
---
## giriiş
Sunumların dinamik dünyasında, animasyonları kontrol etme yeteneği izleyicinin dikkatini çekmede ve çekmede çok önemli bir rol oynar. Aspose.Slides for .NET, geliştiricilerin slaytlardaki animasyon türlerinin sorumluluğunu üstlenmelerini sağlayarak daha etkileşimli ve görsel açıdan çekici bir sunuma olanak tanır. Bu eğitimde Aspose.Slides for .NET kullanarak bir slayttaki animasyon türlerinin nasıl kontrol edileceğini adım adım inceleyeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1.  Aspose.Slides for .NET Library: Kütüphaneyi şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/slides/net/).
2. .NET Geliştirme Ortamı: Makinenizde bir .NET geliştirme ortamı kurun.
## Ad Alanlarını İçe Aktar
.NET projenize Aspose.Slides tarafından sağlanan işlevlerden yararlanmak için gerekli ad alanlarını içe aktararak başlayın:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Adım 1: Projeyi Kurun
Projeniz için yeni bir dizin oluşturun ve sunum dosyasını temsil edecek Sunum sınıfını başlatın.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // Kodunuz buraya gelecek
}
```
## Adım 2: Efekt Sırasına Erişim
MainSequence özelliğini kullanarak ilk slaydın efekt sırasını alın.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## 3. Adım: İlk Efekte Erişin
Özelliklerini değiştirmek için ana dizinin ilk efektini elde edin.
```csharp
IEffect effect = effectsSequence[0];
```
## Adım 4: Tekrarlama Ayarlarını Değiştirin
Efektin Zamanlama/Tekrar özelliğini "Slaydın Sonuna Kadar" olarak değiştirin.
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Adım 5: Sunuyu Kaydetme
Değişiklikleri görselleştirmek için değiştirilen sunuyu kaydedin.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Ek efektler için bu adımları tekrarlayın veya bunları sunum gereksinimlerinize göre özelleştirin.
## Çözüm
Aspose.Slides for .NET ile PowerPoint sunumlarınıza dinamik animasyonlar eklemek hiç bu kadar kolay olmamıştı. Bu adım adım kılavuz, sizi animasyon türlerini kontrol etme bilgisiyle donatarak slaytlarınızın hedef kitleniz üzerinde kalıcı bir izlenim bırakmasını sağlar.
## Sıkça Sorulan Sorular
### Bu animasyonları slayttaki belirli nesnelere uygulayabilir miyim?
Evet, belirli nesneleri, sıra içindeki bireysel efektlerine erişerek hedefleyebilirsiniz.
### Aspose.Slides en son PowerPoint sürümleriyle uyumlu mu?
Aspose.Slides, çok çeşitli PowerPoint sürümleri için destek sağlayarak hem eski hem de yeni sürümlerle uyumluluk sağlar.
### Ek örnekleri ve kaynakları nerede bulabilirim?
 Keşfedin[dokümantasyon](https://reference.aspose.com/slides/net/) Kapsamlı örnekler ve ayrıntılı açıklamalar için.
### Aspose.Slides için nasıl geçici lisans alabilirim?
 Ziyaret etmek[Burada](https://purchase.aspose.com/temporary-license/) Geçici lisans alma konusunda bilgi için.
### Yardıma mı ihtiyacınız var veya daha fazla sorunuz mu var?
 Aspose.Slides topluluğuyla etkileşime geçin[destek Forumu](https://forum.aspose.com/c/slides/11).