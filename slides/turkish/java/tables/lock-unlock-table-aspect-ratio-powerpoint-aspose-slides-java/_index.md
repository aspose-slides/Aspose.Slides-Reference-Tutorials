---
"date": "2025-04-18"
"description": "Aspose.Slides for Java kullanarak PowerPoint sunumlarında tablo en boy oranlarını nasıl kilitleyeceğinizi veya kilidini nasıl açacağınızı öğrenin. Bu kılavuz kurulumu, kod uygulamasını ve pratik uygulamaları kapsar."
"title": "Aspose.Slides for Java Kullanarak PowerPoint'te Tablo En Boy Oranlarını Kilitleme ve Kilidini Açma"
"url": "/tr/java/tables/lock-unlock-table-aspect-ratio-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java Kullanarak PowerPoint'te Tablo En Boy Oranlarını Kilitleme ve Kilidini Açma

## giriiş

PowerPoint sunumlarınızda tutarlı tablo düzenlerini korumakta zorluk mu çekiyorsunuz? En boy oranlarını kilitleme veya kilidini açma yeteneğiyle, düzenlemeler sırasında tabloların nasıl yeniden boyutlandırılacağını yönetmek çocuk oyuncağı haline geliyor. Bu eğitim, tablo boyutlarını verimli bir şekilde kontrol etmek için "Aspose.Slides for Java"yı kullanma konusunda size rehberlik ediyor. Sadece en boy oranlarını nasıl değiştireceğinizi değil, aynı zamanda bu özelliği daha geniş sunum iş akışlarına nasıl entegre edeceğinizi de öğreneceksiniz.

**Ne Öğreneceksiniz:**
- PowerPoint sunumlarındaki tabloların en boy oranı nasıl kilitlenir ve kilidi nasıl açılır.
- Maven, Gradle veya doğrudan indirmeler kullanılarak Java için Aspose.Slides kurulum süreci.
- Net açıklamalarla adım adım kod uygulaması.
- Büyük slayt gösterileriyle çalışırken pratik uygulamalar ve performans değerlendirmeleri.

Başlamadan önce ön koşullara bir göz atalım.

## Ön koşullar

Bu eğitimi takip edebilmek için şunlara sahip olduğunuzdan emin olun:
- **Java Geliştirme Kiti (JDK):** Bilgisayarınızda 16 veya üzeri sürüm yüklü olmalıdır.
- **İDE:** IntelliJ IDEA veya Eclipse gibi herhangi bir Java IDE'si.
- **Maven/Gradle:** Bağımlılıklar için paket yöneticilerini kullanmayı seçerseniz.
- Java programlama konusunda temel bilgi ve PowerPoint'in tablo işlevlerine aşinalık.

## Java için Aspose.Slides Kurulumu

### Maven Kurulumu
Maven kullanarak projenize Aspose.Slides'ı eklemek için aşağıdaki bağımlılığı ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Kurulumu
Gradle kullananlar için bunu ekleyin `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
Alternatif olarak, en son sürümü şu adresten indirin: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).

#### Lisans Edinme Adımları
- **Ücretsiz Deneme:** Temel işlevleri keşfetmek için ücretsiz denemeyle başlayın.
- **Geçici Lisans:** Değerlendirme süresince tüm özelliklere erişim için geçici bir lisans edinin.
- **Lisans Satın Al:** Uzun süreli, kesintisiz kullanım için lisans satın almayı düşünebilirsiniz.

Ortamınızı kurduktan ve gerekli lisansları edindikten sonra, Java uygulamanızda Aspose.Slides'ı aşağıdaki şekilde başlatın:

```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        // Kodunuz burada...
    }
}
```

## Uygulama Kılavuzu

### Tablo En Boy Oranını Kilitle/Kilidini Aç

Bu özellik, sunumlarınızdaki tabloların en boy oranını korumanıza veya ayarlamanıza olanak tanır; böylece tutarlı bir tasarım ve okunabilirlik sağlanır.

#### Bir Tabloya Erişim
Öncelikle sunumunuzu yükleyip istediğiniz tabloya erişin:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ITable;

// Sunum dosyasını yükleyin.
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/pres.pptx");
ITable table = (ITable) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

#### En Boy Oranını Kontrol Etme ve Değiştirme

Görüntü oranının kilitli olup olmadığını kontrol edin, ardından durumunu değiştirin:

```java
// Mevcut en boy oranı kilidi durumunu kontrol edin.
boolean isLocked = table.getGraphicalObjectLock().getAspectRatioLocked();

// En boy oranı kilitleme durumunu tersine çevirin.
table.getGraphicalObjectLock().setAspectRatioLocked(!isLocked);
```

Bu geçiş özelliği tasarım süreciniz boyunca esnek ayarlamalar yapmanıza olanak tanır.

#### Değişiklikleri Kaydetme
Değişiklikleri yaptıktan sonra güncellenen sunumu kaydedin:

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/pres-out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}