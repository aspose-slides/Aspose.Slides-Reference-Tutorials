---
title: Gömülü Resimlerle HTML Sunumunu Dönüştürün
linktitle: Gömülü Resimlerle HTML Sunumunu Dönüştürün
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak HTML sunumlarını gömülü görsellerle zahmetsizce dönüştürün. PowerPoint dosyalarını sorunsuz bir şekilde oluşturun, özelleştirin ve kaydedin.
type: docs
weight: 11
url: /tr/net/presentation-conversion/convert-html-presentation-with-embedded-images/
---

## 1. Giriş

Aspose.Slides for .NET, gömülü görüntüleri korurken PowerPoint sunumlarını HTML5 formatına dönüştürmenin kullanışlı bir yolunu sunar. Bu, sunumlarınızı web sitelerinde veya web uygulamalarında görüntülemek için inanılmaz derecede yararlı olabilir.

## 2. Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio veya herhangi bir C# geliştirme ortamı.
- Aspose.Slides for .NET kitaplığı.
- Gömülü görseller içeren örnek bir PowerPoint sunumu.
- Temel C# programlama bilgisi.

## 3. Projenizi Kurma

Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturarak başlayın. Projenizde Aspose.Slides for .NET kitaplığına doğru şekilde başvurulduğundan emin olun.

## 4. Kaynak Sunumunu Yükleme

```csharp
string dataDir = "Your Document Directory";
string presentationName = Path.Combine(dataDir, "PresentationDemo.pptx");

using (Presentation pres = new Presentation(presentationName))
{
    // Sunuyu işlemeye yönelik kodunuz buraya gelecek
}
```

## 5. HTML Dönüştürme Seçeneklerini Yapılandırma

 HTML dönüştürme seçeneklerini yapılandırmak için`Html5Options` sınıf. Bazı seçeneklerin nasıl ayarlanacağına dair bir örnek:

```csharp
Html5Options options = new Html5Options()
{
    EmbedImages = false, // Görüntüleri HTML5 belgesine kaydetmeyin
    OutputPath = "Your Output Directory" // Harici görüntülerin yolunu ayarlayın
};
```

## 6. Çıkış Dizini Oluşturma

Sunuyu HTML5 formatında kaydetmeden önce, eğer mevcut değilse çıktı dizinini oluşturmak iyi bir uygulamadır:

```csharp
string outFilePath = Path.Combine(outPath, "HTMLConversion");

if (!Directory.Exists(outFilePath))
{
    Directory.CreateDirectory(outFilePath);
}
```

## 7. Sunumu HTML5 Formatında Kaydetmek

Şimdi sunuyu HTML5 formatında kaydedelim:

```csharp
pres.Save(Path.Combine(outFilePath, "pres.html"), SaveFormat.Html5, options);
```

## 8. Sonuç

Tebrikler! Gömülü görseller içeren bir PowerPoint sunumunu Aspose.Slides for .NET'i kullanarak başarıyla HTML5 formatına dönüştürdünüz. Bu, sunumlarınızı çevrimiçi paylaşmak için değerli bir araç olabilir.

## 9. SSS

**Q1: Can I customize the appearance of the HTML5 presentation?**
Evet, Aspose.Slides tarafından oluşturulan HTML ve CSS dosyalarını değiştirerek görünümü özelleştirebilirsiniz.

**Q2: Does Aspose.Slides for .NET support other output formats?**
Evet, PDF, resimler ve daha fazlası dahil olmak üzere çeşitli çıktı formatlarını destekler.

**Q3: Are there any limitations to converting presentations with embedded images?**
Aspose.Slides for .NET güçlü olsa da, oldukça karmaşık sunumlarda bazı sınırlamalarla karşılaşabilirsiniz.

**Q4: Is Aspose.Slides for .NET compatible with the latest PowerPoint versions?**
Evet, en son sürümler de dahil olmak üzere farklı sürümlerdeki PowerPoint dosyalarıyla uyumludur.

**Q5: Where can I find more documentation and resources for Aspose.Slides for .NET?**
 Kapsamlı belgeler ve kaynaklar için şu adresi ziyaret edin:[Aspose.Slides for .NET belgeleri](https://reference.aspose.com/slides/net/).