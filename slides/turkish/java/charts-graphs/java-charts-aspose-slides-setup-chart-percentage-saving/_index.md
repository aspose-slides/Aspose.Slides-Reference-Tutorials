---
"date": "2025-04-17"
"description": "Aspose.Slides kullanarak Java sunumlarında yüzde etiketleriyle grafiklerin nasıl oluşturulacağını, özelleştirileceğini ve kaydedileceğini öğrenin. Sunum becerilerinizi bugün geliştirin!"
"title": "Aspose.Slides Kullanarak Java Sunularında Grafikler Oluşturun ve Özelleştirin"
"url": "/tr/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Kullanarak Java Sunularında Grafikler Oluşturun ve Özelleştirin

## giriiş
İkna edici sunumlar oluşturmak genellikle sadece metinden fazlasını gerektirir; bilgileri etkili bir şekilde ileten dinamik grafikler gerektirir. Java tabanlı sunumlarınızı Aspose.Slides kullanarak gelişmiş grafik özellikleriyle geliştirmek istiyorsanız, bu eğitim tam size göre. Bir sunum oluşturma, grafik ekleme ve yapılandırma, toplamları hesaplama, yüzde etiketlerini görüntüleme ve çalışmanızı kaydetme konusunda size rehberlik edeceğiz; hepsi sadece birkaç kolay adımda.

**Ne Öğreneceksiniz:**
- Java için Aspose.Slides'ı kullanarak grafiklerle sunumlar nasıl oluşturulur ve özelleştirilir
- Grafiklerde kategori toplamlarının hesaplanması
- Verileri grafiklerde yüzde etiketleri olarak görüntüleme
- Gelişmiş grafik özellikleriyle sunumları kaydetme

Başlamadan önce ihtiyacınız olan ön koşullara bir göz atalım.

## Ön koşullar
Bu eğitimi takip edebilmek için aşağıdakilere sahip olduğunuzdan emin olun:

- **Java Geliştirme Kiti (JDK)**: Sürüm 8 veya üzeri.
- **İDE**: IntelliJ IDEA, Eclipse veya herhangi bir Java destekli IDE gibi.
- **Java Kütüphanesi için Aspose.Slides**: Bu, sunum özelliklerinin kullanımı açısından kritik öneme sahiptir.

### Gerekli Kütüphaneler ve Sürümler
Java için Aspose.Slides'a ihtiyacınız olacak. Bunu projenize nasıl dahil edeceğiniz aşağıda açıklanmıştır:

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

Alternatif olarak, en son sürümü doğrudan şu adresten indirebilirsiniz: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).

### Çevre Kurulumu
Geliştirme ortamınızın JDK 8 veya üzerini kullanacak şekilde yapılandırıldığından ve IDE'nizin Maven veya Gradle kullanarak bağımlılıkları yönetecek şekilde ayarlandığından emin olun.

**Lisans Edinimi:**
- **Ücretsiz Deneme**: Test amaçlı temel özelliklere erişin.
- **Geçici Lisans**: Değerlendirme sınırlamaları olmadan gelişmiş özellikleri test edin.
- **Satın almak**: Uzun vadeli ticari kullanım için lisans satın almayı düşünebilirsiniz.

## Java için Aspose.Slides Kurulumu
Java projenizde Aspose.Slides kütüphanesini kurarak başlayın. İşte nasıl başlatacağınız ve yapılandıracağınız:

1. Yukarıda gösterildiği gibi Maven veya Gradle üzerinden bağımlılığı ekleyin.
2. Gerekli Aspose.Slides paketlerini içe aktarın:
   ```java
   import com.aspose.slides.*;
   ```

3. Yeni bir tane başlat `Presentation` misal:
   ```java
   Presentation presentation = new Presentation();
   ```

Bu kurulum, sunumları programlı olarak oluşturmaya başlamanızı sağlayacaktır.

## Uygulama Kılavuzu

