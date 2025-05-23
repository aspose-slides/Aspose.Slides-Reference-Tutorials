---
"description": ".NET için Aspose.Slides'ın gücünü keşfedin, sunumlarınızda şekilleri zahmetsizce birleştirin. Slaytlarınızı dinamik bağlayıcılarla yükseltin."
"linktitle": "Sunumda Bağlayıcıları Kullanarak Şekilleri Bağlama"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides - Şekilleri .NET'te Sorunsuz Bir Şekilde Bağlayın"
"url": "/tr/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Şekilleri .NET'te Sorunsuz Bir Şekilde Bağlayın

## giriiş
Sunumların dinamik dünyasında, bağlayıcılar kullanarak şekilleri bağlama yeteneği slaytlarınıza bir katman karmaşıklık katar. Aspose.Slides for .NET geliştiricilerin bunu sorunsuz bir şekilde başarmalarını sağlar. Bu eğitim, her adımı açık bir şekilde anladığınızdan emin olmak için sizi süreçte yönlendirecektir.
## Ön koşullar
Eğitime başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- C# ve .NET framework hakkında temel bilgi.
- Aspose.Slides for .NET yüklü. Değilse, indirin [Burada](https://releases.aspose.com/slides/net/).
- Bir geliştirme ortamı kuruldu.
## Ad Alanlarını İçe Aktar
C# kodunuzda, gerekli ad alanlarını içe aktararak başlayın:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Belge Dizinini Ayarlayın
Öncelikle belgenizin dizinini tanımlayarak başlayın:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Sunum Sınıfını Örneklendirin
PPTX dosyanızı temsil edecek bir Presentation sınıfı örneği oluşturun:
```csharp
using (Presentation input = new Presentation())
{
    // Seçili slayt için şekil koleksiyonuna erişim
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Slayda Şekiller Ekleyin
Slaydınıza Elips ve Dikdörtgen gibi gerekli şekilleri ekleyin:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Bağlayıcı Şeklini Ekle
Slaydın şekil koleksiyonuna bir bağlayıcı şekil ekleyin:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Şekilleri Bağlayıcıyla Bağlayın
Bağlayıcı ile bağlanacak şekilleri belirtin:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Yeniden Yönlendirme Bağlayıcısı
Şekiller arasındaki otomatik en kısa yolu ayarlamak için yeniden yönlendirme yöntemini çağırın:
```csharp
connector.Reroute();
```
## 7. Sunumu Kaydet
Bağlantılı şekilleri görüntülemek için sununuzu kaydedin:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Çözüm
Tebrikler! Aspose.Slides for .NET kullanarak sunum slaytlarındaki bağlayıcıları kullanarak şekilleri başarıyla bağladınız. Bu gelişmiş özellik ile sunumlarınızı geliştirin ve izleyicilerinizi büyüleyin.
## SSS
### Aspose.Slides for .NET en son .NET framework ile uyumlu mudur?
Evet, Aspose.Slides for .NET, en son .NET framework sürümleriyle uyumluluğun sağlanması için düzenli olarak güncellenmektedir.
### Tek bir bağlayıcı kullanarak ikiden fazla şekli birbirine bağlayabilir miyim?
Kesinlikle, kodunuzdaki bağlayıcı mantığını genişleterek birden fazla şekli birbirine bağlayabilirsiniz.
### Bağlayabileceğim şekillerde herhangi bir sınırlama var mı?
Aspose.Slides for .NET, temel şekiller, akıllı resimler ve özel şekiller de dahil olmak üzere çeşitli şekillerin birbirine bağlanmasını destekler.
### Konektörün görünümünü nasıl özelleştirebilirim?
Bağlayıcı görünümünü özelleştirme yöntemleri (çizgi stili ve renk gibi) için Aspose.Slides belgelerini inceleyin.
### Aspose.Slides desteği için bir topluluk forumu var mı?
Evet, yardım alabilir ve deneyimlerinizi paylaşabilirsiniz. [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}