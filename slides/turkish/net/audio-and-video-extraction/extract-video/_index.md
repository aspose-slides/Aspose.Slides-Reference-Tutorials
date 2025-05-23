---
"description": "Aspose.Slides for .NET kullanarak PowerPoint slaytlarından videoların nasıl çıkarılacağını öğrenin. Bu adım adım kılavuz sizin için süreci basitleştirir."
"linktitle": "Slayttan Videoyu Çıkar"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides for .NET Kullanılarak Slayttan Video Nasıl Çıkarılır"
"url": "/tr/net/audio-and-video-extraction/extract-video/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for .NET Kullanılarak Slayttan Video Nasıl Çıkarılır


Aspose.Slides for .NET, .NET ortamında PowerPoint sunumlarıyla çalışmanıza olanak tanıyan güçlü bir kütüphanedir. Sağladığı kullanışlı özelliklerden biri de slaytlardan video çıkarma yeteneğidir. Bu adım adım kılavuzda, Aspose.Slides for .NET kullanarak bir PowerPoint slaydından video çıkarmayı göstereceğiz.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Aspose.Slides for .NET: Aspose.Slides for .NET'in yüklü olması gerekir. Bunu şuradan edinebilirsiniz: [web sitesi](https://purchase.aspose.com/buy).

- PowerPoint Sunumu: Çıkarmak istediğiniz videoyu içeren bir PowerPoint sunumu (örneğin, Video.pptx) hazırlayın.

## Ad Alanlarını İçe Aktar

Aspose.Slides for .NET ile çalışmak için gerekli ad alanlarını içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Şimdi bir slayttan video çıkarma sürecini birden fazla adıma bölelim.

## Adım 1: Belge Dizinini Ayarlayın

```csharp
string dataDir = "Your Document Directory";
```

Yer değiştirmek `"Your Document Directory"` PowerPoint sunumunuzun bulunduğu dizinin yolunu belirtin.

## Adım 2: Sunumu Yükleyin

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Bu kod, PowerPoint sunum dosyanızı temsil eden bir Sunum nesnesini başlatır.

## Adım 3: Slaytlar ve Şekiller Arasında Gezinin

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Burada, sunumdaki her slaytta dolaşıyoruz ve ardından ilk slayttaki şekiller üzerinde yineleme yapıyoruz (gerektiğinde değiştiriyoruz).

## Adım 4: Şeklin bir Video Karesi olup olmadığını kontrol edin

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Bu adımda slayttaki şeklin video karesi olup olmadığı kontrol edilir.

## Adım 5: Video Verilerini Çıkarın

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Bu kod, videonun içerik türü ve ikili veriler de dahil olmak üzere video hakkında bilgi çıkarır.

## Adım 6: Videoyu Kaydedin

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Son olarak bu adım, videoyu belirtilen dizindeki yeni bir dosyaya kaydeder.

Bu adımları tamamladığınızda, Aspose.Slides for .NET kullanarak bir PowerPoint slaydından videoyu başarıyla çıkarmış olacaksınız.

## Çözüm

Aspose.Slides for .NET, PowerPoint sunumlarıyla çalışma sürecini basitleştirir ve slaytlardan video çıkarma gibi görevleri kolaylıkla gerçekleştirmenizi sağlar. Bu adım adım kılavuzu izleyerek ve Aspose.Slides kitaplığından yararlanarak, .NET uygulamalarınızı güçlü PowerPoint özellikleriyle geliştirebilirsiniz.

## Sıkça Sorulan Sorular (SSS)

### Aspose.Slides for .NET nedir?
Aspose.Slides for .NET, .NET uygulamalarının PowerPoint sunumlarıyla çalışmasını, içerik oluşturma, düzenleme ve çıkarma gibi işlevleri yerine getirmesini sağlayan bir kütüphanedir.

### Aspose.Slides for .NET'in belgelerini nerede bulabilirim?
Belgeleri bulabilirsiniz [Burada](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET ücretsiz deneme için mevcut mu?
Evet, ücretsiz deneme sürümünü şu adresten alabilirsiniz: [Burada](https://releases.aspose.com/).

### Aspose.Slides for .NET için geçici lisansı nasıl alabilirim?
Geçici lisans talebinde bulunabilirsiniz [bu bağlantı](https://purchase.aspose.com/temporary-license/).

### Aspose.Slides for .NET için desteği nereden alabilirim?
Destek için buraya tıklayabilirsiniz. [Aspose.Slides forumu](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}