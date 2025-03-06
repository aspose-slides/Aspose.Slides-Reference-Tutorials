---
title: Özel Boyutlu Slaytlarda Küçük Resim Oluşturma
linktitle: Özel Boyutlarla Küçük Resim Oluşturun
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint sunumlarından özel küçük resimler oluşturmayı öğrenin. Kullanıcı deneyimini ve işlevselliğini geliştirin.
weight: 13
url: /tr/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


İster etkileşimli bir uygulama oluşturuyor olun, ister kullanıcı deneyimini geliştiriyor olun, ister içeriği çeşitli platformlar için optimize ediyor olun, PowerPoint sunumlarınızın özel küçük resim görüntülerini oluşturmak değerli bir varlık olabilir. Bu eğitimde, Aspose.Slides for .NET kütüphanesini kullanarak PowerPoint sunumlarından özel küçük resimler oluşturma sürecinde size rehberlik edeceğiz. Bu güçlü kitaplık, PowerPoint dosyalarını .NET uygulamalarında programlı olarak değiştirmenize, dönüştürmenize ve geliştirmenize olanak tanır.

## Önkoşullar

Özel küçük resimler oluşturmaya başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

### 1. Aspose.Slides for .NET

 Aspose.Slides for .NET kütüphanesinin projenizde kurulu olması gerekir. Henüz yapmadıysanız gerekli belgeleri ve indirme bağlantılarını bulabilirsiniz.[Burada](https://reference.aspose.com/slides/net/).

### 2. PowerPoint Sunumu

Özel bir küçük resim oluşturmak istediğiniz PowerPoint sunumunuza sahip olduğunuzdan emin olun. Bu sunuma proje dizininizden erişilebilir olmalıdır.

### 3. Geliştirme Ortamı

Bu öğreticiyi takip etmek için, C# kullanarak .NET programlama konusunda çalışma bilgisine ve Visual Studio gibi bir geliştirme ortamı kurulumuna sahip olmanız gerekir.

Artık önkoşulları ele aldığımıza göre, özel küçük resimler oluşturma sürecini adım adım talimatlara ayıralım.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını C# kodunuza eklemeniz gerekir. Bu ad alanları Aspose.Slides ile çalışmanıza ve PowerPoint sunumlarını değiştirmenize olanak tanır.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## 1. Adım: Sunuyu Yükleyin

Başlamak için özel bir küçük resim oluşturmak istediğiniz PowerPoint sunumunu yükleyin. Bu, Aspose.Slides kütüphanesi kullanılarak gerçekleştirilir.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Sunum dosyasını temsil eden bir Sunum sınıfının örneğini oluşturun
using (Presentation pres = new Presentation(srcFileName))
{
    // Küçük resim oluşturmaya yönelik kodunuz buraya gelecek
}
```

## 2. Adım: Slayta Erişin

Yüklenen sunumda, özel küçük resim görüntüsünü oluşturmak istediğiniz belirli slayda erişmeniz gerekir. Slaytı indeksine göre seçebilirsiniz.

```csharp
// İlk slayda erişin (gerektiğinde dizini değiştirebilirsiniz)
ISlide sld = pres.Slides[0];
```

## 3. Adım: Özel Küçük Resim Boyutlarını Tanımlayın

Özel küçük resim görseliniz için istediğiniz boyutları belirtin. Uygulamanızın gereksinimlerine göre genişlik ve yüksekliği piksel cinsinden tanımlayabilirsiniz.

```csharp
int desiredX = 1200; // Genişlik
int desiredY = 800;  // Yükseklik
```

## Adım 4: Ölçeklendirme Faktörlerini Hesaplayın

Slaydın en boy oranını korumak için slaydın boyutuna ve istediğiniz boyutlara göre X ve Y boyutlarına ilişkin ölçeklendirme faktörlerini hesaplayın.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Adım 5: Küçük Resim Görüntüsünü Oluşturun

Belirtilen özel boyutlarla slaydın tam ölçekli bir görüntüsünü oluşturun ve bunu JPEG formatında diske kaydedin.

```csharp
// Tam ölçekli bir görüntü oluşturun
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Görüntüyü JPEG formatında diske kaydedin
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Artık bu adımları izlediğinize göre PowerPoint sunumunuzdan başarıyla özel bir küçük resim oluşturmuş olmalısınız.

## Çözüm

Aspose.Slides for .NET'i kullanarak PowerPoint sunumlarından özel küçük resimler oluşturmak, uygulamalarınızın kullanıcı deneyimini ve işlevselliğini geliştirebilecek değerli bir beceridir. Bu eğitimde özetlenen adımları izleyerek, özel gereksinimlerinizi karşılayan özel küçük resimleri kolayca oluşturabilirsiniz.

---

## SSS (Sık Sorulan Sorular)

### Aspose.Slides for .NET nedir?
Aspose.Slides for .NET, geliştiricilerin .NET uygulamalarında PowerPoint sunumlarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir kitaplıktır.

### Aspose.Slides for .NET belgelerini nerede bulabilirim?
 Belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET'in kullanımı ücretsiz mi?
 Aspose.Slides for .NET ticari bir kütüphanedir. Fiyatlandırma ve lisans bilgilerini bulabilirsiniz[Burada](https://purchase.aspose.com/buy).

### Aspose.Slides for .NET'i kullanmak için ileri düzey programlama becerilerine ihtiyacım var mı?
Biraz .NET programlama bilgisi faydalı olsa da Aspose.Slides for .NET, PowerPoint sunumlarıyla çalışmayı kolaylaştıran kullanıcı dostu bir API sağlar.

### Aspose.Slides for .NET için teknik destek mevcut mu?
 Evet, teknik desteğe ve topluluk forumlarına erişebilirsiniz[Burada](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
