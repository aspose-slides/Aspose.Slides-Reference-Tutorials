---
title: PowerPoint'te ActiveX Denetimini Yönetme
linktitle: PowerPoint'te ActiveX Denetimini Yönetme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak PowerPoint sunumlarını ActiveX kontrolleriyle nasıl geliştireceğinizi öğrenin. Adım adım kılavuzumuz ekleme, değiştirme, özelleştirme, olay işleme ve daha fazlasını kapsar.
type: docs
weight: 13
url: /tr/net/slide-view-and-layout-manipulation/manage-activex-control/
---
ActiveX denetimleri, PowerPoint sunumlarınızın işlevselliğini ve etkileşimini geliştirebilecek güçlü öğelerdir. Bu kontroller, multimedya oynatıcılar, veri giriş formları ve daha fazlası gibi nesneleri doğrudan slaytlarınıza yerleştirmenize ve değiştirmenize olanak tanır. Bu makalede, PowerPoint dosyalarının .NET uygulamalarınızda sorunsuz entegrasyonunu ve manipülasyonunu sağlayan çok yönlü bir kitaplık olan Aspose.Slides for .NET'i kullanarak PowerPoint'te ActiveX kontrollerini nasıl yöneteceğinizi keşfedeceğiz.

## PowerPoint Slaytlarına ActiveX Denetimleri Ekleme

ActiveX denetimlerini PowerPoint sunumlarınıza dahil etmeye başlamak için şu adımları izleyin:

1.  Yeni Bir PowerPoint Sunumu Oluşturun: Öncelikle Aspose.Slides for .NET'i kullanarak yeni bir PowerPoint sunumu oluşturun. Şuraya başvurabilirsiniz:[Aspose.Slides for .NET API Referansı](https://reference.aspose.com/slides/net/) sunumlarla nasıl çalışılacağı konusunda rehberlik için.

2. Slayt Ekle: Sununuza yeni bir slayt eklemek için kitaplığı kullanın. Bu, ActiveX kontrolünü eklemek istediğiniz slayt olacaktır.

3. ActiveX Denetimini Ekleme: Şimdi ActiveX denetimini slayta ekleme zamanı. Aşağıdaki örnek kodu takip ederek bunu başarabilirsiniz:

```csharp
// Sunuyu yükle
Presentation presentation = new Presentation("path_to_your_presentation.pptx");

// Slaydı ActiveX denetimini eklemek istediğiniz yere getirin
ISlide slide = presentation.Slides[0];

// ActiveX denetiminin özelliklerini tanımlama
int left = 100; // Sol konumu belirtin
int top = 100; // Üst konumu belirtin
int width = 200; // Genişliği belirtin
int height = 100; // Yüksekliği belirtin
string progId = "YourActiveXControl.ProgID"; // ActiveX denetiminin ProgID'sini belirtin

// ActiveX kontrolünü slayta ekleme
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(left, top, width, height, progId);
```

 Değiştirdiğinizden emin olun`"YourActiveXControl.ProgID"` eklemek istediğiniz ActiveX kontrolünün gerçek ProgID'si ile.

4. Sunumu Kaydetme: ActiveX kontrolünü ekledikten sonra aşağıdaki kodu kullanarak sunumu kaydedin:

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## ActiveX Denetimlerini Program Aracılığıyla Değiştirme

ActiveX denetimini slaydınıza ekledikten sonra onu programlı olarak değiştirmek isteyebilirsiniz. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

1. ActiveX Denetimine Erişim: ActiveX denetiminin özelliklerine ve yöntemlerine erişmek için ona bir referans almanız gerekir. Denetimi slayttan almak için aşağıdaki kodu kullanın:

```csharp
IOleObjectFrame oleObjectFrame = slide.Shapes[0] as IOleObjectFrame;
```

2. Yöntemleri Çağır: Elde edilen referansı kullanarak ActiveX denetiminin yöntemlerini çağırabilirsiniz. Örneğin, ActiveX denetiminin "Oynat" adında bir yöntemi varsa, bunu şu şekilde çağırabilirsiniz:

```csharp
oleObjectFrame.InvokeMethod("Play");
```

3. Özellikleri Ayarla: ActiveX denetiminin özelliklerini program aracılığıyla da ayarlayabilirsiniz. Örneğin, kontrolün "Ses Düzeyi" adında bir özelliği varsa, bunu şu şekilde ayarlayabilirsiniz:

```csharp
oleObjectFrame.SetProperty("Volume", 50);
```

## ActiveX Denetimi Özelliklerini Özelleştirme

ActiveX kontrolünüzün özelliklerini özelleştirmek, sunumunuzun kullanıcı deneyimini büyük ölçüde geliştirebilir. Bu özellikleri şu şekilde özelleştirebilirsiniz:

1.  Erişim Özellikleri: Daha önce de belirtildiği gibi, ActiveX kontrolünün özelliklerine aşağıdaki komutu kullanarak erişebilirsiniz:`IOleObjectFrame` referans.

