---
date: '2026-01-14'
description: Aspose.Slides for Java kullanarak .NET sunumlarına kümelenmiş sütun grafiği
  eklemeyi ve slayta grafik eklemeyi öğrenin. Tam kod örnekleriyle adım adım bu rehberi
  izleyin.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: Aspose.Slides Java ile .NET slaytlarına küme sütun grafiği ekleyin
url: /tr/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# .NET Sunumlarında Aspose.Slides for Java Kullanarak Grafik Oluşturma
## Giriş
Etkileyici sunumlar oluşturmak, izleyicilerin anlayışını ve katılımını artırmak için grafikler gibi görsel veri temsillerini entegre etmeyi gerektirir. .NET sunumlarınıza dinamik, özelleştirilebilir grafikler eklemek isteyen bir geliştiriciyseniz, bu öğretici tam size göre. Sunumları nasıl başlatacağınızı, çeşitli grafik türlerini nasıl ekleyeceğinizi, grafik verilerini nasıl yöneteceğinizi ve seri verilerini etkili bir şekilde nasıl biçimlendireceğinizi inceleyeceğiz.

**Öğrenecekleriniz:**
- Aspose.Slides for Java’yı .NET ortamınızda nasıl kurup kullanacağınız.
- Aspose.Slides ile yeni bir sunumun başlatılması.
- Slaytlara grafik ekleme ve özelleştirme.
- Grafik veri çalışma kitaplarının yönetimi.
- Seri verilerinin biçimlendirilmesi, özellikle negatif değerlerin işlenmesi.

Ön koşullar bölümüne geçmek, sorunsuz bir şekilde ilerlemenizi sağlayacaktır.

## Hızlı Yanıtlar
- **Ana hedef nedir?** .NET slaytına bir kümelenmiş sütun grafiği eklemek.
- **Hangi kütüphane gereklidir?** Aspose.Slides for Java (v25.4+).
- **Bunu bir .NET projesinde kullanabilir miyim?** Evet – Java kütüphanesi Java‑to‑.NET köprüsü aracılığıyla çalışır.
- **Lisans gerekiyor mu?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gereklidir.
- **Uygulama ne kadar sürer?** Temel bir grafik için yaklaşık 10‑15 dakika.

## Kümelenmiş Sütun Grafiği Nedir?
Kümelenmiş sütun grafiği, her kategori için birden fazla veri serisini yan yana gösterir ve gruplar arasındaki değerleri karşılaştırmayı kolaylaştırır. Bu görsel, iş panoları, performans raporları ve birden fazla metriği karşılaştırmanız gereken her senaryo için idealdir.

## Aspose.Slides for Java ile slayta neden grafik eklenir?
Aspose.Slides, Microsoft PowerPoint yüklü olmadan sunumları oluşturmanıza, değiştirmenize ve kaydetmenize olanak tanır. Grafik türleri, veri ve stil üzerinde tam kontrol sağlar; bu da .NET uygulamalarınızdan doğrudan rapor üretimini otomatikleştirmenize imkan verir.

## Ön Koşullar
Aspose.Slides for Java ile grafik oluşturmaya başlamadan önce ihtiyaç duyacaklarınızın bir özetini aşağıda bulabilirsiniz:

### Gereken Kütüphaneler ve Sürümler
- **Aspose.Slides for Java**: Sürüm 25.4 veya üzeri.

### Ortam Kurulum Gereksinimleri
- .NET uygulamalarını destekleyen bir geliştirme ortamı.
- Java programlama kavramlarına temel bir anlayış.

### Bilgi Ön Koşulları
- .NET uygulama bağlamında sunum oluşturma konusunda aşina olmak.
- Java bağımlılıkları ve yönetimi (Maven/Gradle) hakkında bilgi sahibi olmak.

## Aspose.Slides for Java Kurulumu
Aspose.Slides’i projenize bağımlılık olarak eklemeniz gerekir. İşte nasıl yapacağınız:

