---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET kullanarak dağılım grafikleriyle sunumlarınızı nasıl geliştireceğinizi öğrenin. Grafikleri etkili bir şekilde oluşturmak ve özelleştirmek için bu kapsamlı kılavuzu izleyin."
"title": "Aspose.Slides .NET&#58;i Kullanarak Sunulara Dağılım Grafikleri Ekleme Adım Adım Kılavuz"
"url": "/tr/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides .NET Kullanarak Sunulara Dağılım Grafikleri Ekleme: Adım Adım Kılavuz

## giriiş
Dağılım grafiklerini zahmetsizce entegre ederek sunumlarınızı geliştirmek mi istiyorsunuz? Aspose.Slides for .NET'in gücüyle, grafikler oluşturmak ve özelleştirmek çocuk oyuncağı haline geliyor. Bu eğitim, Aspose.Slides for .NET kullanarak slaytlarınıza dağılım grafikleri eklemenizde size rehberlik edecektir. Bu tekniklerde ustalaşarak, verileri daha etkili bir şekilde sunacak ve görsel olarak çekici sunumlar yaratacaksınız.

**Ne Öğreneceksiniz:**
- Projenizde .NET için Aspose.Slides'ı kurma
- Yeni bir sunum oluşturma ve ilk slaydına erişme
- Slaytlara düzgün çizgiler içeren dağılım grafikleri ekleme
- Mevcut serileri temizleme ve grafiklere yenilerini ekleme
- Gelişmiş görselleştirme için veri noktalarını ve işaretleyici stillerini değiştirme
- Sunumu belirtilen bir dizine kaydetme

Öncelikle ön koşulları gözden geçirelim.

## Ön koşullar
Aspose.Slides'ı .NET için uygulamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- **Aspose.Slides .NET Kütüphanesi için**: Sürüm 23.7 veya üzeri.
- **Geliştirme Ortamı**: Visual Studio 2019 veya daha yenisi, .NET Framework 4.6.1+ veya .NET Core/5+.
- **Temel C# Bilgisi**: C# dilinde nesne yönelimli programlamaya aşinalık.

## Aspose.Slides'ı .NET için Ayarlama
Aspose.Slides'ı kullanmaya başlamak için, projenize kütüphaneyi yüklemeniz gerekir. İşte nasıl:

**.NET CLI kullanımı:**
```bash
dotnet add package Aspose.Slides
```

**Paket Yöneticisi Konsolunu Kullanma:**
```powershell
Install-Package Aspose.Slides
```

**NuGet Paket Yöneticisi Kullanıcı Arayüzü:**
- "Aspose.Slides"ı arayın ve en son sürümü yükleyin.

### Lisans Edinimi
Ücretsiz denemeyle başlayabilir veya tüm özellikleri keşfetmek için geçici bir lisans başvurusunda bulunabilirsiniz. Satın almak için şu adımları izleyin:
1. Ziyaret etmek [Aspose.Slides'ı satın alın](https://purchase.aspose.com/buy) tam lisans satın almak.
2. Geçici lisans için şu adresi ziyaret edin: [Geçici Lisans Sayfası](https://purchase.aspose.com/temporary-license/).

Lisans dosyanızı aldıktan sonra, şunu kullanarak projenize ekleyin:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Uygulama Kılavuzu
Uygulamayı özelliklere göre mantıksal bölümlere ayıracağız.

### Sunum Oluştur ve Slayt Ekle
Bu bölümde bir sunumun nasıl oluşturulacağı ve ilk slaydına nasıl erişileceği gösterilmektedir.

#### Genel bakış
Bir örnek oluşturarak başlayın `Presentation` PowerPoint dosyanızı temsil eden sınıf. Bu nesne modelini kullanarak slaytlara erişmek basittir.

#### Uygulama Adımları
**Adım 1: Sunumu Başlatın**
```csharp
using Aspose.Slides;

// Yeni bir sunum oluştur
t Presentation pres = new Presentation();
```
Bu kod yeni bir sunum belgesi başlatır.

**Adım 2: İlk Slayta Erişim**
```csharp
// Sunumdaki ilk slayda erişin
ISlide slide = pres.Slides[0];
```
Burada, `pres.Slides[0]` ilk slayda erişir. 

### Slayda Dağılım Grafiği Ekle
Şimdi sununuza bir dağılım grafiği ekleyelim.

#### Genel bakış
Grafik eklemek, sunumlarda verileri görsel olarak temsil etmenize yardımcı olabilir. Aspose.Slides, dağılım grafikleri de dahil olmak üzere çeşitli grafik türlerini dahil etmeyi kolaylaştırır.

#### Uygulama Adımları
**Adım 1: Dağılım Grafiği Oluşturun ve Ekleyin**
```csharp
using Aspose.Slides.Charts;

// Düzgün çizgilerle varsayılan bir dağılım grafiği oluşturun ve ekleyin
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Bu kod parçası belirtilen konum ve boyutta bir dağılım grafiği ekler.

### Serileri Temizle ve Grafik Verilerine Ekle
#### Genel bakış
Mevcut serileri temizleyip yenilerini ekleyerek grafiğinizi özelleştirmeniz gerekebilir. Bu bölüm bu işlevi ele almaktadır.

#### Uygulama Adımları
**Adım 1: Grafik Veri Çalışma Kitabına Erişim**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Önceden var olan tüm serileri temizleyin
chart.ChartData.Series.Clear();
```
Bu kod mevcut verileri temizleyerek yeni serilerle başlamayı sağlar.

**Adım 2: Yeni Seri Ekle**
```csharp
// "Seri 1" adında yeni bir seri ekleyin
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// "Seri 2" adında başka bir seri ekleyin
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Bu adımlar grafiğe iki yeni seri ekler.

### İlk Seri Veri Noktalarını ve İşaretçi Stilini Değiştirin
#### Genel bakış
Dağılım grafiklerinizin daha iyi görselleştirilmesi için veri noktalarını ve işaretleyici stillerini özelleştirin.

#### Uygulama Adımları
**Adım 1: Veri Noktalarına Erişim ve Ekleme**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// (1, 3) ve (2, 10) veri noktalarını ekleyin
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Adım 2: İşaretçi Stilini Değiştirin**
```csharp
// Seri türünü değiştirin ve işaretleyici stilini düzenleyin
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### İkinci Seri Veri Noktalarını ve İşaretçi Stilini Değiştirin
#### Genel bakış
Benzer şekilde ikinci seriyi de sunum ihtiyaçlarınıza göre özelleştirebilirsiniz.

#### Uygulama Adımları
**Adım 1: Birden Fazla Veri Noktasına Erişim ve Ekleme**
```csharp
// İkinci grafik serisine erişin
series = chart.ChartData.Series[1];

// Birden fazla veri noktası ekleyin
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Adım 2: İşaretçi Stilini Değiştirin**
```csharp
// İkinci seri için işaretleyici boyutunu ve sembolünü değiştirin
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Sunumu Kaydet
Son olarak sunumunuzu belirtilen dizine kaydedin.

#### Uygulama Adımları
**Adım 1: Dizin Tanımlama**
Çıktı dizininin mevcut olduğundan emin olun. Eğer mevcut değilse, oluşturun:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Sunumu kaydet
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Bu kod sunum dosyanızı belirtilen bir konuma kaydeder.

## Çözüm
Artık Aspose.Slides for .NET kullanarak sunumlarınıza dağılım grafiklerini başarıyla eklediniz. Veri görselleştirme becerilerinizi geliştirmek için kitaplıkta bulunan ek özellikleri ve özelleştirmeleri keşfetmeye devam edin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}