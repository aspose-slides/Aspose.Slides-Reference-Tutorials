---
title: Notlardaki Slayttan Küçük Resim Oluştur
linktitle: Notlardaki Slayttan Küçük Resim Oluştur
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak sunumunuzun notlar bölümünde slaytlardan küçük resimler oluşturmayı öğrenin. Görsel içeriğinizi geliştirin!
type: docs
weight: 12
url: /tr/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

Modern sunum dünyasında görsel içerik kraldır. Etkili iletişim için ilgi çekici slaytlar oluşturmak çok önemlidir. Sunumlarınızı geliştirmenin bir yolu, özellikle belirli ayrıntıları vurgulamak veya bir genel bakışı paylaşmak istediğinizde slaytlardan küçük resimler oluşturmaktır. Aspose.Slides for .NET bunu sorunsuz bir şekilde başarmanıza yardımcı olabilecek güçlü bir araçtır. Bu adım adım kılavuzda, Aspose.Slides for .NET kullanarak bir sunumun notlar bölümündeki slaytlardan küçük resimler oluşturma sürecinde size yol göstereceğiz.

## Önkoşullar

Ayrıntılara dalmadan önce aşağıdaki önkoşulları yerine getirmelisiniz:

### 1. Aspose.Slides for .NET

 Aspose.Slides for .NET'in kurulu ve kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

### 2. .NET Ortamı

Sisteminizde .NET geliştirme ortamının hazır olması gerekmektedir.

### 3. Bir Sunum Dosyası

 Bir sunum dosyanız olsun (örn.`ThumbnailFromSlideInNotes.pptx`) küçük resimler oluşturmak istediğiniz yer.

Şimdi süreci adımlara ayıralım:

## 1. Adım: Ad Alanlarını İçe Aktarın

Öncelikle Aspose.Slides ile çalışmak için gerekli ad alanlarını içe aktarmanız gerekiyor. C# betiğinizin başına aşağıdaki kodu ekleyin:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## 2. Adım: Sunuyu Yükleyin

 Daha sonra notların bulunduğu slaytları içeren sunum dosyasını yüklemeniz gerekecektir. Bir örneği oluşturmak için aşağıdaki kodu kullanın`Presentation` sınıf:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Kodunuz buraya gelecek
}
```

## 3. Adım: Slayta Erişin

Sunumdaki hangi slayt için küçük resim oluşturmak istediğinizi seçebilirsiniz. Bu örnekte ilk slayda erişeceğiz:

```csharp
ISlide sld = pres.Slides[0];
```

## Adım 4: İstenilen Boyutları Tanımlayın

Oluşturmak istediğiniz küçük resmin boyutlarını (genişlik ve yükseklik) belirtin. Örneğin:

```csharp
int desiredX = 1200; // Genişlik
int desiredY = 800;  // Yükseklik
```

## Adım 5: Ölçeklendirme Faktörlerini Hesaplayın

Küçük resmin istenen boyutlara uyduğundan emin olmak için ölçeklendirme faktörlerini aşağıdaki şekilde hesaplayın:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Adım 6: Küçük Resim Oluşturun

Şimdi hesaplanan ölçeklendirme faktörlerini kullanarak tam ölçekli bir görsel küçük resmi oluşturun:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Adım 7: Küçük Resmi Kaydedin

Son olarak, oluşturulan küçük resmi JPEG görüntüsü olarak kaydedin:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

Bu kadar! Aspose.Slides for .NET'i kullanarak sunumunuzun notlar bölümündeki bir slayttan başarıyla küçük resim oluşturdunuz.

## Çözüm

Küçük resimleri sunumlarınıza dahil etmek, sunumlarınızın görsel çekiciliğini ve etkinliğini önemli ölçüde artırabilir. Aspose.Slides for .NET bu süreci basit hale getirerek slaytlarınızdan özelleştirilmiş küçük resimleri kolaylıkla oluşturmanıza olanak tanır.

## SSS (Sık Sorulan Sorular)

### Oluşturulan küçük resimleri hangi formatlarda kaydedebilirim?
Gereksinimlerinize bağlı olarak küçük resimleri JPEG, PNG ve daha fazlasını içeren çeşitli formatlarda kaydedebilirsiniz.

### Aynı anda birden fazla slayt için küçük resimler oluşturabilir miyim?
Evet, sununuzdaki slaytlar arasında geçiş yapabilir ve her biri için küçük resimler oluşturabilirsiniz.

### Aspose.Slides for .NET farklı .NET çerçeveleriyle uyumlu mu?
Evet, Aspose.Slides for .NET, .NET Core ve .NET Framework dahil olmak üzere çeşitli .NET çerçeveleriyle uyumludur.

### Oluşturulan küçük resimlerin görünümünü özelleştirebilir miyim?
Kesinlikle! Aspose.Slides for .NET küçük resimlerin görünümünü özelleştirmek için boyutlar, kalite ve daha fazlası gibi seçenekler sunar.

### Aspose.Slides for .NET ile ilgili nereden destek veya daha fazla yardım alabilirim?
 Yardım bulabilir ve Aspose topluluğuyla iletişim kurabilirsiniz.[Aspose Destek Forumu](https://forum.aspose.com/).