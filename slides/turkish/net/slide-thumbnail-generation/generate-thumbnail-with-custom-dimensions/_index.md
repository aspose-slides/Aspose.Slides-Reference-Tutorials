---
"description": "Aspose.Slides for .NET kullanarak PowerPoint sunumlarından özel küçük resim görüntüleri oluşturmayı öğrenin. Kullanıcı deneyimini ve işlevselliği geliştirin."
"linktitle": "Özel Boyutlarla Küçük Resim Oluştur"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Slaytlarda Özel Boyutlarla Küçük Resim Oluşturma"
"url": "/tr/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Slaytlarda Özel Boyutlarla Küçük Resim Oluşturma


PowerPoint sunumlarınızın özel küçük resim görüntülerini oluşturmak, etkileşimli bir uygulama oluşturuyor, kullanıcı deneyimini geliştiriyor veya çeşitli platformlar için içeriği optimize ediyor olun, değerli bir varlık olabilir. Bu eğitimde, Aspose.Slides for .NET kitaplığını kullanarak PowerPoint sunumlarından özel küçük resim görüntüleri oluşturma sürecinde size rehberlik edeceğiz. Bu güçlü kitaplık, PowerPoint dosyalarını .NET uygulamalarında programatik olarak düzenlemenize, dönüştürmenize ve geliştirmenize olanak tanır.

## Ön koşullar

Özel küçük resim görüntüleri oluşturmaya başlamadan önce, aşağıdaki ön koşulların mevcut olduğundan emin olun:

### 1. .NET için Aspose.Slides

Projenizde Aspose.Slides for .NET kütüphanesinin yüklü olması gerekir. Henüz yüklü değilse, gerekli belgeleri ve indirme bağlantılarını bulabilirsiniz [Burada](https://reference.aspose.com/slides/net/).

### 2. Bir PowerPoint Sunumu

Özel bir küçük resim görüntüsü oluşturmak istediğiniz PowerPoint sunumuna sahip olduğunuzdan emin olun. Bu sunum, proje dizininizde erişilebilir olmalıdır.

### 3. Geliştirme Ortamı

Bu eğitimi takip edebilmek için, C# kullanarak .NET programlama hakkında çalışma bilgisine sahip olmanız ve Visual Studio gibi bir geliştirme ortamı kurmuş olmanız gerekir.

Artık ön koşulları ele aldığımıza göre, özel küçük resimler oluşturma sürecini adım adım talimatlara ayıralım.

## Ad Alanlarını İçe Aktar

Öncelikle, C# kodunuza gerekli ad alanlarını eklemeniz gerekir. Bu ad alanları, Aspose.Slides ile çalışmanıza ve PowerPoint sunumlarını düzenlemenize olanak tanır.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Adım 1: Sunumu Yükleyin

Başlamak için, özel bir küçük resim görüntüsü oluşturmak istediğiniz PowerPoint sunumunu yükleyin. Bu, Aspose.Slides kitaplığı kullanılarak gerçekleştirilir.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Sunum dosyasını temsil eden bir Sunum sınıfı örneği oluşturun
using (Presentation pres = new Presentation(srcFileName))
{
    // Küçük resim oluşturma kodunuz buraya gelecek
}
```

## Adım 2: Slayda Erişim

Yüklenen sunum içinde, özel küçük resim görüntüsünü oluşturmak istediğiniz belirli slayta erişmeniz gerekir. Slaydı dizinine göre seçebilirsiniz.

```csharp
// İlk slayda erişin (ihtiyacınız olduğunda dizini değiştirebilirsiniz)
ISlide sld = pres.Slides[0];
```

## Adım 3: Özel Küçük Resim Boyutlarını Tanımlayın

Özel küçük resim görüntünüz için istediğiniz boyutları belirtin. Genişliği ve yüksekliği uygulamanızın gereksinimlerine göre piksel olarak tanımlayabilirsiniz.

```csharp
int desiredX = 1200; // Genişlik
int desiredY = 800;  // Yükseklik
```

## Adım 4: Ölçekleme Faktörlerini Hesaplayın

Slaydın en boy oranını korumak için slaydın boyutuna ve istediğiniz boyutlara göre X ve Y boyutları için ölçekleme faktörlerini hesaplayın.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Adım 5: Küçük Resim Görüntüsünü Oluşturun

Belirtilen özel boyutlarla slaydın tam ölçekli bir görüntüsünü oluşturun ve JPEG formatında diske kaydedin.

```csharp
// Tam ölçekli bir görüntü oluşturun
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Görüntüyü JPEG formatında diske kaydedin
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Artık bu adımları takip ettiğinize göre, PowerPoint sununuzdan özel bir küçük resim görüntüsünü başarıyla oluşturmuş olmalısınız.

## Çözüm

Aspose.Slides for .NET kullanarak PowerPoint sunumlarından özel küçük resim görüntüleri oluşturmak, uygulamalarınızın kullanıcı deneyimini ve işlevselliğini artırabilecek değerli bir beceridir. Bu eğitimde özetlenen adımları izleyerek, özel gereksinimlerinizi karşılayan özel küçük resimleri kolayca oluşturabilirsiniz.

---

## SSS (Sıkça Sorulan Sorular)

### Aspose.Slides for .NET nedir?
Aspose.Slides for .NET, geliştiricilerin .NET uygulamalarında PowerPoint sunumlarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir kütüphanedir.

### Aspose.Slides for .NET'in belgelerini nerede bulabilirim?
Belgeleri bulabilirsiniz [Burada](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET'i kullanmak ücretsiz mi?
Aspose.Slides for .NET ticari bir kütüphanedir. Fiyatlandırma ve lisanslama bilgilerini bulabilirsiniz [Burada](https://purchase.aspose.com/buy).

### Aspose.Slides for .NET'i kullanmak için gelişmiş programlama becerilerine ihtiyacım var mı?
.NET programlama hakkında bir miktar bilgi sahibi olmak faydalı olsa da, .NET için Aspose.Slides, PowerPoint sunumlarıyla çalışmayı basitleştiren kullanıcı dostu bir API sağlar.

### Aspose.Slides for .NET için teknik destek mevcut mu?
Evet, teknik desteğe ve topluluk forumlarına erişebilirsiniz [Burada](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}