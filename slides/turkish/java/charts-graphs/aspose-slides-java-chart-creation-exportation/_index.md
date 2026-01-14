---
date: '2026-01-14'
description: Aspose.Slides for Java kullanarak grafiği Excel’e nasıl dışa aktaracağınızı
  ve sunumlara pasta grafik slaytı eklemeyi öğrenin. Adım adım kodlu rehber.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Aspose.Slides Java ile Grafiği Excel'e Aktar
url: /tr/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java Kullanarak Grafiği Excel'e Aktarma

**Aspose.Slides for Java ile Veri Görselleştirme Tekniklerinde Uzmanlaşın**

Bugünün veri odaklı ortamında, Java uygulamanızdan doğrudan **export chart to excel** yapabilmek, statik PowerPoint görsellerini yeniden kullanılabilir, analiz edilebilir veri setlerine dönüştürebilir. Raporlar oluşturmanız, analiz hatlarını beslemeniz ya da iş kullanıcılarının grafik verilerini Excel'de düzenlemesine izin vermeniz gerektiğinde, Aspose.Slides bunu kolaylaştırır. Bu öğreticide bir grafik oluşturmayı, bir pasta grafik slaytı eklemeyi ve bu grafik verilerini bir Excel çalışma kitabına aktarmayı adım adım gösteriyoruz.

**Neler Öğreneceksiniz:**
- Sunum dosyalarını zahmetsizce yükleyin ve manipüle edin
- **Add pie chart slide** ve diğer grafik türlerini slaytlarınıza ekleyin
- **Export chart to excel** (grafikten excel oluşturma) sonraki analizler için
- Verileri senkronize tutmak için **embed chart in presentation** dış çalışma kitabı yolunu ayarlayın

Haydi başlayalım!

## Hızlı Yanıtlar
- **Ana amaç nedir?** PowerPoint slaytındaki grafik verilerini bir Excel dosyasına aktarmak.  
- **Hangi kütüphane sürümü gereklidir?** Aspose.Slides for Java 25.4 veya daha yenisi.  
- **Lisans gerekli mi?** Değerlendirme için ücretsiz deneme çalışır; üretim için ticari lisans gerekir.  
- **Bir pasta grafik slaytı ekleyebilir miyim?** Evet – öğreticide bir Pie (pasta) grafik ekleme gösterilmektedir.  
- **Java 16 minimum mu?** Evet, JDK 16 veya üzeri önerilir.

## Aspose.Slides Kullanarak Grafiği Excel'e Nasıl Aktarırsınız?
Grafik verilerini Excel'e aktarmak, bir sunumu yüklemek, bir grafik oluşturmak ve ardından grafiğin çalışma kitabı akışını bir dosyaya yazmak kadar basittir. Aşağıdaki adımlar, proje kurulumundan son doğrulamaya kadar tüm süreci adım adım gösterir.

## Ön Koşullar
Başlamadan önce, aşağıdakilerin hazır olduğundan emin olun:

### Gerekli Kütüphaneler ve Sürümler
- **Aspose.Slides for Java** sürümü 25.4 veya üzeri

### Ortam Kurulum Gereksinimleri
- Java Development Kit (JDK) 16 veya üzeri
- IntelliJ IDEA veya Eclipse gibi bir kod editörü veya IDE

### Bilgi Ön Koşulları
- Temel Java programlama becerileri
- Maven veya Gradle yapı sistemlerine aşinalık

## Aspose.Slides for Java'ı Kurma
Aspose.Slides'ı kullanmaya başlamak için, Maven veya Gradle kullanarak projenize ekleyin.

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

