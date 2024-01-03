---
title: Aspose.Slides for .NET ile Sunumlarda 3D Döndürmede Uzmanlaşma
linktitle: Sunum Slaytlarındaki Şekillere 3B Döndürme Efekti Uygulama
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET ile sunumlarınızı geliştirin! Bu öğreticide şekillere 3B döndürme efektleri uygulamayı öğrenin. Dinamik ve görsel olarak etkileyici sunumlar oluşturun.
type: docs
weight: 23
url: /tr/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---
## giriiş
İlgi çekici ve dinamik sunum slaytları oluşturmak, etkili iletişimin önemli bir yönüdür. Aspose.Slides for .NET, şekillere 3D döndürme efektleri uygulama yeteneği de dahil olmak üzere sunumlarınızı geliştirmek için güçlü bir araç seti sağlar. Bu eğitimde Aspose.Slides for .NET kullanarak sunum slaytlarındaki şekillere 3D döndürme efekti uygulama sürecini anlatacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.Slides for .NET: Aspose.Slides for .NET kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[İnternet sitesi](https://releases.aspose.com/slides/net/).
- Geliştirme Ortamı: Kodunuzu yazmak ve çalıştırmak için Visual Studio gibi bir .NET geliştirme ortamı kurun.
## Ad Alanlarını İçe Aktar
Aspose.Slides'ın işlevselliğinden yararlanmak için .NET projenize gerekli ad alanlarını içe aktarın. Kodunuzun başına aşağıdaki ad alanlarını ekleyin:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## 1. Adım: Projenizi Kurun
Tercih ettiğiniz .NET geliştirme ortamında yeni bir proje oluşturun. Aspose.Slides referansını projenize eklediğinizden emin olun.
## Adım 2: Sunumu Başlatın
Slaytlarla çalışmaya başlamak için bir Sunum sınıfı oluşturun:
```csharp
Presentation pres = new Presentation();
```
## 3. Adım: Otomatik Şekil Ekle
Slayta türünü, konumunu ve boyutlarını belirten bir Otomatik Şekil ekleyin:
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
## Adım 5: Sunuyu Kaydetme
Değiştirilen sunumu uygulanan 3B döndürme efektiyle kaydedin:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## Adım 6: Diğer Şekiller İçin Tekrarlayın
Ek şekilleriniz varsa, her şekil için 3'ten 5'e kadar olan adımları tekrarlayın.
## Çözüm
Sunum slaytlarınızdaki şekillere 3B döndürme efektleri eklemek, şekillerin görsel çekiciliğini önemli ölçüde artırabilir. Aspose.Slides for .NET ile bu süreç basitleşerek büyüleyici sunumlar oluşturmanıza olanak tanır.
## SSS
### Aspose.Slides for .NET'te metin kutularına 3D döndürme uygulayabilir miyim?
Evet, Aspose.Slides'ı kullanarak metin kutuları da dahil olmak üzere çeşitli şekillere 3D döndürme efektleri uygulayabilirsiniz.
### Aspose.Slides for .NET'in deneme sürümü mevcut mu?
 Evet deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Slides for .NET için nasıl destek alabilirim?
 Ziyaret edin[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) topluluk desteği ve tartışmalar için.
### Aspose.Slides for .NET için geçici bir lisans satın alabilir miyim?
 Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for .NET'in ayrıntılı belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/slides/net/).