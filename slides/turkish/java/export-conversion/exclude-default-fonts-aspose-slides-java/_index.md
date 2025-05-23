---
"date": "2025-04-17"
"description": "Aspose.Slides for Java ile HTML dönüşümü sırasında varsayılan yazı tiplerini nasıl hariç tutacağınızı öğrenin ve platformlar arasında tutarlı tipografi sağlayın."
"title": "Aspose.Slides for Java'yı kullanarak HTML Dönüşümünden Varsayılan Yazı Tiplerini Nasıl Hariç Tutarsınız"
"url": "/tr/java/export-conversion/exclude-default-fonts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java Kullanılarak Varsayılan Yazı Tipleri HTML Dönüşümünden Nasıl Hariç Tutulur
## giriiş
Sunumları HTML'ye dönüştürürken, varsayılan yazı tipi ayarları nedeniyle özel yazı tiplerinizi korumak çok önemlidir. Bu kılavuz, Aspose.Slides for Java'nın bu varsayılanları nasıl hariç tutmanıza ve çeşitli platformlarda tutarlı tipografiyi nasıl sağlamanıza yardımcı olabileceğini gösterir.
**Ne Öğreneceksiniz:**
- Java için Aspose.Slides ile ortamın kurulması
- HTML dönüştürme sırasında varsayılan yazı tiplerini hariç tutma teknikleri
- Temel yapılandırma seçenekleri ve bunların çıktı üzerindeki etkileri
- Gerçek dünya senaryolarında pratik uygulamalar
Uygulama kılavuzuna geçmeden önce ön koşulları tartışarak başlayalım.
## Ön koşullar
Bu eğitimi etkili bir şekilde takip edebilmek için şunlara sahip olduğunuzdan emin olun:
- **Java Kütüphanesi için Aspose.Slides**: 25.4 veya üzeri sürümü yükleyin.
- **Java Geliştirme Kiti (JDK)**: Bu kod örneği JDK 16'yı hedeflemektedir; makinenizde kurulu olduğundan emin olun.
- **Temel Java Programlama Bilgisi**:Java sözdizimi ve temel programlama kavramlarına aşinalık varsayılmaktadır.
## Java için Aspose.Slides Kurulumu
### Bağımlılık Kurulumu
**Usta:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
Alternatif olarak, kütüphaneyi doğrudan şu adresten indirin: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).
### Lisans Edinimi
Ücretsiz denemeyle başlayın veya tüm özellikleri sınırlama olmadan keşfetmek için geçici bir lisans talep edin. Uzun vadeli kullanım için lisans satın almanız önerilir.
**Temel Kurulum:**
Projenizde Aspose.Slides'ı başlatmak için:
```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation pres = new Presentation("your-pptx-file-path");
        // Sunumu manipüle etmek için kodunuz
    }
}
```
## Uygulama Kılavuzu
### Özellik Genel Bakışı: Varsayılan Yazı Tiplerini HTML Dönüşümünden Hariç Tutma
Bu özellik, PowerPoint dosyasının HTML'e dönüştürülmesi sırasında yazı tipi kullanımının özelleştirilmesine yardımcı olarak markalaşmayı ve tutarlılığı artırır.
#### Adım 1: Ortamınızı Hazırlayın
Yukarıdaki talimatlara göre Aspose.Slides'ın doğru şekilde ayarlandığından emin olun. Bu, bağımlılıklar eklemeyi veya JAR'ı doğrudan projenize indirmeyi içerir.
#### Adım 2: Sunumu Yükleyin
Sununuzu şunu kullanarak yükleyin: `Presentation` sınıf:
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/presentation.pptx";
try {
    Presentation pres = new Presentation(dataDir);
```
#### Adım 3: Yazı Tipi Hariç Tutmalarını Tanımlayın
Hariç tutmak istediğiniz yazı tiplerini belirtmek için bir dizi oluşturun. Bu örnekte, yer tutucu olarak boş bir listeyle başlıyoruz:
```java
String[] fontNameExcludeList = {};
```
#### Adım 4: Özel HTML Denetleyicisini Başlatın
The `LinkAllFontsHtmlController` sınıfı, dönüştürme işlemi sırasında özel yazı tipi işleme için kullanılır.
```java
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, "YOUR_DOCUMENT_DIRECTORY");
```
#### Adım 5: HTML Seçeneklerini Yapılandırın
Kurulumunuzu yapın `HtmlOptions` özel biçimlendiriciyi kullanmak için:
```java
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(linkcont));
```
#### Adım 6: HTML olarak kaydet
Son olarak dönüştürülen sunumu HTML formatında kaydedin:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/pres.html", SaveFormat.Html, htmlOptionsEmbed);
} catch (Exception e) {
    e.printStackTrace();
}
```
**Açıklama:** Bu kod parçacığı, HTML dönüştürme sırasında özel bir biçimlendirici yapılandırarak varsayılan yazı tiplerinin nasıl hariç tutulacağını göstermektedir.
## Pratik Uygulamalar
1. **Web Tabanlı Sunumlar**:Marka tutarlılığını koruyarak sunumları kurumsal web sitelerine yerleştirin.
2. **Belge Taşınabilirliği**: Belgelerin farklı cihazlarda ve platformlarda aynı görünmesini sağlayın.
3. **CMS ile Entegrasyon**: Özel yazı tiplerinin önemli olduğu içerik yönetim sistemlerine sorunsuz bir şekilde entegre edin.
## Performans Hususları
- **Bellek Kullanımını Optimize Et**: Büyük sunumları verimli bir şekilde yönetmek için Aspose.Slides'ın bellek yönetimi özelliklerini kullanın.
- **Kaynak Yönetimi**: Kaynakları serbest bırakmak için işlemlerden sonra akışları uygun şekilde kapatın.
- **En İyi Uygulamalar**: Performans iyileştirmeleri ve hata düzeltmeleri için kütüphane sürümünüzü düzenli olarak güncelleyin.
## Çözüm
Aspose.Slides for Java kullanarak HTML dönüşümü sırasında varsayılan yazı tiplerini nasıl hariç tutacağınızı öğrendiniz. Bu yetenek, markalaşma ve profesyonel dokümantasyon için önemli olan farklı platformlar arasında sunum tutarlılığını artırır.
Becerilerinizi daha da geliştirmek için Aspose.Slides'ın diğer özelliklerini keşfedin veya bu işlevselliği daha büyük projelere entegre edin.
**Sonraki Adımlar:**
Farklı yazı tipi hariç tutmalarını deneyin ve bunların nihai HTML çıktısını nasıl etkilediğini görün. Belge dönüştürme süreçlerini kolaylaştırmak için bu teknikleri otomatik iş akışlarına entegre etmeyi düşünün.
## SSS Bölümü
1. **Java için Aspose.Slides nedir?**
   - Java uygulamalarında sunumları düzenlemek için güçlü bir kütüphane.
