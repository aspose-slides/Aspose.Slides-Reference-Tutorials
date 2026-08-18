---
date: '2026-06-23'
description: PowerPoint'te tablo oluşturmayı, tablo hücrelerine metin eklemeyi, metnin
  etrafına çerçeveler çizmeyi ve sunumu pptx olarak kaydetmeyi Aspose.Slides for Java
  kullanarak öğrenin.
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
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
title: PowerPoint'te tablo oluşturma ve Aspose.Slides for Java ile çerçeveler çizme
url: /tr/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint'te tablo oluşturma ve Aspose.Slides for Java ile çerçeveler çizme

## Giriş

PowerPoint'te **create table in PowerPoint** programlı olarak oluşturmak, özellikle ana sayıları vurgulamanız veya açıklayıcı notlar eklemeniz gerektiğinde saatlerce süren manuel biçimlendirmeyi tasarruf ettirebilir. Bu öğreticide tablo hücrelerine metin eklemeyi, belirli paragrafların etrafına çerçeveler çizmeyi, kesin metin hizalamasını ayarlamayı ve sonunda **save presentation as pptx** – tüm bunları güçlü Aspose.Slides for Java API'si ile öğreneceksiniz. Sonunda, cilalı görünen, okunması kolay ve izleyicinin en önemli verilere hemen dikkatini çeken bir slaytınız olacak.

## Hızlı Yanıtlar
- **“add text to table” ne anlama geliyor?** Programlı olarak bireysel tablo hücrelerinin metin içeriğini eklemek veya güncellemek anlamına gelir.  
- **Dosyayı kaydeden yöntem hangisidir?** `pres.save("output.pptx", SaveFormat.Pptx)` – bu **save presentation as pptx** adımı değişikliklerinizi tamamlar.  
- **Bir şekil içinde metni nasıl hizalarım?** `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)` aracılığıyla `TextAlignment.Left` (veya Center/Right) kullanın.  
- **Bir paragrafın etrafına dikdörtgen çizebilir miyim?** Evet – paragraflar üzerinde döngü yapın, sınırlayıcı dikdörtgeni alın ve dolgu olmadan siyah bir çizgiyle bir `IAutoShape` ekleyin.  
- **Lisans gerekli mi?** Değerlendirme için geçici bir lisans çalışır; üretim kullanımı için tam lisans gereklidir.  

## Metin etrafında çerçeveler neden çizilir?

Bir paragrafın veya belirli bir kısmın – örneğin **'0'** karakterini içeren herhangi bir metnin – etrafına bir çerçeve (veya dikdörtgen) çizmek, izleyicinin dikkatini o içeriğe hemen çeker. Alttaki metni değiştirmeden net bir görsel ipucu sağlar ve ana rakamları, uyarıları vurgulamak veya bir slayt içinde bölümleri ayırmak için idealdir.

## Önkoşullar

Koda başlamadan önce aşağıdakilerin olduğundan emin olun:

### Gerekli Kütüphaneler
Aspose.Slides for Java'a ihtiyacınız olacak. İşte Maven veya Gradle kullanarak nasıl ekleyeceğiniz:

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

### Ortam Kurulumu
Bir Java Development Kit (JDK) yüklü olduğundan emin olun, tercihen JDK 16 veya daha yeni bir sürüm, çünkü bu örnek `jdk16` sınıflandırıcısını kullanıyor.

### Bilgi Önkoşulları
- Java programlamaya temel bir anlayış.  
- PowerPoint gibi sunum yazılımlarına aşinalık.  
- IntelliJ IDEA veya Eclipse gibi bir Entegre Geliştirme Ortamı (IDE) kullanma deneyimi.

## Aspose.Slides for Java Kurulumu

`Presentation` Aspose.Slides'ın çekirdek sınıfıdır ve bir PowerPoint dosyasını bellekte temsil eder ve slaytlara, şekillere ve tablolara erişim sağlar. Aspose.Slides'ı kullanmaya başlamak için şu adımları izleyin:

