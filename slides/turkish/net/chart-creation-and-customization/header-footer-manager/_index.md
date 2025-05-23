---
"description": "Aspose.Slides for .NET kullanarak PowerPoint sunumlarına dinamik üstbilgi ve altbilgilerin nasıl ekleneceğini öğrenin."
"linktitle": "Slaytlarda Üst Bilgi ve Alt Bilgiyi Yönetin"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Slaytlarda Üst Bilgi ve Alt Bilgiyi Yönetin"
"url": "/tr/net/chart-creation-and-customization/header-footer-manager/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Slaytlarda Üst Bilgi ve Alt Bilgiyi Yönetin


# Aspose.Slides for .NET'te Dinamik Başlıklar ve Altbilgiler Oluşturma

Dinamik sunumlar dünyasında, Aspose.Slides for .NET güvenilir müttefikinizdir. Bu güçlü kütüphane, bir miktar etkileşimle ilgi çekici PowerPoint sunumları hazırlamanıza olanak tanır. Önemli bir özellik, slaytlarınıza hayat verebilecek dinamik başlıklar ve altbilgiler ekleme yeteneğidir. Bu adım adım kılavuzda, Aspose.Slides for .NET'i sununuza bu dinamik öğeleri eklemek için nasıl kullanacağınızı keşfedeceğiz. Hadi başlayalım!

## Ön koşullar

Başlamadan önce birkaç şeyin hazır olması gerekir:

1. Aspose.Slides for .NET: Aspose.Slides for .NET'i yüklemiş olmanız gerekir. Eğer henüz yüklemediyseniz, kütüphaneyi bulabilirsiniz [Burada](https://releases.aspose.com/slides/net/).

2. Belgeniz: Üzerinde çalışmak istediğiniz PowerPoint sunumunun yerel dizininize kaydedilmiş olması gerekir. Bu belgenin yolunu bildiğinizden emin olun.

## Ad Alanlarını İçe Aktar

Başlamak için, gerekli ad alanlarını projenize içe aktarmanız gerekir. Bu ad alanları, Aspose.Slides ile çalışmak için gereken araçları sağlar.

### Adım 1: Ad Alanlarını İçe Aktarın

C# projenizde, kod dosyanızın en üstüne aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

## Dinamik Başlıklar ve Altbilgiler Ekleme

Şimdi, PowerPoint sununuza dinamik üstbilgi ve altbilgi ekleme sürecini adım adım inceleyelim.

### Adım 2: Sununuzu Yükleyin

Bu adımda PowerPoint sunumunuzu C# projenize yüklemeniz gerekiyor.

```csharp
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "presentation.ppt"))
{
    // Başlık ve altbilgi yönetimi için kodunuz buraya gelecek.
    // ...
}
```

### Adım 3: Başlık ve Altbilgi Yöneticisine Erişim

.NET için Aspose.Slides, başlıkları ve altbilgileri yönetmek için kullanışlı bir yol sağlar. Sununuzdaki ilk slayt için başlık ve altbilgi yöneticisine erişiriz.

```csharp
IBaseSlideHeaderFooterManager headerFooterManager = presentation.Slides[0].HeaderFooterManager;
```

### Adım 4: Altbilgi Görünürlüğünü Ayarlayın

Altbilgi yer tutucusunun görünürlüğünü denetlemek için şunu kullanabilirsiniz: `SetFooterVisibility` yöntem.

```csharp
if (!headerFooterManager.IsFooterVisible)
{
    headerFooterManager.SetFooterVisibility(true);
}
```

### Adım 5: Slayt Numarası Görünürlüğünü Ayarlayın

Benzer şekilde, slayt sayfa numarası yer tutucusunun görünürlüğünü şu şekilde kontrol edebilirsiniz: `SetSlideNumberVisibility` yöntem.

```csharp
if (!headerFooterManager.IsSlideNumberVisible)
{
    headerFooterManager.SetSlideNumberVisibility(true);
}
```

### Adım 6: Tarih ve Saat Görünürlüğünü Ayarlayın

Tarih-saat yer tutucusunun görünür olup olmadığını belirlemek için şunu kullanın: `IsDateTimeVisible` özellik. Görünmüyorsa, kullanarak görünür hale getirebilirsiniz `SetDateTimeVisibility` yöntem.

```csharp
if (!headerFooterManager.IsDateTimeVisible)
{
    headerFooterManager.SetDateTimeVisibility(true);
}
```

### Adım 7: Alt Bilgi ve Tarih-Saat Metnini Ayarlayın

Son olarak, altbilgi ve tarih-saat yer tutucularınız için metni ayarlayabilirsiniz.

```csharp
headerFooterManager.SetFooterText("Footer text");
headerFooterManager.SetDateTimeText("Date and time text");
```

### Adım 8: Sununuzu Kaydedin

Gerekli tüm değişiklikleri yaptıktan sonra güncellenmiş sunumunuzu kaydedin.

```csharp
presentation.Save(dataDir + "Presentation.ppt", SaveFormat.Ppt);
```

## Çözüm

PowerPoint sununuza dinamik başlıklar ve altbilgiler eklemek Aspose.Slides for .NET ile çok kolaydır. Bu özellik slaytlarınızın genel görsel çekiciliğini ve bilgi yayılımını artırarak onları daha ilgi çekici ve profesyonel hale getirir.

Artık PowerPoint sunumlarınızı bir üst seviyeye taşıyacak bilgiye sahipsiniz. O halde slaytlarınızı daha dinamik, bilgilendirici ve görsel olarak çarpıcı hale getirin!

## Sıkça Sorulan Sorular (SSS)

### S1: Aspose.Slides for .NET ücretsiz bir kütüphane midir?
A1: Aspose.Slides for .NET ücretsiz değildir. Fiyatlandırma ve lisanslama ayrıntılarını bulabilirsiniz [Burada](https://purchase.aspose.com/buy).

### S2: Satın almadan önce Aspose.Slides for .NET'i deneyebilir miyim?
A2: Evet, Aspose.Slides for .NET'in ücretsiz deneme sürümünü keşfedebilirsiniz [Burada](https://releases.aspose.com/).

### S3: Aspose.Slides for .NET için dokümanları nerede bulabilirim?
A3: Belgelere erişebilirsiniz [Burada](https://reference.aspose.com/slides/net/).

### S4: Aspose.Slides for .NET için geçici lisansları nasıl alabilirim?
A4: Geçici lisanslar alınabilir [Burada](https://purchase.aspose.com/temporary-license/).

### S5: Aspose.Slides for .NET için bir topluluk veya destek forumu var mı?
A5: Evet, Aspose.Slides for .NET destek forumunu ziyaret edebilirsiniz [Burada](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}