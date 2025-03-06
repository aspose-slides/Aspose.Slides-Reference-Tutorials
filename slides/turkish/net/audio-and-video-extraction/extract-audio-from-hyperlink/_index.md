---
title: Aspose.Slides ile PowerPoint Köprülerinden Sesi Çıkarma
linktitle: Köprüden Sesi Çıkar
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint sunumlarındaki köprülerden ses çıkarın. Multimedya projelerinizi zahmetsizce geliştirin.
weight: 12
url: /tr/net/audio-and-video-extraction/extract-audio-from-hyperlink/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Multimedya sunumları dünyasında ses, slaytlarınızın genel etkisini artırmada hayati bir rol oynar. Hiç ses köprüleri içeren bir PowerPoint sunumuyla karşılaştınız mı ve sesi diğer kullanımlar için nasıl çıkaracağınızı merak ettiniz mi? Aspose.Slides for .NET ile bu görevi zahmetsizce başarabilirsiniz. Bu adım adım kılavuzda, bir PowerPoint sunumundaki köprüden ses çıkarma sürecinde size yol göstereceğiz.

## Önkoşullar

Çıkarma işlemine geçmeden önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

### 1. Aspose.Slides for .NET Kitaplığı

Aspose.Slides for .NET kütüphanesinin geliştirme ortamınızda kurulu olması gerekir. Henüz yapmadıysanız, adresindeki web sitesinden indirebilirsiniz.[Aspose.Slides for .NET Belgeleri](https://reference.aspose.com/slides/net/).

### 2. Sesli Köprülerle PowerPoint Sunumu

İlgili ses ile köprüler içeren bir PowerPoint sunumunuz (PPTX) olduğundan emin olun. Bu, sesi çıkaracağınız kaynak olacaktır.

## Ad Alanlarını İçe Aktarma

Aspose.Slides for .NET'i etkili bir şekilde kullanmak için öncelikle C# projenize gerekli ad alanlarını içe aktaralım. Bu ad alanları, PowerPoint sunumlarıyla çalışmak ve köprülerden ses çıkarmak için gereklidir.

```csharp
using System;
using System.IO;
using Aspose.Slides;
```

Artık ön koşullarımızı yerine getirdiğimize ve gerekli ad alanlarını içe aktardığımıza göre, çıkarma sürecini birden çok adıma ayıralım.

## Adım 1: Belge Dizinini Tanımlayın

 PowerPoint sunumunuzun bulunduğu dizini belirterek başlayın. Değiştirebilirsin`"Your Document Directory"` belge dizininizin gerçek yolu ile.

```csharp
string dataDir = "Your Document Directory";
```

## Adım 2: PowerPoint Sunumunu Yükleyin

 Aspose.Slides'ı kullanarak ses bağlantısını içeren PowerPoint sunumunu (PPTX) yükleyin. Yer değiştirmek`"HyperlinkSound.pptx"`sununuzun gerçek dosya adıyla.

```csharp
string pptxFile = Path.Combine(dataDir, "HyperlinkSound.pptx");

using (Presentation pres = new Presentation(pptxFile))
{
    // Sonraki adıma devam et.
}
```

## 3. Adım: Köprü Sesini Alın

PowerPoint slaytından ilk şeklin köprüsünü alın. Köprünün ilişkili bir sesi varsa, onu çıkarmaya devam edeceğiz.

```csharp
IHyperlink link = pres.Slides[0].Shapes[0].HyperlinkClick;

if (link.Sound != null)
{
    // Sonraki adıma devam et.
}
```

## Adım 4: Sesi Köprüden Çıkarın

Köprünün ilişkili bir sesi varsa, onu bir bayt dizisi olarak çıkarabilir ve bir medya dosyası olarak kaydedebiliriz.

```csharp
// Bayt dizisindeki köprü sesini çıkarır
byte[] audioData = link.Sound.BinaryData;

// Çıkarılan sesi kaydetmek istediğiniz yolu belirtin
string outMediaPath = Path.Combine(dataDir, "HyperlinkSound.mpg");

// Çıkarılan sesi bir medya dosyasına kaydedin
File.WriteAllBytes(outMediaPath, audioData);
```

Tebrikler! Aspose.Slides for .NET'i kullanarak PowerPoint sunumundaki bir köprüden sesi başarıyla çıkardınız. Çıkarılan bu ses artık multimedya projelerinizde başka amaçlar için kullanılabilir.

## Çözüm

Aspose.Slides for .NET, PowerPoint sunumlarındaki köprülerden ses çıkarmak için güçlü ve kullanıcı dostu bir çözüm sunar. Bu kılavuzda özetlenen adımlarla sunumlarınızdaki ses içeriğini yeniden kullanarak multimedya projelerinizi zahmetsizce geliştirebilirsiniz.

### Sıkça Sorulan Sorular (SSS)

### Aspose.Slides for .NET ücretsiz bir kütüphane midir?
 Hayır, Aspose.Slides for .NET ticari bir kütüphanedir ancak özelliklerini ve belgelerini aşağıdaki adresten ücretsiz deneme sürümünü indirerek keşfedebilirsiniz.[Burada](https://releases.aspose.com/).

### PPT gibi eski PowerPoint formatlarındaki köprülerden ses çıkarabilir miyim?
Evet, Aspose.Slides for .NET, köprülerden ses çıkarmak için hem PPTX hem de PPT formatlarını destekler.

### Aspose.Slides desteği için bir topluluk forumu var mı?
 Evet, Aspose.Slides ile ilgili yardım alabilir ve deneyimlerinizi paylaşabilirsiniz.[Aspose.Slides topluluk forumu](https://forum.aspose.com/).

### Kısa süreli bir proje için Aspose.Slides'ın geçici lisansını satın alabilir miyim?
Evet, kısa vadeli proje ihtiyaçlarınızı karşılamak için Aspose.Slides for .NET için geçici bir lisans alabilirsiniz.[bu bağlantı](https://purchase.aspose.com/temporary-license/).

### MPG dışında, çıkarma için desteklenen başka ses formatları var mı?
Aspose.Slides for .NET, MPG ile sınırlı olmamak üzere çeşitli formatlarda ses çıkarmanıza olanak tanır. Çıkarma işleminden sonra tercih ettiğiniz formata dönüştürebilirsiniz.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
