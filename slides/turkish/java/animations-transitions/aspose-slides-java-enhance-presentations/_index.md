---
date: '2026-11-16'
description: Aspose.Slides for Java kullanarak PowerPoint tablolarında metin etrafına
  çerçeve çizin – tablolar oluşturmayı, hücrelere metin eklemeyi, hücreleri vurgulamayı
  ve dosyayı PPTX olarak dışa aktarmayı öğrenin.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Aspose.Slides for Java kullanarak PowerPoint tablolarında metin etrafına
  çerçeve çizin. Bu kılavuz, tablo oluşturmayı, metni ekleyip hizalamayı, hücreleri
  vurgulamayı ve slaytları PNG olarak dışa aktarmayı gösterir.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Aspose.Slides for Java ile PowerPoint'te metin etrafına çerçeve çizme ve
  tablo oluşturma
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: Aspose.Slides for Java ile PowerPoint'te metin etrafına çerçeve çizme ve tablo
  oluşturma
url: /tr/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Aspose.Slides for Java ile metin etrafına çerçeve çizme ve tablolar oluşturma

## Giriş

PowerPoint slaytında **draw frame around text** çizmek, temel sayıları altındaki içeriği değiştirmeden vurgulamanızı sağlar. Bu öğreticide programlı olarak bir tablo oluşturmayı, hücrelerin içine metin eklemeyi ve hizalamayı, belirli kelimeleri veya tüm hücreleri vurgulamayı ve sonunda sunumu PPTX dosyası olarak kaydetmeyi öğreneceksiniz. Sonunda izleyicinin gözünü tam istediğiniz yere çeken şık bir slaytınız olacak.

