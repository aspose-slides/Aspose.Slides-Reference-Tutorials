---
"date": "2025-04-17"
"description": "Aspose.Slides ile Java sunumlarında halka grafikleri oluşturmayı ve özelleştirmeyi, ortamınızı kurmayı ve grafik estetiğini ayarlamayı öğrenin."
"title": "Sunumlar için Aspose.Slides Kullanarak Java'da Halka Grafikleri Nasıl Oluşturulur"
"url": "/tr/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Sunumlar için Aspose.Slides Kullanarak Java'da Halka Grafikleri Nasıl Oluşturulur

## giriiş
Görsel olarak çekici sunumlar oluşturmak, bilgileri etkili bir şekilde iletmek için olmazsa olmazdır. Grafikler, veri dağılımlarının anlaşılmasını geliştiren önemli unsurlardır. Bu eğitim, Aspose.Slides for Java kullanarak özelleştirilebilir halka grafikleri oluşturmanıza rehberlik ederek, delik boyutu ve konumlandırma gibi kapsamlı özelleştirme seçenekleriyle zahmetsiz grafik oluşturmanızı sağlar.

**Ne Öğreneceksiniz:**
- Java için Aspose.Slides Kurulumu
- Sunumlarda halka grafikleri oluşturma ve yapılandırma
- Delik boyutu gibi grafik estetiğini ayarlama
- Sunumu yeni grafiğinizle kaydetme

Ortamımızı ayarlayarak başlayalım!

## Ön koşullar
Başlamadan önce, aşağıdaki ön koşulların sağlandığından emin olun:

### Gerekli Kütüphaneler ve Sürümler
Java için Aspose.Slides ile çalışmak için, bunu Maven veya Gradle aracılığıyla projenize dahil edebilir veya doğrudan indirebilirsiniz.

#### Çevre Kurulum Gereksinimleri
- Çalışan bir Java Geliştirme Kiti (JDK), tercihen sürüm 8 veya üzeri.
- IntelliJ IDEA veya Eclipse gibi Entegre Geliştirme Ortamı (IDE).

### Bilgi Önkoşulları
Java ve temel programlama kavramlarına aşinalık faydalıdır. Maven veya Gradle'ın temel bilgisi kurulum sürecini kolaylaştırmaya yardımcı olacaktır.

## Java için Aspose.Slides Kurulumu
Aspose.Slides'ı projenize dahil etmenin birkaç yolu vardır:

**Usta:**
Bu bağımlılığı şuna ekleyin: `pom.xml` dosya:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
Bunu da ekleyin `build.gradle` dosya:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Doğrudan İndirme:**
Alternatif olarak, en son sürümü şu adresten indirin: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).

### Lisans Edinimi
- **Ücretsiz Deneme**: Aspose.Slides özelliklerini keşfetmek için öncelikle deneme sürümünü indirin.
- **Geçici Lisans**: Sınırlama olmaksızın genişletilmiş işlevsellik için geçici bir lisans edinin.
- **Satın almak**: Sürekli kullanım için lisans satın alınması gerekmektedir.

Kütüphaneyi kurduktan ve ortamınızı hazırladıktan sonra, halka grafiğimizi uygulamaya geçelim.

## Uygulama Kılavuzu

### Bir Çörek Grafiği Oluşturma
Aspose.Slides kullanarak özelleştirilmiş bir halka grafiğiyle bir sunum oluşturmak birkaç adımdan oluşur. Bunları anlaşılırlık için parçalara ayıracağız:

#### Sunum Nesnesini Başlat
Bir örnek oluşturarak başlayın `Presentation` PowerPoint belgenizi temsil eden sınıf.
```java
// Bir PPTX belgesini temsil etmek için bir Sunum sınıfı örneği oluşturun
Presentation presentation = new Presentation();
```
Bu adım, slaytlar ve grafikler ekleyebileceğiniz sunumunuzu başlatır.

#### Slayda Çörek Grafiği Ekle
İlk slayda erişin (veya gerekirse bir tane oluşturun) ve bir halka grafiği ekleyin:
```java
// Sunumdaki ilk slayda erişin
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // (50, 50) konumunda 400x400 boyutunda
```
Bu kod parçacığı ilk slayda bir halka grafiği ekler. Parametreler slayttaki konumunu ve boyutlarını tanımlar.

#### Donut Deliği Boyutunu Yapılandır
Halka grafiğinize benzersiz bir görünüm kazandırmak için delik boyutunu ayarlayın:
```java
// Halka grafiği için delik boyutunu %90 olarak ayarlayın
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```
Burada, delik boyutunu %90'a ayarlıyoruz ve bu da onu neredeyse tam bir daire yapıyor. Bu değeri tasarım ihtiyaçlarınıza göre ayarlayın.