2.  Özellikleri Ayarla:`SetProperty`ActiveX denetiminin çeşitli özelliklerini ayarlama yöntemi. Örneğin arka plan rengini şu şekilde değiştirebilirsiniz:

```csharp
oleObjectFrame.SetProperty("BackColor", Color.Red);
```

## ActiveX Denetimleriyle İlişkili Olayları Yönetme

ActiveX denetimleri genellikle kullanıcı etkileşimlerine dayalı eylemleri tetikleyebilen ilişkili olaylara sahiptir. Bu olayları şu şekilde ele alabilirsiniz:

1. Etkinliklere Abone Ol: Öncelikle ActiveX kontrolünün istediğiniz olayına abone olun. Örneğin, kontrolde "Clicked" olayı varsa buna şu şekilde abone olabilirsiniz:

```csharp
oleObjectFrame.EventClick += (sender, args) =>
{
    // Etkinlik işleme kodunuz burada
};
```

## ActiveX Denetimlerini Slaytlardan Silme

Bir ActiveX denetimini slayttan kaldırmak istiyorsanız şu adımları izleyin:

1.  Denetime Erişim: ActiveX denetimine bir başvuru elde etmek için`IOleObjectFrame` daha önce gösterildiği gibi referans.

2. Denetimi Kaldırma: Denetimi slayttan kaldırmak için aşağıdaki kodu kullanın:

```csharp
slide.Shapes.Remove(oleObjectFrame);
```

## Değiştirilen Sunumu Kaydetme ve Dışa Aktarma

Sununuzda gerekli tüm değişiklikleri yaptıktan sonra aşağıdaki kodu kullanarak kaydedip dışa aktarabilirsiniz:

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Aspose.Slides for .NET Kullanmanın Yararları

Aspose.Slides for .NET, bu kontrolleri sorunsuz bir şekilde entegre etmenize ve değiştirmenize olanak tanıyan kullanıcı dostu bir API sağlayarak PowerPoint sunumlarında ActiveX kontrolleriyle çalışma sürecini basitleştirir. Aspose.Slides for .NET kullanmanın bazı yararları şunlardır:

- ActiveX kontrollerinin slaytlara kolayca eklenmesi.
- Denetimlerle programlı etkileşime geçmek için kapsamlı yöntemler.
- Kontrol özelliklerinin basitleştirilmiş özelleştirilmesi.
- Etkileşimli sunumlar için etkin etkinlik yönetimi.
- Kontrollerin slaytlardan kolaylaştırılmış şekilde kaldırılması.

## Çözüm

ActiveX kontrollerini PowerPoint sunumlarınıza dahil etmek, hedef kitlenizin etkileşimini ve katılım düzeyini yükseltebilir. Aspose.Slides for .NET ile ActiveX kontrollerini sorunsuz bir şekilde yönetebileceğiniz, kalıcı bir izlenim bırakan dinamik ve büyüleyici sunumlar oluşturmanıza olanak tanıyan güçlü bir araca sahipsiniz.

## SSS

### Belirli bir slayda ActiveX denetimini nasıl ekleyebilirim?

 Belirli bir slayda ActiveX denetimi eklemek için`AddOleObjectFrame` Aspose.Slides for .NET tarafından sağlanan yöntem. Bu yöntem, eklemek istediğiniz ActiveX denetiminin konumunu, boyutunu ve ProgID'sini belirtmenize olanak tanır.

### ActiveX denetimlerini programlı olarak değiştirebilir miyim?

 Evet, Aspose.Slides for .NET'i kullanarak ActiveX kontrollerini programlı olarak değiştirebilirsiniz. Referans alarak`IOleObjectFrame` Denetimi temsil ederek, yöntemleri çağırabilir ve özellikleri denetimle dinamik olarak etkileşim kuracak şekilde ayarlayabilirsiniz.

### Olayları nasıl halledebilirim

 ActiveX denetimleri tarafından mı tetikleniyor?

ActiveX denetimleri tarafından tetiklenen olayları, ilgili olaylara abone olarak kullanarak yönetebilirsiniz.`EventClick` (veya benzeri) olay işleyicisi. Bu, kullanıcının kontrolle etkileşimlerine yanıt olarak belirli eylemleri yürütmenize olanak tanır.

### ActiveX kontrollerinin görünümünü özelleştirmek mümkün mü?

 Kesinlikle, ActiveX kontrollerinin görünümünü aşağıdakileri kullanarak özelleştirebilirsiniz:`SetProperty` Aspose.Slides for .NET tarafından sağlanan yöntem. Bu yöntem, arka plan rengi, yazı tipi stili ve daha fazlası gibi çeşitli özellikleri değiştirmenizi sağlar.

### Bir ActiveX denetimini slayttan kaldırabilir miyim?

 Evet, ActiveX denetimini slayttan kaldırabilirsiniz.`Remove` yöntemi`Shapes` Toplamak. Referansı şuraya iletin:`IOleObjectFrame` kontrolü bir argüman olarak temsil etmek`Remove` yöntem ve denetim slayttan kaldırılacaktır.