### Sununuzda Grafikler Oluşturun ve Özelleştirin

#### Genel bakış
Bir grafik oluşturmak, sununuzu başlatmayı, slaytlara erişmeyi ve tür, konum ve boyut gibi belirli niteliklere sahip bir grafik eklemeyi içerir.

**Adımlar:**
1. **Sunum Örneği Oluştur**: Bir örnek oluşturarak başlayın `Presentation` sınıf.
2. **Erişim Slaytı**: İlk slaydı kullanarak alın `get_Item(0)`.
3. **Grafik Ekle**: Kullanmak `addChart()` Belirtilen koordinatlara tanımlanmış boyutlara sahip yığılmış sütun grafiği eklemek için.

```java
// Özellik: Grafikle Bir Sunum Oluşturun
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Kategoriler için Toplamları Hesapla

#### Genel bakış
Kategori toplamlarının hesaplanması, kategori başına değerleri toplamak için grafikteki her bir seri üzerinde yineleme yapmayı içerir.

**Adımlar:**
1. **Diziyi Başlat**: Toplam değerleri tutacak bir dizi oluşturun.
2. **Kategoriler ve Seriler Arasında Yineleme**: Tüm serilerden her kategori için toplamları toplamak amacıyla iç içe döngüler kullanın.

```java
// Özellik: Bir Grafikteki Kategoriler için Toplamları Hesapla
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Verileri Bir Grafikte Yüzde Etiketleri Olarak Görüntüleme

#### Genel bakış
Bu özellik, görselleştirmede netlik sağlamak amacıyla, değerleri yüzde olarak gösterecek şekilde veri etiketlerinin yapılandırılmasına odaklanır.

**Adımlar:**
1. **Seri Etiketlerini Yapılandır**: Yazı tipi boyutu ve efsane tuşlarının görünürlüğü gibi etiket özelliklerini ayarlayın.
2. **Yüzdeleri Hesapla**:Toplam kategori değerine göre her veri noktası için yüzdeyi hesaplayın.
3. **Etiket Metnini Ayarla**: Etiketleri yüzdeleri iki ondalık nokta ile gösterecek şekilde biçimlendirin.

```java
// Özellik: Verileri Bir Grafikte Yüzde Etiketleri Olarak Görüntüleme
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Sunumu Grafikle Kaydet

#### Genel bakış
Son olarak sunumunuzu PPTX formatında belirtilen yola kaydedin.

**Adımlar:**
1. **Kaydetme Yöntemi**: Kullanın `save()` yöntem üzerinde `Presentation` misal.
2. **Kaynakları elden çıkarın**:Kaydedildikten sonra kaynakların serbest bırakıldığından emin olun.

```java
// Özellik: Sunumu Grafikle Kaydet
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Pratik Uygulamalar

1. **Finansal Raporlama**: Departmanlar arası gelir büyüme yüzdelerini görüntülemek için grafikleri kullanın.
2. **Satış Veri Analizi**:Daha net içgörüler için satış verilerini bölgelere göre yüzde etiketleriyle görselleştirin.
3. **Eğitim Sunumları**: Akademik sunumlarınızı görsel istatistiklerle geliştirin.
4. **Pazarlama Kampanyaları**:Kampanya performans metriklerini ilgi çekici görsellerle görüntüleyin.
5. **İş Stratejisi Toplantıları**: Stratejik planlama tartışmalarında karmaşık verileri aktarmak için grafikleri kullanın.

## Performans Hususları
- **Bellek Yönetimi**: Bertaraf etmek `Presentation` Kaynakları serbest bırakmak için nesneleri derhal serbest bırakın.
- **Grafik Yüklemesini Optimize Et**: Mümkünse yalnızca gerekli grafik öğelerini belleğe yükleyin.
- **Toplu İşleme**: Birden fazla sunumu işlerken, kaynak tüketimini etkili bir şekilde yönetmek için bunları gruplar halinde ele almayı düşünün.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}