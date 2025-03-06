---
title: Aspose.Slides ile PowerPoint'te Animasyon Sonrası Efektlerde Uzmanlaşma
linktitle: Slaytta Animasyon Yazımından Sonra Kontrol
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak PowerPoint slaytlarındaki animasyon sonrası efektleri nasıl kontrol edeceğinizi öğrenin. Sunumlarınızı dinamik görsel öğelerle geliştirin.
weight: 11
url: /tr/net/slide-animation-control/control-after-animation-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
Sunumlarınızı dinamik animasyonlarla geliştirmek, izleyicilerinizin ilgisini çekmenin çok önemli bir yönüdür. Aspose.Slides for .NET, slaytlardaki animasyon sonrası efektleri kontrol etmek için güçlü bir çözüm sunar. Bu eğitimde, slaytlardaki animasyon sonrası türünü değiştirmek için Aspose.Slides for .NET'i kullanma sürecinde size rehberlik edeceğiz. Bu adım adım kılavuzu izleyerek daha etkileşimli ve görsel olarak çekici sunumlar oluşturabileceksiniz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilerin mevcut olduğundan emin olun:
- Temel C# ve .NET programlama bilgisi.
-  Aspose.Slides for .NET kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/slides/net/).
- Visual Studio gibi entegre bir geliştirme ortamı (IDE).
## Ad Alanlarını İçe Aktar
Aspose.Slides işlevlerine erişmek için gerekli ad alanlarını içe aktararak başlayın. Kodunuza aşağıdaki satırları ekleyin:
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
Şimdi, daha iyi anlaşılması için verilen kodu birden fazla adıma ayıralım:
## 1. Adım: Belge Dizinini Ayarlayın
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Belirtilen dizinin mevcut olduğundan emin olun veya yoksa oluşturun.
## Adım 2: Çıktı Dosyası Yolunu Tanımlayın
```csharp
string outPath = Path.Combine(dataDir, "AnimationAfterEffect-out.pptx");
```
Değiştirilen sunum için çıktı dosyası yolunu belirtin.
## 3. Adım: Sunuyu Yükleyin
```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```
Sunum sınıfını oluşturun ve mevcut sunumu yükleyin.
## Adım 4: Slayt 1'deki Animasyon Sonrası Efektleri Değiştirin
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
İlk slaydı kopyalayın, zaman çizelgesi sırasına erişin ve animasyon sonrası efektini "Sonraki Fare Tıklamasında Gizle" olarak ayarlayın.
## Adım 5: Slayt 2'de Animasyon Sonrası Efektleri Değiştirin
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
İlk slaydı tekrar kopyalayın, bu sefer animasyon sonrası efektini yeşil renkli "Renkli" olarak değiştirin.
## Adım 6: Slayt 3'te Animasyon Sonrası Efektleri Değiştirin
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
Animasyon sonrası efektini "Animasyondan Sonra Gizle" olarak ayarlayarak ilk slaydı bir kez daha kopyalayın.
## Adım 7: Değiştirilen Sunumu Kaydetme
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
Değiştirilen sunumu belirtilen çıktı dosyası yoluyla kaydedin.
## Çözüm
Tebrikler! Aspose.Slides for .NET'i kullanarak slaytlardaki animasyon sonrası efektleri nasıl kontrol edeceğinizi başarıyla öğrendiniz. Daha dinamik ve ilgi çekici sunumlar oluşturmak için farklı animasyon sonrası türlerini deneyin.
## SSS
### Bir slayttaki tek tek öğelere farklı animasyon sonrası efektleri uygulayabilir miyim?
Evet yapabilirsin. Öğeleri yineleyin ve animasyon sonrası efektlerini buna göre ayarlayın.
### Aspose.Slides .NET'in en son sürümleriyle uyumlu mu?
Evet, Aspose.Slides, en yeni .NET framework sürümleriyle uyumluluğun sağlanması için düzenli olarak güncellenmektedir.
### Aspose.Slides'ı kullanarak slaytlara nasıl özel animasyonlar ekleyebilirim?
 Belgelere bakın[Burada](https://reference.aspose.com/slides/net/) özel animasyonlar ekleme hakkında ayrıntılı bilgi için.
### Aspose.Slides sunumları kaydetmek için hangi dosya formatlarını destekliyor?
Aspose.Slides, PPTX, PPT, PDF ve daha fazlası dahil olmak üzere çeşitli formatları destekler. Tam liste için belgelere bakın.
### Aspose.Slides ile ilgili nereden destek alabilirim veya soru sorabilirim?
 Ziyaret edin[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) destek ve topluluk etkileşimi için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
