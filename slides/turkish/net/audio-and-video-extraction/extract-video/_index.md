---
title: Aspose.Slides for .NET Kullanarak Slayttan Video Çıkarma
linktitle: Slayttan Video Çıkart
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint slaytlarından nasıl video çıkaracağınızı öğrenin. Bu adım adım kılavuz süreci sizin için basitleştirir.
weight: 14
url: /tr/net/audio-and-video-extraction/extract-video/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Aspose.Slides for .NET, PowerPoint sunumlarıyla .NET ortamında çalışmanıza olanak tanıyan güçlü bir kitaplıktır. Sağladığı kullanışlı özelliklerden biri, slaytlardan video çıkarma yeteneğidir. Bu adım adım kılavuzda, Aspose.Slides for .NET kullanarak bir PowerPoint slaytından nasıl video çıkaracağınızı göstereceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

-  Aspose.Slides for .NET: Aspose.Slides for .NET'in kurulu olması gerekir. adresinden temin edebilirsiniz.[İnternet sitesi](https://purchase.aspose.com/buy).

- PowerPoint Sunumu: Çıkarmak istediğiniz videoyu içeren bir PowerPoint sunumu (örneğin, Video.pptx) hazırlayın.

## Ad Alanlarını İçe Aktar

Aspose.Slides for .NET ile çalışmak için gerekli ad alanlarını içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Şimdi bir slayttan video çıkarma işlemini birden fazla adıma ayıralım.

## 1. Adım: Belge Dizinini Ayarlayın

```csharp
string dataDir = "Your Document Directory";
```

 Yer değiştirmek`"Your Document Directory"` PowerPoint sunumunuzun bulunduğu dizinin yolu ile birlikte.

## 2. Adım: Sunuyu Yükleyin

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Bu kod, PowerPoint sunum dosyanızı temsil eden bir Sunum nesnesini başlatır.

## 3. Adım: Slaytlar ve Şekiller Üzerinde Yineleme Yapın

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Burada, sunumdaki her slaytta döngü yapıyoruz ve ardından ilk slayttaki şekilleri yineliyoruz (gerektiğinde değişiklik yapıyoruz).

## 4. Adım: Şeklin bir Video Çerçevesi olup olmadığını kontrol edin

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Bu adım, slayttaki şeklin bir video karesi olup olmadığını kontrol eder.

## Adım 5: Video Verilerini Çıkarın

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Bu kod, içerik türü ve ikili veriler de dahil olmak üzere video hakkındaki bilgileri çıkarır.

## Adım 6: Videoyu Kaydet

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Son olarak bu adım, videoyu belirtilen dizindeki yeni bir dosyaya kaydeder.

Bu adımları tamamladıktan sonra Aspose.Slides for .NET'i kullanarak PowerPoint slaytından başarıyla video çıkarmış olacaksınız.

## Çözüm

Aspose.Slides for .NET, PowerPoint sunumlarıyla çalışma sürecini basitleştirerek slaytlardan video çıkarma gibi görevleri kolaylıkla gerçekleştirmenize olanak tanır. Bu adım adım kılavuzu takip ederek ve Aspose.Slides kütüphanesinden yararlanarak .NET uygulamalarınızı güçlü PowerPoint özellikleriyle geliştirebilirsiniz.

## Sıkça Sorulan Sorular (SSS)

### Aspose.Slides for .NET nedir?
Aspose.Slides for .NET, içerik oluşturma, düzenleme ve çıkarma dahil olmak üzere .NET uygulamalarının PowerPoint sunumlarıyla çalışmasını sağlayan bir kitaplıktır.

### Aspose.Slides for .NET belgelerini nerede bulabilirim?
 Belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan edinebilirsiniz:[Burada](https://releases.aspose.com/).

### Aspose.Slides for .NET için nasıl geçici lisans alabilirim?
 Geçici lisans talebinde bulunabilirsiniz.[bu bağlantı](https://purchase.aspose.com/temporary-license/).

### Aspose.Slides for .NET için nereden destek alabilirim?
 Şu adreste destek bulabilirsiniz:[Aspose.Slides forumu](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
