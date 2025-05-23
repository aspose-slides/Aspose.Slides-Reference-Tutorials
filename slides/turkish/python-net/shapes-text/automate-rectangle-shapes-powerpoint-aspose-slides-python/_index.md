---
"date": "2025-04-23"
"description": "Aspose.Slides for Python ile PowerPoint'te dikdörtgen şekillerin nasıl oluşturulup biçimlendirileceğini otomatikleştirmeyi öğrenin. Sunum becerilerinizi zahmetsizce geliştirin."
"title": "Aspose.Slides for Python Kullanarak PowerPoint'te Dikdörtgen Şekillerini Otomatikleştirin"
"url": "/tr/python-net/shapes-text/automate-rectangle-shapes-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Python kullanarak PowerPoint'te Dikdörtgen Şekli Nasıl Oluşturulur ve Biçimlendirilir
## giriiş
PowerPoint sunumlarınıza hızlıca özel şekiller eklemeniz gerektiğini ama otomasyon eksikliğiyle boğuştuğunuzu hiç fark ettiniz mi? Dikdörtgenleri slayt slayt manuel olarak biçimlendirmekten bıktıysanız, o zaman bu eğitim günü kurtarmak için burada. "Python için Aspose.Slides"tan yararlanarak, sadece birkaç satır kodla dikdörtgen şekli eklemeyi ve biçimlendirmeyi otomatikleştireceğiz. Bu kılavuzun sonunda şunlarda ustalaşacaksınız:
- Programatik olarak dikdörtgen şekli oluşturma
- Renk ve çizgi stili gibi biçimlendirme seçeneklerini uygulama
- Sunumunuzu kolaylıkla kaydedin
Slayt oluşturma sürecinizi nasıl dönüştürebileceğinize bir göz atalım!
### Ön koşullar
Kodlamaya başlamadan önce aşağıdakilerin hazır olduğundan emin olun:
- **piton** makinenize kurulu olmalıdır (3.6 veya üzeri sürüm önerilir)
- **Python için Aspose.Slides** PowerPoint sunumlarını düzenlememize olanak sağlayan kütüphane
- Python programlama kavramlarının temel düzeyde anlaşılması ve pip kullanarak paket yükleme konusunda bilgi sahibi olunması
## Python için Aspose.Slides Kurulumu
### Kurulum
Aspose.Slides paketini yüklemek için terminalinizi veya komut isteminizi açın ve şunu çalıştırın:
```bash
pip install aspose.slides
```
Bu komut PyPI'den Python için Aspose.Slides'ın en son sürümünü getirir ve yükler.
### Lisans Edinimi
Aspose.Slides ticari bir üründür, ancak ücretsiz deneme lisansı kullanarak kullanmaya başlayabilirsiniz. İşte bir tane edinmenin yolu:
1. **Ücretsiz Deneme:** Ziyaret etmek [Aspose Ücretsiz Deneme](https://releases.aspose.com/slides/python-net/) ve değerlendirme için kaydolun.
2. **Geçici Lisans:** Sınırlama olmaksızın daha kapsamlı testler için geçici lisans talebinde bulunun [Geçici Lisans Sayfası](https://purchase.aspose.com/temporary-license/).
3. **Satın almak:** Canlı yayına geçmeye hazır olduğunuzda, şu adresten bir lisans satın alın: [Aspose Satınalma sayfası](https://purchase.aspose.com/buy).
Lisansınızı aldıktan sonra projenizde kullanmak için dokümantasyonu takip edin.
### Temel Başlatma
Aspose.Slides'ı Python için nasıl başlatabileceğinizi burada bulabilirsiniz:
```python
import aspose.slides as slides
\# Sunum sınıfını başlat
with slides.Presentation() as pres:
    print("Presentation is ready!")
```
Bu kod parçası yeni bir sunum hazırlar ve üzerinde değişiklik yapmaya hazır olduğunu doğrular.
## Uygulama Kılavuzu
### Dikdörtgen Şeklini Oluşturma
#### Genel bakış
Bu bölümde, Python için Aspose.Slides'ı kullanarak bir PowerPoint slaydına dikdörtgen şekli eklemeye odaklanacağız.
#### Şekli Oluşturma Adımları
1. **Bir Sunum açın veya oluşturun:**
   ```python
   import aspose.slides as slides
   
   with slides.Presentation() as pres:
       # Dikdörtgenimizi buraya ekleyeceğiz
   ```
2. **Slayta Erişim:**
   Şekli eklemek istediğimiz ilk slaydı alalım.
   ```python
   slide = pres.slides[0]
   ```
3. **Dikdörtgen Şekli Ekle:**
   Kullanın `add_auto_shape` Slaytta dikdörtgen oluşturma yöntemi.
   ```python
   shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 150, 50)
   ```
   - Parametreler: `ShapeType.RECTANGLE`, x konumu (50), y konumu (150), genişlik (150), yükseklik (50).
### Dikdörtgeni Biçimlendirme
#### Genel bakış
Daha sonra dikdörtgen şeklimize dolgu rengi ve çizgi stili gibi biçimlendirmeler uygulayacağız.
#### Biçimlendirme Adımları
1. **Dolgu Rengi:**
   Dikdörtgenin arka planı için belirli bir renkle düz bir dolgu ayarlayın.
   ```python
   shape.fill_format.fill_type = slides.FillType.SOLID
   shape.fill_format.solid_fill_color.color = drawing.Color.chocolate
   ```
2. **Çizgi Stili:**
   Dikdörtgenin çizgisini, rengini ve genişliğini özelleştirin.
   ```python
   shape.line_format.fill_format.fill_type = slides.FillType.SOLID
   shape.line_format.fill_format.solid_fill_color.color = drawing.Color.black
   shape.line_format.width = 5
   ```
3. **Sunumu Kaydet:**
   Son olarak sunumu bir dosyaya kaydedin.
   ```python
   pres.save("YOUR_OUTPUT_DIRECTORY/shapes_formatted_rectangle_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}