---
title: Medya Dosyalarını Sunumdan HTML'ye Aktarma
linktitle: Medya Dosyalarını Sunumdan HTML'ye Aktarma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET ile sunum paylaşımınızı optimize edin! Bu adım adım kılavuzda sunumunuzdaki medya dosyalarını HTML'ye nasıl aktaracağınızı öğrenin.
weight: 15
url: /tr/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Bu eğitimde, Aspose.Slides for .NET kullanarak medya dosyalarını bir sunumdan HTML'ye aktarma sürecinde size yol göstereceğiz. Aspose.Slides, PowerPoint sunumlarıyla programlı olarak çalışmanıza olanak tanıyan güçlü bir API'dir. Bu kılavuzun sonunda sunumlarınızı kolaylıkla HTML formatına dönüştürebileceksiniz. Öyleyse başlayalım!

## 1. Giriş

PowerPoint sunumları genellikle videolar gibi multimedya öğeleri içerir ve web uyumluluğu için bu sunumları HTML formatına aktarmanız gerekebilir. Aspose.Slides for .NET bu görevi programlı olarak gerçekleştirmenin kolay bir yolunu sunar.

## 2. Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

-  Aspose.Slides for .NET: Aspose.Slides for .NET kütüphanesinin kurulu olması gerekir. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## 3. Sunum Yükleme

Başlamak için HTML'ye dönüştürmek istediğiniz PowerPoint sunumunu yüklemeniz gerekir. Ayrıca HTML dosyasının kaydedileceği çıktı dizinini de belirtmeniz gerekecektir. İşte bir sunumu yükleme kodu:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// Sunum yükleniyor
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // Kodunuz burada
}
```

## 4. HTML Seçeneklerini Ayarlama

Şimdi dönüşüm için HTML seçeneklerini ayarlayalım. Bir HTML denetleyicisi, HTML biçimlendiricisi ve slayt görüntü biçimini yapılandıracağız. Bu kod, HTML dosyanızın multimedya öğelerini görüntülemek için gerekli bileşenleri içermesini sağlayacaktır.

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.example.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// HTML seçeneklerini ayarlama
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. HTML Dosyasını Kaydetme

 HTML seçenekleri yapılandırıldığında artık HTML dosyasını kaydedebilirsiniz.`Save` Sunum nesnesinin yöntemi, gömülü multimedya öğeleri içeren HTML dosyasını oluşturacaktır.

```csharp
// Dosyayı kaydetme
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Sonuç

Tebrikler! Aspose.Slides for .NET'i kullanarak medya dosyalarını PowerPoint sunumundan başarıyla HTML'ye aktardınız. Bu, sunumlarınızı çevrimiçi olarak kolaylıkla paylaşmanıza ve multimedya öğelerinin düzgün şekilde görüntülendiğinden emin olmanıza olanak tanır.

## 7. SSS

### S1: Aspose.Slides for .NET ücretsiz bir kütüphane midir?
 Cevap1: Aspose.Slides for .NET ticari bir kütüphanedir ancak şu adresten ücretsiz deneme sürümü edinebilirsiniz:[Burada](https://releases.aspose.com/) denemek için.

### S2: HTML çıktısını daha da özelleştirebilir miyim?
Cevap2: Evet, koddaki HTML seçeneklerini değiştirerek HTML çıktısını özelleştirebilirsiniz.

### S3: Aspose.Slides for .NET diğer dışa aktarma formatlarını destekliyor mu?
Cevap3: Evet, Aspose.Slides for .NET, PDF, görüntü formatları ve daha fazlası dahil olmak üzere çeşitli dışa aktarma formatlarını destekler.

### S4: Aspose.Slides for .NET desteğini nereden alabilirim?
 Cevap4: Aspose forumlarında destek bulabilir ve soru sorabilirsiniz[Burada](https://forum.aspose.com/).

### S5: Aspose.Slides for .NET lisansını nasıl satın alabilirim?
 Cevap5: Şu adresten lisans satın alabilirsiniz:[bu bağlantı](https://purchase.aspose.com/buy).

Artık bu eğitimi tamamladığınıza göre, Aspose.Slides for .NET kullanarak medya dosyalarını PowerPoint sunumlarından HTML'ye aktarma becerisine sahipsiniz. Multimedya açısından zengin sunumlarınızı çevrimiçi paylaşmanın tadını çıkarın!
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
