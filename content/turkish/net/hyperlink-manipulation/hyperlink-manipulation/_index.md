---
title: Aspose.Slides'ta Hyperlink Manipülasyonu
linktitle: Aspose.Slides'ta Hyperlink Manipülasyonu
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak PowerPoint sunumlarını köprülerle nasıl geliştireceğinizi öğrenin. Etkileşimli içeriği sorunsuz bir şekilde oluşturun, değiştirin ve yönetin.
type: docs
weight: 10
url: /tr/net/hyperlink-manipulation/hyperlink-manipulation/
---

## Köprü Manipülasyonuna Giriş

Köprüler slaytları, belgeleri, web sayfalarını ve daha fazlasını birbirine bağlayarak sunumları zenginleştirir. İzleyicinin katılımını artıran etkileşimli bir deneyim sağlarlar. Aspose.Slides for .NET, köprüleri programlı olarak yönetmek için kapsamlı işlevsellik sunarak sunumunuzun navigasyonu üzerinde tam kontrol sahibi olmanızı sağlar.

## Slaytlarda Köprüleri Ayarlama

 Köprüler oluşturmak için Aspose.Slides for .NET'i kullanabilirsiniz.`HyperlinkManager` sınıf. Bu sınıf, slaytlarınızdaki belirli şekillere veya metinlere çeşitli türlerde köprüler eklemenize olanak tanır.

```csharp
// Bir şekle köprü eklemek için kod örneği
HyperlinkManager.AddHyperlinkToShape(shape, "https://www.example.com", "Web sitemizi ziyaret edin");
```

## Köprüleri Değiştirme

Aspose.Slides for .NET'i kullanarak mevcut köprüleri kolayca değiştirebilirsiniz. Bu, hedef URL'yi güncellemeniz veya köprünün metnini değiştirmeniz gerektiğinde kullanışlıdır.

```csharp
// Köprünün URL'sini değiştirmek için kod örneği
HyperlinkManager.ModifyHyperlinkUrl(shape, "https://yeniurl.com");
```

## Köprüleri Kaldırma

Bir şekilden bir köprüyü kaldırmak istiyorsanız Aspose.Slides for .NET bunu yapmak için basit bir yöntem sunar.

```csharp
// Bir şekilden köprüyü kaldırmak için kod örneği
HyperlinkManager.RemoveHyperlink(shape);
```

## Bağlantı Noktalarıyla Çalışmak

Slaytlardaki köprülerle uğraşırken bağlantı noktaları çok önemlidir. Hedef slaytta köprünün işaret ettiği konumu belirlerler.

```csharp
// Köprü için bağlantı noktası ayarlamaya yönelik kod örneği
HyperlinkManager.SetHyperlinkAnchor(shape, targetSlide, anchorX, anchorY);
```

## Farklı Köprü Türlerini Kullanma

Aspose.Slides for .NET, URL bağlantıları, dahili belge bağlantıları, e-posta adreslerine bağlantılar ve daha fazlası dahil olmak üzere çeşitli köprü türlerini destekler.

```csharp
// E-posta köprüsü eklemek için kod örneği
HyperlinkManager.AddEmailHyperlink(shape, "support@example.com", "Contact Support");
```

## Köprülere Araç İpuçları Ekleme

Araç ipuçları, kullanıcılar köprülerin üzerine geldiğinde ek bilgiler sağlar. Aspose.Slides for .NET, köprüleriniz için araç ipuçlarını ayarlamanıza olanak tanır.

```csharp
// Köprüye araç ipucu eklemek için kod örneği
HyperlinkManager.AddHyperlinkWithTooltip(shape, "https://www.example.com", "Web sitemizi ziyaret edin", "Keşfetmek için tıklayın");
```

## Dış Köprüleri Yönetme

Ayrıca Aspose.Slides for .NET'i kullanarak harici köprüleri yönetebilir, sunumlarınızın ilgili çevrimiçi kaynaklara bağlı kalmasını sağlayabilirsiniz.

```csharp
// Bir web tarayıcısında köprü açmak için kod örneği
HyperlinkManager.OpenHyperlinkInBrowser(shape);
```

## Ana Slaytlardaki Köprüler

Ana slaytlar genellikle yinelenen öğeler içerir. Aspose.Slides for .NET, ana slaytlara köprüler uygulamanıza olanak tanıyarak sunumunuz genelinde tutarlılık sağlar.

