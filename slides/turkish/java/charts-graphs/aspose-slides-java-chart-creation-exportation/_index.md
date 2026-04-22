---
date: '2026-02-09'
description: Aspose.Slides for Java kullanarak grafik oluşturmayı ve grafiği Excel’e
  aktarmayı öğrenin. Veri görselleştirme, iş raporu slaytları ve çalışma kitabı oluşturma
  konularında uzmanlaşın.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Aspose.Slides Java ile Grafik Nasıl Oluşturulur
url: /tr/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java Kullanarak Grafik Nasıl Oluşturulur

**Aspose.Slides for Java ile Veri Görselleştirme Tekniklerinde Uzmanlaşın**

Günümüzün veri odaklı ortamında, *how to create chart* programlaması ham sayıları etkileyici görsel hikayelere dönüştürebilen bir beceridir. İster bir iş raporu slayt seti, ister etkileşimli bir analiz panosu oluşturuyor olun, Aspose.Slides for Java kodunuzdan doğrudan grafikler oluşturma, özelleştirme ve dışa aktarma gücünü sağlar. Bu öğreticide grafik nesneleri oluşturmayı, grafik verilerini Excel’e dışa aktarmayı ve sorunsuz veri yönetimi için grafikleri harici çalışma kitaplarına bağlamayı öğreneceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Slides for Java (v25.4+).  
- **Grafik verilerini Excel’e dışa aktarabilir miyim?** Evet – `readWorkbookStream()` kullanın ve baytları bir *.xlsx* dosyasına yazın.  
- **Hangi Java sürümü gerekiyor?** JDK 16 veya üzeri.  
- **Lisans gerekiyor mu?** Ücretsiz deneme değerlendirme için çalışır; üretim için kalıcı bir lisans gereklidir.  
- **Hangi grafik türü gösteriliyor?** Bir Pasta grafiği, ancak aynı yaklaşım Bar, Line ve diğer grafik türleri için de çalışır.

## Aspose.Slides for Java Nedir?
Aspose.Slides for Java, geliştiricilerin Microsoft Office olmadan PowerPoint sunumları oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan saf Java API'sidir. Grafik türlerinin tam bir yelpazesini, veri bağlamayı ve dışa aktarma yeteneklerini destekler, bu da **data visualization java** projeleri için ideal kılar.

## Aspose.Slides'ı Grafik Oluşturmak ve Grafiği Excel’e Dışa Aktarmak İçin Neden Kullanmalısınız?
- **Office kurulumu gerekmez** – herhangi bir sunucu veya bulut ortamında çalışır.  
- **Zengin grafik kütüphanesi** – onlarca grafik türü ve tam stil kontrolü.  
- **Doğrudan Excel dışa aktarımı** – sonraki analiz için harici bir çalışma kitabı oluşturur.  
- **Performansa odaklı** – büyük sunumlar için düşük bellek ayak izi ve hızlı işleme.

## Önkoşullar
İlerlemeye başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler ve Sürümler
- **Aspose.Slides for Java** sürüm 25.4 veya üzeri

### Ortam Kurulum Gereksinimleri
- Java Development Kit (JDK) 16 veya üzeri  
- IntelliJ IDEA veya Eclipse gibi bir IDE (veya tercih ettiğiniz herhangi bir metin düzenleyici)

### Bilgi Önkoşulları
- Temel Java programlama becerileri  
- Maven veya Gradle yapı araçlarına aşinalık

