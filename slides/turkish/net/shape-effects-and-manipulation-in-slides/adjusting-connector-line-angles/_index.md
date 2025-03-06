---
title: Aspose.Slides ile PowerPoint'te Bağlayıcı Çizgi Açılarını Ayarlayın
linktitle: Aspose.Slides Kullanarak Sunum Slaytlarında Bağlayıcı Çizgi Açılarını Ayarlama
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint slaytlarında bağlayıcı çizgi açılarını nasıl ayarlayacağınızı öğrenin. Sunumlarınızı hassasiyetle ve kolaylıkla geliştirin.
weight: 28
url: /tr/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Görsel olarak çekici sunum slaytları oluşturmak genellikle bağlayıcı hatlarda hassas ayarlamalar gerektirir. Bu eğitimde Aspose.Slides for .NET kullanarak sunum slaytlarında bağlayıcı çizgi açılarının nasıl ayarlanacağını inceleyeceğiz. Aspose.Slides, geliştiricilerin PowerPoint dosyalarıyla programlı olarak çalışmasına olanak tanıyan, sunum oluşturma, değiştirme ve düzenleme için kapsamlı yetenekler sağlayan güçlü bir kitaplıktır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Temel C# programlama dili bilgisi.
- Visual Studio veya başka herhangi bir C# geliştirme ortamı yüklü.
-  Aspose.Slides for .NET kitaplığı. İndirebilirsin[Burada](https://releases.aspose.com/slides/net/).
- Ayarlamak istediğiniz bağlayıcı çizgileri içeren bir PowerPoint sunum dosyası.
## Ad Alanlarını İçe Aktar
Başlamak için C# kodunuza gerekli ad alanlarını eklediğinizden emin olun:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## 1. Adım: Projenizi Kurun
Visual Studio'da yeni bir C# projesi oluşturun ve Aspose.Slides NuGet paketini yükleyin. Aspose.Slides kütüphanesine referansla proje yapısını kurun.
## 2. Adım: Sunuyu Yükleyin
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
 PowerPoint sunum dosyanızı şuraya yükleyin:`Presentation`nesne. "Belge Dizininiz"i dosyanızın gerçek yolu ile değiştirin.
## 3. Adım: Slayt ve Şekillere Erişin
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
Sunumdaki ilk slayda erişin ve slayttaki şekilleri temsil edecek bir değişkeni başlatın.
## Adım 4: Şekiller Arasında Yineleme Yapın
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // Bağlayıcı hatlarını yönetme kodu
}
```
Bağlayıcı çizgileri tanımlamak ve işlemek için slayttaki her şeklin üzerinden geçin.
## Adım 5: Konektör Çizgi Açılarını Ayarlayın
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // Otomatik Şekilleri işlemeye yönelik kod
}
else if (shape is Connector)
{
    // Konektörleri işleme kodu
}
Console.WriteLine(dir);
```
 Şeklin Otomatik Şekil mi yoksa Bağlayıcı mı olduğunu belirleyin ve sağlanan yöntemi kullanarak bağlayıcı çizgi açılarını ayarlayın.`getDirection` yöntem.
##  Adım 6: Tanımlayın`getDirection` Method
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // Yön hesaplama kodu
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
 Uygulamak`getDirection` boyutlarına ve yönüne göre bağlantı çizgisinin açısını hesaplama yöntemi.
## Çözüm
Bu adımlarla Aspose.Slides for .NET'i kullanarak PowerPoint sunumunuzdaki bağlayıcı çizgi açılarını programlı bir şekilde ayarlayabilirsiniz. Bu eğitim, slaytlarınızın görsel çekiciliğini artırmak için bir temel sağlar.
## SSS
### Aspose.Slides hem Windows hem de web uygulamaları için uygun mudur?
Evet, Aspose.Slides hem Windows hem de web uygulamalarında kullanılabilir.
### Satın almadan önce Aspose.Slides'ın ücretsiz deneme sürümünü indirebilir miyim?
 Evet, ücretsiz deneme sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Slides for .NET'in kapsamlı belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/slides/net/).
### Aspose.Slides için nasıl geçici lisans alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides için bir destek forumu var mı?
 Evet, destek forumunu ziyaret edebilirsiniz[Burada](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
