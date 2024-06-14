---
title: Aspose.Slides'ta Slayt Yorumlarını Oluşturma
linktitle: Aspose.Slides'ta Slayt Yorumlarını Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Adım adım eğitimimizle Aspose.Slides for .NET'te slayt yorumlarının nasıl oluşturulacağını keşfedin. Yorum görünümünü özelleştirin ve PowerPoint otomasyonunuzu geliştirin.
type: docs
weight: 12
url: /tr/net/printing-and-rendering-in-slides/rendering-slide-comments/
---
## giriiş
Aspose.Slides for .NET'i kullanarak slayt yorumlarını işlemeye ilişkin kapsamlı eğitimimize hoş geldiniz! Aspose.Slides, geliştiricilerin .NET uygulamalarında PowerPoint sunumlarıyla sorunsuz bir şekilde çalışmasına olanak tanıyan güçlü bir kitaplıktır. Bu kılavuzda belirli bir göreve (slayt yorumlarını oluşturma) odaklanacağız ve süreç boyunca size adım adım yol göstereceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilerin mevcut olduğundan emin olun:
-  Aspose.Slides for .NET Kütüphanesi: Geliştirme ortamınızda Aspose.Slides for .NET kütüphanesinin kurulu olduğundan emin olun. Henüz yapmadıysanız indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).
- Geliştirme Ortamı: Çalışan bir .NET geliştirme ortamı kurun ve temel C# anlayışına sahip olun.
Şimdi öğreticiye başlayalım!
## Ad Alanlarını İçe Aktar
Aspose.Slides özelliklerini kullanmak için C# kodunuzda gerekli ad alanlarını içe aktarmanız gerekir. Dosyanızın başına aşağıdaki satırları ekleyin:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;
```
## 1. Adım: Belge Dizininizi Kurun
PowerPoint sunumunun bulunduğu belge dizininizin yolunu belirterek başlayın:
```csharp
string dataDir = "Your Document Directory";
```
## Adım 2: Çıkış Yolunu Belirleyin
İşlenen görüntüyü yorumlarla kaydetmek istediğiniz yolu tanımlayın:
```csharp
string resultPath = Path.Combine(dataDir, "OutPresBitmap_Comments.png");
```
## 3. Adım: Sunuyu Yükleyin
Aspose.Slides kütüphanesini kullanarak PowerPoint sunumunu yükleyin:
```csharp
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```
## Adım 4: İşleme için bir Bitmap Oluşturun
İstediğiniz boyutlara sahip bir bitmap nesnesi oluşturun:
```csharp
Bitmap bmp = new Bitmap(740, 960);
```
## 5. Adım: Oluşturma Seçeneklerini Yapılandırın
Notlar ve yorumlar için düzen seçenekleri dahil, oluşturma seçeneklerini yapılandırın:
```csharp
IRenderingOptions renderOptions = new RenderingOptions();
NotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
notesOptions.CommentsAreaColor = Color.Red;
notesOptions.CommentsAreaWidth = 200;
notesOptions.CommentsPosition = CommentsPositions.Right;
notesOptions.NotesPosition = NotesPositions.BottomTruncated;
renderOptions.SlidesLayoutOptions = notesOptions;
```
## Adım 6: Grafiğe Dönüştürme
Yorumlar içeren ilk slaydı belirtilen grafik nesnesine aktarın:
```csharp
using (Graphics graphics = Graphics.FromImage(bmp))
{
    pres.Slides[0].RenderToGraphics(renderOptions, graphics);
}
```
## Adım 7: Sonucu Kaydet
İşlenen görüntüyü yorumlarla birlikte belirtilen yola kaydedin:
```csharp
bmp.Save(resultPath, ImageFormat.Png);
```
## Adım 8: Sonucu Görüntüleyin
İşlenen görüntüyü varsayılan resim görüntüleyiciyi kullanarak açın:
```csharp
System.Diagnostics.Process.Start(resultPath);
```
Tebrikler! Aspose.Slides for .NET'i kullanarak slayt yorumlarını başarıyla oluşturdunuz.
## Çözüm
Bu eğitimde Aspose.Slides for .NET kullanarak slayt yorumlarını oluşturma sürecini inceledik. Adım adım kılavuzu izleyerek PowerPoint otomasyon yeteneklerinizi kolaylıkla geliştirebilirsiniz.
## Sıkça Sorulan Sorular
### S: Aspose.Slides en son .NET framework sürümleriyle uyumlu mu?
C: Evet, Aspose.Slides en son .NET framework sürümlerini destekleyecek şekilde düzenli olarak güncellenmektedir.
### S: Oluşturulan yorumların görünümünü özelleştirebilir miyim?
C: Kesinlikle! Eğitici, yorum alanı rengini, genişliğini ve konumunu özelleştirmeye yönelik seçenekler içerir.
### S: Aspose.Slides for .NET hakkında daha fazla belgeyi nerede bulabilirim?
 C: Belgeleri inceleyin[Burada](https://reference.aspose.com/slides/net/).
### S: Aspose.Slides için geçici lisansı nasıl edinebilirim?
 C: Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Slides için nereden yardım ve destek alabilirim?
 C: Ziyaret edin[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) topluluk desteği için.