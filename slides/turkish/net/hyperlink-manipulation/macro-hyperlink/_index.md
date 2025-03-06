---
title: Aspose.Slides for .NET'te Makro Köprü Tıklaması Nasıl Ayarlanır
linktitle: Makroları Kullanarak Köprü Yönetimi
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET ile sunumlarınızda makro köprüleri nasıl ayarlayacağınızı öğrenin. Etkileşimi artırın ve hedef kitlenizin ilgisini çekin.
weight: 13
url: /tr/net/hyperlink-manipulation/macro-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Modern yazılım geliştirme dünyasında dinamik ve etkileşimli sunumlar oluşturmak önemli bir husustur. Aspose.Slides for .NET, sunumlarla sorunsuz bir şekilde çalışmanıza olanak tanıyan güçlü bir kütüphanedir. İster bir iş sunumu ister eğitici bir slayt gösterisi oluşturuyor olun, makro köprü tıklamalarını ayarlama yeteneği, kullanıcı deneyimini büyük ölçüde geliştirebilir. Bu adım adım kılavuzda, Aspose.Slides for .NET'i kullanarak bir makro köprü tıklaması ayarlama sürecinde size yol göstereceğiz. 

## Önkoşullar

Adım adım öğreticiye dalmadan önce, yerine getirmeniz gereken birkaç önkoşul vardır:

1.Visual Studio: Bilgisayarınızda Visual Studio'nun kurulu olduğundan emin olun, çünkü bu bizim geliştirme ortamımız olacaktır.

 2.Aspose.Slides for .NET: Aspose.Slides for .NET kütüphanesinin kurulu olması gerekir. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

3.Temel C# Bilgisi: Bu eğitimle birlikte C# programlama diline aşina olmak çok önemlidir.

## Ad Alanlarını İçe Aktar

İlk adımda Aspose.Slides ile çalışmak için gerekli ad alanlarını içe aktaralım:

### 1. Adım: Ad Alanlarını İçe Aktarın

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 Şunu içe aktardık:`Aspose.Slides` sunumlarla çalışmak için temel ad alanı olan ad alanı ve`Aspose.Slides.Export` ad alanı.

## Makro Köprü Tıklamasını Ayarlama

Şimdi bu eğitimin ana kısmına geçelim: sunumunuzda bir makro köprü tıklaması ayarlama.

### Adım 2: Sunumu Başlatın

Öncelikle yeni bir sunum başlatmamız gerekiyor.

```csharp
using (Presentation presentation = new Presentation())
{
    // Kodunuz buraya gelecek.
}
```

Bu kullanma deyimi içerisinde yeni bir sunum nesnesi oluşturup içindeki tüm işlemlerinizi gerçekleştiriyorsunuz.

### 3. Adım: Otomatik Şekil ekleyin

Bir makro köprü tıklamasını ayarlamak için kullanıcının tıklayabileceği bir nesneye ihtiyacınız olacaktır. Bu örnekte tıklanabilir öğe olarak Otomatik Şekil kullanacağız.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Burada "BlankButton" tipinde belirli koordinatlarda (20, 20) ve 80x30 boyutlarında bir Otomatik Şekil oluşturuyoruz. Bu değerleri sununuzun düzenine uyacak şekilde özelleştirebilirsiniz.

### Adım 4: Makro Köprü Tıklamasını Ayarlayın

Şimdi makro köprü tıklamasını ayarlayacağınız kısım geliyor. Parametre olarak bir makro adı sağlamanız gerekir.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

Bu örnekte makro köprü tıklamasını "TestMacro" olarak ayarladık. Kullanıcı Otomatik Şekil'e tıkladığında bu makroyu tetikleyecektir.

### Adım 5: Bilgileri Alın

Ayrıca ayarladığınız köprüyle ilgili bilgileri de alabilirsiniz.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Bu kod satırları, harici URL'yi ve köprünün eylem türünü yazdırmanıza olanak tanır.

Ve bu kadar! Aspose.Slides for .NET kullanarak sunumunuzda makro köprü tıklamasını başarıyla ayarladınız.

## Çözüm

Bu eğitimde, Aspose.Slides for .NET kullanarak sunumunuzda makro köprü tıklamasını nasıl ayarlayacağınızı öğrendik. Bu, hedef kitlenizin ilgisini çekecek etkileşimli ve dinamik sunumlar oluşturmak için değerli bir özellik olabilir. Aspose.Slides for .NET ile sunum gelişiminizi bir sonraki seviyeye taşıyacak güçlü bir araca sahipsiniz.

 Artık denemeler yapıp özel makro köprülerle büyüleyici sunumlar oluşturmanın zamanı geldi. Keşfetmekten çekinmeyin[Aspose.Slides for .NET belgeleri](https://reference.aspose.com/slides/net/) Daha ayrıntılı bilgi ve olasılıklar için.

## SSS (Sık Sorulan Sorular)

### Aspose.Slides for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Slides öncelikle .NET için tasarlanmıştır ancak Aspose, Java gibi diğer programlama dilleri için de benzer kütüphaneler sunar.

### Aspose.Slides for .NET ücretsiz bir kütüphane midir?
Aspose.Slides for .NET, ücretsiz deneme sürümü bulunan ticari bir kütüphanedir. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.Slides for .NET ile oluşturulan sunumlarda makro kullanmanın herhangi bir sınırlaması var mı?
Aspose.Slides for .NET makrolarla çalışmanıza olanak tanır, ancak sunumlarda makroları kullanırken güvenlik ve uyumluluk hususlarının farkında olmalısınız.

### Köprü için kullanılan Otomatik Şekil'in görünümünü özelleştirebilir miyim?
Evet, boyut, renk ve yazı tipi gibi özelliklerini ayarlayarak Otomatik Şekil'in görünümünü özelleştirebilirsiniz.

### Aspose.Slides for .NET için nereden yardım veya destek alabilirim?
 Sorunlarla karşılaşırsanız veya sorularınız varsa Aspose destek forumundan yardım alabilirsiniz.[Burada](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
