---
date: '2026-02-09'
description: Aspose.Slides for Java kullanarak PowerPoint'te metnin etrafına çerçeve
  çizmeyi ve tablo hücrelerine metin eklemeyi öğrenin. Bu öğreticide tablo oluşturma,
  metin hizalamasını ayarlama ve sunumu pptx olarak kaydetme konuları ele alınmaktadır.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides for Java ile Çerçeveler Çizme ve Tabloya Metin Ekleme
url: /tr/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java ile Sunumlarda Çerçeveler Çizme ve Tabloya Metin Ekleme

## Giriş

PowerPoint'te verileri net bir şekilde sunmak özellikle tablo hücrelerine metin eklemek ve önemli değerleri görsel ipuçlarıyla vurgulamak zor olabilir. Bu rehberde belirli paragrafların etrafına çerçeve çizmeyi, şekiller içinde metin hizalamasını ayarlamayı ve sonunda **sunumu pptx olarak kaydetmeyi** Aspose.Slides for Java kullanarak öğreneceksiniz. Sonunda izleyicinin gözünü tam istediğiniz yere çeken cilalı bir slayt destesi elde edeceksiniz.

Slaytlarınızı öne çıkarmaya hazır mısınız? Süreci adım adım inceleyelim.

## Hızlı Yanıtlar
- **“add text to table” ne anlama geliyor?** Bireysel tablo hücrelerinin metin içeriğini programlı olarak eklemek veya güncellemek anlamına gelir.  
- **Dosyayı hangi yöntem kaydeder?** `pres.save("output.pptx", SaveFormat.Pptx)` – bu **sunumu pptx olarak kaydet** adımı değişikliklerinizi sonlandırır.  
- **Bir şekil içinde metni nasıl hizalarım?** `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)` aracılığıyla `TextAlignment.Left` (veya Center/Right) kullanın.  
- **Bir paragrafın etrafına dikdörtgen çizebilir miyim?** Evet – paragrafları döngüyle işleyin, sınırlayıcı dikdörtgeni alın ve dolgu olmadan siyah bir çizgiyle `IAutoShape` ekleyin.  
- **Lisans gerekli mi?** Değerlendirme için geçici bir lisans yeterlidir; üretim kullanımı için tam lisans gereklidir.  

## Metnin etrafına çerçeve çizmenin nedeni

Metnin etrafına çerçeve (veya dikdörtgen) çizmek, örneğin **'0'** karakterini içeren herhangi bir metin gibi belirli bir bölümü vurgulamak, anında dikkat çeker. Bu teknik şunlar için idealdir:

- Tablodaki önemli finansal rakamları vurgulama.  
- Bir slayttaki uyarıları veya önemli notları vurgulama.  
- Ekstra şekiller eklemeden görsel ayırıcılar oluşturma.

## Önkoşullar

Koda başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler
Aspose.Slides for Java'ı gereksinim duyacaksınız. Maven veya Gradle kullanarak nasıl ekleyeceğiniz aşağıdadır:

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
Bu örnek `jdk16` sınıflandırıcısını kullandığı için, tercihen JDK 16 veya daha yeni bir Java Development Kit (JDK) yüklü olduğundan emin olun.

### Bilgi Önkoşulları
- Java programlamaya temel bir anlayış.  
- PowerPoint gibi sunum yazılımlarına aşinalık.  
- IntelliJ IDEA veya Eclipse gibi Entegre Geliştirme Ortamı (IDE) kullanma deneyimi.

## Aspose.Slides for Java Kurulumu

Aspose.Slides'ı kullanmaya başlamak için şu adımları izleyin:

