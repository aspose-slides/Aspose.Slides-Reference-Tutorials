---
title: PowerPoint'te ActiveX Denetimi aracılığıyla Videoyu Bağlama
linktitle: ActiveX Kontrolü Aracılığıyla Videoyu Bağlama
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak videoları PowerPoint slaytlarına nasıl bağlayacağınızı öğrenin. Bu adım adım kılavuz, bağlantılı videolarla etkileşimli ve ilgi çekici sunumlar oluşturmaya yönelik kaynak kodunu ve ipuçlarını içerir.
weight: 12
url: /tr/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

Aspose.Slides for .NET kullanarak bir Sunumda ActiveX Kontrolü aracılığıyla bir Videoyu Bağlama

Aspose.Slides for .NET'te, ActiveX kontrolünü kullanarak bir videoyu programlı olarak bir sunum slaytına bağlayabilirsiniz. Bu, video içeriğinin doğrudan slayt içinde oynatılabileceği etkileşimli sunumlar oluşturmanıza olanak tanır. Bu adım adım kılavuzda, Aspose.Slides for .NET kullanarak bir videoyu sunum slaytına bağlama sürecinde size yol göstereceğiz.

## Önkoşullar:
- Visual Studio (veya başka herhangi bir .NET geliştirme ortamı)
-  Aspose.Slides for .NET kitaplığı. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## Adım 1: Yeni Bir Proje Oluşturun
Tercih ettiğiniz .NET geliştirme ortamında (örn. Visual Studio) yeni bir proje oluşturun ve Aspose.Slides for .NET kütüphanesine referanslar ekleyin.

## Adım 2: Gerekli Ad Alanlarını İçe Aktarın
Aspose.Slides ile çalışmak için gerekli ad alanlarını projenize aktarın:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## 3. Adım: Sunumu Yükleyin
Bağlantılı videoyu eklemek istediğiniz yere PowerPoint sunumunu yükleyin:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Bağlantılı videoyu ekleme kodunuz buraya gelecek
}
```

## 4. Adım: ActiveX Denetimi Ekleme
 Bir örneğini oluşturun`IOleObjectFrame` ActiveX kontrolünü slayta eklemek için arayüz:

```csharp
ISlide slide = presentation.Slides[0]; // Videoyu eklemek istediğiniz slaydı seçin
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

Yukarıdaki kodda slayta 640x480 boyutlarında bir ActiveX kontrol çerçevesi ekliyoruz. Videoları gömmek için yaygın olarak kullanılan ShockwaveFlash ActiveX kontrolü için ProgID'yi belirliyoruz.

## Adım 5: ActiveX Denetiminin Özelliklerini Ayarlayın
Bağlantılı video kaynağını belirtmek için ActiveX denetiminin özelliklerini ayarlayın:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Gerçek video dosyası yolu ile değiştirin
oleObjectFrame.AlternativeText = "Linked Video";
```

 Yer değiştirmek`"YourVideoPathHere"` video dosyanızın gerçek yolunu içerir.`AlternativeText` özelliği, bağlantılı video için bir açıklama sağlar.

## Adım 6: Sunuyu Kaydet
Değiştirilen sunumu kaydedin:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## SSS:

### Bağlantılı videonun slayttaki boyutunu ve konumunu nasıl belirleyebilirim?
ActiveX kontrol çerçevesinin boyutlarını ve konumunu, ActiveX kontrol çerçevesinin parametrelerini kullanarak ayarlayabilirsiniz.`AddOleObjectFrame` yöntem. Dört sayısal argüman sırasıyla sol üst köşenin X ve Y koordinatlarını ve çerçevenin genişliğini ve yüksekliğini temsil eder.

### Bu yaklaşımı kullanarak farklı formatlardaki videoları birbirine bağlayabilir miyim?
Evet, çeşitli formatlardaki videoları, söz konusu format için uygun ActiveX kontrolü mevcut olduğu sürece bağlayabilirsiniz. Örneğin, bu kılavuzda kullanılan ShockwaveFlash ActiveX kontrolü Flash videoları (SWF) için uygundur. Diğer formatlar için farklı ProgID'ler kullanmanız gerekebilir.

### Bağlantılı videonun boyutunda bir sınır var mı?
Bağlantılı videonun boyutu sununuzun genel boyutunu ve performansını etkileyebilir. Videolarınızı sunuma bağlamadan önce web'de oynatılmak üzere optimize etmeniz önerilir.

### Çözüm:
Bu kılavuzda özetlenen adımları takip ederek Aspose.Slides for .NET kullanarak bir sunumdaki ActiveX kontrolü aracılığıyla bir videoyu kolayca bağlayabilirsiniz. Bu özellik, multimedya içeriğini sorunsuz bir şekilde birleştiren ilgi çekici ve etkileşimli sunumlar oluşturmanıza olanak tanır.

 Daha fazla ayrıntı ve gelişmiş seçenekler için şu adrese başvurabilirsiniz:[Aspose.Slides for .NET belgeleri](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
