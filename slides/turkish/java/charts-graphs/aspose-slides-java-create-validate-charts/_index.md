---
date: '2026-07-22'
description: Java'da Aspose.Slides ile clustered column chart eklemeyi öğrenin, adım
  adım grafik oluşturma, düzen doğrulama ve grafiği slayta ekleme konularını kapsar.
keywords:
- add clustered column chart
- how to add chart
- create chart in java
- add chart to slide
lastmod: '2026-07-22'
og_description: Aspose.Slides kullanarak Java'da clustered column chart ekleyin. Bu
  rehber, adım adım oluşturma, doğrulama ve PowerPoint file içinde grafiği slayta
  ekleme işlemlerini gösterir.
og_image_alt: 'Developer guide: add clustered column chart in Java using Aspose.Slides'
og_title: Java'da Aspose.Slides ile clustered column chart ekleme
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn how to add clustered column chart in Java with Aspose.Slides,
    covering step‑by‑step chart creation, layout validation, and how to add chart
    to slide.
  headline: How to add clustered column chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add clustered column chart in Java with Aspose.Slides,
    covering step‑by‑step chart creation, layout validation, and how to add chart
    to slide.
  name: How to add clustered column chart in Java with Aspose.Slides
  steps:
  - name: Set Up Your Presentation
    text: 'Load an existing file or start a new one:'
  - name: Add a clustered column chart
    text: '`ChartType.ClusteredColumn` specifies a clustered column chart type. Here
      we **add clustered column chart** to the first slide at a specific location:'
  - name: Validate the chart layout
    text: '`validateChartLayout()` checks the chart''s geometry and ensures elements
      are correctly positioned. After placing the chart, make sure everything lines
      up correctly:'
  type: HowTo
- questions:
  - answer: It’s a powerful Java library for creating, editing, and converting PowerPoint
      files without Microsoft Office.
    question: What is Aspose.Slides?
  - answer: Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/)
      and follow the request steps.
    question: How do I obtain a temporary license?
  - answer: Yes, Aspose.Slides supports bar, line, pie, area, and many more chart
      types.
    question: Can I create other chart types besides clustered column?
  - answer: Absolutely. Use `chart.getChartData().getSeries().add(...)` and `chart.getChartData().getCategories().add(...)`.
    question: Is there a way to add data to the chart programmatically?
  - answer: The Java version is cross‑platform and runs on Windows, Linux, and macOS.
    question: Does the library work on all operating systems?
  type: FAQPage
tags:
- add clustered column chart
- Aspose.Slides
- Java charting
- create chart in java
- add chart to slide
title: Java'da Aspose.Slides ile clustered column chart ekleme
url: /tr/java/charts-graphs/aspose-slides-java-create-validate-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java ile Aspose.Slides kullanarak kümelenmiş sütun grafiği ekleme

Bugünün veri odaklı dünyasında, bilgiyi grafiklerle görselleştirmek, ham sayıları net içgörülere dönüştürmek için gereklidir. Programlı olarak bir PowerPoint sunusuna **kümelenmiş sütun grafiği** eklemeniz gerekiyorsa, Aspose.Slides for Java, PowerPoint'i hiç açmadan grafik oluşturmanıza, yapılandırmanıza ve doğrulamanıza olanak tanıyan temiz, tamamen yönetilen bir API sunar. Raporlama motoru, eğitim uygulaması veya gerçek zamanlı bir gösterge paneli oluşturuyor olsanız da, bu öğretici sizi kütüphane kurulumundan sununun son halini kaydetmeye kadar her adımda yönlendirir.

## Hızlı Yanıtlar
- **Java'da kümelenmiş sütun grafiği eklemenizi sağlayan kütüphane nedir?** Aspose.Slides for Java.
- **Hangi grafik türü gösterilmektedir?** Kümelenmiş sütun grafiği.
- **Grafik düzenini nasıl doğrularsınız?** Grafik nesnesi üzerinde `validateChartLayout()` metodunu çağırın.
- **Çizim alanı boyutunu alabilir misiniz?** Evet, `chart.getPlotArea().getActualX()` ve ilgili metodlar aracılığıyla.
- **Son adım nedir?** Sunuyu `pres.save(...)` ile kaydedin.

