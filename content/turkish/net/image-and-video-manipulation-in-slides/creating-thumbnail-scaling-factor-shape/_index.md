---
title: Aspose.Slides'ta Şekil için Ölçekleme Faktörü ile Küçük Resim Oluşturma
linktitle: Aspose.Slides'ta Şekil için Ölçekleme Faktörü ile Küçük Resim Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak belirli sınırlara sahip PowerPoint küçük resimleri oluşturmayı öğrenin. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin.
type: docs
weight: 12
url: /tr/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/
---
## giriiş
Aspose.Slides for .NET'te şekiller için sınırlar içeren küçük resimler oluşturmaya ilişkin kapsamlı kılavuzumuza hoş geldiniz. Aspose.Slides, geliştiricilerin .NET uygulamalarında PowerPoint sunumlarıyla sorunsuz bir şekilde çalışmasına olanak tanıyan güçlü bir kitaplıktır. Bu eğitimde Aspose.Slides'ı kullanarak bir sunumdaki şekiller için belirli sınırlara sahip küçük resimler oluşturma sürecini inceleyeceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.Slides for .NET: Aspose.Slides kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).
- Geliştirme Ortamı: Makinenizde Visual Studio gibi .NET için uygun bir geliştirme ortamı kurun.
## Ad Alanlarını İçe Aktar
.NET uygulamanızda Aspose.Slides işlevlerine erişmek için gerekli ad alanlarını içe aktararak başlayın:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## 1. Adım: Sunumu Hazırlayın
Çalışmak istediğiniz PowerPoint sunum dosyasını temsil eden bir Sunum sınıfının örneğini oluşturarak başlayın:
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // Küçük resim oluşturma kodunuz buraya gelecek
}
```
## Adım 2: Tam Ölçekli Bir Görüntü Oluşturun
Sunum bloğunda, küçük resmini oluşturmak istediğiniz şeklin tam ölçekli görüntüsünü oluşturun:
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    //Resmi kaydetme kodunuz buraya gelecek
}
```
## 3. Adım: Görüntüyü Diske Kaydedin
Oluşturulan görüntüyü formatı belirterek (bu durumda PNG) diske kaydedin:
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## Çözüm
Tebrikler! Aspose.Slides for .NET'i kullanarak şekiller için sınırları olan küçük resimlerin nasıl oluşturulacağını başarıyla öğrendiniz. Bu özellik, PowerPoint sunumlarınızda programlı olarak belirli boyutlu şekil görüntüleri oluşturmanız gerektiğinde inanılmaz derecede yararlı olabilir.
## Sıkça Sorulan Sorular
### S1: Aspose.Slides'ı diğer .NET çerçeveleriyle kullanabilir miyim?
Evet, Aspose.Slides çeşitli .NET çerçeveleriyle uyumludur ve farklı uygulama türlerine entegrasyon esnekliği sağlar.
### S2: Aspose.Slides'ın deneme sürümü mevcut mu?
 Evet, deneme sürümünü indirerek Aspose.Slides'ın işlevlerini keşfedebilirsiniz.[Burada](https://releases.aspose.com/).
### S3: Aspose.Slides için nasıl geçici lisans alabilirim?
 adresini ziyaret ederek Aspose.Slides için geçici bir lisans alabilirsiniz.[bu bağlantı](https://purchase.aspose.com/temporary-license/).
### S4: Aspose.Slides için ek desteği nerede bulabilirim?
Sorularınız veya yardımlarınız için Aspose.Slides destek forumunu ziyaret etmekten çekinmeyin[Burada](https://forum.aspose.com/c/slides/11).
### S5: Aspose.Slides for .NET'i satın alabilir miyim?
 Kesinlikle! Aspose.Slides for .NET'i satın almak için lütfen satın alma sayfasını ziyaret edin[Burada](https://purchase.aspose.com/buy).