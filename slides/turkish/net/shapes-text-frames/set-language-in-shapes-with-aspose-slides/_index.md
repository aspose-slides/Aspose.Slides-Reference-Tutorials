---
"date": "2025-04-16"
"description": "Aspose.Slides for .NET kullanarak şekiller içindeki metinler için dil niteliklerinin nasıl ayarlanacağını öğrenin. Bu kılavuz, otomatik şekiller eklemeyi, dil kimliklerini ayarlamayı ve sunumları kaydetmeyi kapsar."
"title": "Aspose.Slides for .NET Kullanarak PowerPoint Şekillerinde Dil Nasıl Ayarlanır"
"url": "/tr/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET Kullanarak PowerPoint Şekillerinde Dil Nasıl Ayarlanır

Dijital sunumlar dünyasında, içeriğinizin erişilebilir ve farklı dillerde doğru biçimde biçimlendirilmiş olmasını sağlamak zor olabilir. Aspose.Slides for .NET ile PowerPoint slaytlarındaki şekillerin içindeki metinler için dil niteliklerini zahmetsizce ayarlayabilirsiniz. Bu özellik, çok dilli belgeler hazırlarken veya küresel iletişimlerde tutarlılığı sağlarken özellikle faydalıdır.

**Ne Öğreneceksiniz:**
- Otomatik şekiller ekleme ve içlerine metin yerleştirme.
- Aspose.Slides kullanarak metin bölümleri için dil kimliğini ayarlama.
- Özel yapılandırmalarla sunumları kaydetme.

Bu özelliği sorunsuz bir şekilde nasıl uygulayabileceğinize bir bakalım.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- **Kütüphaneler ve Bağımlılıklar**: Aspose.Slides for .NET'in yüklü olması gerekir. Bu kütüphane, C# dilinde PowerPoint sunumlarını düzenlemek için gereklidir.
  
- **Çevre Kurulumu**: .NET Core veya .NET Framework'ü çalıştıran bir geliştirme ortamı gereklidir.

- **Bilgi Önkoşulları**: Temel C# programlama kavramlarına aşinalık ve nesne yönelimli programlama prensiplerini anlamak faydalı olacaktır.

## Aspose.Slides'ı .NET için Ayarlama

Başlamak için Aspose.Slides kütüphanesini yüklemeniz gerekir. Bunu aşağıdaki yöntemlerden birini kullanarak yapabilirsiniz:

**.NET Komut Satırı Arayüzü**
```shell
dotnet add package Aspose.Slides
```

**Paket Yöneticisi**
```powershell
Install-Package Aspose.Slides
```

**NuGet Paket Yöneticisi Kullanıcı Arayüzü**
"Aspose.Slides"ı arayın ve en son sürümü yükleyin.

### Lisans Edinimi

Geçici bir lisans indirerek ücretsiz denemeye başlayabilirsiniz. [Burada](https://purchase.aspose.com/temporary-license/)Devam eden kullanım için, bir lisans satın almayı düşünün [bu bağlantı](https://purchase.aspose.com/buy).

Kurulumunuz hazır olduğunda projenizde Aspose.Slides'ı başlatın:

```csharp
using Aspose.Slides;
```

## Uygulama Kılavuzu

Artık kurulumu tamamladığımıza göre, şekil metni için dil ayarlama özelliğini uygulayalım.

### Özellik Genel Bakışı: Şekil Metin Dilini Ayarlama

Bu özellik, bir PowerPoint şekli içindeki metnin dilini belirtmenize olanak tanır. Dil kimliğini ayarlayarak, yazım denetiminin ve diğer dil-özel özelliklerinin doğru şekilde uygulanmasını sağlarsınız.

#### Adım 1: Sunumu Başlatın

Bir örnek oluşturarak başlayın `Presentation` sınıf.

```csharp
using (Presentation pres = new Presentation())
{
    // Kodunuz burada
}
```

Bu, üzerinde değişiklik yapacağımız yeni bir PowerPoint sunum nesnesini başlatır.

#### Adım 2: Otomatik Şekil ve Metin Çerçevesi Ekle

Slaydınıza bir dikdörtgen şekli ekleyin ve içine metin yerleştirin:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Burada, `AddAutoShape` ilk slayda bir dikdörtgen ekler. Parametreler konumunu ve boyutunu tanımlar.

#### Adım 3: Dil Kimliğini Ayarla

Şekil içindeki metin bölümünün dilini ayarlayın:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

Bu, yazım denetimi için dili İngilizce (İngiltere) olarak atar.

#### Adım 4: Sunumu Kaydedin

Son olarak sununuzu belirtilen yola kaydedin:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}