---
"description": "Aspose.Slides API ile sunumlarınıza derinlik ve etkileşim katın. .NET kullanarak slaytlarınıza yorumları kolayca nasıl entegre edeceğinizi öğrenin. Etkileşimi artırın ve izleyicilerinizi büyüleyin."
"linktitle": "Slayta Yorum Ekle"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Slayta Yorum Ekle"
"url": "/tr/net/slide-comments-manipulation/add-slide-comments/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Slayta Yorum Ekle


Sunum yönetimi dünyasında, slaytlara yorum ekleme yeteneği oyunun kurallarını değiştirebilir. Yorumlar yalnızca iş birliğini geliştirmekle kalmaz, aynı zamanda slayt içeriğinin anlaşılmasına ve gözden geçirilmesine de yardımcı olur. Güçlü ve çok yönlü bir kütüphane olan Aspose.Slides for .NET ile sunum slaytlarınıza yorumları zahmetsizce dahil edebilirsiniz. Bu adım adım kılavuzda, Aspose.Slides for .NET kullanarak bir slayta yorum ekleme sürecini adım adım anlatacağız. İster deneyimli bir geliştirici olun, ister .NET geliştirme dünyasına yeni adım atan biri olun, bu eğitim ihtiyacınız olan tüm içgörüleri sağlayacaktır.

## Ön koşullar

Adım adım kılavuza geçmeden önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1. Aspose.Slides for .NET: Aspose.Slides for .NET'in yüklü olması gerekir. Henüz yüklü değilse, şuradan indirebilirsiniz: [Aspose.Slides .NET web sitesi için](https://releases.aspose.com/slides/net/).

2. Geliştirme Ortamı: Sisteminizde bir .NET geliştirme ortamı kurulu olmalıdır.

3. Temel C# Bilgisi: Uygulamayı göstermek için C# kullanacağımızdan, C# programlamaya aşina olmanız faydalıdır.

Bu ön koşulları sağladıktan sonra, sununuzdaki bir slayda yorum ekleme sürecine geçelim.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli namespace'leri import ederek geliştirme ortamımızı kuralım.

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Artık önkoşulları ve ad alanlarını hallettiğimize göre adım adım kılavuza geçebiliriz.

## Adım 1: Yeni Bir Sunum Oluşturun

Bir slayta yorum ekleyebileceğimiz yeni bir sunum oluşturarak başlayacağız. Bunu yapmak için aşağıdaki kodu izleyin:

```csharp
string FilePath = @"..\..\..\..\Sample Files\";
string FileName = FilePath + "Add a comment to a slide.pptx";

using (Presentation pres = new Presentation())
{
    // Boş bir slayt ekleme
    pres.Slides.AddEmptySlide(pres.LayoutSlides[0]);

    // Yazar Ekleme
    ICommentAuthor author = pres.CommentAuthors.AddAuthor("Zeeshan", "MZ");

    // Yorumların konumu
    PointF point = new PointF();
    point.X = 1;
    point.Y = 1;

    // Slaytta bir yazar için slayt yorumu ekleme
    author.Comments.AddComment("Hello Zeeshan, this is a slide comment", pres.Slides[0], point, DateTime.Now);
    
    // Sunumu kaydet
    pres.Save(FileName, SaveFormat.Pptx);
}
```

Bu kodda neler olduğunu inceleyelim:

- Yeni bir sunum oluşturarak başlıyoruz `Presentation()`.
- Daha sonra sunumumuza boş bir slayt ekliyoruz.
- Yorum için bir yazar ekliyoruz `ICommentAuthor`.
- Slayttaki yorumun konumunu şunu kullanarak tanımlıyoruz: `PointF`.
- Yazar için slayda bir yorum ekliyoruz `author.Comments.AddComment()`.
- Son olarak sunumumuzu yorumlar eklenerek kaydediyoruz.

Bu kod ilk slaytta bir yorum bulunan bir PowerPoint sunumu oluşturur. Yazarın adını, yorum metnini ve diğer parametreleri gereksinimlerinize göre özelleştirebilirsiniz.

Bu adımlarla, Aspose.Slides for .NET kullanarak bir slayda başarıyla yorum eklediniz. Artık ekibinizle veya izleyicilerinizle iş birliğini ve iletişimi geliştirerek sunum yönetiminizi bir üst seviyeye taşıyabilirsiniz.

## Çözüm

Slaytlara yorum eklemek, ister işbirlikli projeler ister eğitim amaçlı olsun, sunumlarla çalışanlar için değerli bir özelliktir. Aspose.Slides for .NET bu süreci basitleştirir ve yorumları zahmetsizce oluşturmanıza, düzenlemenize ve yönetmenize olanak tanır. Bu kılavuzda özetlenen adımları izleyerek, sunumlarınızı geliştirmek için Aspose.Slides for .NET'in gücünden yararlanabilirsiniz.

Herhangi bir sorunla karşılaşırsanız veya sorularınız varsa, yardım istemekten çekinmeyin. [Aspose.Slides forumu](https://forum.aspose.com/).

---

## SSS

### 1. Aspose.Slides for .NET'te yorumların görünümünü nasıl özelleştirebilirim?

Aspose.Slides kitaplığını kullanarak renk, boyut ve yazı tipi gibi çeşitli özellikleri değiştirerek yorumların görünümünü özelleştirebilirsiniz. Ayrıntılı rehberlik için belgelere bakın.

### 2. Slayt içindeki şekiller veya resimler gibi belirli öğelere yorum ekleyebilir miyim?

Evet, Aspose.Slides for .NET yalnızca slaytların tamamına değil, aynı zamanda slayt içindeki şekiller veya resimler gibi ayrı ayrı öğelere de yorum eklemenize olanak tanır.

### 3. Aspose.Slides for .NET, PowerPoint dosyalarının farklı sürümleriyle uyumlu mudur?

Evet, Aspose.Slides for .NET, PPTX, PPT ve daha fazlası dahil olmak üzere çeşitli PowerPoint dosya biçimlerini destekler.

### 4. Aspose.Slides for .NET'i .NET uygulamama nasıl entegre edebilirim?

Aspose.Slides for .NET'i .NET uygulamanıza entegre etmek için kurulum ve kullanım hakkında ayrıntılı bilgi sağlayan belgelere başvurabilirsiniz.

### 5. Aspose.Slides for .NET'i satın almadan önce deneyebilir miyim?

Evet, ücretsiz denemeyi kullanarak Aspose.Slides for .NET'i keşfedebilirsiniz. Ziyaret edin [Aspose.Slides ücretsiz deneme sayfası](https://releases.aspose.com/) Başlamak için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}