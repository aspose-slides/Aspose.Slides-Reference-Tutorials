---
"description": "Aspose.Slides for .NET kullanarak PowerPoint sunumlarınızı gömülü yazı tipleriyle HTML'ye dönüştürün. Özgünlüğünüzü sorunsuz bir şekilde koruyun."
"linktitle": "Sunumları Gömülü Yazı Tipleriyle HTML'ye Dönüştürün"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Sunumları Gömülü Yazı Tipleriyle HTML'ye Dönüştürün"
"url": "/tr/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Sunumları Gömülü Yazı Tipleriyle HTML'ye Dönüştürün


Günümüzün dijital çağında, sunumları ve belgeleri çevrimiçi paylaşmak yaygın bir uygulama haline geldi. Ancak, sıklıkla ortaya çıkan bir zorluk, sunumları HTML'ye dönüştürürken yazı tiplerinizin doğru şekilde görüntülendiğinden emin olmaktır. Bu adım adım eğitim, sunumları gömülü yazı tipleriyle HTML'ye dönüştürmek için Aspose.Slides for .NET'i kullanma sürecinde size rehberlik edecek ve belgelerinizin tam olarak istediğiniz gibi görünmesini sağlayacaktır.

## .NET için Aspose.Slides'a Giriş

Eğitime dalmadan önce, .NET için Aspose.Slides'ı kısaca tanıtalım. Geliştiricilerin .NET uygulamalarında PowerPoint sunumlarıyla çalışmasına olanak tanıyan güçlü bir kütüphanedir. Aspose.Slides ile PowerPoint dosyalarını programatik olarak oluşturabilir, değiştirebilir ve dönüştürebilirsiniz.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- .NET için Aspose.Slides: Projenizde Aspose.Slides kütüphanesi yüklü olmalıdır. Bunu şuradan indirebilirsiniz: [Burada](https://releases.aspose.com/slides/net/).

## Adım 1: Projenizi Kurun

1. Tercih ettiğiniz .NET geliştirme ortamında yeni bir proje oluşturun veya mevcut bir projeyi açın.

2. Projenize Aspose.Slides kütüphanesine bir referans ekleyin.

3. Gerekli ad alanlarını kodunuza aktarın:

   ```csharp
   using Aspose.Slides;
   ```

## Adım 2: Sununuzu Yükleyin

Başlamak için, HTML'ye dönüştürmek istediğiniz sunumu yüklemeniz gerekir. Değiştir `"Your Document Directory"` sunum dosyanızın bulunduğu gerçek dizinle.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Kodunuz buraya gelecek
}
```

## Adım 3: Varsayılan Sunum Yazı Tiplerini Hariç Tut

Bu adımda, yerleştirmeden hariç tutmak istediğiniz varsayılan sunum yazı tiplerini belirtebilirsiniz. Bu, ortaya çıkan HTML dosyasının boyutunu optimize etmeye yardımcı olabilir.

```csharp
string[] fontNameExcludeList = { };
```

## Adım 4: Bir HTML Denetleyicisi Seçin

Artık HTML'e fontları yerleştirmek için iki seçeneğiniz var:

### Seçenek 1: Tüm Yazı Tiplerini Göm

Sunumda kullanılan tüm yazı tiplerini yerleştirmek için şunu kullanın: `EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Seçenek 2: Tüm Yazı Tiplerini Bağla

Sunumda kullanılan tüm yazı tiplerine bağlantı vermek için şunu kullanın: `LinkAllFontsHtmlController`Fontların sisteminizde bulunduğu dizini belirtmelisiniz.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Adım 5: HTML Seçeneklerini Tanımlayın

Bir tane oluştur `HtmlOptions` nesnesini seçin ve HTML biçimlendiricisini önceki adımda seçtiğiniz biçimlendiriciye ayarlayın.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Tüm yazı tiplerini yerleştirmek için embedFontsController'ı kullanın
};
```

## Adım 6: HTML olarak kaydet

Son olarak, sunumu bir HTML dosyası olarak kaydedin. İkisinden birini seçebilirsiniz: `SaveFveyamat.Html` or `SaveFormat.Html5` İhtiyaçlarınıza bağlı olarak.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Çözüm

Tebrikler! Aspose.Slides for .NET kullanarak sununuzu gömülü yazı tipleriyle HTML'ye başarıyla dönüştürdünüz. Bu, sunumlarınızı çevrimiçi paylaşırken yazı tiplerinizin doğru şekilde görüntülenmesini sağlar.

Artık, güzelce biçimlendirilmiş sunumlarınızı, izleyicilerinizin bunları tam olarak istediğiniz gibi göreceğinden emin olarak güvenle paylaşabilirsiniz.

Daha fazla bilgi ve ayrıntılı API referansları için şuraya bakın: [Aspose.Slides for .NET belgeleri](https://reference.aspose.com/slides/net/).

## SSS

### 1. Aspose.Slides for .NET'i toplu modda kullanarak PowerPoint sunumlarını HTML'ye dönüştürebilir miyim?

Evet, Aspose.Slides for .NET'i kullanarak birden fazla sunumu toplu olarak HTML'ye dönüştürebilirsiniz; bunun için sunum dosyalarınız arasında döngü oluşturup dönüştürme işlemini her birine uygulayabilirsiniz.

### 2. HTML çıktısının görünümünü özelleştirmenin bir yolu var mı?

Elbette! Aspose.Slides for .NET, renkleri, yazı tiplerini ve düzeni ayarlamak gibi HTML çıktısının görünümünü ve biçimlendirmesini özelleştirmek için çeşitli seçenekler sunar.

### 3. Aspose.Slides for .NET kullanarak HTML'e font yerleştirme konusunda herhangi bir sınırlama var mı?

Aspose.Slides for .NET mükemmel font yerleştirme yetenekleri sunarken, fontları yerleştirirken HTML dosyalarınızın boyutunun artabileceğini unutmayın. Font seçimlerinizi web kullanımı için optimize ettiğinizden emin olun.

### 4. Aspose.Slides for .NET ile PowerPoint sunumlarımı başka formatlara dönüştürebilir miyim?

Evet, Aspose.Slides for .NET, PDF, resimler ve daha fazlası dahil olmak üzere çok çeşitli çıktı biçimlerini destekler. Sunumlarınızı kolayca istediğiniz biçime dönüştürebilirsiniz.

### 5. Aspose.Slides for .NET için ek kaynakları ve desteği nerede bulabilirim?

Belgeler de dahil olmak üzere çok sayıda kaynağa erişebilirsiniz. [Aspose.Slides for .NET API Referansı](https://reference.aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}