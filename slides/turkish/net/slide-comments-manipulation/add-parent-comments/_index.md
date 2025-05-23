---
"description": "Aspose.Slides for .NET kullanarak PowerPoint sunularınıza etkileşimli yorumlar ve yanıtlar eklemeyi öğrenin. Katılımı ve iş birliğini artırın."
"linktitle": "Slayta Ebeveyn Yorumları Ekle"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides kullanarak Slayta Üst Yorumlar Ekleyin"
"url": "/tr/net/slide-comments-manipulation/add-parent-comments/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides kullanarak Slayta Üst Yorumlar Ekleyin


PowerPoint sunumlarınızı etkileşimli özelliklerle zenginleştirmek mi istiyorsunuz? Aspose.Slides for .NET yorumları ve yanıtları eklemenize olanak tanır ve izleyicileriniz için dinamik ve ilgi çekici bir deneyim yaratır. Bu adım adım eğitimde, Aspose.Slides for .NET kullanarak slaytlara üst yorumların nasıl ekleneceğini göstereceğiz. Hadi başlayalım ve bu heyecan verici özelliği keşfedelim.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. Aspose.Slides for .NET: Aspose.Slides for .NET'in yüklü olduğundan emin olun. İndirebilirsiniz [Burada](https://releases.aspose.com/slides/net/).

2. Visual Studio: .NET uygulamanızı oluşturmak ve çalıştırmak için Visual Studio'ya ihtiyacınız olacak.

3. Temel C# Bilgisi: Bu eğitimde C# programlama hakkında temel bir anlayışa sahip olduğunuzu varsayıyoruz.

Artık ön koşulları sağladığımıza göre, gerekli ad alanlarını içe aktarmaya geçebiliriz.

## Ad Alanlarını İçe Aktarma

Öncelikle, ilgili ad alanlarını projenize aktarmanız gerekir. Bu ad alanları, .NET için Aspose.Slides ile çalışmak için gereken sınıfları ve yöntemleri sağlar.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Ön koşullar ve ad alanları hazır olduğunda, bir slayda üst yorum ekleme sürecini birden fazla adıma bölelim.

## Adım 1: Bir Sunum Oluşturun

Başlamak için, .NET için Aspose.Slides kullanarak yeni bir sunum oluşturmanız gerekir. Bu sunum, yorumlarınızı ekleyeceğiniz tuval olacaktır.

```csharp
// Çıktı dizinine giden yol.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Yorum ekleme kodunuz buraya gelecek.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

Yukarıdaki kodda şunu değiştirin: `"Output Path"` Çıktı sunumunuz için istediğiniz yol ile.

## Adım 2: Yorum Yazarlarını Ekleyin

Yorum eklemeden önce, bu yorumların yazarlarını tanımlamanız gerekir. Bu örnekte, her biri bir örneğiyle temsil edilen "Author_1" ve "Author_2" adlı iki yazarımız var `ICommentAuthor`.

```csharp
// Yorum ekle
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Yorum1 için cevap ekle
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

Bu adımda iki yorum yazarı oluşturuyoruz ve yoruma ilk yorumu ve cevabı ekliyoruz.

## Adım 3: Daha Fazla Yanıt Ekle

Yorumların hiyerarşik bir yapısını oluşturmak için mevcut yorumlara daha fazla yanıt ekleyebilirsiniz. Burada, "comment1"e ikinci bir yanıt ekliyoruz.

```csharp
// Yorum1 için cevap ekle
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Bu, sunumunuz içerisinde bir konuşma akışı oluşturur.

## Adım 4: İç İçe Yanıtlar Ekle

Yorumlarda iç içe geçmiş yanıtlar da olabilir. Bunu göstermek için, "yorum 1 için yanıt 2"ye bir yanıt ekleyerek bir alt yanıt oluşturuyoruz.

```csharp
// Cevap ekle cevaba cevap ekle
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Bu adım, Aspose.Slides for .NET'in yorum hiyerarşilerini yönetmedeki çok yönlülüğünü vurgular.

## Adım 5: Daha Fazla Yorum ve Yanıt

Gerektiğinde daha fazla yorum ve yanıt eklemeye devam edebilirsiniz. Bu örnekte, iki yorum daha ve bunlardan birine bir yanıt ekliyoruz.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Bu adım, sunumlarınız için ilgi çekici ve etkileşimli içeriklerin nasıl oluşturulabileceğini göstermektedir.

## Adım 6: Hiyerarşiyi Görüntüle

Yorum hiyerarşisini görselleştirmek için konsolda görüntüleyebilirsiniz. Bu adım isteğe bağlıdır ancak hata ayıklama ve yapıyı anlama açısından faydalı olabilir.

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

## Adım 7: Yorumları Kaldırın

Bazı durumlarda yorumları ve yanıtlarını kaldırmanız gerekebilir. Aşağıdaki kod parçası "comment1" ve tüm yanıtlarının nasıl kaldırılacağını gösterir.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Bu adım sunum içeriğinizi yönetmek ve güncellemek için faydalıdır.

Bu adımlarla, Aspose.Slides for .NET kullanarak etkileşimli yorumlar ve yanıtlar içeren sunular oluşturabilirsiniz. İster izleyicilerinizle etkileşim kurmak, ister ekip üyeleriyle iş birliği yapmak isteyin, bu özellik çok çeşitli olanaklar sunar.

## Çözüm

.NET için Aspose.Slides, PowerPoint sunumlarınızı geliştirmek için güçlü bir araç seti sunar. Yorumlar ve yanıtlar ekleme yeteneğiyle, izleyicilerinizi büyüleyen dinamik ve etkileşimli içerikler oluşturabilirsiniz. Bu adım adım kılavuz, slaytlara üst yorumları nasıl ekleyeceğinizi, hiyerarşiler nasıl kuracağınızı ve hatta gerektiğinde yorumları nasıl kaldıracağınızı göstermiştir. Bu adımları izleyerek ve Aspose.Slides belgelerini inceleyerek [Burada](https://reference.aspose.com/slides/net/), sunumlarınızı bir üst seviyeye taşıyabilirsiniz.

## SSS

### Sunumumdaki belirli slaytlara yorum ekleyebilir miyim?
Evet, yorum oluştururken hedef slaydı belirterek sununuzdaki herhangi bir slayda yorum ekleyebilirsiniz.

### Sunumdaki yorumların görünümünü özelleştirmek mümkün mü?
Aspose.Slides for .NET, yorumların metinleri, yazar bilgileri ve slayttaki konumları dahil olmak üzere görünümünü özelleştirmenize olanak tanır.

### Yorumları ve cevapları ayrı bir dosyaya aktarabilir miyim?
Evet, 7. adımda gösterildiği gibi yorumları ve yanıtları ayrı bir sunum dosyasına aktarabilirsiniz.

### Aspose.Slides for .NET, PowerPoint'in en son sürümleriyle uyumlu mudur?
Aspose.Slides for .NET, en son sürümlerle uyumluluğu garanti altına alarak çok çeşitli PowerPoint sürümleriyle çalışacak şekilde tasarlanmıştır.

### Aspose.Slides for .NET için herhangi bir lisanslama seçeneği mevcut mu?
Evet, geçici lisanslar da dahil olmak üzere lisanslama seçeneklerini Aspose web sitesinde inceleyebilirsiniz [Burada](https://purchase.aspose.com/buy) veya ücretsiz denemeyi deneyin [Burada](https://releases.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}