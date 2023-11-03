---
title: Aspose.Slides'ı kullanarak Slayt Yorumlarına Erişin
linktitle: Slayt Yorumlarına Erişim
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak PowerPoint sunumlarındaki slayt yorumlarına nasıl erişeceğinizi öğrenin. İşbirliğini ve iş akışını zahmetsizce geliştirin.
type: docs
weight: 11
url: /tr/net/slide-comments-manipulation/access-slide-comments/
---

Dinamik ve etkileşimli sunumlar dünyasında slaytlarınızdaki yorumları yönetmek, işbirliği sürecinin çok önemli bir parçası olabilir. Aspose.Slides for .NET, slayt yorumlarına erişmek ve bunları değiştirmek için güçlü ve çok yönlü bir çözüm sunarak sunum iş akışınızı geliştirir. Bu adım adım kılavuzda Aspose.Slides for .NET kullanarak slayt yorumlarına erişme sürecini ayrıntılı olarak ele alacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

### 1. Aspose.Slides for .NET

Geliştirme ortamınızda Aspose.Slides for .NET'in kurulu olması gerekir. Bunu henüz yapmadıysanız, şuradan indirebilirsiniz:[İnternet sitesi](https://releases.aspose.com/slides/net/).

### 2. Sunumunuzdaki Slayt Yorumları

Erişmek istediğiniz slayt yorumlarını içeren bir PowerPoint sunumunuz olduğundan emin olun. Bu yorumları PowerPoint'te veya slayt yorumlarını destekleyen başka bir araçta oluşturabilirsiniz.

## Ad Alanlarını İçe Aktar

Aspose.Slides for .NET ile çalışmak ve slayt yorumlarına erişmek için gerekli ad alanlarını içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

### 1. Adım: Ad Alanlarını İçe Aktarın

Öncelikle C# kod düzenleyicinizi açın ve gerekli ad alanlarını kod dosyanızın en üstüne ekleyin:

```csharp
using Aspose.Slides;
using Aspose.Slides.Comment;
using System;
```

Artık önkoşulları ele aldığımıza ve gerekli ad alanlarını içe aktardığımıza göre, Aspose.Slides for .NET'i kullanarak slayt yorumlarına erişmenin adım adım sürecine geçelim.

## Adım 2: Belge Dizinini Ayarlayın

 Slayt yorumlarını içeren PowerPoint sunumunun bulunduğu belge dizininizin yolunu tanımlayın. Yer değiştirmek`"Your Document Directory"` gerçek yolla:

```csharp
string dataDir = "Your Document Directory";
```

## Adım 3: Sunum Sınıfını Başlatın

Şimdi bunun bir örneğini oluşturalım.`Presentation` PowerPoint sunumunuzla çalışmanıza olanak sağlayacak sınıf:

```csharp
using (Presentation presentation = new Presentation(dataDir + "YourPresentation.pptx"))
{
    // Kodunuz buraya gelecek.
}
```

## Adım 4: Yorum Yazarları Üzerinden Yineleme Yapın

Bu adımda sunumunuzdaki yorum yazarlarını yineliyoruz. Yorum yazarı, yorumu bir slayda ekleyen kişidir:

```csharp
foreach (var commentAuthor in presentation.CommentAuthors)
{
    var author = (CommentAuthor)commentAuthor;
    
    // Kodunuz buraya gelecek.
}
```

## 5. Adım: Yorumlara Erişin

Her yorum yazarının içinden yorumların kendisine erişebiliriz. Yorumlar belirli slaytlarla ilişkilendirilir ve yorumlar hakkında metin, yazar ve oluşturulma zamanı gibi bilgileri çıkarabiliriz:

```csharp
foreach (var commentAuthor in presentation.CommentAuthors)
{
    var author = (CommentAuthor)commentAuthor;
    
    foreach (var comment1 in author.Comments)
    {
        var comment = (Comment)comment1;
        Console.WriteLine("Slide #" + comment.Slide.SlideNumber + " has the following comment:");
        Console.WriteLine("Comment Text: " + comment.Text);
        Console.WriteLine("Author: " + comment.Author.Name);
        Console.WriteLine("Posted on: " + comment.CreatedTime + "\n");
    }
}
```

Tebrikler! Aspose.Slides for .NET'i kullanarak PowerPoint sunumunuzdaki slayt yorumlarına başarıyla eriştiniz. Bu güçlü araç, sunumlarınızı yönetmek ve üzerinde işbirliği yapmak için bir fırsatlar dünyasının kapılarını açar.

## Çözüm

Aspose.Slides for .NET, PowerPoint sunumlarınızda slayt yorumlarına erişmeniz ve bunları değiştirmeniz için kusursuz bir yol sağlar. Bu kılavuzda özetlenen adımları izleyerek slaytlarınızdan değerli bilgileri etkili bir şekilde çıkarabilir, işbirliğinizi ve iş akışınızı geliştirebilirsiniz.

### Sıkça Sorulan Sorular (SSS)

### Aspose.Slides for .NET nedir?
Aspose.Slides for .NET, geliştiricilerin PowerPoint sunumlarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir kitaplıktır. PowerPoint dosyalarını oluşturmak, değiştirmek ve yönetmek için çok çeşitli özellikler sağlar.

### Aspose.Slides for .NET'i farklı .NET uygulamalarında kullanabilir miyim?
Evet, Aspose.Slides for .NET; Windows Forms, ASP.NET ve konsol uygulamaları dahil olmak üzere çeşitli .NET uygulamalarında kullanılabilir.

### Aspose.Slides for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, Aspose.Slides for .NET'in ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/). Bu deneme sürümü, kitaplığın yeteneklerini keşfetmenize olanak tanır.

### Aspose.Slides for .NET için belge ve desteği nerede bulabilirim?
 Dokümantasyona şu adresten ulaşabilirsiniz:[reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/) ve bu konuda destek isteyin[Aspose.Slides forumu](https://forum.aspose.com/).

### Aspose.Slides for .NET için lisans satın alabilir miyim?
 Evet, Aspose.Slides for .NET lisansını şu adresten satın alabilirsiniz:[bu bağlantı](https://purchase.aspose.com/buy) Projelerinizde kütüphanenin tüm potansiyelini ortaya çıkarmak için.