2. **Uzun süreli kullanım için lisans nasıl alınır?**
   - Ziyaret edin [satın alma sayfası](https://purchase.aspose.com/buy) Lisanslama seçeneklerini satın almak veya sorgulamak için.
3. **Birden fazla yazı tipini aynı anda hariç tutabilir miyim?**
   - Evet, hariç tutmak istediğiniz tüm yazı tipi adlarını ekleyin `fontNameExcludeList` sıralamak.
4. **HTML çıktımda eksik fontlar varsa ne yapmalıyım?**
   - Özel HTML denetleyicinizin doğru şekilde yapılandırıldığından ve yolların doğru şekilde ayarlandığından emin olun.
5. **Yazı tiplerini hariç tutmanın performans üzerinde etkileri var mı?**
   - Büyük font kütüphaneleri performansı etkileyebilir; Aspose'un bellek yönetimi özelliklerini kullanarak gerektiği gibi optimize edin.
## Kaynaklar
- [Belgeleme](https://reference.aspose.com/slides/java/)
- [Kütüphaneyi İndir](https://releases.aspose.com/slides/java/)
- [Lisans Satın Al](https://purchase.aspose.com/buy)
- [Ücretsiz Deneme](https://releases.aspose.com/slides/java/)
- [Geçici Lisans](https://purchase.aspose.com/temporary-license/)
- [Destek Forumu](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}