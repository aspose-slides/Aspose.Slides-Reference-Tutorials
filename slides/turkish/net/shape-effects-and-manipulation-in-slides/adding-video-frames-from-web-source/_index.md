---
title: Aspose.Slides for .NET ile Video Karelerini Gömme Eğitimi
linktitle: Aspose.Slides ile Sunum Slaytlarına Web Kaynağından Video Kareleri Ekleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak video karelerini PowerPoint slaytlarına nasıl sorunsuz bir şekilde yerleştireceğinizi öğrenin. Sunumlarınızı multimedya ile zahmetsizce geliştirin.
weight: 20
url: /tr/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
Sunumların dinamik dünyasında, multimedya öğelerinin dahil edilmesi katılımı önemli ölçüde artırabilir ve etkili mesajlar iletebilir. Bunu başarmanın güçlü bir yolu, video çerçevelerini sunum slaytlarına yerleştirmektir. Bu eğitimde Aspose.Slides for .NET kullanarak bunu sorunsuz bir şekilde nasıl gerçekleştirebileceğimizi inceleyeceğiz. Aspose.Slides, geliştiricilerin PowerPoint sunumlarını programlı olarak değiştirmelerine olanak tanıyan, slayt oluşturma, düzenleme ve geliştirme için kapsamlı yetenekler sağlayan güçlü bir kitaplıktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilerin yerinde olduğundan emin olun:
1.  Aspose.Slides for .NET Library: Kitaplığı şuradan indirip yükleyin:[Aspose.Slides for .NET Belgeleri](https://reference.aspose.com/slides/net/).
2. Örnek Video Dosyası: Sunumunuza eklemek istediğiniz bir video dosyası hazırlayın. Sağlanan örneği "Wildlife.mp4" adlı bir videoyla kullanabilirsiniz.
## Ad Alanlarını İçe Aktar
.NET projenize Aspose.Slides işlevselliklerinden yararlanmak için gerekli ad alanlarını ekleyin:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Aspose.Slides for .NET kullanarak video karelerini sunum slaytlarına yerleştirme işlemini yönetilebilir adımlara ayıralım:
## 1. Adım: Dizinleri Ayarlayın
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
// Henüz mevcut değilse dizin oluşturun.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
"Belge Dizininiz" ve "Medya Dizininiz"i projenizdeki uygun yollarla değiştirdiğinizden emin olun.
## Adım 2: Sunum Nesnesi Oluşturun
```csharp
using (Presentation pres = new Presentation())
{
    // İlk slaydı alın
    ISlide sld = pres.Slides[0];
```
Yeni bir sunum başlatın ve video çerçevesini yerleştirmek için ilk slayda erişin.
## 3. Adım: Videoyu Sunuma Yerleştirin
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
 Kullanın`AddVideo` Dosya yolunu ve yükleme davranışını belirterek videoyu sunuma yerleştirme yöntemini kullanın.
## 4. Adım: Video Çerçevesi Ekleyin
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
Slayt üzerinde konumunu ve boyutlarını tanımlayan bir video çerçevesi oluşturun.
## Adım 5: Video Ayarlarını Yapılandırın
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
Video çerçevesini gömülü videoyla ilişkilendirin, oynatma modunu ayarlayın ve ses seviyesini tercihlerinize göre ayarlayın.
## Adım 6: Sunuyu Kaydet
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Değiştirilen sunumu gömülü video çerçevesiyle kaydedin.
## Çözüm
Tebrikler! Aspose.Slides for .NET'i kullanarak video karelerini sunum slaytlarına nasıl yerleştireceğinizi başarıyla öğrendiniz. Bu özellik, izleyicilerinizi büyüleyen dinamik ve ilgi çekici sunumlar oluşturmak için heyecan verici olanaklar sunar.
## SSS
### Aspose.Slides'ı kullanarak farklı formatlardaki videoları gömebilir miyim?
Evet, Aspose.Slides çeşitli video formatlarını destekleyerek sunumlarınızda esneklik sağlar.
### Gömülü videonun oynatma ayarlarını nasıl kontrol edebilirim?
 Ayarlayın`PlayMode` Ve`Volume` Oynatma davranışını özelleştirmek için video karesinin özellikleri.
### Aspose.Slides .NET'in en son sürümleriyle uyumlu mu?
Aspose.Slides, en yeni .NET çerçeveleriyle uyumluluğu sürdürmek için düzenli olarak güncellenmektedir.
### Aspose.Slides'ı kullanarak tek bir slayda birden fazla video yerleştirebilir miyim?
Evet, bir slayda ek video kareleri ekleyerek birden fazla video gömebilirsiniz.
### Aspose.Slides ile ilgili sorgular için nereden destek bulabilirim?
 Ziyaret edin[Aspose.Slides Forumu](https://forum.aspose.com/c/slides/11) topluluk desteği ve tartışmalar için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
