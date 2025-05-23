---
"description": "Aspose.Slides for .NET kullanarak sunumları XAML formatına nasıl aktaracağınızı öğrenin. Zahmetsizce etkileşimli içerik oluşturun!"
"linktitle": "Sunumu XAML Formatına Aktar"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Sunumu XAML Formatına Aktar"
"url": "/tr/net/presentation-conversion/export-presentation-to-xaml-format/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Sunumu XAML Formatına Aktar


Yazılım geliştirme dünyasında, karmaşık görevleri basitleştirebilecek araçlara sahip olmak önemlidir. Aspose.Slides for .NET, PowerPoint sunumlarıyla programatik olarak çalışmanızı sağlayan bu araçlardan biridir. Bu adım adım eğitimde, Aspose.Slides for .NET kullanarak bir sunumun XAML formatına nasıl aktarılacağını inceleyeceğiz. 

## .NET için Aspose.Slides'a Giriş

Eğitime dalmadan önce, Aspose.Slides for .NET'i kısaca tanıtalım. Geliştiricilerin Microsoft PowerPoint'e ihtiyaç duymadan PowerPoint sunumları oluşturmasına, değiştirmesine, dönüştürmesine ve yönetmesine olanak tanıyan güçlü bir kütüphanedir. Aspose.Slides for .NET ile PowerPoint sunumlarıyla ilgili çeşitli görevleri otomatikleştirebilir ve geliştirme sürecinizi daha verimli hale getirebilirsiniz.

## Ön koşullar

Bu eğitimi takip edebilmek için aşağıdakilere ihtiyacınız olacak:

1. Aspose.Slides for .NET: Aspose.Slides for .NET kitaplığının .NET projenizde yüklü ve kullanıma hazır olduğundan emin olun.

2. Kaynak Sunumu: XAML formatına aktarmak istediğiniz bir PowerPoint sunumunuz (PPTX) var. Bu sunuma giden yolu bildiğinizden emin olun.

3. Çıktı Dizini: Oluşturulan XAML dosyalarını kaydetmek istediğiniz dizini seçin.

## Adım 1: Projenizi Kurun

Bu ilk adımda, projemizi kuracağız ve gerekli tüm bileşenlerin hazır olduğundan emin olacağız. Projenize Aspose.Slides for .NET kütüphanesine bir referans eklediğinizden emin olun.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// Kaynak sunumuna giden yol
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

Yer değiştirmek `"Your Document Directory"` kaynak PowerPoint sunumunuzu içeren dizinin yolunu belirtin. Ayrıca, oluşturulan XAML dosyalarının kaydedileceği çıktı dizinini belirtin.

## Adım 2: Sunumu XAML'e Aktarın

Şimdi PowerPoint sunumunu XAML formatına aktarmaya geçelim. Bunu başarmak için Aspose.Slides for .NET kullanacağız. 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // Dönüştürme seçenekleri oluşturun
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // Kendi çıktı tasarrufu hizmetinizi tanımlayın
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // Slaytları dönüştür
    pres.Save(xamlOptions);

    // XAML dosyalarını bir çıktı dizinine kaydedin
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

Bu kod parçacığında, kaynak sunumunu yüklüyoruz, XAML dönüştürme seçenekleri oluşturuyoruz ve kullanarak özel bir çıktı kaydetme hizmeti tanımlıyoruz. `NewXamlSaver`Daha sonra XAML dosyalarını belirtilen çıktı dizinine kaydediyoruz.

## Adım 3: Özel XAML Tasarruf Sınıfı

Özel XAML koruyucusunu uygulamak için, adında bir sınıf oluşturacağız. `NewXamlSaver` uygulayan `IXamlOutputSaver` arayüz.

```csharp
class NewXamlSaver : IXamlOutputSaver
{
    private Dictionary<string, string> m_result = new Dictionary<string, string>();

    public Dictionary<string, string> Results
    {
        get { return m_result; }
    }

    public void Save(string path, byte[] data)
    {
        string name = Path.GetFileName(path);
        Results[name] = Encoding.UTF8.GetString(data);
    }
}
```

Bu sınıf, XAML dosyalarının çıktı dizinine kaydedilmesini işleyecektir.

## Çözüm

Tebrikler! Aspose.Slides for .NET kullanarak bir PowerPoint sunumunu XAML formatına nasıl aktaracağınızı başarıyla öğrendiniz. Bu, sunumların düzenlenmesini içeren projeler üzerinde çalışırken değerli bir beceri olabilir.

PowerPoint otomasyon görevlerinizi geliştirmek için Aspose.Slides for .NET'in daha fazla özelliğini ve yeteneğini keşfetmekten çekinmeyin.

## SSS

1. ### Aspose.Slides for .NET nedir?
Aspose.Slides for .NET, PowerPoint sunumlarıyla programlı olarak çalışmaya yarayan bir .NET kütüphanesidir.

2. ### Aspose.Slides for .NET'i nereden edinebilirim?
Aspose.Slides for .NET'i şu adresten indirebilirsiniz: [Burada](https://purchase.aspose.com/buy).

3. ### Ücretsiz deneme imkanı var mı?
Evet, Aspose.Slides for .NET'in ücretsiz deneme sürümünü edinebilirsiniz [Burada](https://releases.aspose.com/).

4. ### Aspose.Slides for .NET için geçici lisansı nasıl alabilirim?
Geçici bir lisans alabilirsiniz [Burada](https://purchase.aspose.com/temporary-license/).

5. ### Aspose.Slides for .NET için desteği nereden alabilirim?
Destek ve topluluk tartışmaları bulabilirsiniz [Burada](https://forum.aspose.com/).

Daha fazla öğretici ve kaynak için şurayı ziyaret edin: [Aspose.Slides API belgeleri](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}