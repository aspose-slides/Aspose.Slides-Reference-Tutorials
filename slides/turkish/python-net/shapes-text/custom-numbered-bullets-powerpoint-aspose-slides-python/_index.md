---
"date": "2025-04-24"
"description": "Aspose.Slides for Python ile PowerPoint'te özel numaralı madde işaretli listelerin nasıl oluşturulacağını öğrenin. Sunumlarınızı benzersiz biçimlendirmeyle geliştirin."
"title": "Aspose.Slides for Python Kullanılarak PowerPoint'te Özel Numaralandırılmış Madde İşaretli Listeler"
"url": "/tr/python-net/shapes-text/custom-numbered-bullets-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Python kullanılarak PowerPoint'te Özel Numaralı Madde İşaretli Listeler

## giriiş
PowerPoint sunumlarınızın görsel çekiciliğini varsayılan madde işaretlerinin ötesine taşımak mı istiyorsunuz? İster kurumsal raporlar, ister akademik dersler veya iş toplantıları için olsun, madde işaretli listeleri özelleştirmek izleyicilerinizin dikkatini daha etkili bir şekilde yakalayabilir ve koruyabilir. **Python için Aspose.Slides**, benzersiz biçimlendirme ihtiyaçlarınıza göre numaralandırılmış madde işaretlerini özelleştirme esnekliğine sahipsiniz.

Bu kapsamlı kılavuzda, Python ile PowerPoint'te Aspose.Slides kullanarak özel numaralı madde işaretlerinin nasıl ayarlanacağını göstereceğiz. Bu özelliği sunumlarınıza entegre ederek profesyonel ve cilalı bir görünüm elde edebilirsiniz.

**Ne Öğreneceksiniz:**
- Python için Aspose.Slides Kurulumu
- Özel numaralı madde işaretli listeler oluşturma
- Madde işareti ayarlarını programlı olarak yapılandırma
- Performansı optimize etme ve yaygın sorunları giderme

Başlayalım! Devam etmek için her şeyin hazır olduğundan emin olun.

## Ön koşullar
Python için Aspose.Slides ile özel numaralı madde işaretlerini uygulamadan önce şunlara sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler:
- **Python için Aspose.Slides**:PowerPoint sunumları oluşturmak ve düzenlemek için sağlam bir kütüphane.

### Çevre Kurulumu:
- Sisteminizde Python 3.x yüklü.
- Python programlama kavramlarının temellerini anlamak faydalıdır ancak zorunlu değildir.

## Python için Aspose.Slides Kurulumu
Başlamak için şunu yükleyin: `aspose.slides` pip kullanan kütüphane:

```bash
pip install aspose.slides
```

### Lisans Edinimi:
Aspose.Slides, yeteneklerini test etmek için ücretsiz deneme sunan ticari bir üründür. Geçici bir lisans edinebilir veya sürekli kullanım için bir tane satın alabilirsiniz.

- **Ücretsiz Deneme**: Temel işlevlere sınırlama olmaksızın erişin.
- **Geçici Lisans**:Aspose web sitesinde geçici olarak tam erişim sağlanması talebi.
- **Satın almak**: Uzun vadeli projeleriniz için lisans satın almayı düşünebilirsiniz.

### Temel Başlatma:
Kurulum tamamlandıktan sonra sunumunuzu aşağıdaki şekilde başlatın:

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Kodunuz burada...
```

Bu kurulum, PowerPoint slaytlarınıza özel numaralı madde işaretleri eklemeniz için ortamı hazırlar.

## Uygulama Kılavuzu
Özel numaralı madde işaretli listeler oluşturmaya dalalım. Her adım, netlik ve uygulama kolaylığı için parçalara ayrılmıştır.

### Metin Çerçeveleriyle Dikdörtgen Şekli Ekleme
#### Genel Bakış:
Öncelikle madde işaretleri için metin çerçeveleri içerecek bir şekil ekleyin.

```python
# İlk slayda dikdörtgen şekli ekleyin
shape = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 200, 200, 400, 200)
```
- **Parametreler Açıklandı**: : `add_auto_shape` yöntem, şekil türü (dikdörtgen), konum (x ve y koordinatları) ve boyutlar (genişlik ve yükseklik) için parametreler alır.

### Metin Çerçevelerini Yapılandırma
#### Genel Bakış:
Madde işaretleri eklemek için dikdörtgenin metin çerçevesine erişin.

```python
# Oluşturulan otomatik şeklin metin çerçevesine erişin
text_frame = shape.text_frame

# Mevcutsa varsayılan olarak var olan herhangi bir paragrafı kaldırın
text_frame.paragraphs.clear()
```
- **Amaç**: Özel madde işaretleri eklemeden önce temiz bir sayfa açılmasını sağlar.

### Özel Numaralandırılmış Madde İşaretleri Ekleme
#### Genel Bakış:
Belirli madde işaretleri ayarlarına sahip paragraflar ekleyin:

```python
# Özel numaralı madde işaretleriyle paragraflar ekleyin
for start_number, bullet_text in [(2, "bullet 2"), (3, "bullet 3"), (7, "bullet 7")]:
    paragraph = slides.Paragraph()
    paragraph.text = bullet_text
    paragraph.paragraph_format.depth = 4
    paragraph.paragraph_format.bullet.numbered_bullet_start_with = start_number
    paragraph.paragraph_format.bullet.type = slides.BulletType.NUMBERED
    text_frame.paragraphs.add(paragraph)
```
- **Yapılandırma**:Her paragraf belirli bir numara ile başlar, bu da sunum biçimlendirmesi üzerinde esneklik ve kontrol sağlar.

### Sunumu Kaydetme
Son olarak yapılandırdığınız sunumu kaydedin:

```python
# Sunuyu kaydet\sunum.save("ÇIKTI_DİZİNİNİZ/metin_ayarla_özel_maddeler_sayısı_çıkış.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}