---
title: Aspose.Slides ile Sunum Slaytlarındaki Şekillere 3D Döndürme Efekti Uygulamak
linktitle: Aspose.Slides ile Sunum Slaytlarındaki Şekillere 3D Döndürme Efekti Uygulamak
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak büyüleyici 3D döndürme efektlerini sunum slaytlarına nasıl uygulayacağınızı öğrenin. Çarpıcı görsel etki için kaynak kodlu adım adım kılavuz.
type: docs
weight: 23
url: /tr/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---

Şekillere dinamik 3D döndürme efektleri ekleyerek sunumunuza çarpıcı bir görsel etki kazandırdığınızı hayal edin. Aspose.Slides for .NET ile bu büyüleyici etkiyi kolayca elde edebilir ve slaytlarınızın öne çıkmasını sağlayabilirsiniz. Bu eğitimde, sunum slaytlarındaki şekillere 3B döndürme efektlerini adım adım uygulama sürecinde size rehberlik edeceğiz. Size kaynak kodunu sağlayacağız ve her adımı ayrıntılı olarak açıklayacağız. Hadi dalalım!

## 3D Döndürme Efektlerine Giriş

3D döndürme efektleri sunum slaytlarınıza derinlik ve gerçekçilik katar. Hedef kitleniz için ilgi çekici bir görsel deneyim yaratarak şekilleri üç boyutlu uzayda dönüyormuş gibi göstermenize olanak tanır.

## Geliştirme Ortamınızı Kurma

 Başlamadan önce projenizde Aspose.Slides for .NET'in kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## Sunum Oluşturma

Başlamak için yeni bir sunum oluşturalım:

```csharp
// Sunuyu başlatma
Presentation presentation = new Presentation();
```

## Slaytlara Şekil Ekleme

Şimdi slaytlarımıza bazı şekiller ekleyelim:

```csharp
// İlk slayda erişin
ISlide slide = presentation.Slides[0];

// Dikdörtgen şekli ekleme
IShape shape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```

## 3D Döndürme Efekti Uygulama

Şekle 3B döndürme efekti uygulamak için aşağıdaki kodu kullanın:

```csharp
// Şekle 3B döndürme efekti uygulama
shape.ThreeDFormat.RotationX = 30;
shape.ThreeDFormat.RotationY = 45;
```

## Döndürme Açısını ve Perspektifi Ayarlama

İstediğiniz efekti elde etmek için dönüş açısını ve perspektifi ayarlayabilirsiniz:

```csharp
// Döndürme açısını ve perspektifi ayarlayın
shape.ThreeDFormat.RotationX = 60;
shape.ThreeDFormat.RotationY = 30;
shape.ThreeDFormat.PresetCamera.PresetType = CameraPresetType.OrthographicFront;
```

## Döndürme Ayarlarının İnce Ayarı

Daha hassas kontrol için döndürme ayarlarında ince ayar yapabilirsiniz:

```csharp
// Döndürme ayarlarına ince ayar yapın
shape.ThreeDFormat.RotationX = 45;
shape.ThreeDFormat.RotationY = 15;
shape.ThreeDFormat.RotationZ = 10;
```

## Animasyon Ekleme (İsteğe Bağlı)

Döndürme efektine animasyon eklemek için:

```csharp
// Döndürme efektine animasyon ekleme
ITransition transition = slide.SlideShowTransition;
transition.AdvanceOnTime = true;
transition.AdvanceTime = 2; // saniye
```

## Sununuzu Kaydetme ve Dışa Aktarma

3B döndürme efektini ve istediğiniz diğer ayarlamaları uyguladıktan sonra sununuzu kaydedin ve dışa aktarın:

```csharp
// Sunuyu kaydedin ve dışa aktarın
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Çözüm

Tebrikler! Aspose.Slides for .NET'i kullanarak sunum slaytlarındaki şekillere 3D döndürme efektlerini nasıl uygulayacağınızı başarıyla öğrendiniz. Bu teknik, sunumlarınızın görsel çekiciliğini büyük ölçüde artırabilir ve dinleyicilerinizin ilgisini canlı tutabilir.

## SSS

### Animasyonun dönüş hızını nasıl ayarlayabilirim?

 Dönüştürme hızını değiştirerek ayarlayabilirsiniz.`AdvanceTime` geçiş ayarlarındaki özellik.

### Metin kutularına 3B döndürme uygulayabilir miyim?

Evet, sununuzdaki metin kutularına veya diğer şekillere 3B döndürme efektleri uygulayabilirsiniz.

### Aspose.Slides farklı PowerPoint sürümleriyle uyumlu mu?

Evet, Aspose.Slides çeşitli PowerPoint sürümleriyle uyumludur ve farklı PowerPoint yazılımlarıyla açılıp görüntülenebilen sunumlar oluşturmanıza olanak tanır.

### Tek bir şekle birden fazla 3B efekt uygulayabilir miyim?

Evet, şekilleriniz için karmaşık görsel efektler oluşturmak amacıyla döndürme, derinlik ve aydınlatma gibi birden fazla 3B efekti birleştirebilirsiniz.

### Aspose.Slides diğer animasyon türleri için destek sağlıyor mu?

Evet, Aspose.Slides, sunum slaytlarınızı daha dinamik ve ilgi çekici hale getirmek için uygulayabileceğiniz çok çeşitli animasyon efektleri sunar.