1. **Install the Library**: Maven veya Gradle kullanarak bağımlılıkları yönetin veya doğrudan [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.  
2. **License Acquisition**:
   - Start with a free trial by downloading a temporary license from [Temporary License](https://purchase.aspose.com/temporary-license/).
   - For full access, consider purchasing a license at [Purchase Aspose.Slides](https://purchase.aspose.com/buy).  
3. **Basic Initialization**:
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

## Aspose.Slides for Java'da Tabloya Metin Ekleme

### Özellik 1: Tablo Oluşturma ve Hücrelere Metin Ekleme

#### Genel Bakış
Bu özellik, **tablo oluşturma**, ardından **tablo hücrelerine metin ekleme** ve son olarak **sunumu pptx olarak kaydetme** nasıl yapılır gösterir.

#### Adımlar

**1. Tablo Oluşturma**  
Öncelikle sunumunuzu başlatın ve belirtilen sütun genişlikleri ve satır yükseklikleriyle (50, 50) konumunda bir tablo ekleyin.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Hücrelere Metin Ekleme**  
Metin parçacıklarından oluşan paragraflar oluşturun ve bunları belirli bir hücreye ekleyin.
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

### Özellik 2: AutoShape'e TextFrame Ekleme ve Hizalama Ayarlama

#### Genel Bakış
Bir auto shape'e belirli hizalama ile bir text frame eklemeyi öğrenin—**set text alignment java** örneği.

#### Adımlar

**1. AutoShape Ekleme**  
Belirtilen boyutlarla (400, 100) konumunda bir dikdörtgeni AutoShape olarak ekleyin.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Metin Hizalamasını Ayarlama**  
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

### Özellik 3: Tablo Hücrelerindeki Paragraflar ve Bölümler Çevresinde Çerçeve Çizme

#### Genel Bakış
Bu özellik, **metnin etrafına çerçeve çizme** ve ‘0’ karakterini içeren bölümler için **paragrafın etrafına dikdörtgen çizme** üzerine odaklanır.

#### Adımlar

**1. Tablo Oluşturma**  
İlk kurulum için “Tablo Oluşturma ve Hücrelere Metin Ekleme” kodunu yeniden kullanın.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Paragraflar Ekleme**  
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

**3. Çerçeve Çizme**  
Paragrafları ve bölümleri döngüyle işleyerek etraflarına çerçeve çizin.
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

## Yaygın Hatalar ve İpuçları

- **Null kontrolleri** – `Presentation` kullanımınızı her zaman bir try‑finally bloğuna sarın, böylece `pres.dispose()` çalışır ve yerel kaynakları serbest bırakır.  
- **Sınırlayıcı dikdörtgen doğruluğu** – `para.getRect()` tarafından döndürülen dikdörtgen mevcut yerleşimi yansıtır; yazı tipi boyutunu veya kenar boşluklarını değiştirirseniz, çerçeve çizmeye başlamadan önce dikdörtgeni yeniden hesaplayın.  
- **Performans** – Çok büyük tablolarla çalışırken, şekil eklemelerini toplu olarak yapmayı veya güncellenmiş geometriyle tek bir `IAutoShape` örneğini yeniden kullanmayı düşünün, böylece bellek yükünü azaltırsınız.

## Sık Sorulan Sorular

**S: Bu API'leri eski JDK sürümleriyle kullanabilir miyim?**  
C: Kütüphane JDK 8 ve üzerini destekler, ancak `jdk16` sınıflandırıcısı yeni çalışma zamanlarında en iyi performansı sağlar.

**S: Çerçeve rengini nasıl değiştiririm?**  
C: Çizgi formatının dolgu rengini değiştirin, örneğin `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**S: Son slaytı bir görüntü olarak dışa aktarmak mümkün mü?**  
C: Evet—`pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` kullanın ve ardından bayt dizisini kaydedin.

**S: Bir hücre içinde sadece “Total” kelimesini vurgulamam gerekirse ne yapmalıyım?**  
C: `cell.getTextFrame().getParagraphs()` içinde döngü yapın, “Total” içeren bölümü bulun ve o bölümün sınırlayıcı kutusunun etrafına bir dikdörtgen çizin.

**S: Aspose.Slides büyük sunumları verimli bir şekilde yönetiyor mu?**  
C: API verileri akış olarak işler ve `pres.dispose()` çağrıldığında kaynakları serbest bırakır; bu, büyük dosyalar için bellek yönetimine yardımcı olur.

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-02-09  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}