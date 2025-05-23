---
"description": "Aspose.Slides for .NET kullanarak sunumlarınızı gömülü videolarla geliştirin. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin."
"linktitle": "Aspose.Slides - .NET Sunumlarına Gömülü Videolar Ekleme"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides - .NET Sunumlarına Gömülü Videolar Ekleme"
"url": "/tr/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - .NET Sunumlarına Gömülü Videolar Ekleme

## giriiş
Sunumların dinamik dünyasında, multimedya öğelerini entegre etmek etkileşimi önemli ölçüde artırabilir. Aspose.Slides for .NET, gömülü video karelerini sunum slaytlarınıza dahil etmek için güçlü bir çözüm sunar. Bu eğitim, sorunsuz bir deneyim sağlamak için her adımı parçalara ayırarak sizi süreçte yönlendirecektir.
## Ön koşullar
Eğitime başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Aspose.Slides for .NET Kütüphanesi: Kütüphaneyi şu adresten indirin ve yükleyin: [yayın sayfası](https://releases.aspose.com/slides/net/).
- Medya İçeriği: Sununuza yerleştirmek istediğiniz bir video dosyanız (örneğin, "Wildlife.mp4") var.
## Ad Alanlarını İçe Aktar
.NET projenize gerekli ad alanlarını içe aktararak başlayın:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Adım 1: Dizinleri Ayarlayın
Projenizin belge ve medya dosyaları için gerekli dizinlere sahip olduğundan emin olun:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Eğer mevcut değilse dizin oluşturun.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Adım 2: Sunum Sınıfını Oluşturun
PPTX dosyasını temsil etmek için Presentation sınıfının bir örneğini oluşturun:
```csharp
using (Presentation pres = new Presentation())
{
    // İlk slaydı alın
    ISlide sld = pres.Slides[0];
```
## Adım 3: Videoyu Sunumun İçine Yerleştirin
Sunumun içine video yerleştirmek için aşağıdaki kodu kullanın:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Adım 4: Video Çerçevesi Ekle
Şimdi slayda bir video karesi ekleyelim:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Adım 5: Video Özelliklerini Ayarlayın
Videoyu video karesine ayarlayın ve oynatma modunu ve ses seviyesini yapılandırın:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Adım 6: Sunumu Kaydedin
Son olarak PPTX dosyasını diske kaydedin:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Sununuza yerleştirmek istediğiniz her video için bu adımları tekrarlayın.
## Çözüm
Tebrikler! Aspose.Slides for .NET kullanarak sununuza gömülü bir video karesi eklemeyi başardınız. Bu dinamik özellik, sunumlarınızı yeni zirvelere taşıyabilir ve slaytlarınıza kusursuz bir şekilde entegre edilmiş multimedya öğeleriyle izleyicilerinizi büyüleyebilir.
## SSS
### Sunumun herhangi bir slaydına video ekleyebilir miyim?
Evet, dizini değiştirerek herhangi bir slaydı seçebilirsiniz. `pres.Slides[index]`.
### Hangi video formatları destekleniyor?
Aspose.Slides, MP4, AVI ve WMV dahil olmak üzere çeşitli video formatlarını destekler.
### Video karesinin boyutunu ve konumunu özelleştirebilir miyim?
Kesinlikle! Parametreleri ayarlayın `AddVideoFrame(x, y, width, height, video)` ihtiyaç duyulduğu takdirde.
### Gömebileceğim video sayısında bir sınır var mı?
Gömülü videoların sayısı genellikle sunum yazılımınızın kapasitesiyle sınırlıdır.
### Daha fazla yardıma nasıl ulaşabilirim veya deneyimlerimi nasıl paylaşabilirim?
Ziyaret edin [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) Topluluk desteği ve tartışmaları için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}