---
"date": "2025-04-17"
"description": "Java için Aspose.Slides kullanarak .NET sunumlarında grafiklerin nasıl oluşturulacağını ve özelleştirileceğini öğrenin. Sunum verilerinizin görselleştirilmesini geliştirmek için bu adım adım kılavuzu izleyin."
"title": "Java için Aspose.Slides&#58; .NET Sunularında Grafikler Oluşturma"
"url": "/tr/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java için Aspose.Slides Kullanarak .NET Sunumlarında Grafikler Oluşturma
## giriiş
İkna edici sunumlar oluşturmak, genellikle izleyici anlayışını ve etkileşimini geliştirmek için grafikler gibi görsel veri gösterimlerini entegre etmeyi içerir. Java için Aspose.Slides kullanarak .NET sunumlarınıza dinamik, özelleştirilebilir grafikler eklemek isteyen bir geliştiriciyseniz, bu eğitim tam size göre. Sunumları nasıl başlatabileceğinizi, çeşitli grafik türlerini nasıl ekleyebileceğinizi, grafik verilerini nasıl yönetebileceğinizi ve seri verilerini nasıl etkili bir şekilde biçimlendirebileceğinizi inceleyeceğiz.
**Ne Öğreneceksiniz:**
- .NET ortamınızda Java için Aspose.Slides'ı nasıl kurabilir ve kullanabilirsiniz.
- Aspose.Slides kullanılarak yeni bir sunum başlatılıyor.
- Slaytlara grafik ekleme ve özelleştirme.
- Grafik veri çalışma kitaplarını yönetme.
- Seri verilerinin biçimlendirilmesi, özellikle negatif değerlerin işlenmesi.
Ön koşullar bölümüne geçiş yapmanız, süreci kolaylıkla takip edebilmenizi sağlayacaktır.
## Ön koşullar
Aspose.Slides for Java ile grafik oluşturmaya başlamadan önce, neye ihtiyacınız olduğunu ana hatlarıyla belirtelim:
### Gerekli Kütüphaneler ve Sürümler
Aşağıdaki bağımlılıklara sahip olduğunuzdan emin olun:
- **Java için Aspose.Slides**: Sürüm 25.4 veya üzeri.
### Çevre Kurulum Gereksinimleri
- .NET uygulamalarını destekleyen bir geliştirme ortamı.
- Java programlama kavramlarının temel düzeyde anlaşılması.
### Bilgi Önkoşulları
- .NET uygulama bağlamında sunum oluşturma konusunda bilgi sahibi olmak.
- Java bağımlılıklarını ve bunların yönetimini anlamak (Maven/Gradle).
## Java için Aspose.Slides Kurulumu
Aspose.Slides'ı kullanmaya başlamak için onu projenize bir bağımlılık olarak eklemeniz gerekir. Bunu şu şekilde yapabilirsiniz:
### Usta
Aşağıdaki bağımlılığı ekleyin `pom.xml` dosya:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
Bunu da ekleyin `build.gradle` dosya:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Doğrudan İndirme
Alternatif olarak, en son sürümü şu adresten indirebilirsiniz: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).
#### Lisans Edinme Adımları
- **Ücretsiz Deneme**:Özellikleri keşfetmek için geçici bir lisansla başlayın.
- **Satın almak**Geniş kapsamlı kullanım için lisans satın almayı düşünebilirsiniz.
#### Temel Başlatma ve Kurulum
Aspose.Slides'ı kodunuzda şu şekilde başlatabilirsiniz:
```java
import com.aspose.slides.Presentation;
// Yeni bir Sunum nesnesi başlatın
Presentation pres = new Presentation();
try {
    // Buradaki mantığınız...
} finally {
    if (pres != null) pres.dispose();
}
```
Bu kurulum kaynak yönetiminin etkin bir şekilde yapılmasını sağlar.
## Uygulama Kılavuzu
Özelliklerin nasıl uygulanacağını adım adım anlatacağız.
### Sunumu Başlatma
**Genel Bakış:**
Bir sunum örneği oluşturmak, sonraki tüm işlemler için sahneyi hazırlar. Bu özellik, Aspose.Slides'ı kullanarak sıfırdan nasıl başlayacağınızı gösterir.
#### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.aspose.slides.Presentation;
```
#### Adım 2: Yeni Bir Sunum Nesnesi Oluşturun
İşte bunu nasıl yapacağınız:
```java
Presentation pres = new Presentation();
try {
    // Kod mantığınız burada...
} finally {
    if (pres != null) pres.dispose(); // Kaynakların serbest bırakılmasını sağlar
}
```
*Bu, sunum nesnesinin kullanımdan sonra uygun şekilde atılmasını sağlayarak bellek sızıntılarının önlenmesini sağlar.*
### Slayta Grafik Ekleme
**Genel Bakış:**
Slaydınıza bir grafik eklemek, veri görselleştirmesini daha etkili ve ilgi çekici hale getirebilir.
#### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```
#### Adım 2: Sunumu Başlatın ve Grafik Ekleyin
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Grafik özelleştirme için ek mantık...
} finally {
    if (pres != null) pres.dispose();
}
```
*Burada, ilk slayta belirtilen koordinatlarda ve boyutlarda kümelenmiş sütun grafiği ekliyoruz.*
### Grafik Verilerini Yönetme Çalışma Kitabı
**Genel Bakış:**
Grafiklerinizin veri çalışma kitabını etkin bir şekilde yönetmek, serileri ve kategorileri sorunsuz bir şekilde düzenlemenize olanak tanır.
#### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```
#### Adım 2: Veri Çalışma Kitabına Erişim ve Temizleme
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Mevcut verileri temizle
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Özelleştirme mantığınız burada...
} finally {
    if (pres != null) pres.dispose();
}
```
*Yeni seriler ve kategoriler eklerken temiz bir sayfa ile başlamak için çalışma kitabını temizlemek çok önemlidir.*
### Tabloya Seri ve Kategori Ekleme
**Genel Bakış:**
Bu özellik, serileri ve kategorileri yöneterek anlamlı veri noktalarının nasıl eklenebileceğini gösterir.
#### Adım 1: Seri ve Kategoriler Ekleyin
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Mevcut serileri ve kategorileri temizle
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Yeni seriler ve kategoriler ekleyin
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Daha fazla özelleştirme mantığı...
} finally {
    if (pres != null) pres.dispose();
}
```
*Seri ve kategori eklemek, verilerin daha düzenli bir şekilde sunulmasını sağlar.*
### Seri Verilerinin Doldurulması ve Biçimlendirilmesi
**Genel Bakış:**
Özellikle negatif değerlerle uğraşırken okunabilirliği artırmak için grafiğinizi veri noktalarıyla doldurun ve görünümü biçimlendirin.
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

    // Seri ve kategoriler ekleyin (önceki mantığı yeniden kullanın)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Negatif değerler için seriyi biçimlendir
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

    // Sunumu kaydet
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*Bu bölümde, verilerin nasıl doldurulacağı ve daha iyi görselleştirme için renk biçimlendirmesinin nasıl uygulanacağı gösterilmektedir.*

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}