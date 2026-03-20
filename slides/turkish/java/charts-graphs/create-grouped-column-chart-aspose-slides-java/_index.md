---
date: '2026-03-20'
description: PowerPoint sunumuna gruplanmış sütun grafiği eklemeyi, PowerPoint grafiğini
  özelleştirmeyi ve Aspose.Slides for Java kullanarak veri serisi grafiği eklemeyi
  öğrenin.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Aspose.Slides for Java kullanarak PowerPoint'e küme sütun grafiği nasıl eklenir
url: /tr/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint'te Aspose.Slides for Java kullanarak kümelenmiş sütun grafiği ekleme

## Giriş

PowerPoint sunumuna **kümelenmiş sütun grafiği** eklemeniz gerektiğinde, net bir görsel ham sayıları anında anlaşılır bir hikayeye dönüştürebilir. Bunu PowerPoint'te manuel olarak yapmak zaman alıcı olabilir, özellikle birçok slaytı programlı olarak oluşturmanız gerektiğinde. **Aspose.Slides for Java** bu zorluğu ortadan kaldırır – sadece birkaç satır kodla PowerPoint grafiği oluşturmanıza, özelleştirmenize ve veri serisi grafiği eklemenize olanak tanır.

Bu öğreticide şunları öğreneceksiniz:
- Aspose.Slides for Java ile yeni bir PowerPoint sunumu başlatın.
- **Grafiği slayta ekleyin** ve kümelenmiş sütun grafiği olarak yapılandırın.
- **Gruplandırılmış sütun grafiği oluşturun** kategori için grup seviyeleri tanımlayarak.
- **Veri serisi grafiği ekleyin** böylece verileriniz doğru şekilde görüntülenir.
- Tamamlanmış sunumu PPTX dosyası olarak kaydedin.

Kodun içine dalmadan önce ihtiyacınız olan her şeyin elinizde olduğundan emin olalım.

## Hızlı Yanıtlar
- **Birincil sınıf nedir?** `Presentation` from `com.aspose.slides`.
- **Hangi grafik türü kullanılıyor?** `ChartType.ClusteredColumn`.
- **Test için lisansa ihtiyacım var mı?** Ücretsiz deneme çalışır, ancak lisans değerlendirme sınırlamalarını kaldırır.
- **Hangi Java sürümü destekleniyor?** JDK 16 veya daha yeni (örnek JDK 16 kullanıyor).
- **Örneği nasıl çalıştırırım?** Maven/Gradle bağımlılığını ekleyin, derleyin ve `main` metodunu çalıştırın.

## “Kümelenmiş sütun grafiği ekleme” nedir?
*Kümelenmiş sütun grafiği* (aynı zamanda *gruplandırılmış sütun grafiği* olarak da adlandırılır) her kategori için birden fazla veri serisini yan yana gösterir, böylece gruplar arasındaki değerleri karşılaştırmak kolaylaşır. PowerPoint'te bu grafik türü çeyrek satışları, anket sonuçlarını veya aynı kategori içinde birden fazla veri setini karşılaştırmanız gereken herhangi bir senaryo için idealdir.

## Kümelenmiş sütun grafiği eklemek için neden Aspose.Slides kullanmalı?
- **Tam otomasyon** – manuel çaba harcamadan onlarca slayt oluşturun.
- **İnce ayarlı özelleştirme** – renkleri, etiketleri, grup seviyelerini ve daha fazlasını kontrol edin.
- **Çapraz platform** – Java destekleyen herhangi bir işletim sisteminde çalışır.
- **Office kurulumu gerektirmez** – sunucularda veya CI boru hatlarında PPTX dosyaları oluşturun.

