---
"description": "Aspose.Slides for .NET kullanarak PowerPoint slaytlarındaki bağlayıcı çizgi açılarını nasıl ayarlayacağınızı öğrenin. Sunumlarınızı hassasiyet ve kolaylıkla geliştirin."
"linktitle": "Aspose.Slides'ı kullanarak Sunum Slaytlarında Bağlayıcı Çizgi Açılarını Ayarlama"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "PowerPoint'te Aspose.Slides ile Bağlayıcı Çizgi Açılarını Ayarlayın"
"url": "/tr/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/"
"weight": 28
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Aspose.Slides ile Bağlayıcı Çizgi Açılarını Ayarlayın

## giriiş
Görsel olarak çekici sunum slaytları oluşturmak genellikle bağlayıcı çizgilerde hassas ayarlamalar yapmayı gerektirir. Bu eğitimde, .NET için Aspose.Slides kullanarak sunum slaytlarındaki bağlayıcı çizgi açılarının nasıl ayarlanacağını inceleyeceğiz. Aspose.Slides, geliştiricilerin PowerPoint dosyalarıyla programatik olarak çalışmasına olanak tanıyan, sunumlar oluşturmak, değiştirmek ve düzenlemek için kapsamlı yetenekler sağlayan güçlü bir kütüphanedir.
## Ön koşullar
Eğitime başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- C# programlama dilinin temel bilgisi.
- Visual Studio veya herhangi bir C# geliştirme ortamı yüklü.
- Aspose.Slides for .NET kütüphanesi. İndirebilirsiniz [Burada](https://releases.aspose.com/slides/net/).
- Ayarlamak istediğiniz bağlayıcı çizgilere sahip bir PowerPoint sunum dosyası.
## Ad Alanlarını İçe Aktar
Başlamak için, C# kodunuza gerekli ad alanlarını eklediğinizden emin olun:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## Adım 1: Projenizi Kurun
Visual Studio'da yeni bir C# projesi oluşturun ve Aspose.Slides NuGet paketini yükleyin. Proje yapısını Aspose.Slides kitaplığına bir referansla ayarlayın.
## Adım 2: Sunumu Yükleyin
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
PowerPoint sunum dosyanızı yükleyin `Presentation` nesne. "Belge Dizininiz" ifadesini dosyanızın gerçek yoluyla değiştirin.
## Adım 3: Slayt ve Şekillere Erişim
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
Sunumdaki ilk slayda erişin ve slayttaki şekilleri temsil edecek bir değişken başlatın.
## Adım 4: Şekiller Arasında Yineleme Yapın
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // Bağlantı hatlarını işleme kodu
}
```
Bağlantı çizgilerini belirlemek ve işlemek için slayttaki her şeklin üzerinde dolaşın.
## Adım 5: Bağlantı Hattı Açılarını Ayarlayın
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // Otomatik Şekilleri işleme kodu
}
else if (shape is Connector)
{
    // Bağlayıcıları işlemek için kod
}
Console.WriteLine(dir);
```
Şeklin Otomatik Şekil mi yoksa Bağlayıcı mı olduğunu belirleyin ve sağlanan bağlantı çizgilerinin açılarını ayarlayın. `getDirection` yöntem.
## Adım 6: Tanımlayın `getDirection` Yöntem
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
Uygula `getDirection` Bağlantı hattının boyutlarına ve yönüne bağlı olarak açısını hesaplama yöntemi.
## Çözüm
Bu adımlarla, Aspose.Slides for .NET kullanarak PowerPoint sunumunuzdaki bağlayıcı çizgi açılarını programatik olarak ayarlayabilirsiniz. Bu eğitim, slaytlarınızın görsel çekiciliğini artırmak için bir temel sağlar.
## SSS
### Aspose.Slides hem Windows hem de web uygulamaları için uygun mudur?
Evet, Aspose.Slides hem Windows hem de web uygulamalarında kullanılabilir.
### Aspose.Slides'ı satın almadan önce ücretsiz deneme sürümünü indirebilir miyim?
Evet, ücretsiz denemeyi indirebilirsiniz [Burada](https://releases.aspose.com/).
### Aspose.Slides for .NET için kapsamlı dokümanları nerede bulabilirim?
Belgeler mevcuttur [Burada](https://reference.aspose.com/slides/net/).
### Aspose.Slides için geçici lisansı nasıl alabilirim?
Geçici bir lisans alabilirsiniz [Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides için bir destek forumu var mı?
Evet, destek forumunu ziyaret edebilirsiniz [Burada](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}