---
"date": "2025-04-23"
"description": "Aspose.Slides for Python'ı kullanarak sunumlardaki grafik başlıklarının dönüş açısını nasıl ayarlayacağınızı öğrenin, böylece okunabilirliği ve estetiği artırın."
"title": "Python için Aspose.Slides'ta Bir Grafiğin Dikey Eksen Başlığı Dönmesi Nasıl Ayarlanır"
"url": "/tr/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python için Aspose.Slides'ta Bir Grafiğin Dikey Eksen Başlığı Dönmesi Nasıl Ayarlanır

## giriiş

Veri sunumlarında, grafik okunabilirliğini iyileştirmek çok önemlidir. Python için Aspose.Slides kullanarak grafiğinizin dikey eksen başlığının dönüş açısını ayarlamak, başlıkların slaytlarınızda düzgün bir şekilde oturmasını veya öne çıkmasını sağlayabilir. Bu eğitim, hem işlevselliği hem de görsel çekiciliği artırmak için bu dönüş açısını ayarlama konusunda size rehberlik eder.

**Ne Öğreneceksiniz:**
- Python için Aspose.Slides nasıl kurulur ve yapılandırılır.
- Slaytlarınıza grafik ekleme ve özelleştirme adımları.
- Grafik başlıklarının dönüş açısını ayarlama teknikleri.
- Veri görselleştirmede bu özelliklerin gerçek dünya uygulamaları.

Uygulamaya geçmeden önce ön koşulları ele alalım.

## Ön koşullar

Başlamadan önce şunlara sahip olduğunuzdan emin olun:
- **Python Ortamı**: Python 3.x'i şuradan yükleyin: [python.org](https://www.python.org/).
- **Aspose.Slides Kütüphanesi**: Sunumları etkili bir şekilde yönetmek için pip aracılığıyla kurulum yapın.
- **Python Programlamanın Temel Bilgileri**:Python sözdizimi ve dosya işlemlerine aşina olmanız takip etmenize yardımcı olacaktır.

## Python için Aspose.Slides Kurulumu

Aspose.Slides'ı kullanmak için pip kullanarak yükleyin. Terminalinizi veya komut isteminizi açın ve şunu çalıştırın:

```bash
pip install aspose.slides
```

### Lisans Edinme Adımları

Aspose farklı lisans seçenekleri sunuyor:
- **Ücretsiz Deneme**: Deneme sürümünü şu adresten indirin: [Aspose'un yayın sayfası](https://releases.aspose.com/slides/python-net/).
- **Geçici Lisans**: Genişletilmiş özellikler için geçici bir lisans edinin [satın alma portalı](https://purchase.aspose.com/temporary-license/).
- **Satın almak**: Aracı vazgeçilmez bulursanız, satın almayı düşünün. [Aspose satın alma sayfası](https://purchase.aspose.com/buy).

#### Temel Başlatma ve Kurulum

Python betiğinizde Aspose.Slides'ı nasıl başlatacağınız aşağıda açıklanmıştır:

```python
import aspose.slides as slides

# Bir sunum nesnesi oluşturun
def main():
    with slides.Presentation() as pres:
        # Kodunuz buraya gelecek
        pass

if __name__ == "__main__":
    main()
```

## Uygulama Kılavuzu

### Grafikleri Ekleme ve Özelleştirme

#### Genel bakış

Bu bölümde slaydınıza kümelenmiş sütun grafiği ekleyeceğiz ve dikey eksen başlığının dönüş açısını ayarlayarak özelleştireceğiz.

#### Adımlar:

##### Adım 1: Kümelenmiş Sütun Grafiği Ekleme

Belirli koordinatlarda ve tanımlanmış boyutlarda bir grafik ekleyerek başlayın:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # 1. slayda kümelenmiş sütun grafiği ekleyin
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Adım 2: Dikey Eksen Başlığını Yapılandırın

Dikey eksen başlığı için dönüş açısını etkinleştirin ve ayarlayın:

```python
def configure_chart(chart):
    # Dikey eksen başlığını etkinleştir
    chart.axes.vertical_axis.has_title = True
    
    # Dönüş açısını 90 dereceye ayarlayın
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Adım 3: Sununuzu Kaydedin

Son olarak sununuzu değişikliklerle kaydedin:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Sunumu kaydet
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}