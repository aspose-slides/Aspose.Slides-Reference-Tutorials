---
title: Aspose.Slides ile Görüntü Doldurma Slaytlarına Uzatma Ofseti Ekleme
linktitle: Slaytlarda Görüntü Dolgusu için Uzatma Uzaklığı Ekleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak sunum slaytlarınızı nasıl geliştireceğinizi öğrenin. Bu adım adım kılavuz, görüntü dolgusu için uzatma ofseti eklemeyi, dinamik görseller oluşturmayı ve tasarımı optimize etmeyi kapsar.
type: docs
weight: 18
url: /tr/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

Modern sunumlarda görseller, mesajların etkili bir şekilde iletilmesinde önemli bir rol oynamaktadır. .NET'te sunum dosyalarıyla çalışmak için güçlü bir API olan Aspose.Slides, görüntülerin şekillerin içine nasıl doldurulacağını tam olarak kontrol etmenize olanak tanıyan "Uzatma Ofseti" adı verilen bir özellik sunar. Bu makale, Aspose.Slides for .NET kullanarak sunum slaytlarına görüntü dolgusu için uzatma ofseti ekleme sürecinde size rehberlik edecektir.

## Stretch Offset'e Giriş

Uzatma Ofseti, görüntülerin şekiller içinde nasıl görüntüleneceğini özelleştirmeniz gerektiğinde değerli bir tekniktir. Bir şekil içindeki görüntünün konumunu ve hizalamasını kontrol etmenizi sağlayarak yaratıcı ve görsel olarak çekici slayt tasarımlarına olanak tanır. Aspose.Slides API'sini kullanarak esnek ofseti programlı olarak uygulayabilir ve sunumlarınıza hayat verebilirsiniz.

## Geliştirme Ortamınızı Kurma

 Uygulamaya geçmeden önce, geliştirme ortamınızda Aspose.Slides for .NET'in kurulu olduğundan emin olun. Aspose web sitesinden indirebilirsiniz.[İndirme: {link](https://releases.aspose.com/slides/net/)İndirdikten sonra projeniz için API'yi ayarlamak üzere kurulum talimatlarını izleyin.

## Slayta Resim Eklemek

Stretch offset özelliğini göstermek için Aspose.Slides'ı kullanarak bir slayta resim ekleyerek başlayalım. Aşağıdaki kod parçacığı bunun nasıl başarılacağını göstermektedir:

```csharp
// Bir Sunum nesnesinin örneğini oluşturma
Presentation presentation = new Presentation();

// İlk slayda erişin
ISlide slide = presentation.Slides[0];

// Görüntü dosyası yolunu tanımlayın
string imagePath = "path_to_your_image.jpg";

// Slayta resim ekleme
byte[] imageBytes = File.ReadAllBytes(imagePath);
IPictureFillFormat pictureFill = slide.Shapes.AddPictureFrame(ShapeType.Rectangle, 100, 100, 400, 300).FillFormat.PictureFillFormat;
pictureFill.Picture.Image = presentation.Images.AddImage(imageBytes);

// Sunuyu kaydet
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Görüntülere Uzatma Ofseti Uygulama

 Artık slayda eklenmiş bir görüntümüz olduğuna göre, buna uzatma ofsetinin nasıl uygulanacağını keşfedelim. Esneme ofseti iki özellik tarafından kontrol edilir:`StretchX` Ve`StretchY`. Bu özellikler görüntünün şekil içindeki uzaklığını sırasıyla yatay ve dikey olarak belirler.

Aspose.Slides'ı kullanarak streç ofsetini şu şekilde uygulayabilirsiniz:

```csharp
// Resim dolgusu formatına erişin
IPictureFillFormat pictureFill = slide.Shapes[0].FillFormat.PictureFillFormat;

// Uzatma ofseti uygula
pictureFill.StretchX = 0.5; // %50 yatay sapma
pictureFill.StretchY = -0.2; // -%20'lik dikey sapma
```

Bu örnekte yatay uzaklığı %50 ve dikey uzaklığı -%20 olarak ayarladık. Dikey uzaklığın negatif değeri görüntüyü şekil içinde yukarı doğru hareket ettirir.

## Esnetme Ofseti Değerlerinin Ayarlanması

 Mükemmel esneme ofseti değerlerini bulmak, istenen görsel efekti elde etmek için biraz deneme yanılma gerektirebilir. Değerlerini ayarlayın`StretchX` Ve`StretchY` tasarım ve hizalama tercihlerinize uyacak şekilde. Resim yerleşiminin nasıl değiştiğini görmek için pozitif ve negatif değerlerle denemeler yapın.

## Farklı Şekillerle Streç Ofset Kullanımı

 Uzatma ofseti dikdörtgenler, elipsler ve daha fazlası dahil olmak üzere çeşitli şekil türlerine uygulanabilir. Erişim yöntemi`PictureFillFormat` şekiller arasında tutarlı kalır. Benzersiz slayt kompozisyonları oluşturmak için farklı şekilleri keşfetmekten ve denemekten çekinmeyin.

## İleri Teknikler ve İpuçları

- Karmaşık tasarımlar için streç ofseti diğer biçimlendirme özellikleriyle birleştirin.
- Bir şeklin içindeki görüntünün belirli kısımlarını vurgulamak için uzatma ofsetini kullanın.
-  Kullanın`PictureFillFormat.TileAsTexture`Görüntüleri genişletmek yerine şekillerin içine döşeme özelliği.

## Çözüm

Aspose.Slides kullanarak sunum slaytlarına görüntü dolgusu için esnek ofsetin dahil edilmesi, yaratıcı olasılıklarla dolu bir dünyanın kapılarını açar. Görüntü konumlandırma üzerinde hassas kontrol sayesinde sunumlarınızın görsel etkisini artırabilirsiniz. Bu makalede özetlenen adımları izleyerek bu özellikten etkili bir şekilde nasıl yararlanabileceğinizi öğrendiniz.

## SSS

### Aspose.Slides for .NET'i nasıl indirebilirim?

 Aspose.Slides for .NET'i Aspose web sitesinden indirebilirsiniz.[İndirme: {link](https://releases.aspose.com/slides/net/).

### Uzatma ofsetini herhangi bir görüntü türüyle kullanabilir miyim?

Evet, JPG, PNG ve daha fazlası dahil olmak üzere çeşitli formatlardaki görüntülere uzatma ofseti uygulanabilir.

###  Her ikisini de ayarlarsam ne olur?`StretchX` and `StretchY` to the same value?

Her iki özelliğin de aynı değere ayarlanması, şekil içindeki konumunu değiştirirken görüntünün en boy oranını korur.

### Streç ofset animasyonlarla uyumlu mu?

Evet, streç ofset, slayt animasyonlarıyla sorunsuz bir şekilde çalışarak dinamik sunumlar oluşturmanıza olanak tanır.

### Gelişmiş streç ofset seçeneklerine nasıl erişebilirim?

Gelişmiş esnek ofset teknikleri ve özellikleri hakkında ayrıntılı bilgi için Aspose.Slides belgelerini inceleyin.