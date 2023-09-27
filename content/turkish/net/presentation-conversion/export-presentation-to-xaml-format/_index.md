---
title: Sunumu XAML Formatına Dışa Aktarma
linktitle: Sunumu XAML Formatına Dışa Aktarma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak sunumları XAML formatına nasıl aktaracağınızı öğrenin. Zahmetsizce etkileşimli içerik oluşturun!
type: docs
weight: 27
url: /tr/net/presentation-conversion/export-presentation-to-xaml-format/
---

Yazılım geliştirme dünyasında karmaşık görevleri basitleştirebilecek araçlara sahip olmak çok önemlidir. Aspose.Slides for .NET, PowerPoint sunumlarıyla programlı olarak çalışmanıza olanak tanıyan araçlardan biridir. Bu adım adım eğitimde, Aspose.Slides for .NET kullanarak bir sunumun XAML formatına nasıl aktarılacağını keşfedeceğiz. 

## Aspose.Slides for .NET'e Giriş

Eğitime dalmadan önce Aspose.Slides for .NET'i kısaca tanıtalım. Geliştiricilerin Microsoft PowerPoint'e ihtiyaç duymadan PowerPoint sunumları oluşturmasına, değiştirmesine, dönüştürmesine ve yönetmesine olanak tanıyan güçlü bir kitaplıktır. Aspose.Slides for .NET ile PowerPoint sunumlarıyla ilgili çeşitli görevleri otomatikleştirerek geliştirme sürecinizi daha verimli hale getirebilirsiniz.

## Önkoşullar

Bu öğreticiyi takip etmek için aşağıdakilere ihtiyacınız olacak:

1. Aspose.Slides for .NET: .NET projenizde Aspose.Slides for .NET kitaplığının kurulu ve kullanıma hazır olduğundan emin olun.

2. Kaynak Sunumu: XAML formatına aktarmak istediğiniz bir PowerPoint sunumunuz (PPTX) olsun. Bu sunumun yolunu bildiğinizden emin olun.

3. Çıkış Dizini: Oluşturulan XAML dosyalarını kaydetmek istediğiniz dizini seçin.

## 1. Adım: Projenizi Kurun

Bu ilk adımda projemizi oluşturacağız ve gerekli tüm bileşenlerin hazır olduğundan emin olacağız. Projenize Aspose.Slides for .NET kitaplığına bir referans eklediğinizden emin olun.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// Kaynak sunumuna giden yol
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

 Yer değiştirmek`"Your Document Directory"` Kaynak PowerPoint sunumunuzu içeren dizinin yolu ile birlikte. Ayrıca oluşturulan XAML dosyalarının kaydedileceği çıkış dizinini de belirtin.

## 2. Adım: Sunumu XAML'e Aktarın

Şimdi PowerPoint sunumunu XAML formatına aktarmaya devam edelim. Bunu başarmak için Aspose.Slides for .NET'i kullanacağız. 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // Dönüşüm seçenekleri oluşturun
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // Kendi çıktı tasarrufu hizmetinizi tanımlayın
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // Slaytları dönüştür
    pres.Save(xamlOptions);

    // XAML dosyalarını bir çıktı dizinine kaydetme
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

 Bu kod parçacığında kaynak sunumunu yüklüyoruz, XAML dönüştürme seçeneklerini oluşturuyoruz ve kullanarak özel bir çıktı kaydetme hizmeti tanımlıyoruz.`NewXamlSaver`. Daha sonra XAML dosyalarını belirtilen çıktı dizinine kaydediyoruz.

## 3. Adım: Özel XAML Tasarruf Sınıfı

 Özel XAML koruyucuyu uygulamak için adında bir sınıf oluşturacağız.`NewXamlSaver` bunu uygulayan`IXamlOutputSaver` arayüz.

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

Bu sınıf, XAML dosyalarının çıktı dizinine kaydedilmesini yönetecektir.

## Çözüm

Tebrikler! Aspose.Slides for .NET'i kullanarak bir PowerPoint sunumunu XAML formatına nasıl aktaracağınızı başarıyla öğrendiniz. Bu, sunumların manipülasyonunu içeren projeler üzerinde çalışırken değerli bir beceri olabilir.

PowerPoint otomasyon görevlerinizi geliştirmek için Aspose.Slides for .NET'in diğer özelliklerini ve yeteneklerini keşfetmekten çekinmeyin.

## SSS

1. ### Aspose.Slides for .NET nedir?
Aspose.Slides for .NET, PowerPoint sunumlarıyla programlı olarak çalışmaya yönelik bir .NET kitaplığıdır.

2. ### Aspose.Slides for .NET'i nereden edinebilirim?
 Aspose.Slides for .NET'i şu adresten indirebilirsiniz:[Burada](https://purchase.aspose.com/buy).

3. ### Ücretsiz deneme mevcut mu?
 Evet, Aspose.Slides for .NET'in ücretsiz deneme sürümünü edinebilirsiniz[Burada](https://releases.aspose.com/).

4. ### Aspose.Slides for .NET için nasıl geçici lisans alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

5. ### Aspose.Slides for .NET için nereden destek alabilirim?
 Destek ve topluluk tartışmalarını bulabilirsiniz[Burada](https://forum.aspose.com/).

Daha fazla eğitim ve kaynak için şu adresi ziyaret edin:[Aspose.Slides API belgeleri](https://reference.aspose.com/slides/net/).