### Maven
`pom.xml` dosyanıza aşağıdaki bağımlılığı ekleyin:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` dosyanıza şunu ekleyin:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
Alternatif olarak, en son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

#### Lisans Edinme Adımları
- **Ücretsiz Deneme**: Özellikleri keşfetmek için geçici bir lisansla başlayın.
- **Satın Alma**: Yoğun kullanım için bir lisans almayı düşünün.

#### Temel Başlatma ve Kurulum
Kodunuzda Aspose.Slides’i nasıl başlatacağınız aşağıda gösterilmiştir:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
Bu kurulum, kaynak yönetiminin etkili bir şekilde ele alınmasını sağlar.

## Uygulama Kılavuzu
Özellikleri adım adım uygulamanız için size rehberlik edeceğiz.

### Sunumu Başlatma
**Genel Bakış:**  
Bir sunum örneği oluşturmak, sonraki tüm işlemler için temeli atar. Bu özellik, Aspose.Slides kullanarak sıfırdan nasıl başlanacağını gösterir.

#### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.aspose.slides.Presentation;
```

#### Adım 2: Yeni Bir Presentation Nesnesi Oluşturun
Şöyle yapabilirsiniz:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Bu, sunum nesnesinin kullanım sonrası doğru şekilde dispose edilmesini sağlayarak bellek sızıntılarını önler.*

### Slayta Grafik Ekleme
**Genel Bakış:**  
Slayta bir grafik eklemek, veri görselleştirmesini daha etkili ve ilgi çekici hâle getirir.

#### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Adım 2: Sunumu Başlatın ve Grafiği Ekleyin
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*Burada, belirtilen koordinat ve boyutlarda ilk slayta bir kümelenmiş sütun grafiği ekliyoruz.*

### Grafik Veri Çalışma Kitabını Yönetme
**Genel Bakış:**  
Grafiğinizin veri çalışma kitabını verimli bir şekilde yönetmek, serileri ve kategorileri sorunsuz bir şekilde manipüle etmenizi sağlar.

#### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Adım 2: Veri Çalışma Kitabına Erişin ve Temizleyin
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*Yeni seriler ve kategoriler eklerken temiz bir başlangıç yapmak için çalışma kitabının temizlenmesi kritik öneme sahiptir.*

### Grafiğe Seri ve Kategori Ekleme
**Genel Bakış:**  
Bu özellik, anlamlı veri noktaları eklemek için serileri ve kategorileri nasıl yöneteceğinizi gösterir.

#### Adım 1: Seri ve Kategorileri Ekleyin
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*Seri ve kategorilerin eklenmesi, daha düzenli bir veri sunumu sağlar.*

### Seri Verilerini Doldurma ve Biçimlendirme
**Genel Bakış:**  
Grafiğinizi veri noktalarıyla doldurun ve özellikle negatif değerlerle çalışırken okunabilirliği artırmak için görünümü biçimlendirin.

#### Adım 1: Seri Verilerini Doldurun
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*Bu bölüm, verileri doldurmayı ve daha iyi görselleştirme için renk biçimlendirmeyi gösterir.*

## Yaygın Sorunlar ve Çözümler
- **Bellek sızıntıları:** `Presentation` nesnesi üzerinde `finally` bloğunda her zaman `dispose()` çağırın.
- **Yanlış grafik türü:** Kümelenmiş sütun grafiği istediğinizde `ChartType.ClusteredColumn` kullandığınızdan emin olun; diğer türler farklı görsel sonuçlar üretir.
- **Negatif değer renkleri uygulanmıyor:** `IDataPoint` değerinin karşılaştırmadan önce doğru şekilde `Number` tipine cast edildiğini doğrulayın.

## Sık Sorulan Sorular

**S: Aspose.Slides for Java’yı saf bir .NET projesinde Java olmadan kullanabilir miyim?**  
C: Evet. Kütüphane, Java‑to‑.NET köprüsü aracılığıyla çalışır ve .NET dillerinden Java API’lerini çağırmanıza olanak tanır.

**S: Ücretsiz deneme sürümü grafik oluşturmayı destekliyor mu?**  
C: Deneme sürümü tam grafik işlevselliğini içerir, ancak oluşturulan dosyalarda küçük bir değerlendirme filigranı bulunur.

**S: Hangi .NET sürümleri uyumludur?**  
C: Java 16+ ile etkileşime girebilen herhangi bir .NET sürümü; .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7 dahil.

**S: Çok sayıda grafik içeren büyük sunumları nasıl yönetirim?**  
C: Mümkün olduğunca aynı `IChartDataWorkbook` örneğini yeniden kullanın ve her `Presentation` nesnesini zamanında dispose ederek belleği serbest bırakın.

**S: Grafiği görüntü olarak dışa aktarmak mümkün mü?**  
C: Evet. `chart.getImage()` veya `chart.exportChartImage()` metodlarını kullanarak PNG/JPEG temsilleri elde edebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-01-14  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4  
**Yazar:** Aspose  

---