```csharp
// Ana slaytta köprü ayarlamak için kod örneği
HyperlinkManager.SetHyperlinkInMasterSlide(masterSlide, "https://www.example.com", "Web sitemizi ziyaret edin");
```

## Köprü Bilgilerini Çıkarma

Aspose.Slides for .NET'i kullanarak mevcut köprülerden bilgi çıkarabilirsiniz; bu, analiz veya raporlama amacıyla yararlı olabilir.

```csharp
// Köprü bilgilerini ayıklamak için kod örneği
HyperlinkManager.ExtractHyperlinkInfo(shape, out string linkUrl, out string linkText);
```

## Görüntülere ve Şekillere Köprüler Ekleme

Köprüler yalnızca metne değil aynı zamanda slaytlarınızdaki resimlere ve şekillere de eklenebilir.

```csharp
// Bir resme köprü eklemek için kod örneği
HyperlinkManager.AddHyperlinkToImage(imageShape, "https://www.example.com", "Daha fazla bilgi edinmek için resme tıklayın");
```

## E-posta Adreslerine ve Telefon Numaralarına Bağlantı Verme

Aspose.Slides for .NET, tıklandığında e-posta oluşturmayı tetikleyen veya telefon çağrıları başlatan köprüler oluşturmanıza olanak tanır.

```csharp
// E-posta köprüsü oluşturmak için kod örneği
HyperlinkManager.AddEmailHyperlink(shape, "support@example.com", "Contact Support");

// Telefon numarası köprüsü oluşturmak için kod örneği
HyperlinkManager.AddPhoneHyperlink(shape, "+1234567890", "Call our support");
```

## Köprü Biçimlendirmesi

Köprüleri normal metin veya şekillerden görsel olarak farklı kılmak için bunlara biçimlendirme uygulayabilirsiniz.

```csharp
// Köprünün görünümünü biçimlendirmek için kod örneği
HyperlinkManager.FormatHyperlink(shape, HyperlinkFormat.Highlighted);
```

## API aracılığıyla Köprüler Ekleme

Aspose.Slides for .NET, köprü manipülasyonu için güçlü bir API sağlar. Bu özellikleri uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.

```csharp
// API aracılığıyla köprü eklemek için kod örneği
HyperlinkManager.AddHyperlink(shape, HyperlinkType.Url, "https://www.example.com");
```

## Çözüm

Aspose.Slides for .NET kullanarak köprü manipülasyonu, PowerPoint sunumlarınızın etkileşimini ve etkileşimini geliştirmek için kapsamlı bir araç seti sunar. Köprü oluşturma, değiştirme ve yönetme yeteneği sayesinde izleyicilerinizi büyüleyen dinamik ve bilgilendirici slayt gösterileri oluşturabilirsiniz.

## SSS'ler

### Bir şekildeki köprüyü nasıl kaldırabilirim?

Bir şekilden köprüyü kaldırmak için aşağıdaki kodu kullanabilirsiniz:

```csharp
HyperlinkManager.RemoveHyperlink(shape);
```

### Slaytlarımdaki resimlere köprüler uygulayabilir miyim?

Evet, Aspose.Slides for .NET'i kullanarak slaytlarınızdaki görsellere ve şekillere köprüler ekleyebilirsiniz. Örneğin:

```csharp
HyperlinkManager.AddHyperlinkToImage(imageShape, "https://www.example.com", "Daha fazla bilgi edinmek için resme tıklayın");
```

### Bir köprünün görünümünü biçimlendirmek mümkün mü?

Kesinlikle! Aspose.Slides for .NET'i kullanarak bir köprünün görünümünü biçimlendirebilirsiniz. İşte bir örnek:

```csharp
HyperlinkManager.FormatHyperlink(shape, HyperlinkFormat.Highlighted);
```

### Mevcut bir köprüden nasıl bilgi çıkarabilirim?

Aşağıdaki yaklaşımı kullanarak mevcut bir köprüden bilgi çıkarabilirsiniz:

```csharp
HyperlinkManager.ExtractHyperlinkInfo(shape, out string linkUrl, out string linkText);
```

### Aspose.Slides for .NET hakkında daha ayrıntılı belgelere nereden ulaşabilirim?

Daha detaylı bilgi ve kod örnekleri için bkz.[dokümantasyon](https://reference.aspose.com/slides/net/) Aspose.Slides for .NET için.