## Öğrenecekleriniz
- Projenizde Aspose.Slides for Java'ı nasıl kuracağınızı öğrenin  
- **Grafik eklemeyi** – özellikle bir kümelenmiş sütun grafiği – ve bunu bir slayta eklemeyi öğrenin  
- **Grafik düzenini** programlı olarak doğrulamayı öğrenin  
- Çizim alanı boyutlarını almayı ve yorumlamayı öğrenin  
- Güncellenmiş grafikle sunuyu kaydetmeyi öğrenin  

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- **Java Development Kit (JDK)** – JDK 16 veya daha yeni bir sürüm.  
- **Aspose.Slides for Java** – kütüphane (örneklerde sürüm 25.4'ü kullanacağız).  
- **IDE** – IntelliJ IDEA, Eclipse veya herhangi bir Java uyumlu editör.  

## Aspose.Slides for Java Kurulumu
Aspose.Slides'ı projenize Maven, Gradle veya doğrudan indirme yoluyla ekleyebilirsiniz.

### Maven
Maven kod parçacığı, Aspose.Slides kütüphanesini projenizin sınıf yoluna ekler.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` dosyanıza bu satırı ekleyerek kütüphaneyi Maven Central'dan çekin.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
Alternatif olarak, kütüphaneyi doğrudan [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

#### Lisans Edinimi
- **Ücretsiz Deneme** – hızlı değerlendirme için sınırlı özellikler.  
- **[Aspose Geçici Lisans](https://purchase.aspose.com/temporary-license/)** – tam test için kısa vadeli bir anahtar isteyin.  
- **Satın Al** – üretim kullanımı için bir abonelik satın alın.

#### Temel Başlatma ve Kurulum
`Presentation`, Aspose.Slides'ın bellek içindeki bir PowerPoint dosyasını temsil eden temel sınıfıdır. Bir örnek oluşturduktan sonra slayt, şekil veya grafik eklemeye başlayabilirsiniz.

```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your chart creation logic will go here
        presentation.dispose();  // Clean up resources
    }
}
```

## Slayta grafik ekleme ve kümelenmiş sütun grafiği oluşturma
`Presentation`, düzenlediğiniz PowerPoint belgesini temsil eder. Bir `Presentation` yükleyin veya oluşturun, ilk slayta erişin ve `ChartType.ClusteredColumn` ile `addChart` metodunu çağırın. Bu, belirtilen koordinatlarda tam işlevsel bir kümelenmiş sütun grafiği ekler; ardından kaydetmeden önce serileri ve kategorileri doldurabilirsiniz. Grafik otomatik olarak slaytın temasını benimser ve gerektiğinde renkleri, başlıkları ve açıklamaları daha da özelleştirebilirsiniz.

Aspose.Slides ile sunularda grafik oluşturmak oldukça basittir. Aşağıdaki bölümler her adımı ayrıntılı olarak açıklar.

### Adım 1: Sununuzu Hazırlayın
Mevcut bir dosyayı yükleyin veya yeni bir tane oluşturun:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.Pptx");
```

### Adım 2: Kümelenmiş sütun grafiği ekleyin
`ChartType.ClusteredColumn`, bir kümelenmiş sütun grafik türünü belirtir. Burada, ilk slayta belirli bir konumda **kümelenmiş sütun grafiği** ekliyoruz:

```java
import com.aspose.slides.ShapeType;

Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 500, 350
);
```

### Adım 3: Grafik düzenini doğrulayın
`validateChartLayout()` grafik geometrisini kontrol eder ve öğelerin doğru konumlandırıldığından emin olur. Grafiği yerleştirdikten sonra, her şeyin düzgün hizalandığını kontrol edin:

```java
chart.validateChartLayout();
```

#### Doğrulamanın önemi
`validateChartLayout()` çakışan öğeleri, eksik eksenleri ve diğer görsel tutarsızlıkları kontrol eder, izleyicilerinizin düzgün bir grafik görmesini sağlar.

## Bir grafikten çizim alanı boyutlarını alma
`Chart`, bir grafiğin tüm görsel ve veri yönlerini kapsayan nesnedir. `getPlotArea()` grafiğin çizim alanı dikdörtgenini döndürür, ek şekillerin hassas hizalanmasını sağlar. Çizim alanı ölçümlerini okumak için grafik nesnesine erişin:

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

Çizim alanı ölçümlerini alın:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();

