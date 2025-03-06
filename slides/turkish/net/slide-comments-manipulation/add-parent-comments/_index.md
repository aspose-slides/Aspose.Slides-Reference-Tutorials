---
title: Aspose.Slides'ı kullanarak Slayta Ana Yorumları Ekleme
linktitle: Slayta Ebeveyn Yorumları Ekle
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint sunumlarınıza nasıl etkileşimli yorum ve yanıt ekleyeceğinizi öğrenin. Katılımı ve işbirliğini geliştirin.
weight: 12
url: /tr/net/slide-comments-manipulation/add-parent-comments/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


PowerPoint sunumlarınızı etkileşimli özelliklerle geliştirmek mi istiyorsunuz? Aspose.Slides for .NET, yorumları ve yanıtları birleştirerek hedef kitleniz için dinamik ve ilgi çekici bir deneyim oluşturmanıza olanak tanır. Bu adım adım eğitimde, Aspose.Slides for .NET kullanarak slaytlara üst yorumların nasıl ekleneceğini göstereceğiz. Gelin bu heyecan verici özelliği derinlemesine inceleyelim ve keşfedelim.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Aspose.Slides for .NET: Aspose.Slides for .NET'in kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/slides/net/).

2. Visual Studio: .NET uygulamanızı oluşturmak ve çalıştırmak için Visual Studio'ya ihtiyacınız olacak.

3. Temel C# Bilgisi: Bu eğitimde, C# programlama konusunda temel bir anlayışa sahip olduğunuz varsayılmaktadır.

Artık önkoşulları ele aldığımıza göre, gerekli ad alanlarını içe aktarmaya devam edelim.

## Ad Alanlarını İçe Aktarma

Öncelikle ilgili ad alanlarını projenize aktarmanız gerekir. Bu ad alanları Aspose.Slides for .NET ile çalışmak için gereken sınıfları ve yöntemleri sağlar.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Önkoşullar ve ad alanları mevcut olduğundan, bir slayda ana yorumlar ekleme sürecini birden çok adıma ayıralım.

## 1. Adım: Bir Sunu Oluşturun

Başlamak için Aspose.Slides for .NET'i kullanarak yeni bir sunum oluşturmanız gerekir. Bu sunum yorumlarınızı ekleyeceğiniz tuval olacaktır.

```csharp
// Çıkış dizininin yolu.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Yorum ekleme kodunuz buraya gelecek.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 Yukarıdaki kodda değiştirin`"Output Path"` çıktı sunumunuz için istediğiniz yolla.

## 2. Adım: Yorum Yazarları Ekleme

Yorum eklemeden önce bu yorumların yazarlarını tanımlamanız gerekir. Bu örnekte, her biri şu örnekle temsil edilen "Yazar_1" ve "Yazar_2" adında iki yazarımız var:`ICommentAuthor`.

```csharp
// Yorum ekle
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Yoruma yanıt ekle1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

Bu adımda iki yorum yazarı oluşturup ilk yorumu ve yoruma bir yanıt ekliyoruz.

## 3. Adım: Daha Fazla Yanıt Ekleyin

Hiyerarşik bir yorum yapısı oluşturmak için mevcut yorumlara daha fazla yanıt ekleyebilirsiniz. Burada "yorum1"e ikinci bir yanıt ekliyoruz.

```csharp
// Yoruma yanıt ekle1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Bu, sunumunuzda bir konuşma akışı oluşturur.

## 4. Adım: İç İçe Yanıtları Ekleyin

Yorumlarda iç içe yanıtlar da bulunabilir. Bunu göstermek için, "1. yorum için yanıt 2"ye bir yanıt ekleyerek bir alt yanıt oluşturuyoruz.

```csharp
// Yanıta yanıt ekle
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Bu adım, Aspose.Slides for .NET'in yorum hiyerarşilerini yönetmedeki çok yönlülüğünü vurguluyor.

## Adım 5: Daha Fazla Yorum ve Yanıt

Gerektiğinde daha fazla yorum ve yanıt eklemeye devam edebilirsiniz. Bu örnekte iki yorum daha ve bunlardan birine bir yanıt ekliyoruz.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Bu adım, sunumlarınız için nasıl ilgi çekici ve etkileşimli içerik oluşturabileceğinizi gösterir.

## Adım 6: Hiyerarşiyi Görüntüleyin

Yorum hiyerarşisini görselleştirmek için bunu konsolda görüntüleyebilirsiniz. Bu adım isteğe bağlıdır ancak hata ayıklamak ve yapıyı anlamak için yararlı olabilir.

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## 7. Adım: Yorumları Kaldır

Bazı durumlarda yorumları ve yanıtlarını kaldırmanız gerekebilir. Aşağıdaki kod parçacığı, "yorum1"in ve tüm yanıtlarının nasıl kaldırılacağını gösterir.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Bu adım sunum içeriğinizi yönetmek ve güncellemek için kullanışlıdır.

Bu adımlarla Aspose.Slides for .NET'i kullanarak etkileşimli yorumlar ve yanıtlar içeren sunumlar oluşturabilirsiniz. Hedef kitlenizin ilgisini çekmek veya ekip üyeleriyle işbirliği yapmak istiyorsanız, bu özellik çok çeşitli olanaklar sunar.

## Çözüm

Aspose.Slides for .NET, PowerPoint sunumlarınızı geliştirmek için güçlü bir araç seti sağlar. Yorum ve yanıt ekleme özelliği sayesinde hedef kitlenizi büyüleyen dinamik ve etkileşimli içerikler oluşturabilirsiniz. Bu adım adım kılavuz size slaytlara üst yorumların nasıl ekleneceğini, hiyerarşilerin nasıl oluşturulacağını ve hatta gerektiğinde yorumların nasıl kaldırılacağını göstermiştir. Bu adımları izleyerek ve Aspose.Slides belgelerini inceleyerek[Burada](https://reference.aspose.com/slides/net/)sunumlarınızı bir üst seviyeye taşıyabilirsiniz.

## SSS

### Sunumumdaki belirli slaytlara yorum ekleyebilir miyim?
Evet, yorum oluştururken hedef slaydı belirterek sununuzdaki herhangi bir slayta yorum ekleyebilirsiniz.

### Sunumdaki yorumların görünümünü özelleştirmek mümkün mü?
Aspose.Slides for .NET, metin, yazar bilgileri ve slayttaki konum dahil olmak üzere yorumların görünümünü özelleştirmenize olanak tanır.

### Yorumları ve yanıtları ayrı bir dosyaya aktarabilir miyim?
Evet, yorumları ve yanıtları 7. adımda gösterildiği gibi ayrı bir sunum dosyasına aktarabilirsiniz.

### Aspose.Slides for .NET, PowerPoint'in en son sürümleriyle uyumlu mu?
Aspose.Slides for .NET, çok çeşitli PowerPoint sürümleriyle çalışacak şekilde tasarlanmıştır ve en son sürümlerle uyumluluk sağlar.

### Aspose.Slides for .NET için herhangi bir lisanslama seçeneği mevcut mu?
 Evet, geçici lisanslar da dahil olmak üzere lisanslama seçeneklerini Aspose web sitesinde keşfedebilirsiniz[Burada](https://purchase.aspose.com/buy) veya ücretsiz denemeyi deneyin[Burada](https://releases.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
