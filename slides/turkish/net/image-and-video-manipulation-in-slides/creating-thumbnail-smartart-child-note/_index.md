---
title: Aspose.Slides'ta SmartArt Alt Notu için Küçük Resim Oluşturma
linktitle: Aspose.Slides'ta SmartArt Alt Notu için Küçük Resim Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak büyüleyici SmartArt Child Note küçük resimlerini nasıl oluşturacağınızı öğrenin. Sunumlarınızı dinamik görsellerle zenginleştirin!
weight: 15
url: /tr/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides'ta SmartArt Alt Notu için Küçük Resim Oluşturma

## giriiş
Dinamik sunumlar alanında Aspose.Slides for .NET, geliştiricilere PowerPoint sunumlarını programlı olarak değiştirme ve geliştirme yeteneği sağlayan güçlü bir araç olarak öne çıkıyor. İlgi çekici özelliklerden biri, SmartArt Çocuk Notları için küçük resimler oluşturarak sunumlarınıza görsel çekicilik katmanı ekleme yeteneğidir. Bu adım adım kılavuz, Aspose.Slides for .NET kullanarak SmartArt Alt Notları için küçük resimler oluşturma sürecinde size yol gösterecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.Slides for .NET: Aspose.Slides kütüphanesinin .NET projenize entegre olduğundan emin olun. Değilse, şuradan indirin:[sürümler sayfası](https://releases.aspose.com/slides/net/).
- Geliştirme Ortamı: Çalışan bir .NET geliştirme ortamı kurun ve C# programlama konusunda temel bir anlayışa sahip olun.
- Örnek Sunum: Test için SmartArt ile Çocuk Notlarını içeren bir PowerPoint sunumu oluşturun veya edinin.
## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını C# projenize aktararak başlayın. Bu ad alanları Aspose.Slides ile çalışmak için gereken sınıflara ve yöntemlere erişim sağlar.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## Adım 1: Sunum Sınıfını Başlatın
 Örnekleme yaparak başlayın`Presentation` çalışacağınız PPTX dosyasını temsil eden sınıf.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## 2. Adım: SmartArt'ı ekleyin
 Şimdi SmartArt'ı sunumdaki bir slayda ekleyin. Bu örnekte, şunu kullanıyoruz:`BasicCycle` düzen.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Adım 3: Düğüm Referansı Alın
SmartArt'ta belirli bir düğümle çalışmak için indeksini kullanarak referansını alın.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## 4. Adım: Küçük Resmi Alın
SmartArt düğümü içindeki Çocuk Notunun küçük resim görüntüsünü alın.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## Adım 5: Küçük Resmi Kaydet
Oluşturulan küçük resim görüntüsünü belirtilen dizine kaydedin.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
Düzeni ve stilleri gerektiği gibi özelleştirerek sununuzdaki her SmartArt düğümü için bu adımları tekrarlayın.
## Çözüm
Sonuç olarak Aspose.Slides for .NET, geliştiricilere ilgi çekici sunumları kolaylıkla oluşturma olanağı sağlıyor. SmartArt Çocuk Notları için küçük resimler oluşturma yeteneği, sunumlarınızın görsel çekiciliğini artırarak dinamik ve etkileşimli bir kullanıcı deneyimi sağlar.
## Sıkça Sorulan Sorular
### S: Oluşturulan küçük resmin boyutunu ve biçimini özelleştirebilir miyim?
C: Evet, koddaki ilgili parametreleri değiştirerek küçük resmin boyutlarını ve formatını ayarlayabilirsiniz.
### S: Aspose.Slides diğer SmartArt düzenlerini destekliyor mu?
C: Kesinlikle! Aspose.Slides çeşitli SmartArt düzenleri sunarak sunum ihtiyaçlarınıza en uygun olanı seçmenize olanak tanır.
### S: Test amaçlı olarak geçici bir lisans mevcut mu?
 C: Evet, adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/) Test ve değerlendirme için.
### S: Nereden yardım alabilirim veya Aspose.Slides topluluğuyla bağlantı kurabilirim?
 C: Ziyaret edin[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) toplulukla etkileşime geçmek, sorular sormak ve çözümler bulmak.
### S: Aspose.Slides for .NET'i satın alabilir miyim?
 C: Kesinlikle! Satın alma seçeneklerini keşfedin[Burada](https://purchase.aspose.com/buy) Projelerinizde Aspose.Slides'ın tüm potansiyelini açığa çıkarmak için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
