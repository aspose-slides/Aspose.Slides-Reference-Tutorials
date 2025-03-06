---
title: Sunumları Gömülü Yazı Tipleriyle HTML'ye Dönüştürün
linktitle: Sunumları Gömülü Yazı Tipleriyle HTML'ye Dönüştürün
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint sunumlarını yerleşik yazı tipleriyle HTML'ye dönüştürün. Orijinalliği sorunsuz bir şekilde koruyun.
weight: 13
url: /tr/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sunumları Gömülü Yazı Tipleriyle HTML'ye Dönüştürün


Günümüzün dijital çağında sunum ve dokümanların çevrimiçi olarak paylaşılması yaygın bir uygulama haline geldi. Ancak sıklıkla karşılaşılan zorluklardan biri, sunumları HTML'ye dönüştürürken yazı tiplerinizin doğru şekilde görüntülenmesini sağlamaktır. Bu adım adım eğitim, Aspose.Slides for .NET'i kullanarak sunumları gömülü yazı tipleriyle HTML'ye dönüştürme sürecinde size rehberlik edecek ve belgelerinizin tam istediğiniz gibi görünmesini sağlayacaktır.

## Aspose.Slides for .NET'e Giriş

Eğitime dalmadan önce Aspose.Slides for .NET'i kısaca tanıtalım. Geliştiricilerin .NET uygulamalarında PowerPoint sunumlarıyla çalışmasına olanak tanıyan güçlü bir kitaplıktır. Aspose.Slides ile PowerPoint dosyalarını programlı olarak oluşturabilir, değiştirebilir ve dönüştürebilirsiniz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

-  Aspose.Slides for .NET: Projenizde Aspose.Slides kütüphanesinin kurulu olması gerekir. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## 1. Adım: Projenizi Kurun

1. Tercih ettiğiniz .NET geliştirme ortamında yeni bir proje oluşturun veya mevcut bir projeyi açın.

2. Projenize Aspose.Slides kütüphanesine bir referans ekleyin.

3. Gerekli ad alanlarını kodunuza aktarın:

   ```csharp
   using Aspose.Slides;
   ```

## 2. Adım: Sunumunuzu Yükleyin

 Başlamak için HTML'ye dönüştürmek istediğiniz sunumu yüklemeniz gerekir. Yer değiştirmek`"Your Document Directory"` sunum dosyanızın bulunduğu gerçek dizinle.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Kodunuz buraya gelecek
}
```

## 3. Adım: Varsayılan Sunum Yazı Tiplerini Hariç Tut

Bu adımda, yerleştirmenin dışında bırakmak istediğiniz varsayılan sunum yazı tiplerini belirtebilirsiniz. Bu, ortaya çıkan HTML dosyasının boyutunun optimize edilmesine yardımcı olabilir.

```csharp
string[] fontNameExcludeList = { };
```

## Adım 4: Bir HTML Denetleyicisi seçin

Artık yazı tiplerini HTML'ye gömmek için iki seçeneğiniz var:

### 1. Seçenek: Tüm Yazı Tiplerini Göm

 Sunuda kullanılan tüm yazı tiplerini gömmek için`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Seçenek 2: Tüm Yazı Tiplerini Bağla

 Sunumda kullanılan tüm yazı tiplerine bağlantı vermek için`LinkAllFontsHtmlController`. Sisteminizde fontların bulunduğu dizini belirtmelisiniz.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Adım 5: HTML Seçeneklerini Tanımlayın

 Oluşturduğunuz bir`HtmlOptions` nesnesini seçin ve HTML biçimlendiriciyi önceki adımda seçtiğiniz biçime ayarlayın.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Tüm yazı tiplerini gömmek için embedFontsController'ı kullanın
};
```

## Adım 6: HTML olarak kaydedin

 Son olarak sunuyu HTML dosyası olarak kaydedin. İkisinden birini seçebilirsiniz`SaveFormat.Html` veya`SaveFormat.Html5` gereksinimlerinize bağlı olarak.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Çözüm

Tebrikler! Aspose.Slides for .NET'i kullanarak sunumunuzu gömülü yazı tipleriyle başarıyla HTML'ye dönüştürdünüz. Bu, sunumlarınızı çevrimiçi paylaşırken yazı tiplerinizin doğru şekilde görüntülenmesini sağlar.

Artık güzel biçimlendirilmiş sunumlarınızı güvenle, izleyicilerinizin onları tam olarak istediğiniz gibi göreceğini bilerek kolayca paylaşabilirsiniz.

 Daha fazla bilgi ve ayrıntılı API referansları için şu adrese göz atın:[Aspose.Slides for .NET belgeleri](https://reference.aspose.com/slides/net/).

## SSS

### 1. Aspose.Slides for .NET'i toplu modda kullanarak PowerPoint sunumlarını HTML'ye dönüştürebilir miyim?

Evet, Aspose.Slides for .NET'i kullanarak sunum dosyalarınız arasında dolaşıp dönüştürme işlemini her birine uygulayarak birden fazla sunumu toplu olarak HTML'ye dönüştürebilirsiniz.

### 2. HTML çıktısının görünümünü özelleştirmenin bir yolu var mı?

Kesinlikle! Aspose.Slides for .NET, HTML çıktısının görünümünü ve formatını özelleştirmek için renkleri, yazı tiplerini ve düzeni ayarlamak gibi çeşitli seçenekler sunar.

### 3. Aspose.Slides for .NET kullanarak HTML'ye yazı tipi yerleştirme konusunda herhangi bir sınırlama var mı?

Aspose.Slides for .NET mükemmel yazı tipi yerleştirme yetenekleri sunsa da, yazı tiplerini gömerken HTML dosyalarınızın boyutunun artabileceğini unutmayın. Yazı tipi seçimlerinizi web kullanımı için optimize ettiğinizden emin olun.

### 4. Aspose.Slides for .NET ile PowerPoint sunumlarını diğer formatlara dönüştürebilir miyim?

Evet, Aspose.Slides for .NET, PDF, görseller ve daha fazlasını içeren çok çeşitli çıktı formatlarını destekler. Sunumlarınızı dilediğiniz formata kolaylıkla dönüştürebilirsiniz.

### 5. Aspose.Slides for .NET için ek kaynakları ve desteği nerede bulabilirim?

 Belgeler de dahil olmak üzere çok sayıda kaynağa şu adresten erişebilirsiniz:[Aspose.Slides for .NET API Referansı](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
