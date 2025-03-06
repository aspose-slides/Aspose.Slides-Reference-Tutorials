---
title: Slaytlarda Üstbilgi ve Altbilgiyi Yönetme
linktitle: Slaytlarda Üstbilgi ve Altbilgiyi Yönetme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak PowerPoint sunumlarına dinamik üstbilgi ve altbilgileri nasıl ekleyeceğinizi öğrenin.
weight: 14
url: /tr/net/chart-creation-and-customization/header-footer-manager/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


# Aspose.Slides for .NET'te Dinamik Üstbilgi ve Altbilgi Oluşturma

Dinamik sunumlar dünyasında Aspose.Slides for .NET güvenilir müttefikinizdir. Bu güçlü kitaplık, bir miktar etkileşimle ilgi çekici PowerPoint sunumları hazırlamanıza olanak tanır. Önemli özelliklerden biri, slaytlarınıza hayat verebilecek dinamik üstbilgiler ve altbilgiler ekleme yeteneğidir. Bu adım adım kılavuzda, bu dinamik unsurları sunumunuza eklemek için Aspose.Slides for .NET'ten nasıl yararlanabileceğinizi keşfedeceğiz. O halde hadi dalalım!

## Önkoşullar

Başlamadan önce birkaç şeye ihtiyacınız olacak:

1.  Aspose.Slides for .NET: Aspose.Slides for .NET'in kurulu olması gerekir. Henüz yapmadıysanız kütüphaneyi bulabilirsiniz[Burada](https://releases.aspose.com/slides/net/).

2. Belgeniz: Üzerinde çalışmak istediğiniz PowerPoint sunumunun yerel dizininizde kayıtlı olması gerekir. Bu belgenin yolunu bildiğinizden emin olun.

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını projenize aktarmanız gerekir. Bu ad alanları Aspose.Slides ile çalışmak için gerekli araçları sağlar.

### 1. Adım: Ad Alanlarını İçe Aktarın

C# projenizde kod dosyanızın en üstüne aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

## Dinamik Üstbilgi ve Altbilgi Ekleme

Şimdi PowerPoint sunumunuza dinamik üstbilgi ve altbilgi ekleme sürecini adım adım inceleyelim.

### 2. Adım: Sunumunuzu Yükleyin

Bu adımda PowerPoint sunumunuzu C# projenize yüklemeniz gerekiyor.

```csharp
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "presentation.ppt"))
{
    // Üstbilgi ve altbilgi yönetimi kodunuz buraya gelecek.
    // ...
}
```

### 3. Adım: Üstbilgi ve Altbilgi Yöneticisine Erişim

Aspose.Slides for .NET, üstbilgileri ve altbilgileri yönetmek için kullanışlı bir yol sağlar. Sununuzdaki ilk slaydın üstbilgi ve altbilgi yöneticisine erişiyoruz.

```csharp
IBaseSlideHeaderFooterManager headerFooterManager = presentation.Slides[0].HeaderFooterManager;
```

### 4. Adım: Alt Bilgi Görünürlüğünü Ayarlayın

 Alt bilgi yer tutucusunun görünürlüğünü kontrol etmek için`SetFooterVisibility` yöntem.

```csharp
if (!headerFooterManager.IsFooterVisible)
{
    headerFooterManager.SetFooterVisibility(true);
}
```

### Adım 5: Slayt Numarası Görünürlüğünü Ayarlayın

 Benzer şekilde, slayt sayfası numarası yer tutucusunun görünürlüğünü kullanarak kontrol edebilirsiniz.`SetSlideNumberVisibility` yöntem.

```csharp
if (!headerFooterManager.IsSlideNumberVisible)
{
    headerFooterManager.SetSlideNumberVisibility(true);
}
```

### 6. Adım: Tarih ve Saat Görünürlüğünü Ayarlayın

 Tarih-saat yer tutucusunun görünür olup olmadığını belirlemek için`IsDateTimeVisible`mülk. Görünmüyorsa butonunu kullanarak görünür hale getirebilirsiniz.`SetDateTimeVisibility` yöntem.

```csharp
if (!headerFooterManager.IsDateTimeVisible)
{
    headerFooterManager.SetDateTimeVisibility(true);
}
```

### Adım 7: Alt Bilgiyi ve Tarih-Saat Metnini Ayarlayın

Son olarak altbilgi ve tarih-saat yer tutucularınızın metnini ayarlayabilirsiniz.

```csharp
headerFooterManager.SetFooterText("Footer text");
headerFooterManager.SetDateTimeText("Date and time text");
```

### Adım 8: Sunumunuzu Kaydedin

Gerekli tüm değişiklikleri yaptıktan sonra güncellenen sununuzu kaydedin.

```csharp
presentation.Save(dataDir + "Presentation.ppt", SaveFormat.Ppt);
```

## Çözüm

Aspose.Slides for .NET ile PowerPoint sunumunuza dinamik üstbilgi ve altbilgi eklemek çok kolaydır. Bu özellik, slaytlarınızın genel görsel çekiciliğini ve bilgi dağıtımını geliştirerek onları daha ilgi çekici ve profesyonel hale getirir.

Artık PowerPoint sunumlarınızı bir sonraki seviyeye taşıyacak bilgiyle donatıldınız. Öyleyse devam edin ve slaytlarınızı daha dinamik, bilgilendirici ve görsel olarak büyüleyici hale getirin!

## Sıkça Sorulan Sorular (SSS)

### S1: Aspose.Slides for .NET ücretsiz bir kütüphane midir?
 Cevap1: Aspose.Slides for .NET ücretsiz değil. Fiyatlandırma ve lisans ayrıntılarını bulabilirsiniz[Burada](https://purchase.aspose.com/buy).

### S2: Satın almadan önce Aspose.Slides for .NET'i deneyebilir miyim?
C2: Evet, Aspose.Slides for .NET'in ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.aspose.com/).

### S3: Aspose.Slides for .NET belgelerini nerede bulabilirim?
 A3: Belgelere erişebilirsiniz[Burada](https://reference.aspose.com/slides/net/).

### S4: Aspose.Slides for .NET için nasıl geçici lisans alabilirim?
 Cevap4: Geçici lisanslar alınabilir[Burada](https://purchase.aspose.com/temporary-license/).

### S5: Aspose.Slides for .NET için bir topluluk veya destek forumu var mı?
 Cevap5: Evet, Aspose.Slides for .NET destek forumunu ziyaret edebilirsiniz.[Burada](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