## Aspose.Slides for Java Kurulumu
Kütüphaneyi favori yapı sisteminizi kullanarak projenize ekleyin.

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatif olarak, en son sürümü doğrudan indirin([en son sürümü doğrudan indirin](https://releases.aspose.com/slides/java/)).

### Lisans Edinme Adımları
Aspose.Slides, tam yeteneklerini keşfetmeniz için ücretsiz deneme lisansı sunar. Ayrıca geçici bir lisans başvurabilir veya uzun vadeli kullanım için satın alabilirsiniz. Aşağıdaki adımları izleyin:

1. Lisansınızı almak için [Aspose Satın Alma Sayfası](https://purchase.aspose.com/buy) ziyaret edin.  
2. Ücretsiz deneme için [Sürümler](https://releases.aspose.com/slides/java/) adresinden indirin.  
3. Geçici bir lisans için [buradan](https://purchase.aspose.com/temporary-license/) başvurun.

Lisansi dosyasına sahip olduğunuzda, Java uygulamanızda başlatın:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Adım‑Adım Kılavuz

### Grafik Oluşturma – Sunumu Yükleme
Mevcut bir PowerPoint dosyasını yüklemek, grafik eklemeden veya değiştirmeden önceki ilk adımdır.

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

**Açıklama:**  
- `Presentation` PowerPoint dosyasını temsil eder.  
- Yerel kaynakları serbest bırakmak için her zaman `dispose()` çağırın.

### Grafik Oluşturma – Slayta Pasta Grafiği Ekleme
Şimdi oranlı verileri göstermek için mükemmel olan bir Pasta grafiği ekleyeceğiz.

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Açıklama:**  
- `addChart` grafiği ilk slayta ekler.  
- Parametreler grafik tipini, X/Y konumunu ve boyutu tanımlar.

### Grafiği Excel’e Dışa Aktarma – Grafik Verilerini Dışa Aktarma
Grafik verilerini dışa aktarmak, analistlerin sayılarla Excel’de çalışmasını sağlar ve daha derin içgörüler elde etmeyi mümkün kılar.

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Açıklama:**  
- `readWorkbookStream()` grafiğin temel Excel çalışma kitabını bir bayt dizisi olarak çıkarır.  
- Bayt dizisi `externalWorkbook1.xlsx` dosyasına yazılır ve kullanıma hazır bir Excel dosyası elde edilir.

### Grafik Oluşturma – Dinamik Veri İçin Harici Çalışma Kitabı Ayarlama
Grafiği harici bir çalışma kitabına bağlamak, grafiği sadece Excel dosyasını düzenleyerek güncellemenizi sağlar.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Açıklama:**  
- `setExternalWorkbook` grafiği belirtilen Excel dosyasına bağlar, slaytı yeniden oluşturmanıza gerek kalmadan canlı veri güncellemelerini etkinleştirir.

## Pratik Uygulamalar
Aspose.Slides, çeşitli gerçek dünya senaryoları için çok yönlü çözümler sunar:

1. **Business Report Slides:** Veri hatlarınızdan çeyrek dönem performans grafiklerini otomatik olarak oluşturun.  
2. **Academic Presentations:** Araştırma verilerini manuel grafik çizmeden net görselleştirmelere dönüştürün.  
3. **Financial Analysis:** Sayıların denetçiler tarafından doğrulanması için grafik verilerini Excel’e dışa aktarın.  
4. **Marketing Analytics:** Kampanya metriklerini görselleştirin ve paydaşlarla düzenlenebilir çalışma kitaplarını paylaşın.

## Yaygın Sorunlar ve Sorun Giderme
- **`FileNotFoundException`** – `dataDir`'in geçerli bir klasöre işaret ettiğini ve çıktı yolunun yazılabilir olduğunu doğrulayın.  
- **Memory leaks** – Yerel kaynakları serbest bırakmak için her zaman `pres.dispose()`'ı bir `finally` bloğunda çağırın.  
- **Chart not appearing** – Slayt indeksinin (`get_Item(0)`) gerçekten var olan bir slayta karşılık geldiğinden emin olun.

## Sıkça Sorulan Sorular

**Q:** Farklı bir grafik türü (ör. Bar, Line) aynı kodla kullanılabilir mi?  
**A:** Evet. `ChartType.Pie` yerine `ChartType.Bar` veya `ChartType.Line` gibi başka bir `ChartType` enum değerini kullanın.

**Q:** Grafik oluşturulduktan sonra harici çalışma kitabı güncellenebilir mi?  
**A:** Kesinlikle. Excel dosyasını doğrudan değiştirin; bağlanan grafik, sunum bir sonraki açıldığında değişiklikleri yansıtacaktır.

**Q:** Excel dışa aktarma özelliği için ayrı bir lisans gerekir mi?  
**A:** Hayır. Excel dışa aktarma yeteneği standart Aspose.Slides for Java lisansına dahildir.

**Q:** Hangi Java sürümleri destekleniyor?  
**A:** Aspose.Slides for Java, JDK 16 ve üzerini destekler; daha eski sürümler çalışabilir ancak resmi olarak test edilmemiştir.

**Q:** Oluşturulan Excel çalışma kitabını PPTX dosyasının içine nasıl gömebilirim?  
**A:** `chart.getChartData().setExternalWorkbook(null)` kullanarak çalışma kitabını gömebilir, ya da dinamik güncellemeler için harici bağlantıyı koruyabilirsiniz.

---

**Son Güncelleme:** 2026-02-09  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}