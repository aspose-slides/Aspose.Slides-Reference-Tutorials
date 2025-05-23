---
"date": "2025-04-22"
"description": "Aspose.Slides for Python kullanarak PowerPoint'te halka grafikleri oluşturmayı ve özelleştirmeyi öğrenin. Bu eğitim, delik boyutunu ayarlamayı, sunumları kaydetmeyi ve en iyi uygulamaları kapsar."
"title": "Aspose.Slides for Python Kullanılarak Özel Delik Boyutuna Sahip PowerPoint'te Bir Çörek Grafiği Nasıl Oluşturulur"
"url": "/tr/python-net/charts-graphs/create-doughnut-chart-aspose-python-custom-hole-size/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Python Kullanılarak Özel Delik Boyutuna Sahip PowerPoint'te Bir Çörek Grafiği Nasıl Oluşturulur

## giriiş
PowerPoint'te görsel olarak çekici grafikler oluşturmak verilerinizi daha ilgi çekici ve anlaşılması daha kolay hale getirebilir. Bu grafikleri programatik olarak oluştururken karşılaşılan yaygın bir zorluk, özelleştirme seçeneklerinin olmamasıdır. Bu eğitim, Python için Aspose.Slides kullanarak özel delik boyutuna sahip bir halka grafiğinin nasıl oluşturulacağını göstererek bunu çözer.

**Anahtar kelimeler:** Aspose.Slides Python, Halka Grafiği, Özel Delik Boyutu

### Ne Öğreneceksiniz:
- Python için Aspose.Slides'ı kurma ve kullanma
- PowerPoint'te halka grafiği oluşturma
- Donut grafiğinizin delik boyutunu özelleştirme
- Sunuları kaydetme ve dışa aktarma konusunda en iyi uygulamalar

## Ön koşullar
Başlamadan önce şunlara sahip olduğunuzdan emin olun:
- **Python 3.x** sisteminize yüklenmiştir.
- Python programlama kavramlarının temel bilgisi.
- The `aspose.slides` kütüphane (kurulum talimatları aşağıda verilmiştir).

## Python için Aspose.Slides Kurulumu
Başlamak için pip kullanarak Python için Aspose.Slides'ı yükleyin:

```bash
pip install aspose.slides
```

### Lisans Edinimi
Aspose, belge sayısı veya kullanım süresi konusunda herhangi bir sınırlama olmaksızın özelliklerini keşfetmenize olanak tanıyan ücretsiz bir deneme sürümü sunuyor:
- **Ücretsiz Deneme:** Tam kapasiteyi test etmek için geçici bir lisansla başlayın.
- **Geçici Lisans:** Değerlendirme amaçlı kullanılabilir.
- **Satın almak:** Uzun süreli kullanım için lisans satın almayı düşünebilirsiniz.

Kurulum ve ayarlamadan sonra, sunumları programatik olarak oluşturmaya başlayabilirsiniz. Aspose.Slides'ı başlatma yöntemi şöyledir:

```python
import aspose.slides as slides

# Bir sunum nesnesini başlat
class PresentationCreator:
    def create_presentation(self):
        with slides.Presentation() as presentation:
            # Kodunuz buraya gelecek
```

## Uygulama Kılavuzu
Bu bölümde, Aspose.Slides kullanarak PowerPoint'te bir halka grafiği oluşturmak ve özelleştirmek için gereken adımlar açıklanmaktadır.

### Adım 1: Bir Slayda Erişim ve Slaydı Değiştirme
Başlamak için, sununuzdaki ilk slayda erişin. Burası, özel donut grafiğinizi ekleyeceğiniz yerdir.

```python
# İlk slayda erişin
class SlideModifier:
    def modify_slide(self, presentation):
        first_slide = presentation.slides[0]
```

### Adım 2: Bir Çörek Grafiği Ekleme
Herhangi bir slayda konumunu ve boyutunu belirterek bir halka grafiği ekleyebilirsiniz. Burada, onu 400x400 boyutlarında (50, 50) koordinatlarına yerleştireceğiz.

```python
class ChartAdder:
    def add_doughnut_chart(self, first_slide):
        # Bir halka grafiği ekleyin
        chart = first_slide.shapes.add_chart(
            slides.charts.ChartType.DOUGHNUT,
            50, 50, 400, 400
        )
```

