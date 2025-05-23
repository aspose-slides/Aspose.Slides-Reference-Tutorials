---
"date": "2025-04-22"
"description": "Aspose.Slides for Python'ı kullanarak PowerPoint sunumlarında Pasta Pasta grafiklerinin nasıl oluşturulacağını ve özelleştirileceğini öğrenin, böylece veri görselleştirme becerilerinizi geliştirin."
"title": "Aspose.Slides for Python Kullanarak PowerPoint'te Pasta Grafiği Nasıl Oluşturulur"
"url": "/tr/python-net/charts-graphs/aspose-slides-python-pie-of-pie-chart-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Python Kullanarak PowerPoint'te Pasta Grafiği Nasıl Oluşturulur

Pie of Pie grafiği gibi görsel olarak çekici grafikler oluşturmak, karmaşık bilgileri daha sindirilebilir hale getirerek PowerPoint sunumlarınızı önemli ölçüde geliştirebilir. Bu eğitim, Python için Aspose.Slides kullanarak Pie of Pie grafiği oluşturmanız konusunda size rehberlik eder.

## Ne Öğreneceksiniz

- Python için Aspose.Slides Kurulumu
- Pasta grafiği ile bir PowerPoint sunumu oluşturma adımları
- Daha iyi okunabilirlik için veri etiketlerini ve seri grubu seçeneklerini yapılandırma
- Sunumlarda Pasta grafiğinin pratik uygulamaları

Ortamınızı kurmaya ve bu özellikleri uygulamaya başlayalım.

### Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- **Python Kurulu**: Python 3.6 veya üzeri önerilir.
- **Python için Aspose.Slides**: Pip kullanarak kurulum:
  ```bash
  pip install aspose.slides
  ```
- **Lisans**: Aspose'dan ücretsiz deneme lisansı edinin ve tüm özellikleri sınırlama olmadan keşfedin.

#### Bilgi Önkoşulları

Python programlamaya dair temel bilgi ve PowerPoint sunumlarını anlamak faydalı olacaktır. Bunlara yeniyseniz, öncelikle giriş kaynaklarını incelemeyi düşünün.

### Python için Aspose.Slides Kurulumu

Python için Aspose.Slides'ı kullanmaya başlamak için şu basit adımları izleyin:

1. **Kurulum**: Kütüphaneyi kurmak için pip'i kullanın:
   ```bash
   pip install aspose.slides
   ```

2. **Lisans Edinimi**: 
   - Ziyaret etmek [Aspose'un Satın Alma Sayfası](https://purchase.aspose.com/buy) lisans satın almak veya geçici ücretsiz deneme edinmek için.
   - Aşağıdaki kod parçacığını kullanarak lisansınızı projenize uygulayın:
     ```python
     import aspose.slides as slides

     # Lisans dosyasını yükleyin
     license = slides.License()
     license.set_license("path_to_your_license.lic")
     ```

3. **Temel Başlatma**:
   Aspose.Slides'ı içe aktararak ve bir sunum nesnesi başlatarak başlayın.

### Uygulama Kılavuzu

#### Özellik 1: Grafikle Sunum Oluşturun

Bu özellik, bir PowerPoint sunumunun nasıl oluşturulacağını ve ilk slayda Pasta Pastası grafiğinin nasıl ekleneceğini gösterecektir.

##### Grafik Ekleme

Yeni bir sunum oluşturarak ve ilk slaydın (50, 50) konumuna bir Pasta Pastası grafiği ekleyerek başlayın:

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Belirtilen boyutlara sahip bir 'Pasta Pastası' grafiği ekleyin
    chart = presentation.slides[0].shapes.add_chart(
        slides.charts.ChartType.PIE_OF_PIE, 50, 50, 500, 400)
```

##### Veri Etiketlerini Yapılandırma

Okunabilirliği artırmak için, veri etiketlerini değerleri görüntüleyecek şekilde yapılandırın:

```python
# Daha iyi netlik için veri etiketlerinde değer gösterimini etkinleştirin
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```

##### Pasta Seçeneklerinin Ayarlanması

Pasta Pasta grafiği için ikinci pasta boyutu ve bölme konumu gibi belirli özellikleri yapılandırın:

```python
# İkinci pasta boyutunu ve bölme özelliklerini ayarlayın
chart.chart_data.series[0].parent_series_group.second_pie_size = 149
chart.chart_data.series[0].parent_series_group.pie_split_by = slides.charts.PieSplitType.BY_PERCENTAGE
chart.chart_data.series[0].parent_series_group.pie_split_position = 53
```

##### Sunumu Kaydetme

Son olarak sunumunuzu istediğiniz dizine kaydedin:

```python
# Sunumu grafikle birlikte kaydedin
presentation.save("YOUR_OUTPUT_DIRECTORY/charts_second_plot_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### Pratik Uygulamalar

Pasta grafiği çok yönlüdür ve çeşitli senaryolarda kullanılabilir:

1. **İş Raporları**: Farklı departmanlar veya ürünler arasında veri dağıtımını görselleştirin.
2. **Akademik Projeler**:Daha az önemli bulguların yanında önemli temaları da gösteren mevcut anket sonuçlarını sunuyoruz.
3. **Finansal Analiz**Bütçe raporunda birincil giderleri ikincil maliyetlerle karşılaştırın.

### Performans Hususları

Aspose.Slides kullanırken en iyi performansı elde etmek için:

- Bellek kullanımını azaltmak için mümkünse slayt ve grafik sayısını en aza indirin.
- Kodunuzdaki kullanılmayan kaynakları veya referansları düzenli olarak temizleyin.
- Python'un yerleşik çöp toplama özelliğini kullanın (`gc` (modül) hafızayı etkin bir şekilde yönetmek için kullanılır.

### Çözüm

Python için Aspose.Slides kullanarak Pasta Pasta grafiğiyle bir PowerPoint sunumu oluşturmayı öğrendiniz. Bu beceri sunumlarınızın görsel çekiciliğini ve etkinliğini büyük ölçüde artırabilir. Animasyonlar ekleme veya multimedya öğelerini entegre etme gibi Aspose.Slides'taki daha fazla özelliği keşfetmeyi düşünün.

### Sonraki Adımlar

- Aspose.Slides'da bulunan farklı grafik türlerini deneyin.
- Bu özelliği daha geniş bir sunum otomasyon iş akışına entegre edin.

### SSS Bölümü

**S: Pasta veya Pasta grafiğinin renklerini özelleştirebilir miyim?**
A: Evet, grafik renklerini kullanarak özelleştirebilirsiniz. `fill_format` Her segment için özellik.

**S: Aspose.Slides ile büyük veri kümelerini nasıl işlerim?**
A: Performansı korumak için veri girişinizi optimize edin ve daha küçük parçalara bölmeyi düşünün.

**S: Birden fazla grafiği tek seferde otomatik olarak eklemenin bir yolu var mı?**
A: Evet, veri kümeleriniz arasında dolaşın ve `add_chart` Tek bir sunum bağlamında yöntem.

### Kaynaklar

- **Belgeleme**: Ayrıntılı kılavuzları keşfedin [Aspose.Slides Belgeleri](https://reference.aspose.com/slides/python-net/).
- **İndirmek**: En son sürümü şu adresten edinin: [Sürümler](https://releases.aspose.com/slides/python-net/).
- **Satın al ve Ücretsiz Deneme**: Lisans seçeneklerine şu adresten erişin: [Aspose Satın Alma](https://purchase.aspose.com/buy) veya bir deneyin [Ücretsiz Deneme](https://releases.aspose.com/slides/python-net/).
- **Destek**: Tartışmaya katılın [Aspose Forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}