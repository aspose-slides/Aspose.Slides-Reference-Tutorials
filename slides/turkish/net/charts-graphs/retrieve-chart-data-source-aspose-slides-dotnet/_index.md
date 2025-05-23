---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET kullanarak PowerPoint sunumlarındaki grafik veri kaynağı türlerini nasıl etkili bir şekilde alacağınızı öğrenin. Sunumları kolaylıkla otomatikleştirin ve entegre edin."
"title": "Aspose.Slides for .NET Kullanılarak Grafik Veri Kaynağı Türü Nasıl Alınır - Grafikler ve Şemalar"
"url": "/tr/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET Kullanılarak Grafik Veri Kaynağı Türü Nasıl Alınır

## giriiş

PowerPoint sunumlarının grafiklerindeki veri kaynaklarını programatik olarak yönetmekte zorlanıyor musunuz? Birçok geliştirici, Microsoft Office dosyalarındaki grafik verilerini C# kullanarak çıkarmaya ve düzenlemeye çalışırken zorluklarla karşılaşıyor. Bu eğitimde, .NET için Aspose.Slides ile bir PowerPoint sunumundaki grafiğin veri kaynağı türünü alma konusunda size rehberlik edeceğiz. Bu çözüm, sunumları otomatikleştirmeniz veya uygulamalarınıza entegre etmeniz gerektiğinde idealdir.

**Ne Öğreneceksiniz:**
- Aspose.Slides for .NET'i kurma ve kullanma
- PowerPoint slaytlarındaki grafiklerin veri kaynağı türünü alma
- Uygulanabilir olduğunda harici çalışma kitabı yollarının işlenmesi
- Değişiklikleri bir sunuma geri kaydetme

Konuya dalmadan önce bazı ön koşullara değinelim.

## Ön koşullar

Bu eğitimi etkili bir şekilde takip etmek için şunlara ihtiyacınız olacak:
1. **.NET Kütüphanesi için Aspose.Slides:** En son sürümün yüklü olduğundan emin olun.
2. **Geliştirme Ortamı:** Visual Studio'nun veya C# geliştirmeyi destekleyen herhangi bir tercih edilen IDE'nin çalışan bir kurulumu.
3. **Temel Bilgiler:** C#, nesne yönelimli programlama kavramları ve .NET'te dosya yollarının kullanımı konusunda bilgi sahibi olmak.

## Aspose.Slides'ı .NET için Ayarlama

Öncelikle Aspose.Slides kütüphanesini yüklemeniz gerekiyor. İşte nasıl:

**.NET CLI kullanımı:**
```bash
dotnet add package Aspose.Slides
```

**Paket Yöneticisini Kullanma:**
```powershell
Install-Package Aspose.Slides
```

**NuGet Paket Yöneticisi Kullanıcı Arayüzü aracılığıyla:**
NuGet Paket Yöneticisi'nde "Aspose.Slides" ifadesini arayın ve yükleyin.

### Lisans Edinimi
- **Ücretsiz Deneme:** İşlevsellikleri keşfetmek için ücretsiz denemeyle başlayın.
- **Geçici Lisans:** Sınırlama olmaksızın genişletilmiş erişim için geçici lisans edinin.
- **Satın almak:** Eğer Aspose.Slides ihtiyaçlarınızı karşılıyorsa satın almayı düşünebilirsiniz.

Kurulum tamamlandıktan sonra, gerekli ad alanlarını ekleyerek projenizi başlatın:
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## Uygulama Kılavuzu

Bu özelliği açıklık sağlamak için adımlara ayıracağız. Bir grafiğin veri kaynağı türünün nasıl alınacağını inceleyelim.

### Adım 1: Sununuzu Yükleyin

Öncelikle grafiklerinizi içeren PowerPoint sunumunu yükleyin:
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Dizin yolunuza ayarlayın

using (Presentation pres = new Presentation(dataDir + "/pres.pptx"))
{
    // Diğer adımlarla devam edin...
}
```

### Adım 2: Bir Slayda ve Grafiğine Erişim

İlk slayta ve içindeki tabloya erişin:
```csharp
// Sunumun ilk slaydını alın
ISlide slide = pres.Slides[0];

// Şeklin gerçekten bir grafik olduğundan emin olun
IChart chart = (IChart)slide.Shapes[0];
```

### Adım 3: Veri Kaynağı Türünü Alın

Şimdi veri kaynağının türünü alalım:
```csharp
// Grafiğin veri kaynağı türünü alın
ChartDataSourceType sourceType = chart.ChartData.DataSourceType;
```

### Adım 4: Harici Çalışma Kitabı Yollarını Yönetin

Eğer grafiğiniz harici bir çalışma kitabı kullanıyorsa, yolunu şu şekilde alabilirsiniz:
```csharp
if (sourceType == ChartDataSourceType.ExternalWorkbook)
{
    string path = chart.ChartData.ExternalWorkbookPath;
}
```

### Adım 5: Sununuzu Kaydedin

Son olarak, herhangi bir değişiklik yaptıktan sonra sunumu kaydedin:
```csharp
pres.Save(dataDir + "/Result.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}