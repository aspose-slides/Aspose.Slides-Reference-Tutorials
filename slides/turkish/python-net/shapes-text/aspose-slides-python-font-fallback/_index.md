---
"date": "2025-04-24"
"description": "Sunumlarınızın farklı sistemlerde tutarlı olmasını sağlamak için Aspose.Slides for Python ile yazı tipi yedek kurallarının nasıl oluşturulacağını ve yönetileceğini öğrenin."
"title": "Aspose.Slides for Python'da Font Fallback'i Ustalaştırma - Kapsamlı Bir Kılavuz"
"url": "/tr/python-net/shapes-text/aspose-slides-python-font-fallback/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python için Aspose.Slides'ta Font Geri Dönüşünü Ustalaştırma: Kapsamlı Bir Kılavuz

## giriiş

Sunumlar oluştururken, özellikle birincil yazı tipleri tarafından desteklenmeyen Unicode karakterleri ile yazı tipi uyumluluğu sorunları zorlu olabilir. **Python için Aspose.Slides** Yazı tipi geri dönüş kuralları aracılığıyla sağlam bir çözüm sunarak sunumunuzun görsel çekiciliğini ve okunabilirliğini çeşitli sistemlerde garanti eder.

Bu kılavuzda, Python için Aspose.Slides kullanarak yazı tipi yedek kurallarının nasıl oluşturulacağını ve yönetileceğini inceleyeceğiz. Şunları öğreneceksiniz:
- Aspose.Slides ile ortamınızı kurma
- Bir yazı tipi yedek kuralları koleksiyonu oluşturma
- Unicode aralıklarına göre yazı tiplerini ekleyerek veya kaldırarak bu kuralları yönetme
- Kuralları sunumlara uygulama ve slaytları resim olarak sunma

Öncelikle ortamınızı hazırlayarak başlayalım.

## Ön koşullar

Ortamınızın bu görev için hazır olduğundan emin olun. İhtiyacınız olanlar şunlardır:
1. **Python için Aspose.Slides**: Bu kütüphane yazı tipi yedek kurallarını yönetir.
2. **Python Ortamı**: Python'un (3.6 veya üzeri sürüm) yüklü olduğundan emin olun.
3. **Temel Python Bilgisi**: Kod parçacıklarını incelerken Python söz dizimi ve kavramlarına aşinalık faydalı olacaktır.

## Python için Aspose.Slides Kurulumu

### Kurulum

Başlamak için pip kullanarak Aspose.Slides kitaplığını yükleyin:

```bash
pip install aspose.slides
```

### Lisans Edinimi

Aspose, özelliklerini sınırlama olmadan keşfetmeniz için ücretsiz deneme lisansı sunar. Bunu nasıl edinebileceğiniz aşağıda açıklanmıştır:
- Ziyaret etmek [Aspose'un Satın Alma Sayfası](https://purchase.aspose.com/buy) satın alma seçenekleri için veya geçici bir lisansa erişmek için.
- Alternatif olarak, ücretsiz deneme sürümünü şu adresten indirin: [İndirmeler Bölümü](https://releases.aspose.com/slides/python-net/).

### Temel Başlatma

Kurulumdan sonra Aspose.Slides'ı Python betiğinizde başlatın:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

## Uygulama Kılavuzu

### Yazı Tipi Geri Dönüş Kuralları Oluşturma ve Yönetme

#### Genel bakış

Yazı tipi yedek kuralları, sunumunuzdaki tüm karakterlerin uygun bir yazı tipine sahip olmasını sağlayarak, benzersiz karakter kümelerine sahip diller için okunabilirliği korur.

#### Uygulama Adımları

**1. Bir Font Geri Dönüş Kuralları Koleksiyonu Oluşturun**

Yedek yazı tiplerini tanımlamak için bir koleksiyon oluşturarak başlayın:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

**2. Bir Yazı Tipi Geri Dönüş Kuralı Ekleyin**

Unicode aralığını ve yedek yazı tipini belirten bir kural tanımlayın:

```python
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))
```
- **Parametreler**: `0x400` Unicode serisinin başlangıcıdır, `0x4FF` son ve `"Times New Roman"` yedek yazı tipidir.

**3. Mevcut Kuralları Yönetin**

Gerektiğinde değiştirmek için her kuralın üzerinde yineleme yapın:

```python
for fallback_rule in rules_list:
    fallback_rule.remove("Tahoma")
    if 0x4000 <= fallback_rule.range_end_index < 0x5000:
        fallback_rule.add_fallBack_fonts("Verdana")
```

**4. Bir Kuralı Kaldırın**

Gerekirse ilk kuralı koleksiyonunuzdan kaldırın:

```python
if len(rules_list) > 0:
    rules_list.remove(rules_list[0])
```

### Bir Sunuma Font Geri Dönüş Kurallarını Uygulama ve Bir Görüntüyü Oluşturma

#### Genel bakış

Yazı tipi yedek kuralları ayarlandıktan sonra, gerektiğinde metnin belirtilen yedek yazı tiplerini kullanmasını sağlamak için bunları sunumlara uygulayın.

#### Uygulama Adımları

**1. Ortamınızı Başlatın**

Giriş ve çıkış için dizinleri hazırlayın:

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. Bir Sunuma Yedek Kuralları Uygulayın**

Sunum dosyanızı yükleyin ve yazı tipi kurallarını uygulayın:

```python
rules_list = slides.FontFallBackRulesCollection()
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))

with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    pres.fonts_manager.font_fall_back_rules_collection = rules_list
    pres.slides[0].get_image(1, 1).save(out_dir + "text_font_fall_back_out.png\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}