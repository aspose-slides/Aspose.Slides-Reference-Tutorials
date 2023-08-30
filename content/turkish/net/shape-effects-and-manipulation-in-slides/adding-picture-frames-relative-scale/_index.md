---
title: Aspose.Slides'ta Göreli Ölçek Yüksekliğine Sahip Resim Çerçeveleri Ekleme
linktitle: Aspose.Slides'ta Göreli Ölçek Yüksekliğine Sahip Resim Çerçeveleri Ekleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak göreceli ölçek yüksekliğine sahip resim çerçeveleri ekleyerek sunumlarınızı nasıl geliştirebileceğinizi öğrenin. Zahmetsizce görsel olarak çekici slaytlar oluşturun.
type: docs
weight: 17
url: /tr/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

## giriiş

Sunumların dinamik dünyasında görsel öğeler, bilginin etkili bir şekilde aktarılmasında önemli bir rol oynar. Aspose.Slides for .NET, temel bilgilerin ötesine geçmenizi ve göreceli ölçek yüksekliğinde resim çerçeveleri ekleyerek sunumlarınızı geliştirmenizi sağlar. Bu kılavuz size süreci adım adım anlatacak ve görsel açıdan büyüleyici, öne çıkan slaytlar oluşturma becerileri sağlayacaktır. İster deneyimli bir geliştirici olun ister Aspose.Slides'ı yeni kullanmaya başlayın, bu kılavuz göreceli ölçek yüksekliğinde resim çerçeveleri ekleme sanatında ustalaşmanıza yardımcı olacaktır.

## Aspose.Slides'ta Göreli Ölçek Yüksekliğine Sahip Resim Çerçeveleri Ekleme

Aspose.Slides'ta göreceli ölçek yüksekliğine sahip resim çerçeveleri ekleme işlemi son derece sezgiseldir. Sunumlarınızı geliştirmek için şu adımları izleyin:

### Adım 1: Sunumu Başlatın

Aşağıdaki kodu kullanarak sunum nesnesini başlatarak başlayın:

```csharp
Presentation presentation = new Presentation();
```

### 2. Adım: Slayt Ekleme

Yeni bir slayt eklemek için aşağıdaki kod parçacığını kullanın:

```csharp
ISlide slide = presentation.Slides.AddEmptySlide(presentation.LayoutSlides[0]);
```

### 3. Adım: Resim Ekleme

Şimdi görüntüyü slayta eklemenin zamanı geldi. Aşağıdaki kod bunun nasıl başarılacağını gösterir:

```csharp
byte[] imageBytes = File.ReadAllBytes("image.jpg");
IPPImage image = presentation.Images.AddImage(imageBytes);
slide.Shapes.AddPictureFrame(ShapeType.Rectangle, 100, 100, image.Width, image.Height, image);
```

### Adım 4: Ölçek Yüksekliğini Ayarlayın

Resim çerçevesi için göreceli bir ölçek yüksekliği oluşturmak için aşağıdaki kod parçasını kullanın:

```csharp
IPictureFrame pictureFrame = (IPictureFrame)slide.Shapes[0];
pictureFrame.PictureFormat.Picture.ImageScale.HeightScale = 50; // Ölçek yüzdesini istediğiniz gibi ayarlayın
```

## SSS

### Resim çerçevesinin ölçek yüksekliğini nasıl değiştirebilirim?

 Resim çerçevesinin ölçek yüksekliğini değiştirmek için`PictureFormat.Picture.ImageScale.HeightScale` özelliği seçin ve ona istediğiniz bir yüzde değeri atayın.

### Tek bir slayda birden fazla resim çerçevesi ekleyebilir miyim?

Evet, eklemek istediğiniz her resim çerçevesi için daha önce belirtilen adımları izleyerek tek bir slayta birden fazla resim çerçevesi ekleyebilirsiniz.

### Bir sunumdaki resim çerçevelerini hareketlendirmek mümkün müdür?

Kesinlikle! Aspose.Slides güçlü animasyon yetenekleri sağlar. Kitaplıkta bulunan çeşitli animasyon efektlerini kullanarak resim çerçevelerine animasyonlar uygulayabilirsiniz.

### Ekleme için hangi resim formatları destekleniyor?

Aspose.Slides, JPEG, PNG, GIF, BMP ve daha fazlasını içeren çok çeşitli görüntü formatlarını destekler. Bu formatlardaki görselleri slaytlarınıza sorunsuz bir şekilde ekleyebilirsiniz.

### Resim çerçevesinin slayttaki konumunu nasıl ayarlayabilirim?

 Resim çerçevesini eklerken X ve Y koordinatlarını belirterek resim çerçevesinin konumunu ayarlayabilirsiniz.`slide.Shapes.AddPictureFrame` yöntem.

### Resim çerçevesinin görünümünü özelleştirmek mümkün mü?

Evet, kenarlık rengi, dolgu rengi ve daha fazlası gibi özellikleri kullanarak resim çerçevesinin görünümünü özelleştirebilirsiniz. Ayrıntılı bilgi için Aspose.Slides belgelerine bakın.

## Çözüm

Sunularınıza göreceli ölçek yüksekliğine sahip resim çerçeveleri eklemek, bunların görsel çekiciliğini ve etkileşimini büyük ölçüde artırabilir. Aspose.Slides for .NET ile süreç basit ve özelleştirilebilir hale gelir ve kalıcı bir etki bırakan çarpıcı slaytlar oluşturmanıza olanak tanır. İster eğitim içeriği, ister iş sunumları veya yaratıcı vitrinler hazırlıyor olun, bu özellikte ustalaşmak şüphesiz sunum oyununuzu geliştirecektir.

Unutmayın, anahtar deney ve yaratıcılıkta yatmaktadır. Aspose.Slides'ın gücünden yararlanarak yalnızca slaytlar oluşturmakla kalmazsınız; Hedef kitleniz için sürükleyici deneyimler yaratıyorsunuz.