System.out.println("Plot Area: X=" + x + ", Y=" + y + ", Width=" + w + ", Height=" + h);
```

Bu değerler, diğer şekilleri hizalamanız veya özel kenar boşlukları hesaplamanız gerektiğinde faydalıdır.

## Yeni grafikle sunuyu kaydetme
`Presentation`, tüm slaytları, şekilleri ve grafikleri tutan kapsayıcıdır. `Presentation` örneği üzerinde `save` metodunu çağırarak çıktı formatını (ör. PPTX) belirtin. Bu, değiştirilen sunuyu diske yazar, yeni eklenen grafiği ve yaptığınız tüm düzen doğrulamalarını korur ve nesne serbest bırakıldığında yerel kaynakları da serbest bırakır.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
```

## Pratik Uygulamalar
- **İş Raporlaması** – Güncel grafiklerle üç aylık sunuları otomatikleştirin.  
- **Eğitim Araçları** – Veri trendlerini anında gösteren ders slaytları oluşturun.  
- **Gösterge Paneli Entegrasyonu** – Gerçek zamanlı analizleri PowerPoint'e aktararak yöneticilere sunun.

## Performans Düşünceleri
- `Presentation` nesnesini (`pres.dispose()`) serbest bırakarak yerel kaynakları temizleyin.  
- Büyük sunular işlenirken, mümkün olduğunca grafik nesnelerini yeniden kullanarak bellek tüketimini azaltın.  
- Büyük veri setleri için tüm veriyi belleğe yüklemek yerine akış API'lerini tercih edin.  
- Aspose.Slides **40'tan fazla grafik türünü** destekler ve **her seri için 10.000 veri noktasına** kadar grafikleri belirgin bir gecikme olmadan işleyebilir.

## Yaygın Sorunlar ve Çözüm Yolları
| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|-------|
| Grafik boş görünüyor | Veri serisi eklenmemiş | `chart.getChartData().getSeries().add(...)` metodunu doğrulamadan önce kullanın. |
| Düzen doğrulaması hatalar veriyor | Slayttaki şekiller çakışıyor | X/Y koordinatlarını ayarlayın veya grafik boyutlarını artırın. |
| `OutOfMemoryError` büyük dosyalarda | Nesneler serbest bırakılmadığı için | `finally` bloğunda `presentation.dispose()` çağırın. |

## Sıkça Sorulan Sorular

**S: Aspose.Slides nedir?**  
C: Microsoft Office olmadan PowerPoint dosyalarını oluşturmak, düzenlemek ve dönüştürmek için güçlü bir Java kütüphanesidir.

**S: Geçici bir lisans nasıl elde ederim?**  
C: [Aspose Temporary License](https://purchase.aspose.com/temporary-license/) adresini ziyaret edin ve istek adımlarını izleyin.

**S: Kümelenmiş sütun dışındaki diğer grafik türlerini oluşturabilir miyim?**  
C: Evet, Aspose.Slides çubuk, çizgi, pasta, alan ve daha birçok grafik türünü destekler.

**S: Grafik verilerini programlı olarak eklemenin bir yolu var mı?**  
C: Kesinlikle. `chart.getChartData().getSeries().add(...)` ve `chart.getChartData().getCategories().add(...)` metodlarını kullanın.

**S: Kütüphane tüm işletim sistemlerinde çalışır mı?**  
C: Java sürümü çapraz platformdur ve Windows, Linux ve macOS'ta çalışır.

## Kaynaklar
- [Dokümantasyon](https://reference.aspose.com/slides/java/)
- [Aspose.Slides for Java'ı İndir](https://releases.aspose.com/slides/java/)
- [Abonelik Satın Al](https://purchase.aspose.com/buy)
- [Ücretsiz Deneme](https://releases.aspose.com/slides/java/)
- [Geçici Lisans Talebi](https://purchase.aspose.com/temporary-license/)
- [Destek Forumu](https://forum.aspose.com/c/slides/11)

---

**Son Güncelleme:** 2026-07-22  
**Test Edildi:** Aspose.Slides for Java 25.4  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Java'da Aspose.Slides ile Grafik Oluşturma: Kapsamlı Rehber](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Aspose.Slides for Java Kullanarak PowerPoint'te Grafik Düzenleri Oluşturma ve Doğrulama | SEO Optimize Rehber](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)
- [Aspose.Slides for Java Kullanarak Sunularda Grafik Ekleme ve Yapılandırma](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}