Alternatif olarak, [en son sürümü doğrudan indirebilirsiniz](https://releases.aspose.com/slides/java/).

### Lisans Edinme Adımları
Aspose.Slides, tam özelliklerini keşfetmeniz için ücretsiz deneme lisansı sunar. Ayrıca geçici bir lisans başvurabilir veya uzun vadeli kullanım için satın alabilirsiniz. Aşağıdaki adımları izleyin:
1. Lisansınızı almak için [Aspose Satın Alma sayfasını](https://purchase.aspose.com/buy) ziyaret edin.  
2. Ücretsiz deneme için [Releases](https://releases.aspose.com/slides/java/) adresinden indirin.  
3. Geçici lisans başvurusu için [buraya](https://purchase.aspose.com/temporary-license/) tıklayın.

Lisans dosyasına sahip olduğunuzda, Java uygulamanızda başlatın:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Uygulama Kılavuzu

### Özellik 1: Sunumu Yükleme
Sunumu yüklemek, herhangi bir manipülasyon görevinin ilk adımıdır.

#### Genel Bakış
Bu özellik, Aspose.Slides for Java kullanarak mevcut bir PowerPoint dosyasını nasıl yükleyeceğinizi gösterir.

#### Adım‑Adım Uygulama
**Load Presentation**
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
- `Presentation`, `.pptx` dosyanızın yolu ile başlatılır.  
- Yerel kaynakları serbest bırakmak için `Presentation` nesnesini her zaman dispose edin.

### Özellik 2: Pasta Grafik Slaytı Ekleme
Grafik eklemek, veri sunumunu önemli ölçüde iyileştirebilir ve birçok geliştirici Java'da **how to add chart slide** sorusunu sorar.

#### Genel Bakış
Bu özellik, bir sunumun ilk slaytına **pie chart slide** (klasik “add pie chart slide” senaryosu) eklemeyi gösterir.

#### Adım‑Adım Uygulama
**Add Pie Chart**
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
- `addChart`, bir Pie (pasta) grafik ekler.  
- Parametreler, grafik tipini ve slayttaki konum/boyutunu tanımlar.

### Özellik 3: Grafikten Excel Oluşturma
Grafik verilerini dışa aktarmak, daha derin analiz için **generate excel from chart** yapmanıza olanak tanır.

#### Genel Bakış
Bu özellik, bir sunumdan grafik verilerini harici bir Excel çalışma kitabına dışa aktarmayı gösterir.

#### Adım‑Adım Uygulama
**Export Data**
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
- `readWorkbookStream`, grafiğin çalışma kitabı verilerini çıkarır.  
- Bayt dizisi, `FileOutputStream` kullanılarak bir `.xlsx` dosyasına yazılır.

### Özellik 4: Dış Çalışma Kitabı ile Sunuma Grafik Gömme
Grafiği dış bir çalışma kitabına bağlamak, **embed chart in presentation** yapmanıza ve verileri senkronize tutmanıza yardımcı olur.

#### Genel Bakış
Bu özellik, grafiğin Excel'den doğrudan veri okuyup yazabilmesi için dış çalışma kitabı yolunu ayarlamayı gösterir.

#### Adım‑Adım Uygulama
**Set External Workbook Path**
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
- `setExternalWorkbook`, grafiği bir Excel dosyasına bağlar ve slaytı yeniden oluşturmak zorunda kalmadan dinamik güncellemeler sağlar.

## Pratik Uygulamalar
1. **Business Reports:** Java uygulamalarından doğrudan grafiklerle ayrıntılı raporlar oluşturun.  
2. **Academic Presentations:** Etkileşimli pasta grafik slaytlarıyla dersleri zenginleştirin.  
3. **Financial Analysis:** Derin finansal modelleme için **Export chart to excel** yapın.  
4. **Marketing Analytics:** Kampanya performansını görselleştirin ve analiz ekibi için **generate excel from chart** oluşturun.

## Sık Sorulan Sorular

**S: Bu yaklaşımı diğer grafik türleriyle (ör. Bar, Line) kullanabilir miyim?**  
C: Kesinlikle. `ChartType.Pie` yerine herhangi bir `ChartType` enum değerini kullanın.

**S: Dışa aktarılan dosyayı okumak için ayrı bir Excel kütüphanesine ihtiyacım var mı?**  
C: Hayır. Dışa aktarılan `.xlsx` dosyası, herhangi bir tablo uygulamasıyla açılabilen standart bir Excel çalışma kitabıdır.

**S: Dış çalışma kitabı slayt boyutunu nasıl etkiler?**  
C: Dış bir çalışma kitabına bağlanmak PPTX dosya boyutunu önemli ölçüde artırmaz; grafik çalışma kitabına çalışma zamanında başvurur.

**S: Excel verilerini güncelleyip slaydın değişiklikleri otomatik olarak yansıtması mümkün mü?**  
C: Evet. `setExternalWorkbook` çağrıldıktan sonra, çalışma kitabına kaydedilen tüm değişiklikler sunum bir sonraki açıldığında yansıtılır.

**S: Aynı sunumdan birden fazla grafik dışa aktarmam gerekirse ne yapmalıyım?**  
C: Her slaydın grafik koleksiyonunu döngüyle gezerek, her biri için `readWorkbookStream()` çağırın ve ayrı çalışma kitabı dosyalarına yazın.

---

**Son Güncelleme:** 2026-01-14  
**Test Edilen Versiyon:** Aspose.Slides 25.4 for Java  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}