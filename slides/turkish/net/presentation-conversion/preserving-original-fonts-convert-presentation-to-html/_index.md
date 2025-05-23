---
"description": "Aspose.Slides for .NET kullanarak sunumları HTML'e dönüştürürken orijinal yazı tiplerini nasıl koruyacağınızı öğrenin. Yazı tipi tutarlılığını ve görsel etkiyi zahmetsizce sağlayın."
"linktitle": "Orijinal Yazı Tiplerini Koruma - Sunumu HTML'ye Dönüştürme"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Orijinal Yazı Tiplerini Koruma - Sunumu HTML'ye Dönüştürme"
"url": "/tr/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Orijinal Yazı Tiplerini Koruma - Sunumu HTML'ye Dönüştürme


Bu kapsamlı kılavuzda, Aspose.Slides for .NET kullanarak bir sunumu HTML'ye dönüştürürken orijinal yazı tiplerini koruma sürecinde size yol göstereceğiz. Size gerekli C# kaynak kodunu sağlayacağız ve her adımı ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, dönüştürülen HTML belgenizdeki yazı tiplerinin orijinal sunuma sadık kalmasını sağlayabileceksiniz.

## 1. Giriş

PowerPoint sunumlarını HTML'ye dönüştürürken, içeriğinizin görsel tutarlılığını sağlamak için orijinal yazı tiplerini korumak çok önemlidir. Aspose.Slides for .NET bunu başarmak için güçlü bir çözüm sunar. Bu eğitimde, dönüştürme işlemi sırasında orijinal yazı tiplerini korumak için gereken adımlarda size rehberlik edeceğiz.

## 2. Önkoşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Bilgisayarınızda Visual Studio yüklü.
- Aspose.Slides for .NET kütüphanesi projenize eklendi.

## 3. Projenizi Kurma

Başlamak için Visual Studio'da yeni bir proje oluşturun ve referans olarak Aspose.Slides for .NET kitaplığını ekleyin.

## 4. Sunumu Yükleme

PowerPoint sununuzu yüklemek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Kodunuz burada
}
```

Yer değiştirmek `"Your Document Directory"` sunum dosyanızın yolunu içeren.

## 5. Varsayılan Yazı Tiplerini Hariç Tutma

Calibri ve Arial gibi varsayılan yazı tiplerini hariç tutmak için aşağıdaki kodu kullanın:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Bu listeyi ihtiyacınıza göre özelleştirebilirsiniz.

## 6. Tüm Yazı Tiplerini Yerleştirme

Sonra, tüm fontları HTML belgesine gömeceğiz. Bu, orijinal fontların korunmasını sağlar. Aşağıdaki kodu kullanın:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. HTML olarak kaydetme

Şimdi sunumu gömülü yazı tipleriyle HTML belgesi olarak kaydedin:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

Yer değiştirmek `"output.html"` İstediğiniz çıktı dosya adı ile.

## 8. Sonuç

Bu eğitimde, Aspose.Slides for .NET kullanarak bir PowerPoint sunumunu HTML'ye dönüştürürken orijinal yazı tiplerinin nasıl korunacağını gösterdik. Bu adımları izleyerek, dönüştürülen HTML belgenizin orijinal sunumun görsel bütünlüğünü koruduğundan emin olabilirsiniz.

## 9. SSS

### S1: Hariç tutulan yazı tiplerinin listesini özelleştirebilir miyim?

Evet, yapabilirsiniz. Değiştirebilirsiniz. `fontNameExcludeList` İhtiyaçlarınıza göre belirli yazı tiplerini dahil etmek veya hariç tutmak için dizi.

### S2: Tüm yazı tiplerini gömmek istemiyorsam ne olur?

Yalnızca belirli yazı tiplerini gömmek istiyorsanız, kodu buna göre değiştirebilirsiniz. Daha fazla ayrıntı için Aspose.Slides for .NET belgelerine bakın.

### S3: Aspose.Slides for .NET'i kullanmak için herhangi bir lisanslama gereksinimi var mı?

Evet, projelerinizde Aspose.Slides for .NET'i kullanmak için geçerli bir lisansa ihtiyacınız olabilir. Lisanslama bilgileri için Aspose web sitesine bakın.

### S4: Aspose.Slides for .NET kullanarak diğer dosya formatlarını HTML'ye dönüştürebilir miyim?

Aspose.Slides for .NET öncelikli olarak PowerPoint sunumlarına odaklanır. Diğer dosya biçimlerini HTML'ye dönüştürmek için, bu biçimler için uyarlanmış diğer Aspose ürünlerini keşfetmeniz gerekebilir.

### S5: Ek kaynaklara ve desteğe nereden ulaşabilirim?

Daha fazla doküman, eğitim ve desteği Aspose web sitesinde bulabilirsiniz. Ziyaret edin [Aspose.Slides .NET Belgeleri için](https://reference.aspose.com/slides/net/) Detaylı bilgi için.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}