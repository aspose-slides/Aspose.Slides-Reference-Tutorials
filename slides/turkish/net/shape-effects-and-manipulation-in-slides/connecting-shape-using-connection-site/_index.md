---
title: Aspose.Slides for .NET ile Bağlantı Ustalığını Şekillendirin
linktitle: Sunumda Bağlantı Sitesini Kullanarak Shape'i Bağlama
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET ile şekilleri kusursuz bir şekilde birbirine bağlayan büyüleyici sunumlar oluşturun. Sorunsuz ve ilgi çekici bir deneyim için rehberimizi takip edin.
weight: 30
url: /tr/net/shape-effects-and-manipulation-in-slides/connecting-shape-using-connection-site/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Sunumların dinamik dünyasında, birbirine bağlı şekillerle görsel olarak çekici slaytlar oluşturmak, etkili iletişim için çok önemlidir. Aspose.Slides for .NET, bağlantı sitelerini kullanarak şekilleri birbirine bağlamanıza olanak tanıyarak bunu başarmanız için güçlü bir çözüm sunar. Bu eğitim, sunumlarınızın kesintisiz görsel geçişlerle öne çıkmasını sağlayarak şekilleri adım adım bağlama sürecinde size rehberlik edecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- C# ve .NET programlamanın temel anlayışı.
-  Aspose.Slides for .NET kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/slides/net/).
- Visual Studio gibi bir Entegre Geliştirme Ortamı (IDE) kuruldu.
## Ad Alanlarını İçe Aktar
Gerekli ad alanlarını C# kodunuza aktararak başlayın:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## 1. Adım: Belge Dizininizi Kurun
Belgeniz için belirlenmiş bir dizininiz olduğundan emin olun. Mevcut değilse bir tane oluşturun:
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## Adım 2: Bir Sunu Oluşturun
PPTX dosyanızı temsil edecek şekilde Sunum sınıfını oluşturun:
```csharp
using (Presentation presentation = new Presentation())
{
    // Sunum kodunuz buraya gelecek
}
```
## 3. Adım: Şekillere Erişin ve Şekiller Ekleyin
Seçilen slaydın şekil koleksiyonuna erişin ve gerekli şekilleri ekleyin:
```csharp
IShapeCollection shapes = presentation.Slides[0].Shapes;
IConnector connector = shapes.AddConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## 4. Adım: Bağlayıcıları Kullanarak Şekilleri Birleştirin
Bağlayıcıyı kullanarak şekilleri bağlayın:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## Adım 5: İstenilen Bağlantı Sitesini Ayarlayın
Bağlayıcı için istenen bağlantı sitesi dizinini belirtin:
```csharp
uint wantedIndex = 6;
if (ellipse.ConnectionSiteCount > wantedIndex)
{
    connector.StartShapeConnectionSiteIndex = wantedIndex;
}
```
## Adım 6: Sunumunuzu Kaydedin
Sununuzu bağlı şekillerle kaydedin:
```csharp
presentation.Save(dataDir + "Connecting_Shape_on_desired_connection_site_out.pptx", SaveFormat.Pptx);
```
Artık sunumunuzdaki bağlantı sitelerini kullanarak şekilleri başarıyla bağladınız.
## Çözüm
Aspose.Slides for .NET, şekilleri bağlama sürecini basitleştirerek görsel olarak ilgi çekici sunumları zahmetsizce oluşturmanıza olanak tanır. Bu adım adım kılavuzu izleyerek slaytlarınızın görsel çekiciliğini artırabilir ve mesajınızı etkili bir şekilde iletebilirsiniz.
## Sıkça Sorulan Sorular
### Aspose.Slides Visual Studio 2019 ile uyumlu mu?
Evet, Aspose.Slides, Visual Studio 2019 ile uyumludur. Uygun sürümün kurulu olduğundan emin olun.
### Tek bir bağlayıcıya ikiden fazla şekli bağlayabilir miyim?
Aspose.Slides, iki şekli tek bir bağlayıcıyla bağlamanıza olanak tanır. Daha fazla şekli bağlamak için ek bağlayıcılara ihtiyacınız olacak.
### Aspose.Slides'ı kullanırken istisnaları nasıl ele alacağım?
İstisnaları işlemek için try-catch bloklarını kullanabilirsiniz. Bakın[dokümantasyon](https://reference.aspose.com/slides/net/) belirli istisnalar ve hata yönetimi için.
### Aspose.Slides'ın deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Slides için nereden destek alabilirim?
 Ziyaret edin[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) topluluk desteği ve tartışmalar için.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
