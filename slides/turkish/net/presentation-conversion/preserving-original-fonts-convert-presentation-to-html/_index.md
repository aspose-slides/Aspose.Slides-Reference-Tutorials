---
title: Orijinal Yazı Tiplerini Koruma - Sunumu HTML'ye Dönüştürme
linktitle: Orijinal Yazı Tiplerini Koruma - Sunumu HTML'ye Dönüştürme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak sunumları HTML'ye dönüştürürken orijinal yazı tiplerini nasıl koruyacağınızı öğrenin. Yazı tipi tutarlılığını ve görsel etkiyi zahmetsizce sağlayın.
weight: 14
url: /tr/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Bu kapsamlı kılavuzda, Aspose.Slides for .NET kullanarak bir sunumu HTML'ye dönüştürürken orijinal yazı tiplerini koruma sürecinde size yol göstereceğiz. Size gerekli C# kaynak kodunu sağlayacağız ve her adımı ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, dönüştürülmüş HTML belgenizdeki yazı tiplerinin orijinal sunuma sadık kalmasını sağlayabileceksiniz.

## 1. Giriş

PowerPoint sunumlarını HTML'ye dönüştürürken, içeriğinizin görsel tutarlılığını sağlamak için orijinal yazı tiplerini korumak çok önemlidir. Aspose.Slides for .NET bunu başarmak için güçlü bir çözüm sunuyor. Bu eğitimde, dönüştürme işlemi sırasında orijinal yazı tiplerini korumak için gereken adımlarda size yol göstereceğiz.

## 2. Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Makinenizde Visual Studio yüklü.
- Aspose.Slides for .NET kütüphanesi projenize eklendi.

## 3. Projenizi Kurma

Başlamak için Visual Studio'da yeni bir proje oluşturun ve Aspose.Slides for .NET kitaplığını referans olarak ekleyin.

## 4. Sunumun Yüklenmesi

PowerPoint sunumunuzu yüklemek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Kodunuz burada
}
```

 Yer değiştirmek`"Your Document Directory"` sunum dosyanızın yolu ile birlikte.

## 5. Varsayılan Yazı Tiplerini Hariç Tutmak

Calibri ve Arial gibi varsayılan yazı tiplerini hariç tutmak için aşağıdaki kodu kullanın:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Bu listeyi ihtiyacınıza göre özelleştirebilirsiniz.

## 6. Tüm Yazı Tiplerini Gömme

Daha sonra tüm yazı tiplerini HTML belgesine gömeceğiz. Bu, orijinal yazı tiplerinin korunmasını sağlar. Aşağıdaki kodu kullanın:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. HTML olarak kaydetme

Şimdi sunuyu gömülü yazı tipleriyle bir HTML belgesi olarak kaydedin:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 Yer değiştirmek`"output.html"` İstediğiniz çıktı dosyası adı ile.

## 8. Sonuç

Bu eğitimde, Aspose.Slides for .NET kullanarak bir PowerPoint sunumunu HTML'ye dönüştürürken orijinal yazı tiplerinin nasıl korunacağını gösterdik. Bu adımları izleyerek, dönüştürülen HTML belgenizin orijinal sunumun görsel bütünlüğünü korumasını sağlayabilirsiniz.

## 9. SSS

### S1: Hariç tutulan yazı tiplerinin listesini özelleştirebilir miyim?

 Evet yapabilirsin. Değiştirmek`fontNameExcludeList`Gereksinimlerinize göre belirli yazı tiplerini dahil etmek veya hariç tutmak için dizi.

### S2: Tüm yazı tiplerini gömmek istemezsem ne olur?

Yalnızca belirli yazı tiplerini gömmek istiyorsanız kodu buna göre değiştirebilirsiniz. Daha fazla ayrıntı için Aspose.Slides for .NET belgelerine bakın.

### S3: Aspose.Slides for .NET'i kullanmak için herhangi bir lisans gereksinimi var mı?

Evet, Aspose.Slides for .NET'i projelerinizde kullanmak için geçerli bir lisansa ihtiyacınız olabilir. Lisans bilgileri için Aspose web sitesine bakın.

### S4: Aspose.Slides for .NET'i kullanarak diğer dosya formatlarını HTML'ye dönüştürebilir miyim?

Aspose.Slides for .NET öncelikle PowerPoint sunumlarına odaklanır. Diğer dosya formatlarını HTML'ye dönüştürmek için bu formatlara uygun diğer Aspose ürünlerini keşfetmeniz gerekebilir.

### S5: Ek kaynaklara ve desteğe nereden erişebilirim?

 Aspose web sitesinde daha fazla belge, eğitim ve destek bulabilirsiniz. Ziyaret etmek[Aspose.Slides for .NET Belgeleri](https://reference.aspose.com/slides/net/) detaylı bilgi için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
