---
title: Aspose.Slides'ta Slayt Küçük Resmi Oluşturma
linktitle: Aspose.Slides'ta Slayt Küçük Resmi Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Adım adım kılavuz ve kod örnekleriyle Aspose.Slides for .NET'te slayt küçük resimleri oluşturun. Görünümü özelleştirin ve küçük resimleri kaydedin. Sunum önizlemelerini geliştirin.
type: docs
weight: 10
url: /tr/net/slide-thumbnail-generation/slide-thumbnail-generation/
---

Aspose.Slides'ı kullanarak .NET uygulamalarınızda slayt küçük resimleri oluşturmak istiyorsanız doğru yerdesiniz. Slayt küçük resimleri oluşturmak, özel PowerPoint görüntüleyicileri oluşturmak veya sunumların görüntü önizlemelerini oluşturmak gibi çeşitli senaryolarda değerli bir özellik olabilir. Bu kapsamlı kılavuzda size süreç boyunca adım adım yol göstereceğiz. Önkoşulları, ad alanlarını içe aktarmayı ve her örneği birden çok adıma bölerek slayt küçük resmi oluşturmayı sorunsuz bir şekilde uygulamanızı kolaylaştıracağız.

## Önkoşullar

Aspose.Slides for .NET ile slayt küçük resimleri oluşturma sürecine dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

### 1. Aspose.Slides Kurulumu
Başlamak için geliştirme ortamınızda Aspose.Slides for .NET'in kurulu olduğundan emin olun. Henüz yapmadıysanız Aspose web sitesinden indirebilirsiniz.

-  İndirme: {link:[Aspose.Slides for .NET](https://releases.aspose.com/slides/net/)

### 2. Çalışılacak Belge
Slayt küçük resimlerini çıkarmak için bir PowerPoint belgesine ihtiyacınız olacak. Sunum dosyanızın hazır olduğundan emin olun.

### 3. .NET Geliştirme Ortamı
Bu eğitim için .NET'e ilişkin çalışma bilgisi ve ayarlanmış bir geliştirme ortamı gereklidir.

Artık önkoşulları ele aldığınıza göre, Aspose.Slides for .NET'te slayt küçük resmi oluşturmaya ilişkin adım adım kılavuza başlayalım.

## Ad Alanlarını İçe Aktarma

Aspose.Slides işlevine erişmek için gerekli ad alanlarını içe aktarmanız gerekir. Bu adım, kodunuzun kitaplıkla doğru şekilde etkileşime girmesini sağlamak için çok önemlidir.

### 1. Adım: Yönergeleri Kullanarak Ekleme

C# kodunuza, dosyanızın başına aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
```

Bu yönergeler, slayt küçük resimleri oluşturmak için gereken sınıfları ve yöntemleri kullanmanızı sağlayacaktır.

Şimdi slayt küçük resmi oluşturma sürecini birden çok adıma ayıralım:

## Adım 2: Belge Dizinini Ayarlayın

 Öncelikle PowerPoint belgenizin bulunduğu dizini tanımlayın. Yer değiştirmek`"Your Document Directory"` dosyanızın gerçek yolu ile.

```csharp
string dataDir = "Your Document Directory";
```

## 3. Adım: Bir Sunum Sınıfını Başlatın

 Bu adımda, şunun bir örneğini oluşturacaksınız:`Presentation` sunum dosyanızı temsil edecek sınıf.

```csharp
using (Presentation presentation = new Presentation(dataDir + "YourPresentation.pptx"))
{
 // Slayt küçük resmi oluşturmaya ilişkin kodunuz buraya gelecek
}
```

 Değiştirdiğinizden emin olun`"YourPresentation.pptx"` PowerPoint dosyanızın gerçek adıyla.

## 4. Adım: Küçük Resmi Oluşturun

 Şimdi sürecin özü geliyor. İçinde`using` bloğuna istediğiniz slaydın küçük resmini oluşturmak için kodu ekleyin. Verilen örnekte, ilk slayttaki ilk şeklin küçük resmini oluşturuyoruz.

```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Appearance, 1, 1))
{
 // Küçük resim görüntüsünü kaydetme kodunuz buraya gelecek
}
```

Gerektiğinde belirli slaytların ve şekillerin küçük resimlerini yakalamak için bu kodu değiştirebilirsiniz.

## Adım 5: Küçük Resmi Kaydedin

Son adım, oluşturulan küçük resmin tercih ettiğiniz görüntü formatında diske kaydedilmesini içerir. Bu örnekte küçük resmi PNG formatında kaydediyoruz.

```csharp
bitmap.Save(dataDir + "Shape_thumbnail_Bound_Shape_out.png", ImageFormat.Png);
```

 Yer değiştirmek`"Shape_thumbnail_Bound_Shape_out.png"` İstediğiniz dosya adı ve konumuyla.

## Çözüm

Tebrikler! Aspose.Slides for .NET kullanarak slayt küçük resimlerinin nasıl oluşturulacağını başarıyla öğrendiniz. Bu güçlü özellik, PowerPoint sunumlarınızın görsel önizlemelerini sağlayarak uygulamalarınızı geliştirebilir. Doğru önkoşulları yerine getirdiğinizde ve adım adım kılavuzu takip ettiğinizde, bu işlevi sorunsuz bir şekilde uygulayabileceksiniz.

## SSS

### S: Bir sunumdaki birden fazla slayt için küçük resimler oluşturabilir miyim?
C: Evet, sununuzdaki herhangi bir slayt veya şekil için küçük resimler oluşturmak üzere kodu değiştirebilirsiniz.

### S: Küçük resimleri kaydetmek için hangi görüntü formatları destekleniyor?
C: Aspose.Slides for .NET PNG, JPEG ve BMP dahil olmak üzere çeşitli görüntü formatlarını destekler.

### S: Küçük resim oluşturma sürecinde herhangi bir sınırlama var mı?
C: İşlem, daha büyük sunumlar veya karmaşık şekiller için ek bellek ve işlem süresi tüketebilir.

### S: Oluşturulan küçük resimlerin boyutunu özelleştirebilir miyim?
C: Evet, parametreleri değiştirerek boyutları ayarlayabilirsiniz.`GetThumbnail` yöntem.

### S: Aspose.Slides for .NET ticari kullanıma uygun mudur?
C: Evet, Aspose.Slides hem kişisel hem de ticari uygulamalar için sağlam bir çözümdür. Lisanslama ayrıntılarını Aspose web sitesinde bulabilirsiniz.

 Daha fazla yardım veya sorularınız için şu adresi ziyaret etmekten çekinmeyin:[Aspose.Slides Destek Forumu](https://forum.aspose.com/).