---
"description": "Aspose.Slides for .NET'te göreceli ölçek yüksekliğine sahip resim çerçeveleri eklemeyi öğrenin. Sorunsuz sunumlar için bu adım adım kılavuzu izleyin."
"linktitle": "Aspose.Slides'ta Göreceli Ölçek Yüksekliğiyle Resim Çerçeveleri Ekleme"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides .NET ile Resim Çerçeveleri Ekleme Eğitimi"
"url": "/tr/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides .NET ile Resim Çerçeveleri Ekleme Eğitimi

## giriiş
Aspose.Slides for .NET, geliştiricilerin .NET uygulamalarında zahmetsizce PowerPoint sunumları oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan güçlü bir kütüphanedir. Bu eğitimde, Aspose.Slides for .NET kullanarak göreceli ölçek yüksekliğine sahip resim çerçeveleri ekleme sürecini ele alacağız. Sunum oluşturma becerilerinizi geliştirmek için bu adım adım kılavuzu takip edin.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- C# programlama dilinin temel bilgisi.
- Visual Studio veya tercih ettiğiniz herhangi bir C# geliştirme ortamı yüklü.
- Aspose.Slides for .NET kütüphanesi projenize eklendi.
## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını C# kodunuza aktararak başlayın. Bu adım, Aspose.Slides kütüphanesi tarafından sağlanan sınıflara ve işlevlere erişiminizin olmasını sağlar.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Adım 1: Projenizi Kurun
Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturarak başlayın. Projenize referans vererek Aspose.Slides for .NET kütüphanesini eklediğinizden emin olun.
## Adım 2: Sunumu ve Görüntüyü Yükle
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Sunum resim koleksiyonuna eklenecek Resmi Yükle
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
Bu adımda yeni bir sunum nesnesi oluşturuyoruz ve sunuma eklemek istediğimiz görseli yüklüyoruz.
## Adım 3: Slayda Resim Çerçevesi Ekleyin
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Şimdi, sunumun ilk slaydına bir resim çerçevesi ekleyin. Şekil türü, konum ve boyutlar gibi parametreleri gereksinimlerinize göre ayarlayın.
## Adım 4: Göreceli Ölçek Genişliğini ve Yüksekliğini Ayarlayın
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
İstediğiniz ölçekleme efektini elde etmek için resim çerçevesinin göreceli ölçek yüksekliğini ve genişliğini ayarlayın.
## Adım 5: Sunumu Kaydedin
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Son olarak sunuyu eklenen resim çerçevesiyle birlikte belirtilen çıktı formatında kaydedin.
## Çözüm
Tebrikler! Aspose.Slides for .NET kullanarak resim çerçevelerini göreceli ölçek yüksekliğiyle eklemeyi başarıyla öğrendiniz. İhtiyaçlarınıza göre uyarlanmış görsel olarak çekici sunumlar oluşturmak için farklı resimler, konumlar ve ölçeklerle denemeler yapın.
## Sıkça Sorulan Sorular
### Aspose.Slides for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Slides öncelikli olarak .NET dillerini destekler, ancak farklı platformlarla uyumluluk için diğer Aspose ürünlerini inceleyebilirsiniz.
### Aspose.Slides for .NET için detaylı dokümantasyonu nerede bulabilirim?
Şuna bakın: [belgeleme](https://reference.aspose.com/slides/net/) Kapsamlı bilgi ve örnekler için.
### Aspose.Slides for .NET için ücretsiz deneme sürümü mevcut mu?
Evet, alabilirsiniz [ücretsiz deneme](https://releases.aspose.com/) Kütüphanenin imkânlarını değerlendirmek.
### Aspose.Slides for .NET desteğini nasıl alabilirim?
Ziyaret edin [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) Topluluktan ve Aspose uzmanlarından yardım istemek.
### Aspose.Slides for .NET'i nereden satın alabilirim?
Aspose.Slides for .NET'i şu adresten satın alabilirsiniz: [satın alma sayfası](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}