## Önkoşullar
- **Aspose.Slides for Java** kütüphanesi (en son sürüm önerilir).  
- JDK 16 veya daha yeni.  
- Maven veya Gradle yapı aracı (veya JAR'ı manuel ekleyebilirsiniz).  
- Java kodunu çalıştırmak için bir IDE veya metin düzenleyici.

## Aspose.Slides for Java Kurulumu
Projenize aşağıdaki yapı betiklerinden birini kullanarak kütüphaneyi ekleyin.

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

Alternatif olarak, en son sürümü doğrudan [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

### Lisans Edinme
Üretime dağıtmadan önce bir lisans edinin:
- **Free trial** – satın almadan tüm özellikleri keşfedin.
- **Temporary license** – kısa bir süre için genişletilmiş yetenekleri değerlendirin.
- **Full license** – sınırsız kullanımın kilidini açın. [Aspose satın alma sayfası](https://purchase.aspose.com/buy) adresinden alın.

## Uygulama Rehberi
Her adımı adım adım inceleyeceğiz, **grafiği nasıl ekleyeceğinizi** ve **PowerPoint grafiğini nasıl özelleştireceğinizi** açıklayarak.

### Sunumu Başlatma
İlk olarak, yeni bir `Presentation` nesnesi oluşturun ve varsayılan slaytı alın.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Slayta Grafik Ekleme
Şimdi `ClusteredColumn` türünü kullanarak **grafiği slayta ekliyoruz** ve varsayılan verileri temizliyoruz.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Grafik Veri Çalışma Kitabını Hazırlama
Grafik verilerini dahili bir çalışma kitabında saklar. Yeni başlamak için temizliyoruz.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Gruplama Seviyeleriyle Kategoriler Ekleme
Kategorileri gruplamak **gruplandırılmış sütun grafiği** etkisini yaratır. Her kategori mantıksal bir gruba ait olabilir.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Grafik'e Veri Serisi Ekleme
Burada **veri serisi grafiği ekliyoruz**; bu girişler ayrı sütunlar olarak görselleştirilecektir.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Grafik ile Sunumu Kaydetme
Son olarak, PPTX dosyasını diske yazın.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Pratik Uygulamalar
- **İş Raporları** – bölgeler arasında çeyrek gelirlerini karşılaştırın.  
- **Akademik Araştırma** – deney sonuçlarını test koşullarına göre gruplayarak gösterin.  
- **Proje Yönetimi** – tek bir slaytta birden fazla ekip için görev tamamlama oranlarını görselleştirin.

## Performans Düşünceleri
- **Bellek yönetimi** – kullanım sonrası büyük çalışma kitaplarını serbest bırakın.  
- **Toplu işlemler** – sıkı döngüler içinde grafiği güncellemekten kaçının; önce verileri toplayın, ardından uygulayın.  
- **Yerleşik optimizasyonlar** – Aspose.Slides büyük dosyalar için `Presentation.optimize()` gibi yöntemler sunar.

## Yaygın Tuzaklar ve İpuçları
- **Pitfall:** Mevcut serileri/kategorileri temizlemeyi unutmak, yinelenen verilere yol açabilir.  
  **Tip:** Yeni verileri doldurmadan önce her zaman `clear()` çağırın.  
- **Pitfall:** Yanlış hücre adresi kullanmak (örneğin `"c2"` yerine `"C2"`).  
  **Tip:** Hücre referansları büyük/küçük harfe duyarsızdır, ancak okunabilirlik için tutarlı tutun.  
- **Tip:** Anlamlı grup etiketleri oluşturmak için `setGroupingItem` kullanın; bunlar otomatik olarak grafik açıklamasında görünür.

## Sıkça Sorulan Sorular
**Q1: Grafiğime birden fazla seri nasıl ekleyebilirim?**  
A1: Her seri için benzersiz bir ad ve veri noktaları sağlayarak `ch.getChartData().getSeries().add()` metodunu tekrarlayarak çağırın.

**Q2: Aspose.Slides grafiklerinde yaygın sorunlar nelerdir?**  
A2: Sorunlar genellikle eşleşmeyen veri aralıkları veya eksik çalışma kitabı hücrelerinden kaynaklanır. Her kategori ve veri noktasının karşılık gelen bir hücresi olduğundan emin olun.

**Q3: Aspose.Slides'ı diğer programlama dilleriyle kullanabilir miyim?**  
A3: Evet, Aspose .NET, C++, Python ve daha fazlası için eşdeğer kütüphaneler sunar.

**Q4: Bir sunumdaki mevcut grafiği nasıl güncellerim?**  
A4: Sunumu yükleyin, `slide.getShapes().get_Item(index)` ile grafiği bulun, ardından gerektiği gibi serilerini veya biçimlendirmesini değiştirin.

**Q5: Aspose.Slides ile grafik türlerinde sınırlamalar var mı?**  
A5: Kütüphane çok çeşitli grafik türlerini destekler, ancak yeni eklenen veya kullanımdan kaldırılan türler için her zaman en son belgeleri kontrol edin.

## Kaynaklar
- **Dokümantasyon**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **İndirme**: [En Son Sürümler](https://releases.aspose.com/slides/java/)
- **Satın Alma**: [Aspose.Slides Satın Al](https://purchase.aspose.com/buy)
- **Ücretsiz Deneme**: [Ücretsiz Denemenizi Başlatın](https://releases.aspose.com/slides/java/)
- **Geçici Lisans**: [Geçici Lisans Talep Et](https://purchase.aspose.com/temporary-license/)
- **Destek Forumu**: [Aspose Destek](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-03-20  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4 (JDK 16)  
**Yazar:** Aspose