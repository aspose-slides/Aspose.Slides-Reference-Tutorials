---
"description": "Sunumlarınızı Aspose.Slides for .NET ile geliştirin! Bu eğitimde şekillere 3D döndürme efektleri uygulamayı öğrenin. Dinamik ve görsel olarak çarpıcı sunumlar yaratın."
"linktitle": "Sunum Slaytlarındaki Şekillere 3D Döndürme Efekti Uygulama"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides for .NET ile Sunumlarda 3D Döndürmeyi Ustalaştırma"
"url": "/tr/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for .NET ile Sunumlarda 3D Döndürmeyi Ustalaştırma

## giriiş
Etkili iletişimin temel bir yönü, ilgi çekici ve dinamik sunum slaytları oluşturmaktır. Aspose.Slides for .NET, şekillere 3D döndürme efektleri uygulama yeteneği de dahil olmak üzere sunumlarınızı geliştirmek için güçlü bir araç seti sunar. Bu eğitimde, Aspose.Slides for .NET kullanarak sunum slaytlarındaki şekillere 3D döndürme efekti uygulama sürecini ele alacağız.
## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
- .NET için Aspose.Slides: .NET için Aspose.Slides kitaplığının yüklü olduğundan emin olun. Bunu şuradan indirebilirsiniz: [web sitesi](https://releases.aspose.com/slides/net/).
- Geliştirme Ortamı: Kodunuzu yazmak ve çalıştırmak için Visual Studio gibi bir .NET geliştirme ortamı kurun.
## Ad Alanlarını İçe Aktar
.NET projenizde, Aspose.Slides işlevselliğinden yararlanmak için gerekli ad alanlarını içe aktarın. Kodunuzun başına aşağıdaki ad alanlarını ekleyin:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Adım 1: Projenizi Kurun
Tercih ettiğiniz .NET geliştirme ortamında yeni bir proje oluşturun. Projenize Aspose.Slides referansını eklediğinizden emin olun.
## Adım 2: Sunumu Başlatın
Slaytlarla çalışmaya başlamak için bir Sunum sınıfı oluşturun:
```csharp
Presentation pres = new Presentation();
```
## Adım 3: Otomatik Şekil Ekle
Slayda bir Otomatik Şekil ekleyin ve türünü, konumunu ve boyutlarını belirtin:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## Adım 4: 3D Döndürme Efektini Ayarlayın
Otomatik Şekil için 3B döndürme efektini yapılandırın:
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## Adım 5: Sunumu Kaydedin
Değiştirilen sunumu uygulanan 3D döndürme efektiyle kaydedin:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## Adım 6: Diğer Şekiller İçin Tekrarlayın
Eğer ek şekilleriniz varsa, her şekil için 3. ila 5. Adımları tekrarlayın.
## Çözüm
Sunum slaytlarınızdaki şekillere 3D döndürme efektleri eklemek görsel çekiciliklerini önemli ölçüde artırabilir. Aspose.Slides for .NET ile bu süreç basit hale gelir ve ilgi çekici sunumlar oluşturmanıza olanak tanır.
## SSS
### Aspose.Slides for .NET'te metin kutularına 3D döndürme uygulayabilir miyim?
Evet, Aspose.Slides'ı kullanarak metin kutuları da dahil olmak üzere çeşitli şekillere 3B döndürme efektleri uygulayabilirsiniz.
### Aspose.Slides for .NET'in deneme sürümü mevcut mu?
Evet, deneme sürümüne erişebilirsiniz [Burada](https://releases.aspose.com/).
### Aspose.Slides for .NET desteğini nasıl alabilirim?
Ziyaret edin [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) Topluluk desteği ve tartışmaları için.
### Aspose.Slides for .NET için geçici bir lisans satın alabilir miyim?
Evet, geçici bir lisans alabilirsiniz [Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for .NET için detaylı dokümantasyonu nerede bulabilirim?
Belgeler mevcuttur [Burada](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}