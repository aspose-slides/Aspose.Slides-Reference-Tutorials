---
"date": "2025-04-22"
"description": "Python ve Aspose.Slides ile halka grafikleri oluşturmayı öğrenin. Bu adım adım kılavuz, sunumlarınızı geliştirmek için kurulum, özelleştirme ve en iyi uygulamaları kapsar."
"title": "Aspose.Slides&#58;ı Kullanarak Python'da Halka Grafikleri Nasıl Oluşturulur Adım Adım Kılavuz"
"url": "/tr/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Kullanarak Python'da Halka Grafikleri Nasıl Oluşturulur: Adım Adım Kılavuz

Veri görselleştirme alanında, bilgileri etkili bir şekilde sunmak, anlayışı ve karar vermeyi önemli ölçüde etkileyebilir. İster bir iş sunumu hazırlıyor olun, ister karmaşık veri kümelerini analiz ediyor olun, grafikler temel araçlardır. Çeşitli grafik türleri arasında, halka grafikler, sezgisel bir merkez deliğiyle orantılı verileri temsil etmenin çekici bir yolunu sunar. Bu adım adım kılavuz, sunumları düzenlemek için güçlü bir kütüphane olan Aspose.Slides kullanarak Python'da halka grafik oluşturma konusunda size yol gösterecektir.

## Ne Öğreneceksiniz
- Python için Aspose.Slides nasıl kurulur ve kullanılır
- Sunum slaytlarınıza bir halka grafiği ekleme süreci
- Grafik içindeki serileri ve kategorileri özelleştirme
- Etiketler, renkler ve patlama efektleri gibi görsel öğeleri ayarlama
- Aspose.Slides ile performansı optimize etmek için en iyi uygulamalar

## Ön koşullar
Başlamadan önce şunlara sahip olduğunuzdan emin olun:
- **Python Ortamı**: Makinenizde Python 3.x kurulu.
- **Python için Aspose.Slides**: Bu kütüphaneyi pip kullanarak kurun.
- **Python Programlamanın Temel Anlayışı**: Döngüler ve nesne yönelimli programlama konusunda bilgi sahibi olmak faydalı olacaktır.

## Python için Aspose.Slides Kurulumu
Başlamak için pip aracılığıyla Aspose.Slides kütüphanesini yükleyin:

```bash
pip install aspose.slides
```

### Lisans Edinimi
Aspose, sınırlı bir süre için sınırlama olmaksızın özellikleri test etmek için ücretsiz deneme sunar. Bunu elde etmek için:
1. Ziyaret edin [Ücretsiz Deneme](https://releases.aspose.com/slides/python-net/) sayfa.
2. Geçici lisansınızı indirmek ve uygulamak için talimatları izleyin.

Sürekli kullanım için, şu adresten bir abonelik satın almayı düşünün: [Satın Alma Sayfası](https://purchase.aspose.com/buy).

### Temel Başlatma
Aspose.Slides'ı kurduktan sonra aşağıdaki şekilde başlatın:

```python
import aspose.slides as slides

# Presentation sınıfının bir örneğini oluşturun.
with slides.Presentation() as pres:
    # Sunumları manipüle etmek için kullanacağınız kod buraya gelecek.

# Değişiklikleri yaptıktan sonra sunuyu kaydedin.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Uygulama Kılavuzu
Aspose.Slides kurulumu tamamlandıktan sonra, sununuza slayt slayt halka grafiği eklemek için şu adımları izleyin.

### Yeni Bir Sunum Oluşturma ve Slayt Ekleme
Bir örnek oluşturarak başlayın `Presentation` sınıf:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Bu bağlamda slaytlara erişin veya slayt oluşturun.
```

### İlk Slayda Bir Halka Grafiği Ekleme
İlk slayda erişin ve şunu kullanın: `add_chart` yöntem. Grafik türünü şu şekilde belirtin: `DOUGHNUT`, pozisyon ve boyutla birlikte:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Grafik Verilerini Yapılandırma
Mevcut verileri temizleyin ve açıklamayı gizleme gibi ayarları yapılandırın:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Seri ve Kategori Ekleme
Bir halka grafiği için birden fazla seri ve kategori ekleyin. Belirli özelliklere sahip 15 seri oluşturmanın yolu şöyledir:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

Kategorileri benzer şekilde ekleyin:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Her seri için veri noktaları ekleyin.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Her veri noktasının görünümünü özelleştirin.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Son seri için etiket ayarlarını yapılandırın.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### Sunumu Kaydetme
Son olarak sununuzu belirtilen dizine kaydedin:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Pratik Uygulamalar
Halka grafikleri çok yönlüdür ve aşağıdaki gibi çeşitli senaryolarda kullanılabilir:
1. **Bütçe Tahsisi**: Farklı departmanların tahsis edilen fonları nasıl kullandığını gösterir.
2. **Pazar Payı Analizi**: Rekabet eden ürün veya şirketlerin pazar paylarının karşılaştırılması.
3. **Anket Sonuçları**: Tercihler veya memnuniyet düzeylerine ilişkin anket sorularına verilen yanıtların görselleştirilmesi.

## Performans Hususları
Aspose.Slides kullanırken en iyi performansı sağlamak için:
- Kullanımdan sonra nesneleri uygun şekilde atarak bellek kullanımını en aza indirin.
- Sunumları yalnızca gerekli olduğunda belleğe yükleyin ve mümkün olan en kısa sürede kapatın.
- Çok sayıda grafikle çalışıyorsanız slaytları toplu olarak işlemeyi düşünün.

## Çözüm
Bu kılavuzu takip ederek, Python için Aspose.Slides kullanarak dinamik halka grafikleri oluşturmayı öğrendiniz. Bu görselleştirmeler, verileri daha sindirilebilir ve ilgi çekici hale getirerek sunumlarınızı geliştirebilir. Grafiklerinizi daha fazla özelleştirmek ve optimize etmek için kütüphanenin özelliklerini keşfetmeye devam edin.

## SSS Bölümü
1. **Lisans satın almadan Aspose.Slides'ı kullanabilir miyim?**
   - Evet, değerlendirme amaçlı ücretsiz deneme lisansıyla başlayabilirsiniz.
2. **Aspose.Slides'ta grafik renklerini nasıl değiştiririm?**
   - Kullanın `fill_format` Grafik öğeleriniz için istediğiniz rengi ayarlamanızı sağlayan özellik.
3. **Grafikleri resim olarak dışarı aktarmak mümkün mü?**
   - Evet, kütüphanenin işleme yeteneklerini kullanarak grafik içeren slaytları resim formatlarına dönüştürebilirsiniz.
4. **Grafik eklerken karşılaşılan yaygın sorunlar nelerdir?**
   - Grafiğinizi kaydetmeye veya görüntülemeye çalışmadan önce tüm veri noktalarının ve kategorilerin doğru şekilde eklendiğinden emin olun.
5. **Aspose.Slides'ı diğer Python kütüphaneleriyle entegre edebilir miyim?**
   - Kesinlikle! Gelişmiş veri işleme yetenekleri için Pandas gibi kütüphanelerle birlikte kullanabilirsiniz.

## Kaynaklar
- [Aspose.Slides Belgeleri](https://reference.aspose.com/slides/python-net/)
- [Aspose.Slides'ı indirin](https://releases.aspose.com/slides/python-net/)
- [Lisans Satın Alın](https://purchase.aspose.com/buy)
- [Ücretsiz Deneme ve Geçici Lisans](https://releases.aspose.com/slides/python-net/)
- [Aspose Topluluk Forumu](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}