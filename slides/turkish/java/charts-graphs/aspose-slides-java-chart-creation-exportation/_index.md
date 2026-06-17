---
date: '2026-06-03'
description: Aspose.Slides for Java kullanarak chart'ı Excel'e dışa aktarmayı ve chart
  Java oluşturmayı öğrenin. data visualization, business report slides ve workbook
  generation konularında uzmanlaşın.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Chart'ı Excel'e Dışa Aktar ve Aspose.Slides ile Charts Oluştur
url: /tr/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Grafiği Excel'e Aktar ve Aspose.Slides ile Grafikler Oluştur

**Aspose.Slides for Java ile Veri Görselleştirme Tekniklerinde Uzmanlaşın**

Günümüzün veri odaklı ortamında, *grafiği excel'e aktar* programlaması, ham sayıları etkileyici görsel hikayelere dönüştürebilen bir beceridir. İş raporu slayt seti ya da etkileşimli analiz panosu oluşturuyor olun, Aspose.Slides for Java, kodunuzdan doğrudan grafikler oluşturma, özelleştirme ve dışa aktarma gücünü verir. Bu öğreticide grafik nesneleri oluşturmayı, grafik verilerini Excel'e aktarmayı ve sorunsuz veri yönetimi için grafikleri harici çalışma kitaplarına bağlamayı öğreneceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Slides for Java (v25.4+).  
- **Grafik verilerini Excel'e aktarabilir miyim?** Evet – `readWorkbookStream()` kullanın ve baytları bir *.xlsx* dosyasına yazın.  
- **Hangi Java sürümü gereklidir?** JDK 16 veya üzeri.  
- **Lisans gerekiyor mu?** Değerlendirme için ücretsiz deneme çalışır; üretim için kalıcı bir lisans gereklidir.  
- **Hangi grafik türü gösteriliyor?** Bir Pasta grafiği, ancak aynı yaklaşım Bar, Line ve diğer grafik türleri için de çalışır.

## Aspose.Slides for Java Nedir?
Aspose.Slides for Java, geliştiricilerin Microsoft Office olmadan PowerPoint sunumları oluşturmasına, düzenlemesine ve dönüştürmesine olanak tanıyan saf Java API'sidir. Slayt manipülasyonu, grafik oluşturma ve format dönüşümü için kapsamlı bir sınıf seti sunar ve otomatik raporlama çözümlerini mümkün kılar. **50+ grafik türünü** destekler, tam veri bağlaması ve doğrudan Excel dışa aktarımı sağlar, bu da **data visualization java** projeleri için idealdir.

## Grafik oluşturmak ve grafiği Excel'e aktarmak için neden Aspose.Slides kullanmalı?
Grafiği Excel'e hızlı ve güvenilir bir şekilde dışa aktarın. Aspose.Slides, Office kurulumlarına gerek kalmadan **50'den fazla yerleşik grafik stili** sunar ve standart sunucu donanımında sunumları **30 saniyenin altında 300 MB'a kadar** işleyebilir. Ayrıca yerel Excel çalışma kitabı oluşturma özelliği sayesinde, alt analizciler ham sayılarla manuel kopyala‑yapıştır yapmadan çalışabilir.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler ve Sürümler
- **Aspose.Slides for Java** sürüm 25.4 veya üzeri (JDK 16+ destekler)

### Ortam Kurulum Gereksinimleri
- Java Development Kit (JDK) 16 veya üzeri  
- IntelliJ IDEA veya Eclipse gibi bir IDE (veya tercih ettiğiniz herhangi bir metin düzenleyici)

### Bilgi Önkoşulları
- Temel Java programlama becerileri  
- Maven veya Gradle yapı araçlarına aşinalık

## Aspose.Slides for Java'ı Kurma
Kütüphaneyi projenize favori yapı sisteminizi kullanarak ekleyin.

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
Aspose.Slides, tam özelliklerini keşfetmeniz için ücretsiz deneme lisansı sunar. Ayrıca geçici bir lisans başvurabilir veya uzun vadeli kullanım için bir lisans satın alabilirsiniz. Aşağıdaki adımları izleyin:

