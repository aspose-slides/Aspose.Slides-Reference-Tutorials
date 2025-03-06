---
title: Slayta Yorum Ekle
linktitle: Slayta Yorum Ekle
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides API ile sunumlarınıza derinlik ve etkileşim katın. .NET'i kullanarak yorumları slaytlarınıza nasıl kolayca entegre edebileceğinizi öğrenin. Etkileşimi artırın ve hedef kitlenizi büyüleyin.
weight: 13
url: /tr/net/slide-comments-manipulation/add-slide-comments/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Sunum yönetimi dünyasında slaytlara yorum ekleme yeteneği oyunun kurallarını değiştirebilir. Yorumlar yalnızca işbirliğini geliştirmekle kalmaz, aynı zamanda slayt içeriğinin anlaşılmasına ve gözden geçirilmesine de yardımcı olur. Güçlü ve çok yönlü bir kütüphane olan Aspose.Slides for .NET ile yorumları sunum slaytlarınıza zahmetsizce dahil edebilirsiniz. Bu adım adım kılavuzda, Aspose.Slides for .NET kullanarak bir slayda yorum ekleme sürecinde size yol göstereceğiz. İster deneyimli bir geliştirici olun ister .NET geliştirme dünyasına yeni başlayan biri olun, bu eğitim ihtiyacınız olan tüm bilgileri sağlayacaktır.

## Önkoşullar

Adım adım kılavuzu incelemeden önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Slides for .NET: Aspose.Slides for .NET'in kurulu olması gerekir. Henüz yapmadıysanız adresinden indirebilirsiniz.[Aspose.Slides for .NET web sitesi](https://releases.aspose.com/slides/net/).

2. Geliştirme Ortamı: Sisteminizde .NET geliştirme ortamının kurulu olması gerekmektedir.

3. Temel C# Bilgisi: Uygulamayı göstermek için C# kullanacağımız için C# programlamaya aşina olmak faydalıdır.

Bu önkoşullar yerine getirildikten sonra sununuzdaki bir slayda yorum ekleme sürecine dalalım.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli namespace’leri import ederek geliştirme ortamımızı kuralım.

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Artık önkoşulları ve ad alanlarını sıraladığımıza göre adım adım kılavuza geçebiliriz.

## 1. Adım: Yeni Bir Sunu Oluşturun

Bir slayda yorum ekleyebileceğimiz yeni bir sunum oluşturarak başlayacağız. Bunu yapmak için aşağıdaki kodu izleyin:

```csharp
string FilePath = @"..\..\..\..\Sample Files\";
string FileName = FilePath + "Add a comment to a slide.pptx";

using (Presentation pres = new Presentation())
{
    // Boş slayt ekleme
    pres.Slides.AddEmptySlide(pres.LayoutSlides[0]);

    // Yazar Ekleme
    ICommentAuthor author = pres.CommentAuthors.AddAuthor("Zeeshan", "MZ");

    // Yorumların konumu
    PointF point = new PointF();
    point.X = 1;
    point.Y = 1;

    // Slayttaki bir yazar için slayt yorumu ekleme
    author.Comments.AddComment("Hello Zeeshan, this is a slide comment", pres.Slides[0], point, DateTime.Now);
    
    // Sunuyu kaydet
    pres.Save(FileName, SaveFormat.Pptx);
}
```

Bu kodda neler olduğunu açıklayalım:

-  Kullanarak yeni bir sunum oluşturarak başlıyoruz.`Presentation()`.
- Daha sonra sunuma boş bir slayt ekliyoruz.
-  Kullanarak yorum için bir yazar ekliyoruz`ICommentAuthor`.
-  Slayttaki yorumun konumunu şunu kullanarak tanımlarız:`PointF`.
- Yazar için slayta bir yorum ekliyoruz.`author.Comments.AddComment()`.
- Son olarak, eklenen yorumlarla birlikte sunumu kaydediyoruz.

Bu kod, ilk slaytta yorum bulunan bir PowerPoint sunusu oluşturur. Yazarın adını, yorum metnini ve diğer parametreleri gereksinimlerinize göre özelleştirebilirsiniz.

Bu adımlarla Aspose.Slides for .NET'i kullanarak bir slayda başarıyla yorum eklediniz. Artık ekibinizle veya izleyicilerinizle işbirliğini ve iletişimi geliştirerek sunum yönetiminizi bir sonraki seviyeye taşıyabilirsiniz.

## Çözüm

Slaytlara yorum eklemek, ister ortak projeler ister eğitim amaçlı olsun, sunumlarla çalışanlar için değerli bir özelliktir. Aspose.Slides for .NET bu süreci basitleştirerek yorumları zahmetsizce oluşturmanıza, düzenlemenize ve yönetmenize olanak tanır. Bu kılavuzda özetlenen adımları takip ederek sunumlarınızı geliştirmek için Aspose.Slides for .NET'in gücünden yararlanabilirsiniz.

 Herhangi bir sorunla karşılaşırsanız veya sorularınız varsa, şu adresten yardım aramaktan çekinmeyin:[Aspose.Slides forumu](https://forum.aspose.com/).

---

## SSS

### 1. Aspose.Slides for .NET'te yorumların görünümünü nasıl özelleştirebilirim?

Aspose.Slides kütüphanesini kullanarak renk, boyut ve yazı tipi gibi çeşitli özellikleri değiştirerek yorumların görünümünü özelleştirebilirsiniz. Ayrıntılı rehberlik için belgelere bakın.

### 2. Slayttaki şekil veya resim gibi belirli öğelere yorum ekleyebilir miyim?

Evet, Aspose.Slides for .NET, yalnızca slaytların tamamına değil aynı zamanda slayt içindeki şekiller veya resimler gibi ayrı ayrı öğelere de yorum eklemenizi sağlar.

### 3. Aspose.Slides for .NET, PowerPoint dosyalarının farklı sürümleriyle uyumlu mudur?

Evet, Aspose.Slides for .NET, PPTX, PPT ve daha fazlası dahil olmak üzere çeşitli PowerPoint dosya formatlarını destekler.

### 4. Aspose.Slides for .NET'i .NET uygulamama nasıl entegre edebilirim?

Aspose.Slides for .NET'i .NET uygulamanıza entegre etmek için kurulum ve kullanıma ilişkin ayrıntılı bilgi sağlayan belgelere başvurabilirsiniz.

### 5. Aspose.Slides for .NET'i satın almadan önce deneyebilir miyim?

Evet, ücretsiz deneme sürümünü kullanarak Aspose.Slides for .NET'i keşfedebilirsiniz. Ziyaret edin[Aspose.Slides ücretsiz deneme sayfası](https://releases.aspose.com/) başlamak.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
