---
"date": "2025-04-22"
"description": "Aspose.Slides with Python kullanarak PowerPoint sunumlarındaki grafik yazı tiplerini nasıl özelleştireceğinizi öğrenin. Ayrıntılı adımlar ve pratik uygulamalar için bu kılavuzu izleyin."
"title": "Aspose.Slides for Python Kullanılarak PowerPoint'te Grafik Yazı Tipleri Nasıl Özelleştirilir"
"url": "/tr/python-net/charts-graphs/customize-chart-fonts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Python Kullanılarak PowerPoint'te Grafik Yazı Tipleri Nasıl Özelleştirilir

## giriiş
PowerPoint sunumlarınızdaki grafiklerin görsel çekiciliğini Python kullanarak mı geliştirmek istiyorsunuz? Yalnız değilsiniz! Birçok geliştirici, grafik yazı tiplerini programatik olarak özelleştirmeye çalışırken zorluklarla karşılaşıyor. Bu kılavuz, PowerPoint'te grafikler için yazı tipi özelliklerini Python kullanarak ayarlama konusunda size yol gösterecek. **Python için Aspose.Slides**Bu tekniklere hakim olarak görsel olarak ilgi çekici ve profesyonel görünümlü slaytları zahmetsizce oluşturabilirsiniz.

Bu eğitimde şunları ele alacağız:
- Python için Aspose.Slides Kurulumu
- Grafik yazı tiplerini kolaylıkla özelleştirin
- Projeleriniz için pratik uygulamalar

Her şeyin hazır olduğundan emin olarak başlayalım!

### Ön koşullar
Başlamadan önce aşağıdaki ön koşulların karşılandığından emin olun:
1. **Python Ortamı**: Python'un yüklü olduğundan emin olun (sürüm 3.6 veya üzeri).
2. **Python için Aspose.Slides**: PowerPoint dosyalarını düzenlemek için bu kütüphaneye ihtiyacınız olacak.
3. **Temel Bilgiler**:Python programlamaya aşinalık ve kütüphanelerle çalışma konusunda temel bir anlayışa sahip olmak faydalı olacaktır.

## Python için Aspose.Slides Kurulumu
Başlamak için şunu yüklemeniz gerekir: `aspose.slides` pip kullanan kütüphane:

```bash
pip install aspose.slides
```

### Lisans Edinme Adımları
- **Ücretsiz Deneme**: Ücretsiz deneme sürümünü indirin [Aspose'un resmi sitesi](https://releases.aspose.com/slides/python-net/).
- **Geçici Lisans**: Daha kapsamlı testler için, onların aracılığıyla geçici bir lisans edinin. [satın alma sayfası](https://purchase.aspose.com/temporary-license/).
- **Satın almak**: Aracı ihtiyaçlarınız için paha biçilmez bulursanız, tam lisans satın almayı düşünün. [Aspose satın alma sitesi](https://purchase.aspose.com/buy).

Kurulum ve lisanslamadan sonra Aspose.Slides'ı Python'da başlatın:

```python
import aspose.slides as slides

# Presentation nesnesini başlat\with slides.Presentation() şu şekilde pres:
    # Kodunuz buraya gelecek
```

## Uygulama Kılavuzu
Bu bölümde adım adım grafik yazı tipi özelliklerinin nasıl ayarlanacağını inceleyeceğiz.

### Kümelenmiş Sütun Grafiği Ekleme
Öncelikle sunumumuza kümelenmiş sütun grafiği ekleyelim:

```python
# Belirtilen konum ve boyutta kümelenmiş sütun grafiği ekleyin.
chart = pres.slides[0].shapes.add_chart(
    slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 500, 400
)
```
**Açıklama**: Bu kod parçası, sununuzun ilk slaydına yeni bir grafik ekler. `add_chart` Bu yöntem, grafik türünü ve slayttaki konumunu ve boyutunu belirtmenizi gerektirir.

### Yazı Tipi Özelliklerini Ayarlama
Şimdi, grafiğimizdeki metnin yazı yüksekliğini ayarlayalım:

```python
# Tablodaki metnin yazı tipi yüksekliğini ayarlayın.
chart.text_format.portion_format.font_height = 20
```
**Açıklama**: Bu satır, grafiğinizdeki tüm metin bölümlerinin yazı tipi boyutunu ayarlar. `font_height` özellik noktalarla belirtilir ve bu değeri tasarım ihtiyaçlarınıza uyacak şekilde ayarlayabilirsiniz.

### Veri Etiketlerini Görüntüleme
Okunabilirliği artırmak için, değerleri veri etiketlerinde göstereceğiz:

```python
# İlk serinin veri etiketlerinde değerleri görüntüleyin.
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```
**Açıklama**: Bu ayar, ilk serideki her veri noktasının değerini göstermesini sağlar. Bu, özellikle tek bakışta kesin bilgileri iletmek için yararlıdır.

### Sununuzu Kaydetme
Son olarak sununuzu istediğiniz yere kaydedin:

```python
# Sunumu belirtilen çıktı dizinine kaydedin.
pres.save(
    "YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_chart_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}