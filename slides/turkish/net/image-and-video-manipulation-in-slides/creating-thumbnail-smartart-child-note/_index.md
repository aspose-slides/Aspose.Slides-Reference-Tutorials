---
"description": "Aspose.Slides for .NET kullanarak büyüleyici SmartArt Child Note küçük resimlerinin nasıl oluşturulacağını öğrenin. Sunumlarınızı dinamik görsellerle geliştirin!"
"linktitle": "Aspose.Slides'ta SmartArt Alt Notu için Küçük Resim Oluşturma"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides'ta SmartArt Alt Notu için Küçük Resim Oluşturma"
"url": "/tr/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides'ta SmartArt Alt Notu için Küçük Resim Oluşturma

## giriiş
Dinamik sunumlar alanında, Aspose.Slides for .NET, geliştiricilere PowerPoint sunumlarını programatik olarak düzenleme ve geliştirme yeteneği sağlayan güçlü bir araç olarak öne çıkıyor. İlgi çekici bir özellik, sunumlarınıza görsel çekicilik katmanı ekleyen SmartArt Child Notes için küçük resimler oluşturma yeteneğidir. Bu adım adım kılavuz, Aspose.Slides for .NET kullanarak SmartArt Child Notes için küçük resimler oluşturma sürecinde size yol gösterecektir.
## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
- .NET için Aspose.Slides: .NET projenize Aspose.Slides kütüphanesinin entegre olduğundan emin olun. Aksi takdirde, şuradan indirin: [sürüm sayfası](https://releases.aspose.com/slides/net/).
- Geliştirme Ortamı: Çalışan bir .NET geliştirme ortamı kurun ve C# programlamaya dair temel bir anlayışa sahip olun.
- Örnek Sunum: Test için Çocuk Notları içeren SmartArt içeren bir PowerPoint sunumu oluşturun veya edinin.
## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını C# projenize aktararak başlayın. Bu ad alanları, Aspose.Slides ile çalışmak için gereken sınıflara ve yöntemlere erişim sağlar.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## Adım 1: Sunum Sınıfını Oluşturun
Örnekleme yaparak başlayın `Presentation` sınıf, üzerinde çalışacağınız PPTX dosyasını temsil eder.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## Adım 2: SmartArt ekleyin
Şimdi, sunumdaki bir slayda SmartArt ekleyin. Bu örnekte, şunu kullanıyoruz: `BasicCycle` düzen.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Adım 3: Düğüm Referansını Edinin
SmartArt'taki belirli bir düğümle çalışmak için, onun indeksini kullanarak referansını edinin.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## Adım 4: Küçük resmi alın
SmartArt düğümü içindeki Çocuk Notunun küçük resim görüntüsünü alın.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## Adım 5: Küçük resmi kaydedin
Oluşturulan küçük resim görüntüsünü belirtilen dizine kaydedin.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
Sununuzdaki her SmartArt düğümü için bu adımları tekrarlayın ve düzeni ve stilleri gerektiği gibi özelleştirin.
## Çözüm
Sonuç olarak, Aspose.Slides for .NET geliştiricilerin ilgi çekici sunumları kolaylıkla oluşturmasını sağlar. SmartArt Child Notes için küçük resimler oluşturma yeteneği, sunumlarınızın görsel çekiciliğini artırarak dinamik ve etkileşimli bir kullanıcı deneyimi sunar.
## Sıkça Sorulan Sorular
### S: Oluşturulan küçük resmin boyutunu ve biçimini özelleştirebilir miyim?
C: Evet, koddaki ilgili parametreleri değiştirerek küçük resmin boyutlarını ve biçimini ayarlayabilirsiniz.
### S: Aspose.Slides diğer SmartArt düzenlerini destekliyor mu?
C: Kesinlikle! Aspose.Slides, sunum ihtiyaçlarınıza en uygun olanı seçmenize olanak tanıyan çeşitli SmartArt düzenleri sunar.
### S: Test amaçlı geçici lisans mevcut mudur?
A: Evet, geçici bir lisans alabilirsiniz. [Burada](https://purchase.aspose.com/temporary-license/) test ve değerlendirme için.
### S: Aspose.Slides topluluğuna nasıl ulaşabilirim veya nereden yardım alabilirim?
A: Ziyaret edin [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) Toplulukla etkileşim kurmak, sorular sormak ve çözümler bulmak.
### S: Aspose.Slides for .NET'i satın alabilir miyim?
A: Elbette! Satın alma seçeneklerini keşfedin [Burada](https://purchase.aspose.com/buy) Projelerinizde Aspose.Slides'ın tüm potansiyelini ortaya çıkarın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}