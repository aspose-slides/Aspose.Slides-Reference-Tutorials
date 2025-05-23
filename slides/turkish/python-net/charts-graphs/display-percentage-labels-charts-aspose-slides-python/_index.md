---
"date": "2025-04-22"
"description": "Aspose.Slides for Python kullanarak PowerPoint sunumlarındaki grafiklerde yüzde etiketlerini zahmetsizce nasıl görüntüleyeceğinizi öğrenin. Veri görselleştirmesini geliştirmek için mükemmeldir."
"title": "Aspose.Slides for Python Kullanarak Grafiklerde Yüzde Etiketleri Nasıl Görüntülenir? Kapsamlı Bir Kılavuz"
"url": "/tr/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python için Aspose.Slides Kullanılarak Grafiklerde Yüzde Etiketleri Nasıl Görüntülenir

## giriiş

Sunumlarda ve raporlarda verileri etkili bir şekilde görselleştirmek, özellikle oranları veya dağılımları açıkça vurgulamak istediğinizde çok önemlidir. Peki ya bu yüzdelerin doğrudan grafiklerinizde görüntülenmesi gerekiyorsa? Bu kapsamlı kılavuz, şunları kullanarak size yol gösterecektir: **Python için Aspose.Slides** yüzdelik değerlerinin grafik üzerinde etiket olarak zahmetsizce görüntülenmesini sağlamak.

### Ne Öğreneceksiniz:
- Aspose.Slides for Python kullanarak PowerPoint sunumlarına grafikler nasıl oluşturulur ve eklenir.
- Grafiklerinizde veri noktalarını yüzde etiketleri olarak gösterme.
- PowerPoint sunumlarını etkin bir şekilde kaydetme ve yönetme.

Verilerinize içgörülü görseller eklemeye hazır mısınız? Koda dalmadan önce neye ihtiyacınız olduğuna bakalım!

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- **Python için Aspose.Slides**: Bu kütüphane, PowerPoint sunumlarını programlı olarak oluşturmak ve düzenlemek için gereklidir.
- **Python Ortamı**: Python programlama ve ortam kurulumu hakkında temel bilgi.
- **PIP Paket Yöneticisi**: Aspose.Slides'ı yüklemek için kullanılır.

## Python için Aspose.Slides Kurulumu

Aspose.Slides'ı kullanmaya başlamak için öncelikle onu yüklemeniz gerekir:

```bash
pip install aspose.slides
```

### Lisans Alma Adımları:
Ücretsiz denemeye başlayabilir veya Aspose.Slides'ın tüm yeteneklerini keşfetmek için geçici bir lisans edinebilirsiniz. Uzun süreli kullanım için bir abonelik satın almayı düşünün.

#### Temel Başlatma ve Kurulum

Kurulum tamamlandıktan sonra sunum ortamınızı şu şekilde başlatacaksınız:

```python
import aspose.slides as slides

# Bir Sunum nesnesini başlatın
def create_presentation():
    with slides.Presentation() as presentation:
        # Kodunuz burada
```

## Uygulama Kılavuzu

Artık kurulumu tamamladığımıza göre, grafiklerde yüzdeleri görüntülemeye geçelim.

### Grafik Oluşturma ve Veri Ekleme

#### Genel bakış
Her veri noktası için yüzde etiketleri içeren yığılmış bir sütun grafiği oluşturacağız; böylece izleyiciler tek bakışta tam oranları görebilecekler.

##### Adım 1: Slaydınıza Bir Grafik Ekleyin

```python
# Sununuzdaki ilk slayda erişin
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Yığılmış sütun grafiği ekleyin
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Bu kod parçacığı ilk slayta temel bir grafik ekler. `add_chart` yöntem, grafiğin türünü, konumunu ve boyutunu belirtir.

##### Adım 2: Kategoriler için Toplam Değerleri Hesaplayın

```python
def calculate_totals(chart):
    total_for_category = []
    # Her kategori için tüm serilerdeki değerleri toplayın
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Bu döngü, yüzde hesaplamaları için kritik öneme sahip olan serideki tüm veri noktalarının toplamını hesaplar.

#### Yüzde Etiketlerini Ayarlama

##### Adım 3: Seri Veri Noktalarını Yapılandırın

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Gerekli olmayan bilgileri gizlemek için varsayılan etiket seçeneklerini ayarlayın
        series.labels.default_data_label_format.show_legend_key = False
        
        # Yüzde etiketlerini hesaplayın ve ayarlayın
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Yüzde değerine sahip bir metin bölümü oluşturun
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Mevcut etiketleri temizleyin ve yeni yüzde etiketi ekleyin
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Diğer veri etiketi öğelerini gizle
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Bu segment, her veri noktasını işleyerek toplam içindeki yüzdesini hesaplar ve ona bir etiket atar.

### Sununuzu Kaydetme

```python
def save_presentation(presentation, output_directory):
    # Sununuzu değişikliklerle kaydedin
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}