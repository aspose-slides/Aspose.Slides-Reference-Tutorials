---
title: HTML Denetleyicisindeki Tüm Yazı Tiplerini Bağla
linktitle: HTML Denetleyicisindeki Tüm Yazı Tiplerini Bağla
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak bir HTML denetleyicideki tüm yazı tiplerini nasıl bağlayacağınızı öğrenin. Kaynak kodu içeren bu adım adım kılavuz, sunumlarınızda tutarlı yazı tipi oluşturma sağlamanıza yardımcı olacaktır.
type: docs
weight: 20
url: /tr/net/presentation-manipulation/link-all-fonts-in-html-controller/
---

## giriiş
Dinamik içeriğe sahip sunumlar oluştururken farklı platformlar ve cihazlar arasında yazı tipi tutarlılığını korumak çok önemlidir. Aspose.Slides for .NET, tüm yazı tiplerini bir HTML denetleyicisine bağlamak için güçlü bir çözüm sunarak sunumlarınızın yazı tiplerini doğru şekilde işlemesini sağlar. Bu kapsamlı kılavuzda, ayrıntılı kaynak kodu örnekleriyle birlikte Aspose.Slides for .NET kullanarak yazı tiplerini bir HTML denetleyicisine bağlama sürecinde size yol göstereceğiz. İster geliştirici ister sunum tasarımcısı olun, bu kılavuz sunumlarınızda tutarlı yazı tipi oluşturma elde etmenize yardımcı olacaktır.

## Aspose.Slides for .NET'i kullanarak HTML Denetleyicisindeki Tüm Fontları Bağlayın

### Önkoşullar
Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Visual Studio veya yüklü herhangi bir .NET IDE
- Aspose.Slides for .NET kitaplığı (şu adresten indirin:[Burada](https://releases.aspose.com/slides/net/))

### Adım 1: Yeni Bir .NET Projesi Oluşturun
Tercih ettiğiniz IDE'de yeni bir .NET projesi oluşturarak ve projeyi gerekli yapılandırmalarla kurarak başlayın.

### Adım 2: Aspose.Slides'a Referans Ekle
Projenize daha önce indirdiğiniz Aspose.Slides kütüphanesine bir referans ekleyin. Bu, bir HTML denetleyicisindeki yazı tiplerini bağlamak için özelliklerini kullanmanızı sağlayacaktır.

### 3. Adım: Sunuyu Yükleyin
Çalışmak istediğiniz sunum dosyasını yükleyin. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
Presentation presentation = new Presentation("your-presentation.pptx");
```

### Adım 4: HTML Denetleyicisini Hazırlayın
Yazı tipi bağlama işlemini yönetmek için bir HTML denetleyicisi oluşturun. Bu denetleyici, sunumunuzda kullanmak istediğiniz yazı tiplerine referanslar içerecektir.

### Adım 5: HTML Denetleyicisindeki Yazı Tiplerini Bağlama
HTML denetleyicinizdeki yazı tiplerini yineleyin ve bunları sununuza bağlayın. Referans olarak aşağıdaki kod parçacığını kullanın:

```csharp
foreach (var fontReference in htmlController.FontReferences)
{
    string fontPath = fontReference.Path;
    presentation.FontsManager.AddEmbeddedFont(FontData.Load(fontPath));
}
```

### 6. Adım: Bağlantılı Yazı Tiplerini Uygulayın
Bağlantılı yazı tiplerini sununuzdaki istediğiniz metin öğelerine uygulayın. Bu, sunum oluşturulurken belirtilen yazı tiplerinin kullanılmasını sağlar.

```csharp
foreach (var slide in presentation.Slides)
{
    foreach (var shape in slide.Shapes)
    {
        if (shape is ITextFrame)
        {
            ITextFrame textFrame = (ITextFrame)shape;
            textFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 18; // Yazı tipi boyutunu uygula
            textFrame.Paragraphs[0].Portions[0].PortionFormat.LatinFont = "YourLinkedFont"; // Bağlantılı yazı tipini uygula
        }
    }
}
```

### Adım 7: Sunuyu Kaydet
Yazı tiplerini bağlayıp uyguladıktan sonra, orijinal şablonu korumak için değiştirilen sunumu yeni bir dosyaya kaydedin.

```csharp
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

## SSS

### Aspose.Slides for .NET kütüphanesini nereden indirebilirim?
Aspose.Slides for .NET kütüphanesini sürümler sayfasından indirebilirsiniz.[Burada](https://releases.aspose.com/slides/net/).

### Aspose.Slides for .NET'i kullanarak tüm yazı tiplerini bağlayabilir miyim?
Evet, Aspose.Slides for .NET'i kullanarak TrueType yazı tiplerini, OpenType yazı tiplerini ve desteklenen diğer yazı tipi türlerini bağlayabilirsiniz.

### Yazı tiplerini bir HTML denetleyicisine bağlamak yaygın bir uygulama mıdır?
Yazı tiplerini bir HTML denetleyicisine bağlamak, farklı platformlar ve aygıtlar arasında tutarlı yazı tipi oluşturmayı sağlamak için önerilen bir uygulamadır.

### Bağlantılı yazı tipleri sunum dosyasının boyutunu nasıl etkiler?
Bağlantılı yazı tipleri, yazı tipi verilerinin eklenmesi nedeniyle sunum dosyasının boyutunu artırabilir. Ancak yazı tipinin doğru şekilde oluşturulmasını sağlarlar.

### Google Fonts gibi harici kaynaklardan yazı tiplerini bağlayabilir miyim?
Aspose.Slides for .NET, yerel kaynaklardan yazı tiplerine bağlantı vermenizi sağlar. Google Fonts gibi harici kaynaklar için yazı tiplerini indirmeniz ve bunları yerel olarak barındırmanız gerekebilir.

### Aspose.Slides diğer sunum değişiklikleri için uygun mu?
Kesinlikle. Aspose.Slides, sunumları değiştirmek için metin biçimlendirme, slayt geçişleri ve daha fazlasını içeren çok çeşitli özellikler sunar.

## Çözüm
Aspose.Slides for .NET kullanarak yazı tiplerini bir HTML denetleyicisine bağlamak, sunumlarınızda tutarlı yazı tipi oluşturma elde etmenizi sağlar. Bu adım adım kılavuzu takip ederek ve sağlanan kaynak kodu örneklerinden yararlanarak sunumlarınızın çeşitli cihaz ve platformlarda amaçlanan görünümünü korumasını sağlayabilirsiniz.