1. Lisansınızı almak için [Aspose Satın Alma sayfasını](https://purchase.aspose.com/buy) ziyaret edin.  
2. Ücretsiz deneme için [Releases](https://releases.aspose.com/slides/java/) üzerinden indirin.  
3. Geçici lisans için [buradan](https://purchase.aspose.com/temporary-license/) başvurun.

Lisans dosyasına sahip olduğunuzda, Java uygulamanızda başlatın:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Adım‑Adım Kılavuz

### Grafik Oluşturma – Sunumu Yükleme
Grafik eklemeden veya değiştirmeden önce mevcut bir PowerPoint dosyasını yükleyin.  
`Presentation` sınıfı, bellekte bir PowerPoint dosyasını temsil eder ve slaytları, şekilleri ve grafik nesnelerini ortaya çıkarır.  
`new Presentation("input.pptx")` ile dosyanızı yükleyin, ardından `presentation.getSlides().get_Item(0)` kullanarak ilk slayt üzerinde çalışın. Yerel kaynakları serbest bırakmak için her zaman bir `finally` bloğunda `presentation.dispose()` çağırın.

### Grafik Oluşturma – Slayta Pasta Grafiği Ekleme
Oran verilerini göstermek için mükemmel bir Pasta grafiği ekleyin.  
`IChart` arayüzü, grafik manipülasyonu için birincil giriş noktasıdır; `addChart` hedef slaytta yeni bir grafik oluşturur. Grafik türünü (`ChartType.Pie`), X/Y koordinatlarını ve genişlik/yüksekliği sağlayın. Oluşturulduktan sonra, başlıkları, lejandı ve veri serilerini `ChartData` nesnesi aracılığıyla özelleştirebilirsiniz.

### Grafiği Excel'e Aktarma – Grafik Verilerini Dışa Aktarma
Grafik verilerini dışa aktarmak, analistlerin sayılarla Excel'de çalışmasını sağlar ve daha derin içgörüler elde etmeyi mümkün kılar.  
`readWorkbookStream()` grafiğin temel Excel çalışma kitabını bir bayt dizisi olarak döndürür. Çalışma kitabını almak için `chart.getChartData().readWorkbookStream()` çağırın ve bu diziyi standart Java I/O kullanarak `externalWorkbook1.xlsx` adlı bir dosyaya yazın. Oluşan Excel dosyası, grafikte kullanılan tam verileri içerir ve daha fazla analiz için hazırdır.

### Grafik Oluşturma – Dinamik Veri için Harici Çalışma Kitabı Ayarlama
Grafiği, slaytı yeniden oluşturmak zorunda kalmadan canlı veri güncellemelerini mümkün kılmak için harici bir çalışma kitabına bağlayın.  
`setExternalWorkbook()` grafiği dinamik veri güncellemeleri için harici bir Excel dosyasına bağlar. Grafiği harici dosyaya bağlamak için `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` kullanın. Excel çalışma kitabı düzenlendiğinde, grafik bir sonraki sunum açılışında değişiklikleri otomatik olarak yansıtır ve dinamik raporlama senaryolarını destekler.

## Pratik Uygulamalar
Aspose.Slides, çeşitli gerçek dünya senaryoları için çok yönlü çözümler sunar:

1. **İş Raporu Slaytları:** Veri hatlarından çeyrek dönem performans grafiklerini otomatik olarak oluşturun.  
2. **Akademik Sunumlar:** Araştırma verilerini manuel grafik oluşturmaya gerek kalmadan net görsellere dönüştürün.  
3. **Finansal Analiz:** Denetçiler için sayıları doğrulamak amacıyla grafik verilerini Excel'e aktarın, manuel hataları azaltın.  
4. **Pazarlama Analitiği:** Kampanya metriklerini görselleştirin ve paydaşlarla işbirlikçi karar alma için düzenlenebilir çalışma kitaplarını paylaşın.  
5. **Otomatik Pano Oluşturma:** Grafik oluşturma API'sini zamanlanmış görevlerle birleştirerek her sabah güncel slayt setleri üretin.

## Yaygın Sorunlar ve Sorun Giderme
- `FileNotFoundException` – `dataDir`'in geçerli bir klasöre işaret ettiğini ve çıktı yolunun yazılabilir olduğunu doğrulayın.  
- Bellek sızıntıları – Yerel kaynakları serbest bırakmak için her zaman bir `finally` bloğunda `presentation.dispose()` çağırın.  
- Grafik görünmüyor – Slayt indeksinin (`get_Item(0)`) mevcut bir slaytla eşleştiğinden ve grafiğin boyutlarının slayt sınırları içinde olduğundan emin olun.  
- Excel dışa aktarımı boş dosya oluşturuyor – `readWorkbookStream()` çağırmadan önce grafiğin gerçekten veri serileri içerdiğini doğrulayın.

## Sık Sorulan Sorular

**Q: Aynı kodla farklı bir grafik türü (ör. Bar, Line) kullanabilir miyim?**  
A: Evet. `ChartType.Pie` yerine `ChartType.Bar` veya `ChartType.Line` gibi başka bir `ChartType` enum değerini kullanın.

**Q: Grafik oluşturulduktan sonra harici çalışma kitabını güncellemek mümkün mü?**  
A: Kesinlikle. Excel dosyasını doğrudan değiştirin; bağlanan grafik bir sonraki sunum açılışında değişiklikleri yansıtacaktır.

**Q: Excel dışa aktarım özelliği için ayrı bir lisansa ihtiyacım var mı?**  
A: Hayır. Excel dışa aktarım yeteneği standart Aspose.Slides for Java lisansına dahildir.

**Q: Hangi Java sürümleri destekleniyor?**  
A: Aspose.Slides for Java, JDK 16 ve üzerini destekler; daha eski sürümler çalışabilir ancak resmi olarak test edilmemiştir.

**Q: Oluşturulan Excel çalışma kitabını PPTX dosyasına nasıl gömebilirim?**  
A: `chart.getChartData().setExternalWorkbook(null)` kullanarak çalışma kitabını gömebilir, ya da dinamik güncellemeler için harici bağlantıyı tutabilirsiniz.

---

**Son Güncelleme:** 2026-06-03  
**Test Edilen:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Yazar:** Aspose  

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

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Java'da Aspose.Slides ile Grafik Oluştur – Grafik Ekle ve Doğrula Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Aspose.Slides Java Kullanarak PowerPoint Grafiklerinden Çalışma Kitabı Verilerini Kurtar](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides for Java Kullanarak PowerPoint Grafik Veri Aralığını Güncelleme](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}