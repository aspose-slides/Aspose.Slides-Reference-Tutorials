---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET kullanarak PowerPoint sunumlarında halka grafiklerini zahmetsizce nasıl oluşturacağınızı ve özelleştireceğinizi öğrenin. Bu kapsamlı kılavuzla görsel veri sunumunuzu geliştirin."
"title": "Aspose.Slides for .NET Kullanarak PowerPoint'te Çörek Grafiği Nasıl Oluşturulur&#58; Adım Adım Kılavuz"
"url": "/tr/net/charts-graphs/create-doughnut-chart-aspose-slides-dot-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET Kullanarak PowerPoint'te Çörek Grafiği Nasıl Oluşturulur: Adım Adım Kılavuz

## giriiş

PowerPoint sunumlarınızı görsel olarak çekici halka grafikleriyle zenginleştirmek, verileri sunma şeklinizi önemli ölçüde iyileştirebilir. Aspose.Slides for .NET, bu grafikleri oluşturmanın ve özelleştirmenin etkili bir yolunu sunar. Bu eğitim, PowerPoint slaytlarınıza delik boyutlarını ayarlama dahil olmak üzere özelleştirilebilir bir halka grafiği eklemek için Aspose.Slides for .NET'i kullanma adımlarında size rehberlik edecektir.

**Ne Öğreneceksiniz:**
- Aspose.Slides'ı .NET için ayarlama
- Slaydınıza bir halka grafiği ekleme adımları
- Halka grafiğinizin delik boyutunu yapılandırma teknikleri
- Pratik uygulamalar ve performans değerlendirmeleri

Hadi dalmadan önce ihtiyacınız olanlarla başlayalım!

## Ön koşullar

Başlamadan önce aşağıdaki gereksinimlerin karşılandığından emin olun:

### Gerekli Kütüphaneler ve Sürümler
- Aspose.Slides for .NET (en son sürüm)
- Visual Studio veya .NET geliştirmeyi destekleyen herhangi bir uyumlu IDE

### Çevre Kurulum Gereksinimleri
- .NET Framework yüklü bir Windows ortamı
- C# programlamanın temel bilgisi

## Aspose.Slides'ı .NET için Ayarlama

Başlamak için Aspose.Slides kitaplığını yüklemeniz gerekir. Bunu farklı yöntemler kullanarak nasıl yapabileceğiniz aşağıda açıklanmıştır:

**.NET CLI kullanımı:**
```bash
dotnet add package Aspose.Slides
```

**Paket Yöneticisi Konsolunu Kullanma:**
```powershell
Install-Package Aspose.Slides
```

**NuGet Paket Yöneticisi Kullanıcı Arayüzü:**
"Aspose.Slides" ifadesini arayın ve en son sürümü doğrudan IDE'nizin NuGet arayüzü aracılığıyla yükleyin.

### Lisans Edinme Adımları
1. **Ücretsiz Deneme:** Özellikleri değerlendirmek için öncelikle ücretsiz deneme sürümünü indirin.
2. **Geçici Lisans:** Daha fazla zamana ihtiyacınız varsa Aspose'dan geçici lisans talep edin.
3. **Satın almak:** Uzun süreli kullanım için tam sürümü satın almayı düşünebilirsiniz.

Kurulum tamamlandıktan sonra projenizi şu temel kurulumla başlatın:
```csharp
using Aspose.Slides;

// Yeni bir Sunum nesnesi başlatın
Presentation presentation = new Presentation();
```

## Uygulama Kılavuzu

Aspose.Slides for .NET kullanarak bir halka grafiği oluşturma sürecini yönetilebilir adımlara bölelim.

### Bir Çörek Grafiği Oluşturun

#### Genel bakış
PowerPoint slaydınıza bir halka grafiği ekleyerek, konumunu ve boyutunu ayarlayarak başlayacağız.

**Grafik Ekleme:**
```csharp
using Aspose.Slides.Charts;

// Sunumdaki ilk slayda erişin (varsayılan olarak bir tane oluşturulur)
ISlide slide = presentation.Slides[0];

// Slayta (50, 50) konumuna 400 birim genişlik ve yükseklikte bir halka grafiği ekleyin
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 50, 50, 400, 400);
```
- **Parametreler:** `ChartType.Doughnut`, x konumu: 50, y konumu: 50, genişlik: 400, yükseklik: 400.

### Delik Boyutunu Ayarla

#### Genel bakış
Daha sonra halka grafiğinin delik boyutunu görsel olarak çekici hale getirecek şekilde yapılandıracağız.