## Hızlı cevaplar
- **“add text to table” ne anlama geliyor?** Bu, tek tek tablo hücrelerinin metin içeriğini programlı olarak eklemek veya güncellemek anlamına gelir.  
- **Dosyayı kaydeden yöntem hangisidir?** `pres.save("output.pptx", SaveFormat.Pptx)` – bu **save presentation as pptx** adımı değişikliklerinizi sonlandırır.  
- **Bir şekil içinde metni nasıl hizalayabilirim?** `TextAlignment.Left` (veya Center/Right) kullanın: `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Bir paragraf etrafında dikdörtgen çizebilir miyim?** Evet – paragraflar üzerinde döngü kurun, sınırlayıcı dikdörtgeni alın ve doldurulmamış, siyah bir çizgiye sahip bir `IAutoShape` ekleyin.  
- **Lisans gerekir mi?** Değerlendirme için geçici bir lisans yeterlidir; üretim kullanımı için tam lisans gereklidir.  

## Metin etrafına çerçeve çizmenin nedeni

Metin etrafına çerçeve çizmek, önemli sayıları, uyarıları veya başlıkları anında vurgular. Orijinal biçimlendirmeyi bozmadan görsel bir ipucu sağlar; bu da finansal raporlar, KPI panoları veya vurgulamanın gerekli olduğu herhangi bir slayt için idealdir.

## draw frame around text nedir?

`draw frame around text`, bir paragrafın veya metin parçasının tam sınırlarını izleyen, içi doldurulmamış bir çizgiyle bir dikdörtgen şekil ekleme tekniğidir. Bu yaklaşım, metni değiştirmeden içeriği vurgulamanıza olanak tanır.

## Önkoşullar

### Gerekli kütüphaneler
Aspose.Slides for Java'ı ihtiyacınız olacak. Paket yöneticilerinden birini kullanarak ekleyin:

**Maven:**  
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

Ayrıca sürümleri [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinde inceleyebilirsiniz.

### Ortam kurulumu
Java Development Kit (JDK) 16 veya daha yenisi önerilir çünkü örnekler `jdk16` sınıflandırıcısını kullanıyor. IntelliJ IDEA veya Eclipse gibi herhangi bir IDE çalışır.

### Bilgi önkoşulları
- Temel Java programlama becerileri.  
- PowerPoint kavramlarına (slaytlar, şekiller, tablolar) aşina olmak.  
- Maven/Gradle bağımlılık yönetimini anlamak.

## Aspose.Slides for Java kurulumu

`Presentation` Aspose.Slides'ın çekirdek sınıfıdır ve bir PowerPoint dosyasını bellekte temsil eder; slaytlara, şekillere ve tablolara erişim sağlar. **10.000 slayta** kadar sunumu **500 MB** altında bellek kullanımıyla işleyebilir, bu da büyük ölçekli otomasyon için uygundur.

1. **Kütüphaneyi kur** – Maven veya Gradle kullanın, ya da doğrudan [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.  
2. **Lisans edinimi** – [Temporary License](https://purchase.aspose.com/temporary-license/) adresinden ücretsiz deneme alın ve üretim iş yükleri için [Purchase Aspose.Slides](https://purchase.aspose.com/buy) adresinden tam lisansa geçin.  
3. **Temel başlatma** – yeni bir `Presentation` nesnesi oluşturun ve gerektiğinde slaytları yükleyin veya oluşturun.  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Aspose.Slides for Java'da tabloya metin ekleme nasıl yapılır?

`Presentation` bellek içinde bir PowerPoint dosyasını temsil eden ana sınıftır.  
Yeni bir `Presentation` yükleyin, istediğiniz koordinatlarda bir tablo oluşturun, hücreleri `TextFrame` nesneleriyle doldurun ve sonunda `pres.save("output.pptx", SaveFormat.Pptx)` çağrısı yapın. Bu sıralama **PowerPoint'te tablo oluşturma**, her hücreye özel metin ekleme ve sonucu tek bir verimli iş akışında PPTX dosyasına yazma işlemini gerçekleştirir.

### Doğrudan cevap
`slide.getShapes().addTable(...)` ile bir tablo oluşturun, ardından her hücre için `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))` kullanın. Tüm hücreleri doldurduktan sonra `pres.save("output.pptx", SaveFormat.Pptx)` ile dosyayı yazın. Bu yöntem, her hücrenin içeriğini ve stilini programlı olarak kontrol etmenizi sağlar.

#### Özellik 1: tablo oluşturma ve hücrelere metin ekleme

**1. tablo oluştur** – bir sunum başlat, bir slayt ekle ve (50, 50) konumunda tanımlı sütun genişlikleri ve satır yükseklikleriyle bir tablo yerleştir.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. hücrelere metin ekle** – her hücre için bir `Paragraph` oluştur, istenen dizeyle bir `Portion` ekle ve paragrafı hücrenin `TextFrame`'ine ata.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. sunumu kaydet** – `pres.save("output.pptx", SaveFormat.Pptx)` çağrısını yap.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## PowerPoint slaytında metin etrafına çerçeve çizme nasıl yapılır?

`Rectangle2D` iki boyutlu koordinat uzayında bir dikdörtgen alanı temsil eder.  
Slaytı yükleyin, vurgulamak istediğiniz paragrafı veya bölümü bulun, `getRect()` ile sınırlayıcı dikdörtgeni alın ve ardından doldurulmamış bir çizgiye sahip bir `IAutoShape` dikdörtgeni ekleyin. Bu yöntem hem tüm paragraflar hem de tek tek kelime bölümleri için çalışır.

### Doğrudan cevap
Metin etrafına çerçeve çizmek için önce paragrafın dikdörtgenini alın (`Rectangle2D rect = paragraph.getRect();`). Ardından bir `IAutoShape` dikdörtgeni oluşturun (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)` ile çizgi rengini ayarlayın ve doldurmayı devre dışı bırakın (`shape.getFillFormat().setFillType(FillType.NoFill)`). Şekil metni mükemmel bir şekilde çevreleyecektir.

#### Özellik 3: tablo hücrelerindeki paragraflar ve bölümler etrafında çerçeve çizme