1. **Kütüphaneyi Kurun**: Bağımlılıkları yönetmek için Maven veya Gradle kullanın, ya da doğrudan [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

2. **Lisans Edinme**:
   - [Temporary License](https://purchase.aspose.com/temporary-license/) adresinden geçici bir lisans indirerek ücretsiz deneme ile başlayın.
   - Tam erişim için [Purchase Aspose.Slides](https://purchase.aspose.com/buy) adresinden bir lisans satın almayı düşünün.

3. **Temel Başlatma**:  
   Aşağıdaki kod parçacığıyla sunum ortamınızı başlatın:  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Aspose.Slides for Java'da Tabloya Metin Nasıl Eklenir?

Yeni bir `Presentation` yükleyin, istenen koordinatlarda bir tablo oluşturun, hücreleri `TextFrame` nesneleriyle doldurun ve sonunda `pres.save("output.pptx", SaveFormat.Pptx)` metodunu çağırın. Bu sıralama bir **create table in PowerPoint** oluşturur, her hücreye özel metin ekler ve sonucu tek bir verimli iş akışında bir PPTX dosyasına yazar.

### Özellik 1: Tablo Oluşturma ve Hücrelere Metin Ekleme

#### Genel Bakış
Bu özellik, **create table** nasıl yapılır, ardından **add text to table** hücrelerine nasıl metin eklenir ve son olarak **save presentation as pptx** nasıl kaydedilir gösterir.

#### Adımlar

**1. Tablo Oluştur**  
Öncelikle sunumunuzu başlatın ve (50, 50) konumunda belirtilen sütun genişlikleri ve satır yükseklikleriyle bir tablo ekleyin.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Hücrelere Metin Ekle**  
Metin parçacıkları içeren paragraflar oluşturun ve bunları belirli bir hücreye ekleyin.  
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

**3. Sunumu Kaydet**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Özellik 2: AutoShape'e TextFrame Ekleme ve Hizalamayı Ayarlama

#### Genel Bakış
Bir auto shape'e belirli hizalama ile bir metin çerçevesi eklemeyi öğrenin—**set text alignment java** örneği.

#### Adımlar

AutoShape, metin ve grafik tutabilen bir şekildir.

**1. AutoShape Ekle**  
(400, 100) konumunda belirtilen boyutlarda bir dikdörtgeni AutoShape olarak ekleyin.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` enum defines horizontal alignment options for text within a shape.

**2. Metin Hizalamasını Ayarla**  
Metni “Text in shape” olarak ayarlayın ve sola hizalayın.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. Sunumu Kaydet**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Özellik 3: Tablo Hücrelerindeki Paragraflar ve Bölümler Çevresinde Çerçeveler Çizme

#### Genel Bakış
Bu özellik, **draw frames around text** ve ‘0’ karakterini içeren bölümler için **draw rectangle around paragraph** üzerine odaklanır.

#### Adımlar

`IAutoShape` bir slayta çizilebilen şekil nesnesini temsil eder, örneğin çerçeveler için kullanılan dikdörtgenler.

**1. Tablo Oluştur**  
İlk kurulum için “Create Table and Add Text to Cells” kodunu yeniden kullanın.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Paragraflar Ekle**  
Önceki özellikteki paragraf oluşturma kodunu yeniden kullanın.  
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

**3. Çerçeveler Çiz**  
Paragraflar ve bölümler üzerinde döngü yaparak etraflarına çerçeve çizin.  
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

**4. Sunumu Kaydet**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Yaygın Tuzaklar ve İpuçları

- **Null kontrolleri** – `Presentation` kullanımınızı her zaman bir try‑finally bloğuna sarın, böylece `pres.dispose()` çalışır ve yerel kaynakları serbest bırakır.  
- **Sınırlayıcı dikdörtgen doğruluğu** – `para.getRect()` tarafından döndürülen dikdörtgen mevcut yerleşimi yansıtır; yazı tipi boyutunu veya kenar boşluklarını değiştirirseniz, çerçeveyi çizmeye başlamadan önce dikdörtgeni yeniden hesaplayın.  
- **Performans** – Çok büyük tablolarla çalışırken, şekil eklemelerini toplu olarak yapmayı veya güncellenmiş geometriyle tek bir `IAutoShape` örneğini yeniden kullanmayı düşünün, böylece bellek yükünü azaltırsınız.  

## Sıkça Sorulan Sorular

**S: Bu API'leri eski JDK sürümleriyle kullanabilir miyim?**  
C: Kütüphane JDK 8 ve üzerini destekler, ancak `jdk16` sınıflandırıcısı yeni çalışma zamanlarında en iyi performansı sağlar.

**S: Çerçeve rengini nasıl değiştiririm?**  
C: Çizgi formatının dolgu rengini değiştirin, örneğin `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**S: Son slaytı bir görüntü olarak dışa aktarmak mümkün mü?**  
C: Evet—`pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` kullanın ve ardından bayt dizisini kaydedin.

**S: Bir hücre içinde sadece “Total” kelimesini vurgulamam gerekirse ne yapmalıyım?**  
C: `cell.getTextFrame().getParagraphs()` içinde döngü yapın, “Total” içeren bölümü bulun ve o bölümün sınırlayıcı kutusunun etrafına bir dikdörtgen çizin.

**S: Aspose.Slides büyük sunumları verimli bir şekilde yönetiyor mu?**  
C: API veri akışı yapar ve `pres.dispose()` çağrıldığında kaynakları serbest bırakır, bu da büyük dosyalar için bellek yönetimine yardımcı olur.

---

**Son Güncelleme:** 2026-06-23  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4 (jdk16)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Slides for Java: PowerPoint Sunumlarında PPTX Tablo ve Metin Manipülasyonunda Ustalık](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Aspose.Slides for Java Kullanarak PowerPoint'te Dinamik Metin Çerçeveleri Oluşturma](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Aspose.Slides for Java ile Metin Çerçevesine Sütun Ekleme](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}