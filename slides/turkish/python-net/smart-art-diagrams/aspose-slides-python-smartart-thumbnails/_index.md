---
"date": "2025-04-23"
"description": "Aspose.Slides for Python kullanarak PowerPoint sunumlarında SmartArt grafiklerinin oluşturulmasını otomatikleştirmeyi, küçük resimleri etkili bir şekilde çıkarmayı ve kaydetmeyi öğrenin."
"title": "Python için Aspose.Slides Kullanarak SmartArt Küçük Resimleri Nasıl Oluşturulur ve Alınır"
"url": "/tr/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python için Aspose.Slides Kullanarak SmartArt Küçük Resimleri Nasıl Oluşturulur ve Alınır

## giriiş

Görsel olarak çekici sunumlar oluşturmak, izleyicilerinizin dikkatini çekmek için olmazsa olmazdır. Slayt destelerini geliştirmenin etkili bir yolu, PowerPoint sunumlarına SmartArt gibi dinamik grafikler eklemektir. Bu görselleri oluşturmak ve bunlardan küçük resimler çıkarmak için otomatik bir yöntem arıyorsanız, "Aspose.Slides Python" hakkındaki bu kılavuz paha biçilmez olacaktır.

Python için Aspose.Slides'ı kullanarak, SmartArt grafikleri zahmetsizce oluşturabilir, grafik içindeki belirli düğümlere erişebilir, bu düğümlerin resim küçük resimlerini alabilir ve bu resimleri projeleriniz için kaydedebilirsiniz. Bu eğitim, her adımda sizi ayrıntılı olarak yönlendirecektir.

**Ne Öğreneceksiniz:**
- Python için Aspose.Slides nasıl kurulur ve ayarlanır.
- PowerPoint sunumunda SmartArt grafiği oluşturma.
- SmartArt grafiğindeki düğümlere erişim.
- Belirli bir düğümden bir görüntü küçük resmini çıkarma ve kaydetme.

Başlamadan önce ön koşullara bir göz atalım.

## Ön koşullar

Başlamadan önce aşağıdakilerin hazır olduğundan emin olun:

- **Gerekli Kütüphaneler:** Python için Aspose.Slides'a ihtiyacınız olacak. Ortamınızın Python 3.x'i desteklediğinden emin olun.
- **Çevre Kurulum Gereksinimleri:** Çalışan bir Python kurulumu ve uygun bir IDE veya VSCode veya PyCharm gibi bir metin editörü.
- **Bilgi Ön Koşulları:** Fonksiyon tanımları ve dosya işlemleri de dahil olmak üzere Python programlamanın temel anlayışı.

## Python için Aspose.Slides Kurulumu

Öncelikle Aspose.Slides kütüphanesini yüklemeniz gerekiyor. Bu, pip kullanılarak kolayca yapılabilir:

```bash
pip install aspose.slides
```

Kurulumdan sonra, tüm özellikleri sınırlama olmaksızın keşfetmek istiyorsanız bir lisans edinin. Ücretsiz denemeyle başlayabilir, geçici bir lisans başvurusunda bulunabilir veya uzun süreli kullanım için satın alabilirsiniz.

Aspose.Slides'ı Python ortamınızda başlatmak için, betiğinizin başına kütüphaneyi içe aktarın:

```python
import aspose.slides as slides
```

## Uygulama Kılavuzu

SmartArt küçük resminin oluşturulması ve alınması sürecini açık adımlara bölelim.

### Adım 1: Yeni Bir Sunum Örneği Oluşturun

Bir sunumun örneğini oluşturarak başlayın. Bu, SmartArt grafiğinizi ekleyeceğiniz kapsayıcı olacaktır.

```python
with slides.Presentation() as pres:
```

Kullanarak `with` kaynakların düzgün bir şekilde yönetilmesini sağlar, çıkışta dosyayı otomatik olarak kaydeder ve kapatır.

### Adım 2: İlk Slayda SmartArt Ekleyin

Sonra, ilk slaydımıza bir SmartArt grafiği ekleyeceğiz. Bunu nasıl yapabileceğinizi anlatalım:

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

Bu, (10, 10) konumundaki SmartArt grafiği için 400x300 piksel boyutlarında temel bir döngü düzeni ekler.

### Adım 3: İkinci Düğüme Erişim

SmartArt'ınızdaki belirli düğümlere erişin. Bu örnekte, ikinci düğüme erişiyoruz:

```python
node = smart.nodes[1]
```

Düğümler sıfırdan başlayarak indekslenir; dolayısıyla, `nodes[1]` listedeki ikinci düğümü ifade eder.

### Adım 4: Görüntü Küçük Resmini Alın

Seçili düğüm içindeki şeklin küçük resmini elde etmek için:

```python
image = node.shapes[0].get_image()
```

Bu, ilk şeklin görüntüsünü belirtilen SmartArt düğümünden küçük resim olarak alır.

### Adım 5: Alınan Görüntüyü Kaydedin

Son olarak bu küçük resmi JPEG formatında istediğiniz yere kaydedin:

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}