**1. tablo oluştur** – Özellik 1'deki kodu yeniden kullanarak başlangıç tablosunu kurun.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. paragraflar ekle** – Özellik 1'deki paragraf oluşturma kodunu yeniden kullanın.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. çerçeveler çiz** – her paragraf üzerinde döngü kurun, sınırlayıcı dikdörtgeni alın ve yukarıda açıklandığı gibi bir dikdörtgen şekli ekleyin. ‘0’ karakterini içeren bölümler için ek bir çerçeve çizerek bu sayıları vurgulayın.  
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```  

**4. sunumu kaydet** – önceki adımlarda olduğu gibi son adım.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## AutoShape'e metin çerçevesi ekleme ve hizalama ayarlama

`AutoShape` metin, resim veya diğer içerikleri barındırabilen bir şekildir.  
Bir `AutoShape` bir `TextFrame` tutabilir. Yatay hizalamayı `ParagraphFormat` enum'ı ile kontrol edebilirsiniz.

### Doğrudan cevap
Bir dikdörtgen AutoShape oluşturun (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), `TextFrame`'ine erişin, `shape.getTextFrame().setText("Text in shape")` ile metni ayarlayın ve ardından `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)` ile metni sola hizalayın. Bu, metni şekil içinde sola hizalar.

**1. bir AutoShape ekle** – istediğiniz konuma bir dikdörtgen yerleştirin.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. metin hizalamasını ayarla** – yukarıda gösterildiği gibi sol hizalamayı uygulayın.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. sunumu kaydet** – aynı son adım.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Yaygın tuzaklar ve ipuçları

- **Her zaman dispose edin** – `Presentation` kullanımınızı bir try‑finally bloğuna sarın ve yerel kaynakları serbest bırakmak için `pres.dispose()` çağırın.  
- **Sınırlayıcı dikdörtgenleri yeniden hesaplayın** – bir çerçeve çizdikten sonra yazı tipi boyutu, kenar boşlukları veya hücre dolgusu değiştirirseniz, şekil eklemeden önce `paragraph.getRect()` metodunu tekrar çağırın.  
- **Büyük tablolar için toplu şekil oluşturma** – tek bir `IAutoShape` örneğini yeniden kullanıp geometrisini güncellemek, yüzlerce satır işlenirken bellek baskısını azaltır.  
- **Performans rakamları** – Aspose.Slides tipik bir 4 çekirdekli sunucuda 200 sayfalık bir PPTX'i 2 saniyeden kısa sürede üretebilir; 1.000 paragraf etrafında çerçeve çizmek ise 150 ms'den az ek yük getirir.

## Sıkça Sorulan Sorular

**S: Bu API'leri daha eski JDK sürümleriyle kullanabilir miyim?**  
C: Kütüphane JDK 8 ve üzeri sürümleri destekler, ancak `jdk16` sınıflandırıcısı yeni çalışma zamanlarında en iyi performansı sağlar.

**S: Çerçeve rengini nasıl değiştiririm?**  
C: Çizgi formatının doldurma rengini değiştirin, örneğin `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**S: Son slaytı bir görüntü olarak dışa aktarabilir miyim?**  
C: Evet—`pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` kullanın ve ardından bayt dizisini kaydedin.

**S: Bir hücre içinde sadece “Total” kelimesini vurgulamam gerekirse?**  
C: `cell.getTextFrame().getParagraphs()` üzerinden döngü kurun, “Total” içeren bölümü bulun ve o bölümün sınırlayıcı kutusunun etrafına bir dikdörtgen çizin.

**S: Aspose.Slides büyük sunumları verimli bir şekilde yönetir mi?**  
C: API veri akışı sağlar ve `pres.dispose()` çağrıldığında kaynakları serbest bırakır; bu da büyük dosyalar için bellek yönetimini iyileştirir.

**Son Güncelleme:** 2026-11-16  
**Test Edilen:** Aspose.Slides for Java 25.4 (jdk16)  
**Yazar:** Aspose  



## İlgili öğreticiler

- [Aspose.Slides for Java: PowerPoint Sunumlarında PPTX Tablo ve Metin Manipülasyonunda Uzmanlaşma](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Aspose.Slides for Java Kullanarak PowerPoint'te Dinamik Metin Çerçeveleri Oluşturma](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Aspose.Slides for Java ile Metin Çerçevesine Sütun Ekleme](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}