---
title: Aspose.Slides - .NET Sunumlarına Gömülü Videolar Ekleme
linktitle: Aspose.Slides - .NET Sunumlarına Gömülü Videolar Ekleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak sunumlarınızı gömülü videolarla geliştirin. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin.
weight: 19
url: /tr/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Sunumların dinamik dünyasında multimedya öğelerinin entegre edilmesi katılımı önemli ölçüde artırabilir. Aspose.Slides for .NET, gömülü video çerçevelerini sunum slaytlarınıza dahil etmek için güçlü bir çözüm sunar. Bu eğitim, kusursuz bir deneyim sağlamak için her adımı parçalara ayırarak süreç boyunca size rehberlik edecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
-  Aspose.Slides for .NET Library: Kitaplığı şuradan indirip yükleyin:[yayın sayfası](https://releases.aspose.com/slides/net/).
- Medya İçeriği: Sununuza eklemek istediğiniz bir video dosyanız (örneğin, "Wildlife.mp4") olsun.
## Ad Alanlarını İçe Aktar
.NET projenize gerekli ad alanlarını içe aktararak başlayın:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## 1. Adım: Dizinleri Ayarlayın
Projenizin belge ve medya dosyaları için gerekli dizinlere sahip olduğundan emin olun:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Henüz mevcut değilse dizin oluşturun.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Adım 2: Sunum Sınıfını Başlatın
PPTX dosyasını temsil edecek Sunum sınıfının bir örneğini oluşturun:
```csharp
using (Presentation pres = new Presentation())
{
    // İlk slaydı alın
    ISlide sld = pres.Slides[0];
```
## 3. Adım: Videoyu Sunumun İçine Yerleştirin
Sunumun içine video eklemek için aşağıdaki kodu kullanın:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## 4. Adım: Video Çerçevesi Ekleyin
Şimdi slayta bir video karesi ekleyin:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## 5. Adım: Video Özelliklerini Ayarlayın
Videoyu video çerçevesine ayarlayın ve oynatma modunu ve ses seviyesini yapılandırın:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Adım 6: Sunuyu Kaydetme
Son olarak PPTX dosyasını diske kaydedin:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Sununuza eklemek istediğiniz her video için bu adımları tekrarlayın.
## Çözüm
Tebrikler! Aspose.Slides for .NET'i kullanarak sunumunuza başarıyla gömülü bir video karesi eklediniz. Bu dinamik özellik, slaytlarınıza kusursuz bir şekilde entegre edilen multimedya öğeleriyle izleyicilerinizi büyüleyerek sunumlarınızı yeni boyutlara taşıyabilir.
## SSS
### Sunumun herhangi bir slaytına video ekleyebilir miyim?
 Evet, dizini değiştirerek herhangi bir slaytı seçebilirsiniz.`pres.Slides[index]`.
### Hangi video formatları destekleniyor?
Aspose.Slides, MP4, AVI ve WMV dahil olmak üzere çeşitli video formatlarını destekler.
### Video çerçevesinin boyutunu ve konumunu özelleştirebilir miyim?
 Kesinlikle! Parametreleri ayarlayın`AddVideoFrame(x, y, width, height, video)` ihyaç olduğu gibi.
### Yerleştirebileceğim video sayısında bir sınır var mı?
Gömülü videoların sayısı genellikle sunum yazılımınızın kapasitesiyle sınırlıdır.
### Nasıl daha fazla yardım isteyebilirim veya deneyimimi nasıl paylaşabilirim?
 Ziyaret edin[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) topluluk desteği ve tartışmalar için.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
