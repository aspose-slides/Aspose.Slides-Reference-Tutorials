---
title: Aspose.Slides - .NET'te Şekilleri Sorunsuz Bir Şekilde Bağlayın
linktitle: Sunumda Bağlayıcılar Kullanarak Şekilleri Bağlama
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Sunumlarınızda şekilleri zahmetsizce birbirine bağlayan Aspose.Slides for .NET'in gücünü keşfedin. Slaytlarınızı dinamik bağlayıcılarla yükseltin.
weight: 29
url: /tr/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Sunumların dinamik dünyasında, bağlayıcıları kullanarak şekilleri birbirine bağlama yeteneği, slaytlarınıza bir gelişmişlik katmanı ekler. Aspose.Slides for .NET, geliştiricilerin bunu sorunsuz bir şekilde başarmalarını sağlar. Bu eğitim, net bir anlayış sağlamak için her adımı parçalara ayırarak süreç boyunca size rehberlik edecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Temel C# ve .NET framework bilgisi.
-  Aspose.Slides for .NET kuruldu. Değilse indirin[Burada](https://releases.aspose.com/slides/net/).
- Bir geliştirme ortamı oluşturuldu.
## Ad Alanlarını İçe Aktar
C# kodunuzda gerekli ad alanlarını içe aktararak başlayın:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Belge Dizinini Kurun
Belgenizin dizinini tanımlayarak başlayın:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Sunum Sınıfını Başlatın
PPTX dosyanızı temsil edecek Sunum sınıfının bir örneğini oluşturun:
```csharp
using (Presentation input = new Presentation())
{
    // Seçilen slayt için şekil koleksiyonuna erişiliyor
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Slayta Şekiller Ekleyin
Elips ve Dikdörtgen gibi gerekli şekilleri slaytınıza ekleyin:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Bağlayıcı Şekli Ekleyin
Slaydın şekil koleksiyonuna bir bağlayıcı şekli ekleyin:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Şekilleri Bağlayıcıyla Bağlayın
Bağlayıcı tarafından bağlanacak şekilleri belirtin:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Bağlayıcıyı Yeniden Yönlendirin
Şekiller arasındaki otomatik en kısa yolu ayarlamak için yeniden yönlendirme yöntemini çağırın:
```csharp
connector.Reroute();
```
## 7. Sunumu Kaydet
Bağlı şekilleri görüntülemek için sununuzu kaydedin:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Çözüm
Tebrikler! Aspose.Slides for .NET'i kullanarak sunum slaytlarındaki bağlayıcıları kullanarak şekilleri başarıyla bağladınız. Bu gelişmiş özellik ile sunumlarınızı geliştirin ve izleyicilerinizi büyüleyin.
## SSS
### Aspose.Slides for .NET en son .NET çerçevesiyle uyumlu mu?
Evet, Aspose.Slides for .NET, en yeni .NET framework sürümleriyle uyumluluğun sağlanması amacıyla düzenli olarak güncellenmektedir.
### Tek bir bağlayıcı kullanarak ikiden fazla şekli bağlayabilir miyim?
Kesinlikle kodunuzdaki bağlayıcı mantığını genişleterek birden çok şekli bağlayabilirsiniz.
### Bağlayabileceğim şekillerde herhangi bir sınırlama var mı?
Aspose.Slides for .NET, temel şekiller, akıllı sanatlar ve özel şekiller de dahil olmak üzere çeşitli şekillerin bağlanmasını destekler.
### Bağlayıcının görünümünü nasıl özelleştirebilirim?
Çizgi stili ve renk gibi bağlayıcı görünümünü özelleştirme yöntemleri için Aspose.Slides belgelerini inceleyin.
### Aspose.Slides desteği için bir topluluk forumu var mı?
 Evet, yardım bulabilir ve deneyimlerinizi paylaşabilirsiniz.[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
