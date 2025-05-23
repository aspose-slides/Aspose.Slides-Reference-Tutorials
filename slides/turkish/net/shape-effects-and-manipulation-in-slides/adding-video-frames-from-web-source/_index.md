---
"description": "Aspose.Slides for .NET kullanarak PowerPoint slaytlarına video karelerini sorunsuz bir şekilde nasıl yerleştireceğinizi öğrenin. Sunumlarınızı multimedya ile zahmetsizce geliştirin."
"linktitle": "Aspose.Slides ile Sunum Slaytlarına Web Kaynağından Video Kareleri Ekleme"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides for .NET ile Video Kareleri Gömme Eğitimi"
"url": "/tr/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for .NET ile Video Kareleri Gömme Eğitimi

## giriiş
Sunumların dinamik dünyasında, multimedya öğelerini dahil etmek etkileşimi önemli ölçüde artırabilir ve etkili mesajlar iletebilir. Bunu başarmanın etkili bir yolu, sunum slaytlarına video kareleri yerleştirmektir. Bu eğitimde, bunu Aspose.Slides for .NET kullanarak sorunsuz bir şekilde nasıl başaracağımızı inceleyeceğiz. Aspose.Slides, geliştiricilerin PowerPoint sunumlarını programatik olarak düzenlemelerine olanak tanıyan, slaytları oluşturma, düzenleme ve geliştirme için kapsamlı yetenekler sağlayan sağlam bir kütüphanedir.
## Ön koşullar
Eğitime başlamadan önce aşağıdakilerin mevcut olduğundan emin olun:
1. Aspose.Slides for .NET Kütüphanesi: Kütüphaneyi şu adresten indirin ve yükleyin: [Aspose.Slides .NET Belgeleri için](https://reference.aspose.com/slides/net/).
2. Örnek Video Dosyası: Sununuza yerleştirmek istediğiniz bir video dosyası hazırlayın. Sağlanan örneği "Wildlife.mp4" adlı bir videoyla kullanabilirsiniz.
## Ad Alanlarını İçe Aktar
.NET projenize, Aspose.Slides işlevlerinden yararlanmak için gerekli ad alanlarını ekleyin:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Aspose.Slides for .NET kullanarak sunum slaytlarına video kareleri yerleştirme sürecini yönetilebilir adımlara bölelim:
## Adım 1: Dizinleri Ayarlayın
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
// Eğer mevcut değilse dizin oluşturun.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Projenizdeki "Belge Dizininiz" ve "Medya Dizininiz" ifadelerini uygun yollarla değiştirdiğinizden emin olun.
## Adım 2: Sunum Nesnesi Oluşturun
```csharp
using (Presentation pres = new Presentation())
{
    // İlk slaydı alın
    ISlide sld = pres.Slides[0];
```
Yeni bir sunum başlatın ve video karesini yerleştirmek için ilk slayda erişin.
## Adım 3: Sunuma Video Yerleştirin
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
Kullanın `AddVideo` Videoyu sunuma yerleştirme yöntemi, dosya yolunu ve yükleme davranışını belirtir.
## Adım 4: Video Çerçevesi Ekle
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
Slaytta bir video karesi oluşturun, konumunu ve boyutlarını belirleyin.
## Adım 5: Video Ayarlarını Yapılandırın
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
Video karesini gömülü videoyla ilişkilendirin, oynatma modunu ayarlayın ve sesi tercihlerinize göre ayarlayın.
## Adım 6: Sunumu Kaydedin
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Değiştirilen sunuyu gömülü video karesiyle birlikte kaydedin.
## Çözüm
Tebrikler! Aspose.Slides for .NET kullanarak sunum slaytlarına video kareleri yerleştirmeyi başarıyla öğrendiniz. Bu özellik, izleyicilerinizi büyüleyen dinamik ve ilgi çekici sunumlar oluşturmak için heyecan verici olanaklar sunar.
## SSS
### Aspose.Slides'ı kullanarak farklı formatlardaki videoları yerleştirebilir miyim?
Evet, Aspose.Slides birçok video formatını destekleyerek sunumlarınızda esneklik sağlar.
### Gömülü videonun oynatma ayarlarını nasıl kontrol edebilirim?
Ayarla `PlayMode` Ve `Volume` oynatma davranışını özelleştirmek için video karesinin özellikleri.
### Aspose.Slides .NET'in son sürümleriyle uyumlu mu?
Aspose.Slides, en son .NET framework'leriyle uyumluluğunu korumak için düzenli olarak güncellenmektedir.
### Aspose.Slides'ı kullanarak tek bir slayta birden fazla video yerleştirebilir miyim?
Evet, bir slayda ek video kareleri ekleyerek birden fazla video yerleştirebilirsiniz.
### Aspose.Slides ile ilgili sorgular için desteği nerede bulabilirim?
Ziyaret edin [Aspose.Slides Forum](https://forum.aspose.com/c/slides/11) Topluluk desteği ve tartışmaları için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}