---
"date": "2025-04-22"
"description": "Python için Aspose.Slides'ı kullanarak grafik efsaneleri yazı tipi özelliklerini nasıl özelleştireceğinizi öğrenin. Bireysel efsane girişleri için kalın, italik ve renkli yazı tipleriyle sunumlarınızı geliştirin."
"title": "Aspose.Slides for Python Kullanarak Grafik Efsaneleri Yazı Tipini Özelleştirin&#58; Kapsamlı Bir Kılavuz"
"url": "/tr/python-net/charts-graphs/customize-chart-legends-font-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python için Aspose.Slides Kullanarak Sunumlarda Grafik Efsaneleri Yazı Tipini Özelleştirme

## giriiş
Görsel olarak çekici sunumlar oluşturmak, özellikle de verileri grafikler aracılığıyla görüntülerken önemlidir. Yaygın bir zorluk, grafik açıklamalarını sunum stilinize veya markalama ihtiyaçlarınıza uyacak şekilde özelleştirmektir. Bu kılavuz, Python için Aspose.Slides kullanarak bir grafikteki bireysel açıklama girişleri için kalınlık, italik, boyut ve renk gibi yazı tipi özelliklerinin nasıl özelleştirileceğini gösterir.

**Ne Öğreneceksiniz:**
- Python için Aspose.Slides'ı kurma ve kullanma
- Grafik efsanelerinin yazı tipi özelliklerini özelleştirme
- Kalın, italik ve renkleri değiştirme gibi belirli yazı tipi stilleri uygulama
- Grafikleri özel yazı tipleriyle geliştirmeye yönelik pratik örnekler

Bu özelleştirmeyi nasıl başarabileceğinizi inceleyelim.

## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- **Kütüphaneler**: Python için Aspose.Slides. Pip kullanarak kurun.
- **Çevre**: Makinenizde kurulu bir Python ortamı (tercihen Python 3.x).
- **Bilgi**Python programlamanın temel bilgisi ve sunumları programlı olarak yönetme konusunda aşinalık.

## Python için Aspose.Slides Kurulumu
### Kurulum
Başlamak için terminalinizde aşağıdaki komutu çalıştırarak Aspose.Slides kitaplığını yükleyin:

```bash
pip install aspose.slides
```

### Lisans Edinimi
Aspose.Slides çeşitli lisanslama seçeneklerine sahip ticari bir üründür:
- **Ücretsiz Deneme**: Tam işlevsellik için geçici bir lisans edinin.
- **Geçici Lisans**:Tüm özellikleri sınırsız bir şekilde test etmek için geçici lisans başvurusunda bulunun.
- **Satın almak**:İhtiyaçlarınıza göre abonelik veya kalıcı lisans satın alın.

### Temel Başlatma
Python betiğinizde Aspose.Slides'ı nasıl başlatıp kurabileceğinizi aşağıda bulabilirsiniz:

```python
import aspose.slides as slides

# Bir sunum örneğini başlat\slides.Presentation() şu şekilde pres:
    # Kodunuz burada
```

## Uygulama Kılavuzu
Bu bölümde, bireysel gösterge girişlerinin yazı tipi özelliklerinin nasıl özelleştirileceğini ele alacağız.

### Bir Grafik Ekleme ve Erişim
Öncelikle slaydınıza kümelenmiş sütun grafiği ekleyelim:

```python
# (50, 50) konumuna genişliği 600 ve yüksekliği 400 olan kümelenmiş bir sütun grafiği ekleyin
class ShapeCollection:
    def __init__(self):
        self.chart = None

    def add_chart(self, chart_type, x, y, width, height):
        # Bu, gerçek Aspose.Slides yöntemi için yalnızca bir yer tutucudur.
        return "ChartObject"

class SlideCollection:
    def __init__(self):
        self.shapes = ShapeCollection()

# pres.slides[0].shapes'i simüle etme
slide_shapes = SlideCollection()
chart = slide_shapes.shapes.add_chart(slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 600, 400)
```

### Efsane Yazı Tipi Özelliklerini Özelleştirme
#### Efsane Girişinin Metin Biçimine Erişim
Belirli bir gösterge girişinin yazı tipi özelliklerini değiştirmek için:

```python
class Chart:
    def __init__(self):
        self.legend = "LegendObject"

# chart.legend.entries[1].text_format'ı simüle ediyor
chart_object = Chart()
tf = "SimulatedTextFormatObject"
```

#### Yazı Tipi Özelliklerini Ayarlama
Burada, kalınlık, boyut, italik ve renk gibi yönleri özelleştiriyoruz:

```python
class TextFormat:
    def __init__(self):
        self.portion_format = PortionFormat()

class PortionFormat:
    def __init__(self):
        self.font_bold = False
        self.font_height = 0
        self.font_italic = False
        self.fill_format = FillFormat()

class FillFormat:
    def __init__(self):
        self.fill_type = "None"
        self.solid_fill_color = SolidFillColor()

class SolidFillColor:
    def __init__(self):
        self.color = None

class Color:
    blue = 'blue'

tf.portion_format.font_bold = True
# Yazı tipi boyutunu 20 puntoya ayarla
tf.portion_format.font_height = 20  
tf.portion_format.font_italic = True

# Düz dolgu türünü kullanarak yazı tipi rengini mavi olarak ayarlayın
tf.portion_format.fill_format.fill_type = "SOLID"
tf.portion_format.fill_format.solid_fill_color.color = Color.blue
```

### Sunumu Kaydetme
Son olarak sununuzu şu özelleştirmelerle kaydedin:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_individual_legend_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}