---
"description": "Aspose.Slides for .NET kullanarak PowerPoint not slaytlarında üstbilgi ve altbilgiyi nasıl yöneteceğinizi öğrenin. Sunumlarınızı zahmetsizce geliştirin."
"linktitle": "Notlar Slaydında Üst Bilgi ve Alt Bilgiyi Yönetin"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides .NET ile Notes'ta Üstbilgi ve Altbilgiyi Yönetme"
"url": "/tr/net/notes-slide-manipulation/header-and-footer-in-notes-slide/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides .NET ile Notes'ta Üstbilgi ve Altbilgiyi Yönetme


Günümüzün dijital çağında, ilgi çekici ve bilgilendirici sunumlar oluşturmak hayati bir beceridir. Bu sürecin bir parçası olarak, ek bağlam ve bilgi sağlamak için not slaytlarınıza genellikle başlıklar ve altbilgiler eklemeniz gerekebilir. Aspose.Slides for .NET, not slaytlarındaki başlık ve altbilgi ayarlarını kolayca yönetmenizi sağlayan güçlü bir araçtır. Bu adım adım kılavuzda, Aspose.Slides for .NET kullanarak bunu nasıl başaracağınızı inceleyeceğiz.

## Ön koşullar

Eğitime başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. Aspose.Slides for .NET: Aspose.Slides for .NET'in yüklü ve yapılandırılmış olduğundan emin olun. İndirebilirsiniz [Burada](https://releases.aspose.com/slides/net/).

2. PowerPoint Sunumu: Çalışmak istediğiniz bir PowerPoint sunumuna (PPTX dosyası) ihtiyacınız olacak.

Artık ön koşulları tamamladığımıza göre, Aspose.Slides for .NET kullanarak not slaytlarındaki üstbilgi ve altbilgiyi yönetmeye başlayalım.

## Adım 1: Ad Alanlarını İçe Aktar

Başlamak için projeniz için gerekli ad alanlarını içe aktarmanız gerekir. Aşağıdaki ad alanlarını ekleyin:

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Export;
```

Bu ad alanları, not slaytlarındaki üstbilgi ve altbilgiyi yönetmek için gereken sınıflara ve yöntemlere erişim sağlar.

## Adım 2: Üstbilgi ve Altbilgi Ayarlarını Değiştirin

Daha sonra, sunumunuzdaki notlar ana sayfası ve tüm not slaytları için başlık ve alt bilgi ayarlarını değiştireceğiz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
using (Presentation presentation = new Presentation("presentation.pptx"))
{
    IMasterNotesSlide masterNotesSlide = presentation.MasterNotesSlideManager.MasterNotesSlide;

    if (masterNotesSlide != null)
    {
        IMasterNotesSlideHeaderFooterManager headerFooterManager = masterNotesSlide.HeaderFooterManager;

        headerFooterManager.SetHeaderAndChildHeadersVisibility(true);
        headerFooterManager.SetFooterAndChildFootersVisibility(true);
        headerFooterManager.SetSlideNumberAndChildSlideNumbersVisibility(true);
        headerFooterManager.SetDateTimeAndChildDateTimesVisibility(true);

        headerFooterManager.SetHeaderAndChildHeadersText("Header text");
        headerFooterManager.SetFooterAndChildFootersText("Footer text");
        headerFooterManager.SetDateTimeAndChildDateTimesText("Date and time text");
    }

    // Sunuyu güncellenmiş ayarlarla kaydedin
    presentation.Save("testresult.pptx", SaveFormat.Pptx);
}
```

Bu adımda ana notlar slaydına erişiriz ve başlıklar, altbilgiler, slayt numaraları ve tarih-saat yer tutucuları için görünürlüğü ve metni ayarlarız.

## Adım 3: Belirli bir Notlar Slaydı için Üstbilgi ve Altbilgi Ayarlarını Değiştirin

Şimdi, belirli bir not slaydı için başlık ve alt bilgi ayarlarını değiştirmek istiyorsanız, şu adımları izleyin:

```csharp
using (Presentation presentation = new Presentation("presentation.pptx"))
{
    INotesSlide notesSlide = presentation.Slides[0].NotesSlideManager.NotesSlide;

    if (notesSlide != null)
    {
        INotesSlideHeaderFooterManager headerFooterManager = notesSlide.HeaderFooterManager;

        if (!headerFooterManager.IsHeaderVisible)
            headerFooterManager.SetHeaderVisibility(true);

        if (!headerFooterManager.IsFooterVisible)
            headerFooterManager.SetFooterVisibility(true);

        if (!headerFooterManager.IsSlideNumberVisible)
            headerFooterManager.SetSlideNumberVisibility(true);

        if (!headerFooterManager.IsDateTimeVisible)
            headerFooterManager.SetDateTimeVisibility(true);

        headerFooterManager.SetHeaderText("New header text");
        headerFooterManager.SetFooterText("New footer text");
        headerFooterManager.SetDateTimeText("New date and time text");
    }

    // Sunuyu güncellenmiş ayarlarla kaydedin
    presentation.Save("testresult.pptx", SaveFormat.Pptx);
}
```

Bu adımda, belirli bir not slaydına erişiriz ve başlık, alt bilgi, slayt numarası ve tarih-saat yer tutucularının görünürlüğünü ve metnini değiştiririz.

## Çözüm

Not slaytlarındaki başlıkları ve alt bilgileri etkili bir şekilde yönetmek, sunumlarınızın genel kalitesini ve netliğini artırmak için çok önemlidir. .NET için Aspose.Slides ile bu süreç basit ve verimli hale gelir. Bu eğitim, ad alanlarını içe aktarmaktan hem ana notlar slaydı hem de bireysel notlar slaytları için ayarları değiştirmeye kadar bunu nasıl başaracağınıza dair kapsamlı bir kılavuz sağlamıştır.

Henüz keşfetmediyseniz, mutlaka keşfedin [Aspose.Slides for .NET belgeleri](https://reference.aspose.com/slides/net/) Daha detaylı bilgi ve örnekler için.

## Sıkça Sorulan Sorular

### Aspose.Slides for .NET'i kullanmak ücretsiz mi?
Hayır, Aspose.Slides for .NET ticari bir üründür ve projelerinizde kullanmak için bir lisans satın almanız gerekecektir. Geçici bir lisans alabilirsiniz [Burada](https://purchase.aspose.com/temporary-license/) test için.

### Başlık ve altbilgilerin görünümünü daha da özelleştirebilir miyim?
Evet, Aspose.Slides for .NET, başlık ve altbilgilerin görünümünü özelleştirmek için kapsamlı seçenekler sunarak bunları özel ihtiyaçlarınıza göre uyarlamanıza olanak tanır.

### Aspose.Slides for .NET'te sunum yönetimi için başka özellikler var mı?
Evet, Aspose.Slides for .NET, slaytlar, şekiller ve slayt geçişleri de dahil olmak üzere sunumlar oluşturmak, düzenlemek ve yönetmek için çok çeşitli özellikler sunar.

### Aspose.Slides for .NET ile PowerPoint sunumlarını otomatikleştirebilir miyim?
Kesinlikle, Aspose.Slides for .NET, PowerPoint sunumlarını otomatikleştirmenize olanak tanır ve bu da onu dinamik ve veri odaklı slayt gösterileri oluşturmak için değerli bir araç haline getirir.

### Aspose.Slides for .NET kullanıcıları için teknik destek mevcut mu?
Evet, Aspose topluluğundan ve uzmanlardan destek ve yardım alabilirsiniz. [Aspose destek forumu](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}