---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET kullanarak sunumları HTML'e dönüştürürken tutarlı yazı tipi oluşturmayı nasıl sağlayacağınızı öğrenin."
"title": "Aspose.Slides for .NET Kullanarak HTML'deki Fontları Nasıl Bağlarsınız? Adım Adım Kılavuz"
"url": "/tr/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET Kullanarak HTML'deki Fontları Nasıl Bağlarsınız

## giriiş

Platformlar arasında tutarlı yazı tipi oluşturmayı koruyarak sunumları HTML'e dönüştürmek zorlu olabilir. **.NET için Aspose.Slides** Bir sunumda kullanılan tüm fontları gömülü font dosyaları aracılığıyla doğrudan HTML çıktısına bağlamanıza olanak sağlayarak kesintisiz bir çözüm sunar.

Bu eğitimde, Aspose.Slides for .NET kullanarak yazı tipi bağlantısının nasıl uygulanacağını ve farklı platformlarda tasarım tutarlılığının nasıl sağlanacağını inceleyeceğiz. 

**Ne Öğreneceksiniz:**
- Aspose.Slides for .NET ile ortamınızı kurma
- HTML dönüşümünde yazı tiplerini bağlama
- Yazı tipi yerleştirme için özel denetleyiciler yazma
- Pratik uygulamalar ve performans değerlendirmeleri

Bunu başarmak için gerekli adımlara bir göz atalım.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler ve Bağımlılıklar
- **.NET için Aspose.Slides** kütüphane: Uygulamamızın temel bileşeni.

### Çevre Kurulum Gereksinimleri
- .NET Framework veya .NET Core yüklü bir geliştirme ortamı.

### Bilgi Önkoşulları
- C# programlamanın temel bilgisi.
- Özellikle HTML ve CSS konusunda bilgi sahibi olmak `@font-face` kural.

## Aspose.Slides'ı .NET için Ayarlama

.NET projenizde Aspose.Slides'ı kullanmak için kütüphaneyi yüklemeniz gerekir. İşte birkaç yöntem:

### .NET CLI'yi kullanma
```bash
dotnet add package Aspose.Slides
```

### Paket Yöneticisi Konsolunu Kullanma
```powershell
Install-Package Aspose.Slides
```

### NuGet Paket Yöneticisi Kullanıcı Arayüzü aracılığıyla
- Projenizi Visual Studio’da açın.
- "NuGet Paket Yöneticisi"ne gidin.
- "Aspose.Slides"ı arayın ve en son sürümü yükleyin.

### Lisans Edinme Adımları
Aşağıdaki adımları izleyerek tüm özellikleri sınırlama olmaksızın test etmek için ücretsiz deneme lisansı alabilirsiniz:
1. **Ücretsiz Deneme**: Geçici bir lisans indirin [Burada](https://releases.aspose.com/slides/net/).
2. **Geçici Lisans**: Genişletilmiş erişim için başvuruda bulunun [Burada](https://purchase.aspose.com/temporary-license/).
3. **Satın almak**: Tam işlevsellik için bir lisans satın alın [Burada](https://purchase.aspose.com/buy).

### Temel Başlatma ve Kurulum
```csharp
// Lisans sınıfının bir örneğini oluşturun
easpose.slides.License license = new aspose.slides.License();

// Lisansı dosya yolundan uygulayın
license.SetLicense("Aspose.Slides.lic");
```

## Uygulama Kılavuzu

Şimdi, HTML dönüşümünde yazı tipi bağlantısını kullanarak uygulayalım **.NET için Aspose.Slides**.

### Özellik Genel Bakışı: HTML Dönüştürmesinde Yazı Tiplerini Bağlama
Bu özellik, bir sunumda kullanılan tüm yazı tiplerinin, yazı tipi dosyalarını gömerek doğrudan sonuç HTML dosyasına bağlanmasını sağlar. Bu yöntem, farklı tarayıcılar ve platformlar arasında tasarım tutarlılığını korumak için sağlam bir çözüm sunar.

#### Adım 1: Özel Denetleyiciyi Oluşturun
Özel bir denetleyici sınıfı oluşturun `LinkAllFontsHtmlController` hangisinden miras alır `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // Yazı tipi dosyalarının saklanacağı dizini ayarlayın
    }
}
```
#### Adım 2: Yazı Tipi Yazma Yöntemini Uygulayın
The `WriteFont` yöntem yazı tipi verilerini bir dosyaya yazar ve yerleştirme için karşılık gelen HTML kodunu üretir:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // Kullanılacak font adını belirleyin, mümkünse ikame fontları tercih edin.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // .woff yazı tipi dosyası için bir dosya yolu oluşturun.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // Yazı tipi verilerini belirtilen dosya yoluna yaz.
    File.WriteAllBytes(path, fontData);

    // @font-face kuralını kullanarak yazı tipini gömen HTML stil bloğu oluşturun.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}