**Delik Boyutunun Yapılandırılması:**
```csharp
// Halka grafiği için delik boyutunu %90 olarak ayarlayın
chart.ChartData.SeriesGroups[0].DoughnutHoleSize = 90;
```
- **Anahtar Yapılandırması:** `DoughnutHoleSize` Merkezin ne kadarının "kesileceğini" belirler. 0 ile 100 arasındaki bir değer yüzdeyi temsil eder.

### Sununuzu Kaydedin

Son olarak değişikliklerinizi yeni bir PowerPoint dosyasına kaydedin:
```csharp
// Sunumun kaydedileceği yolu tanımlayın
string outputPath = \@"YOUR_OUTPUT_DIRECTORY\DoughnutHoleSize_out.pptx";

// Değiştirilen sunumu PPTX formatında kaydedin
presentation.Save(outputPath, SaveFormat.Pptx);
```
- **Not:** Yer değiştirmek `YOUR_OUTPUT_DIRECTORY` İstediğiniz dosya konumuyla.

### Sorun Giderme İpuçları

- Aspose.Slides'ın doğru şekilde yüklendiğinden ve içe aktarıldığından emin olun.
- Sunumu kaydetmeden önce çıktı dizin yolunuzun mevcut olduğundan emin olun.

## Pratik Uygulamalar

Aspose.Slides for .NET ile oluşturulan halka grafikleri çeşitli senaryolarda kullanılabilir:

1. **İşletme Raporları:** Bütçe dağılımları veya satış dağılımları gibi finansal verileri gösterin.
2. **Pazarlama Analitiği:** Farklı markalar arasındaki pazar payı yüzdelerini görüntüleyin.
3. **Eğitim Materyali:** İstatistiksel kavramları görsel olarak ilgi çekici bir şekilde açıklamak için kullanın.

Kurumsal ortamlarda otomatik rapor oluşturma ve dağıtım için Aspose.Slides'ı diğer sistemlerle entegre edin.

## Performans Hususları

Büyük sunumlarla veya çok sayıda grafikle çalışırken aşağıdaki ipuçlarını göz önünde bulundurun:

- Slaytlara eklemeden önce veri işlemeyi optimize edin.
- Hafızayı korumak için mümkün olduğunca sunum nesnelerini yeniden kullanın.
- Performans iyileştirmelerinden yararlanmak için Aspose.Slides kitaplığınızı düzenli olarak güncelleyin.

## Çözüm

Aspose.Slides for .NET kullanarak bir halka grafiğinin nasıl oluşturulacağını ve özelleştirileceğini öğrendiniz. Bu çok yönlü araç, sunumlarınızın görsel çekiciliğini artırarak verilerin bir bakışta anlaşılmasını kolaylaştırır.

**Sonraki Adımlar:**
Aspose.Slides'ta bulunan diğer grafik türlerini keşfedin veya animasyonlar gibi gelişmiş özellikleri inceleyin.

Denemeye hazır mısınız? Aşağıdaki kaynaklar bölümüne gidin ve denemeye başlayın!

## SSS Bölümü

1. **Aspose.Slides for .NET ne için kullanılır?**  
   PowerPoint sunumlarını programlı olarak oluşturmak, değiştirmek ve dönüştürmek için bir kütüphanedir.

2. **Donut dilimlerinin rengini nasıl değiştirebilirim?**  
   Kullanmak `chart.ChartData.SeriesGroups[0].Series[i].Format.Fill.FillType` dolgu özelliklerini ayarlamak için.

3. **Tek bir sunumda birden fazla grafik oluşturabilir miyim?**  
   Evet, grafik oluşturma adımlarını farklı slaytlarda veya konumlarda tekrarlayarak ihtiyacınız olduğu kadar çok grafik ekleyebilirsiniz.

4. **Aspose.Slides for .NET'i ticari amaçlı kullanmak için nasıl lisanslayabilirim?**  
   Ticari amaçlı kullanmak için resmi Aspose web sitesi üzerinden lisans satın alın.

5. **Sunumum düzgün şekilde kaydedilmezse ne yapmalıyım?**  
   Dosya yolu izinlerini kontrol edin ve proje referanslarınızın güncel olduğundan emin olun.

## Kaynaklar

- [Aspose.Slides Belgeleri](https://reference.aspose.com/slides/net/)
- [.NET için Aspose.Slides'ı indirin](https://releases.aspose.com/slides/net/)
- [Lisans Satın Alın](https://purchase.aspose.com/buy)
- [Ücretsiz Deneme Sürümü](https://releases.aspose.com/slides/net/)
- [Geçici Lisans Talebi](https://purchase.aspose.com/temporary-license/)
- [Destek Forumu](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}