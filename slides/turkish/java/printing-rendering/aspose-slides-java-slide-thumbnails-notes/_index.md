---
"date": "2025-04-17"
"description": "Aspose.Slides for Java kullanarak notlarla slayt küçük resimlerinin nasıl oluşturulacağını öğrenin. Bu kılavuz kurulum, yapılandırma ve pratik uygulamaları kapsar."
"title": "Aspose.Slides Java&#58;yı Kullanarak Notlarla Slayt Küçük Resimleri Oluşturun Adım Adım Kılavuz"
"url": "/tr/java/printing-rendering/aspose-slides-java-slide-thumbnails-notes/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java Kullanarak Notlarla Slayt Küçük Resimleri Oluşturun
## Baskı ve Render
### Adım Adım Bir Kılavuz
Günümüzün hızlı dijital dünyasında, sunum içeriğini etkin bir şekilde yönetmek ve paylaşmak hayati önem taşır. İster PowerPoint sunumlarını entegre eden bir geliştirici olun, ister notlarla slayt küçük resimlerini çıkarma sürecini otomatikleştirin, **Java için Aspose.Slides** Bu görevleri kolaylaştırmak için sağlam yetenekler sunar. Bu kapsamlı eğitim, Aspose.Slides kullanarak altta notları görüntülerken slayt küçük resimleri oluşturma ve slaytlarınız için varsayılan yazı tipi ayarlarını değiştirme konusunda size rehberlik edecektir.

## Ne Öğreneceksiniz
- Notların görünür olduğu bir slayt küçük resmi nasıl alınır
- Slayt oluşturmada varsayılan normal yazı tipini değiştirme
- Java için Aspose.Slides'ı kurma ve yapılandırma
- Bu özelliklerin pratik uygulamaları

Başlamadan önce ön koşullara bir göz atalım.

### Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- **Java için Aspose.Slides** kütüphane: 25.4 veya üzeri bir sürüme ihtiyacınız olacak.
- Sisteminizde yüklü bir Java Geliştirme Kiti (JDK)
- Java programlamanın temel bilgisi ve Maven veya Gradle derleme araçlarına aşinalık

## Java için Aspose.Slides Kurulumu
Aspose.Slides'ı kullanabilmek için öncelikle kütüphaneyi projenize eklemeniz gerekmektedir.

### Maven Bağımlılığı
Bunu şuna ekle: `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle Bağımlılığı
Bunu da ekleyin `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Doğrudan İndirme
Alternatif olarak, en son kütüphaneyi şu adresten indirin: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).

#### Lisans Edinimi
Ücretsiz denemeyle başlayabilir veya tüm özellikleri keşfetmek için geçici bir lisans talep edebilirsiniz. Sürekli kullanım için bir lisans satın almayı düşünün.