#### Sunumu Kaydet
Grafiğinizi yapılandırdıktan sonra sunumu kaydedin:
```java
// Sunumu belirtilen dizindeki PPTX formatında diske kaydedin
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```
Bu satır değişikliklerinizi şu adlı bir dosyaya yazar: `DoughnutHoleSize_out.pptx` Belirlediğiniz dizinde.

#### Temizleme Kaynakları
Son olarak sunum nesnesini elden çıkardığınızdan emin olun:
```java
// Kaynakları serbest bırakmak için sunum nesnesini elden çıkarın
if (presentation != null) presentation.dispose();
```
Bu adım kaynak yönetimi ve bellek sızıntılarının önlenmesi açısından kritik öneme sahiptir.

### Pratik Uygulamalar
Donut grafikleri çok yönlüdür. İşte parladıkları bazı senaryolar:
1. **Bütçe Tahsisi**: Bütçenin departmanlar arasında nasıl dağıtıldığını gösterir.
2. **Anket Sonuçları**: Çoktan seçmeli cevaplara sahip soruların yanıtlarını görselleştirin.
3. **Web Sitesi Trafik Kaynakları**: Farklı kaynaklardan gelen trafiğin yüzdesini gösterin.

### Performans Hususları
Aspose.Slides ile çalışırken en iyi performansı elde etmek için şu ipuçlarını göz önünde bulundurun:
- Artık ihtiyaç duyulmayan nesnelerden kurtularak hafızayı yönetin.
- Bellek kullanımını en aza indirmek için büyük veri kümelerinde akışları kullanın.
- Mümkün olan yerlerde örnekleri yeniden kullanarak kodunuzu optimize edin.

## Çözüm
Tebrikler! Java için Aspose.Slides kullanarak bir halka grafiği oluşturmayı ve özelleştirmeyi öğrendiniz. Bu eğitim, kütüphaneyi kurmayı, sunumlara grafikler eklemeyi ve görünümlerini ayarlamayı kapsıyordu.

Aspose.Slides'ın yeteneklerini keşfetmeye devam etmek için diğer grafik türlerini denemeyi veya sunum otomasyonu özelliklerini daha derinlemesine incelemeyi düşünebilirsiniz.

**Sonraki Adımlar:**
- Farklı grafik yapılandırmalarını deneyin.
- Daha gelişmiş özellikler için Aspose.Slides'ın ek belgelerini inceleyin.

Kendi donut grafiklerinizi oluşturmaya hazır mısınız? Bu çözümü bir sonraki projenizde uygulamaya çalışın!

## SSS Bölümü
1. **Halka grafiği segmentlerimin renklerini ayarlayabilir miyim?**
   Evet, segment renklerini kullanarak özelleştirebilirsiniz `chart.getChartData().getSeries(i).getDataPointsForBarChart().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid);` Düz bir dolgu türü belirlemek ve istediğiniz rengi belirtmek için.

2. **Grafiğime veri etiketleri nasıl eklerim?**
   Kullanmak `chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category"));` ve veri noktalarını ve etiketleri programatik olarak eklemek için benzer yöntemler.

3. **Grafikleri PPTX dışındaki formatlarda kaydetmek mümkün müdür?**
   Kesinlikle! Aspose.Slides, PDF, XPS ve PNG veya JPEG gibi çeşitli çıktı formatlarını destekler.

4. **Sunumu kaydederken bir hatayla karşılaşırsam ne olur?**
   Dizin yolunuzun doğru olduğundan ve belirtilen konum için yazma izinlerinizin olduğundan emin olun. Kullandığınız Aspose.Slides sürümünün kaydetmeye çalıştığınız dosya biçimini destekleyip desteklemediğini kontrol edin.

5. **Canlı veri kaynaklarıyla grafik güncellemelerini otomatikleştirebilir miyim?**
   Evet, Java uygulamanıza API'leri veya veritabanlarını entegre ederek grafik verilerini dinamik olarak güncelleyebilir ve sunumları gerektiğinde yenileyebilirsiniz.

## Kaynaklar
- **Belgeleme**: Ayrıntılı API referanslarını şu adreste inceleyin: [Java için Aspose.Slides](https://reference.aspose.com/slides/java/).
- **İndirmek**: En son kütüphane sürümünü şu adresten edinin: [Aspose.Slides sürümleri](https://releases.aspose.com/slides/java/).
- **Satın almak**: Tam erişim için şu adresten bir lisans satın alın: [Aspose Satın Alma](https://purchase.aspose.com/buy).
- **Ücretsiz Deneme**:Aspose.Slides'ı ücretsiz deneme sürümüyle birlikte indirme sayfasından test edin.
- **Geçici Lisans**Sınırlama olmaksızın genişletilmiş testler için geçici lisans edinin.
- **Destek**: Sorularınız mı var? Ziyaret edin [Aspose Forum](https://forum.aspose.com/c/slides/11) yardım için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}