### Adım 3: Delik Boyutunu Özelleştirme
Donut grafiğinizin delik boyutunu ayarlamak basittir. Belirgin bir etki için %90'a ayarlayın.

```python
class ChartCustomizer:
    def customize_hole_size(self, chart):
        # Özel delik boyutunu ayarlayın
        chart.chart_data.series_groups[0].doughnut_hole_size = 90
```

### Adım 4: Sununuzu Kaydetme
Son olarak sununuzu seçtiğiniz dosya adıyla istediğiniz yere kaydedin.

```python
class PresentationSaver:
    def save_presentation(self, presentation):
        # Sunumu kaydet
        presentation.save(
            "charts_doughnut_chart_hole_out.pptx",
            slides.export.SaveFormat.PPTX
        )
```

## Pratik Uygulamalar
Özelleştirilmiş halka grafikleri oluşturmak çeşitli senaryolarda faydalı olabilir, örneğin:
- **İşletme Raporları:** Görsel olarak belirgin segmentlerle temel performans göstergelerini vurgulama.
- **Eğitim İçeriği:** İstatistiksel verileri öğrencilere veya meslektaşlarına göstermek.
- **Pazarlama Materyalleri:** Ürün dökümlerini veya müşteri demografisini sergilemek.

Grafiklerin resim olarak dışarı aktarılması veya Aspose'un kapsamlı API'sini kullanarak web uygulamalarına gömülmesiyle diğer sistemlerle entegrasyonlar mümkündür.

## Performans Hususları
Aspose.Slides ile çalışırken en iyi performansı elde etmek için şu ipuçlarını göz önünde bulundurun:
- Yalnızca gerekli slaytları yükleyerek kaynak kullanımını en aza indirin.
- Sunumları kullandıktan hemen sonra kapatarak hafızayı etkili bir şekilde yönetin.
- Birden fazla grafiği aynı anda oluşturmak için toplu işlemeyi kullanın.

En iyi uygulamaları takip etmek, uygulamanızın sorunsuz ve verimli bir şekilde çalışmasını sağlar.

## Çözüm
Bu kılavuzu takip ederek, Aspose.Slides for Python kullanarak PowerPoint'te özel delik boyutuna sahip bir halka grafiğinin nasıl oluşturulacağını öğrendiniz. Bu, yalnızca sunumlarınızın görsel çekiciliğini artırmakla kalmaz, aynı zamanda daha fazla veri temsil esnekliğine de olanak tanır.

Aspose.Slides'ın yeteneklerini daha fazla keşfetmek için diğer grafik türleri ve sunum özellikleriyle denemeler yapmayı düşünün. İyi kodlamalar!

## SSS Bölümü
1. **Bir halka grafiği için ayarlayabileceğim maksimum delik boyutu nedir?**
   - Tam daire grafiği için bunu %100'e kadar ayarlayabilirsiniz.
2. **Aspose.Slides kullanarak bir PowerPoint dosyasındaki mevcut grafikleri değiştirebilir miyim?**
   - Evet, mevcut sunumlarınızı yükleyebilir ve düzenleyebilirsiniz.
3. **Sunumları kaydederken oluşan hataları nasıl düzeltebilirim?**
   - Çıkış yolunun yazılabilir olduğundan emin olun ve izin sorunlarını kontrol edin.
4. **Halka grafiklerin dışında diğer grafik türleri için destek var mı?**
   - Kesinlikle, Aspose.Slides çok çeşitli grafik türlerini destekler.
5. **Aspose.Slides web uygulamalarıyla kullanılabilir mi?**
   - Evet, API'si arka uç sistemlere entegre edilebilir ve web servisleri aracılığıyla kullanıma sunulabilir.

## Kaynaklar
- [Belgeleme](https://reference.aspose.com/slides/python-net/)
- [İndirmek](https://releases.aspose.com/slides/python-net/)
- [Satın almak](https://purchase.aspose.com/buy)
- [Ücretsiz Deneme](https://releases.aspose.com/slides/python-net/)
- [Geçici Lisans](https://purchase.aspose.com/temporary-license/)
- [Destek Forumu](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}