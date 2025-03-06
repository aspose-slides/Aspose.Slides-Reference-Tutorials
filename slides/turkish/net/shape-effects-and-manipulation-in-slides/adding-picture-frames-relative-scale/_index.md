---
title: Aspose.Slides .NET ile Resim Çerçevesi Ekleme Eğitimi
linktitle: Aspose.Slides'ta Göreli Ölçek Yüksekliğine Sahip Resim Çerçeveleri Ekleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'te göreceli ölçek yüksekliğine sahip resim çerçeveleri eklemeyi öğrenin. Kusursuz sunumlar için bu adım adım kılavuzu izleyin.
weight: 17
url: /tr/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
Aspose.Slides for .NET, geliştiricilerin .NET uygulamalarında PowerPoint sunumlarını zahmetsizce oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır. Bu eğitimde Aspose.Slides for .NET'i kullanarak göreceli ölçek yüksekliğine sahip resim çerçeveleri ekleme sürecini ele alacağız. Sunum oluşturma becerilerinizi geliştirmek için bu adım adım kılavuzu izleyin.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Temel C# programlama dili bilgisi.
- Visual Studio veya tercih edilen herhangi bir C# geliştirme ortamı yüklü.
- Aspose.Slides for .NET kütüphanesi projenize eklendi.
## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını C# kodunuza aktararak başlayın. Bu adım, Aspose.Slides kütüphanesi tarafından sağlanan sınıflara ve işlevlere erişmenizi sağlar.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## 1. Adım: Projenizi Kurun
Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturarak başlayın. Aspose.Slides for .NET kütüphanesini referans alarak projenize eklediğinizden emin olun.
## Adım 2: Sunumu ve Resmi Yükleyin
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    //Sunum görseli koleksiyonuna eklenecek Görseli Yükle
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
Bu adımda yeni bir sunum nesnesi oluşturup sunuma eklemek istediğimiz görseli yüklüyoruz.
## 3. Adım: Slayta Resim Çerçevesi Ekleme
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Şimdi sunumun ilk slaydına bir resim çerçevesi ekleyin. Şekil türü, konum ve boyutlar gibi parametreleri gereksinimlerinize göre ayarlayın.
## Adım 4: Göreli Ölçek Genişliğini ve Yüksekliğini Ayarlayın
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
İstenilen ölçeklendirme efektini elde etmek için resim çerçevesinin göreceli ölçek yüksekliğini ve genişliğini ayarlayın.
## Adım 5: Sunuyu Kaydet
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Son olarak, eklenen resim çerçevesiyle birlikte sunuyu belirtilen çıktı formatında kaydedin.
## Çözüm
Tebrikler! Aspose.Slides for .NET kullanarak göreceli ölçek yüksekliğine sahip resim çerçevelerinin nasıl ekleneceğini başarıyla öğrendiniz. İhtiyaçlarınıza uygun, görsel olarak çekici sunumlar oluşturmak için farklı görseller, konumlar ve ölçeklerle denemeler yapın.
## Sıkça Sorulan Sorular
### Aspose.Slides for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Slides öncelikli olarak .NET dillerini destekler ancak farklı platformlarla uyumluluk açısından diğer Aspose ürünlerini de inceleyebilirsiniz.
### Aspose.Slides for .NET'in ayrıntılı belgelerini nerede bulabilirim?
 Bakın[dokümantasyon](https://reference.aspose.com/slides/net/) Kapsamlı bilgi ve örnekler için.
### Aspose.Slides for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, alabilirsiniz[ücretsiz deneme](https://releases.aspose.com/) Kütüphanenin yeteneklerini değerlendirmek.
### Aspose.Slides for .NET için nasıl destek alabilirim?
 Ziyaret edin[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) topluluktan ve Aspose uzmanlarından yardım istemek.
### Aspose.Slides for .NET'i nereden satın alabilirim?
 Aspose.Slides for .NET'i şu adresten satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
