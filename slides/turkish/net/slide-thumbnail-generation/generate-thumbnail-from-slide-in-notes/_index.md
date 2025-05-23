---
"description": "Aspose.Slides for .NET kullanarak sunumunuzun notlar bölümündeki slaytlardan küçük resimlerin nasıl oluşturulacağını öğrenin. Görsel içeriğinizi geliştirin!"
"linktitle": "Notlarda Slayttan Küçük Resim Oluştur"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Notlarda Slayttan Küçük Resim Oluştur"
"url": "/tr/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Notlarda Slayttan Küçük Resim Oluştur


Modern sunumların dünyasında görsel içerik kraldır. Etkili iletişim için ilgi çekici slaytlar oluşturmak esastır. Sunumlarınızı geliştirmenin bir yolu, özellikle belirli ayrıntıları vurgulamak veya bir genel bakış paylaşmak istediğinizde slaytlardan küçük resimler oluşturmaktır. Aspose.Slides for .NET bunu sorunsuz bir şekilde başarmanıza yardımcı olabilecek güçlü bir araçtır. Bu adım adım kılavuzda, Aspose.Slides for .NET kullanarak bir sunumun notlar bölümündeki slaytlardan küçük resimler oluşturma sürecinde size yol göstereceğiz.

## Ön koşullar

Detaylara dalmadan önce aşağıdaki ön koşulların mevcut olması gerekir:

### 1. .NET için Aspose.Slides

Aspose.Slides for .NET'in yüklü ve ayarlanmış olduğundan emin olun. Bunu şuradan indirebilirsiniz: [Burada](https://releases.aspose.com/slides/net/).

### 2. .NET Ortamı

Sisteminizde hazır bir .NET geliştirme ortamınız olmalıdır.

### 3. Bir Sunum Dosyası

Bir sunum dosyanız olsun (örneğin, `ThumbnailFromSlideInNotes.pptx`) küçük resim oluşturmak istediğiniz yer.

Şimdi süreci adımlara bölelim:

## Adım 1: Ad Alanlarını İçe Aktar

Öncelikle Aspose.Slides ile çalışmak için gerekli ad alanlarını içe aktarmanız gerekir. C# betiğinizin başına aşağıdaki kodu ekleyin:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Adım 2: Sunumu Yükleyin

Sonra, notlarla slaytları içeren sunum dosyasını yüklemeniz gerekecek. Bir örnek oluşturmak için aşağıdaki kodu kullanın `Presentation` sınıf:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Kodunuz buraya gelecek
}
```

## Adım 3: Slayda Erişim

Sunumdaki hangi slayt için küçük resim oluşturmak istediğinizi seçebilirsiniz. Bu örnekte, ilk slayda erişeceğiz:

```csharp
ISlide sld = pres.Slides[0];
```

## Adım 4: İstenilen Boyutları Tanımlayın

Oluşturmak istediğiniz küçük resim için boyutları (genişlik ve yükseklik) belirtin. Örneğin:

```csharp
int desiredX = 1200; // Genişlik
int desiredY = 800;  // Yükseklik
```

## Adım 5: Ölçekleme Faktörlerini Hesaplayın

Küçük resmin istenilen boyutlara uyduğundan emin olmak için ölçekleme faktörlerini aşağıdaki gibi hesaplayın:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Adım 6: Küçük Resim Oluşturun

Şimdi hesaplanan ölçekleme faktörlerini kullanarak tam ölçekli bir görüntü küçük resmi oluşturun:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Adım 7: Küçük resmi kaydedin

Son olarak oluşturulan küçük resmi JPEG resmi olarak kaydedin:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

İşte bu kadar! Aspose.Slides for .NET kullanarak sunumunuzun notlar bölümündeki bir slayttan küçük resim oluşturmayı başardınız.

## Çözüm

Sunumlarınıza küçük resimler eklemek görsel çekiciliğini ve etkinliğini önemli ölçüde artırabilir. Aspose.Slides for .NET bu süreci basitleştirir ve slaytlarınızdan kolayca özelleştirilmiş küçük resimler oluşturmanıza olanak tanır.

## SSS (Sıkça Sorulan Sorular)

### Oluşturulan küçük resimleri hangi formatlarda kaydedebilirim?
İhtiyaçlarınıza bağlı olarak küçük resimleri JPEG, PNG ve daha fazlası dahil olmak üzere çeşitli biçimlerde kaydedebilirsiniz.

### Birden fazla slayt için aynı anda küçük resim oluşturabilir miyim?
Evet, sununuzdaki slaytlar arasında dolaşabilir ve her biri için küçük resimler oluşturabilirsiniz.

### Aspose.Slides for .NET farklı .NET framework'leriyle uyumlu mudur?
Evet, Aspose.Slides for .NET, .NET Core ve .NET Framework dahil olmak üzere çeşitli .NET çerçeveleriyle uyumludur.

### Oluşturulan küçük resimlerin görünümünü özelleştirebilir miyim?
Kesinlikle! Aspose.Slides for .NET, boyutlar, kalite ve daha fazlası gibi küçük resimlerin görünümünü özelleştirmek için seçenekler sunar.

### Aspose.Slides for .NET ile ilgili destek veya daha fazla yardımı nereden alabilirim?
Aspose topluluğuyla yardım alabilir ve etkileşime girebilirsiniz [Aspose Destek Forumu](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}