#### Temel Başlatma ve Kurulum
```java
import com.aspose.slides.Presentation;
// Sunum dosyanızı yükleyin
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/RenderingOptions.pptx");
```
## Uygulama Kılavuzu
### Not Düzeni ile Slayt Küçük Resimlerini Alma
Bu özellik, notların altta görünmesini sağlayarak slayt küçük resimleri oluşturmanıza, bağlam ve ek bilgiler sunmanıza olanak tanır.
#### Adım 1: Sununuzu Yükleyin
Öncelikle Aspose.Slides kullanarak sunum dosyanızı yükleyin:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
String presPath = "YOUR_DOCUMENT_DIRECTORY/RenderingOptions.pptx";
Presentation pres = new Presentation(presPath);
```
#### Adım 2: İşleme Seçeneklerini Yapılandırın
Daha sonra, notları alt tarafa eklemek için oluşturma seçeneklerini ayarlayın:
```java
import com.aspose.slides.IRenderingOptions;
import com.aspose.slides.RenderingOptions;
IRenderingOptions renderingOpts = new RenderingOptions();
INotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
// Kesilecek notaların konumunu alta ayarlayın
notesOptions.setNotesPosition(NotesPositions.BottomTruncated);
renderingOpts.setSlidesLayoutOptions(notesOptions);
```
#### Adım 3: Küçük resmi alın ve kaydedin
Son olarak slayt görüntüsünü istediğiniz boyutlarda alın ve kaydedin:
```java
import com.aspose.slides.IImage;
import java.io.IOException;
// Çıktı yolunu ve biçimini belirtin
String outputPath = "YOUR_OUTPUT_DIRECTORY/RenderingOptions-Slide1-Original.png";
try {
    IImage image = pres.getSlides().get_Item(0).getImage(renderingOpts, 4 / 3f, 4 / 3f);
    image.save(outputPath, com.aspose.slides.export.ImageFormat.getPng());
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
### Varsayılan Düzenli Yazı Tipini Değiştirme
Bu özellik, slayt küçük resimlerinin oluşturulmasında kullanılan varsayılan normal yazı tipinin nasıl değiştirileceğini gösterir.
#### Adım 1: Sununuzu Yükleyin
Önceki bölümde olduğu gibi sunum dosyanızı yükleyerek başlayın:
```java
String presPath = "YOUR_DOCUMENT_DIRECTORY/RenderingOptions.pptx";
Presentation pres = new Presentation(presPath);
```
#### Adım 2: Varsayılan Normal Yazı Tipini Ayarla
Arial Black veya Arial Narrow gibi belirli bir yazı tipini kullanmak için işleme seçeneklerini yapılandırın:
```java
IRenderingOptions renderingOpts = new RenderingOptions();
renderingOpts.setDefaultRegularFont("Arial Black");
```
#### Adım 3: Küçük resmi yeni yazı tipi ayarlarıyla alın ve kaydedin
Slayt görüntüsünü güncellenen yazı tipi ayarlarını kullanarak kaydedin:
```java
String outputPath = "YOUR_OUTPUT_DIRECTORY/RenderingOptions-Slide1-ArialBlackDefault.png";
try {
    IImage image = pres.getSlides().get_Item(0).getImage(renderingOpts, 4 / 3f, 4 / 3f);
    image.save(outputPath, com.aspose.slides.export.ImageFormat.getPng());
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Pratik Uygulamalar
Bu özellikler çeşitli uygulamalara entegre edilebilir, örneğin:
- **İçerik Yönetim Sistemleri**:CMS'nizde saklanan sunumlar için otomatik olarak küçük resimler oluşturun.
- **Belge Arşivleme Çözümleri**: Kolayca erişebilmek için notlarla dizinlenmiş küçük resimler oluşturun.
- **İşbirlikçi Araçlar**:Bağlamsal notlar ekleyerek sunum paylaşımını geliştirin.
Entegrasyon olanakları arasında, üretkenliği daha da artırmak için Aspose.Slides'ı bulut depolama çözümleri, otomatik rapor oluşturucular ve özel belge yönetim sistemleriyle birleştirmek yer alıyor.
## Performans Hususları
Aspose.Slides kullanırken performansı optimize etmek için:
- Sunumları derhal bertaraf ederek verimli bellek yönetimini sağlayın.
- Uygulamanızın ihtiyaçlarına göre uygun resim formatlarını ve çözünürlükleri kullanın.
- Uygun durumlarda birden fazla slaydı aynı anda işlemek için çoklu iş parçacığını kullanın.
## Çözüm
Artık, notlarla slayt küçük resimleri oluşturmak ve varsayılan yazı tiplerini değiştirmek için Aspose.Slides for Java'yı nasıl kullanacağınıza dair sağlam bir anlayışa sahip olmalısınız. Bu özellikler, çeşitli uygulamalarda sunum yönetimi sürecini büyük ölçüde iyileştirebilir. Daha fazla araştırma için, Aspose.Slides içinde mevcut diğer işleme seçeneklerini denemeyi düşünün.
## SSS Bölümü
1. **Varsayılan normal yazı tipini ayarlarken yazı tipi boyutunu değiştirebilir miyim?**
   - Evet, slaytlardaki belirli metin öğelerine erişerek yazı tipi boyutlarını ve stillerini özelleştirebilirsiniz.
2. **Bir sunumdaki tüm slaytların küçük resimlerini oluşturmak mümkün müdür?**
   - Kesinlikle! Her slaytta gezinmek için şunu kullanın: `pres.getSlides().size()` ve buna göre işleme mantığını uygulayın.
3. **Resimleri kaydederken istisnaları nasıl hallederim?**
   - Olası IOException'ları zarif bir şekilde yönetmek için görüntü kaydetme kodunuzun etrafında try-catch bloklarını kullanın.
4. **Aspose.Slides diğer programlama dilleriyle kullanılabilir mi?**
   - Evet, .NET, C++ ve daha fazlası dahil olmak üzere birden fazla dili destekler.
5. **Aspose.Slides'ı deneme süresinden sonra da kullanmak için lisanslama seçenekleri nelerdir?**
   - Tüm özelliklerin kilidini açmak için lisans satın alabilir veya abonelik tabanlı modelleri tercih edebilirsiniz.
## Kaynaklar
- [Aspose.Slides Belgeleri](https://reference.aspose.com/slides/java/)
- [En Son Sürümü İndirin](https://releases.aspose.com/slides/java/)
- [Lisans Satın Al](https://purchase.aspose.com/buy)
- [Ücretsiz Deneme](https://releases.aspose.com/slides/java/)
- [Geçici Lisans Talebi](https://purchase.aspose.com/temporary-license/)
- [Aspose Destek Forumu](https://forum.aspose.com/c/slides/11)

Java projelerinizde Aspose.Slides'ı uygulamaya başladığınızda daha detaylı bilgi ve destek için bu kaynakları keşfetmekten çekinmeyin. İyi kodlamalar!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}