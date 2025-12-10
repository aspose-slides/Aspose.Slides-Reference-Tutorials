---
date: '2025-12-10'
description: PowerPoint'te Aspose.Slides for Java kullanarak tabloya metin eklemeyi
  ve metnin etrafına çerçeve çizmeyi öğrenin. Bu kılavuz, tablolar oluşturmayı, metin
  hizalamasını ayarlamayı ve içeriği çerçevelemeyi kapsar.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides for Java – tabloya metin ekleme ve çerçeve manipülasyonu
url: /tr/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Sunumlarda Tablo ve Çerçeve Manipülasyonunu Aspose.Slides for Java ile Ustalıkla Kullanma

## Introduction

PowerPoint'te verileri etkili bir şekilde sunmak zor olabilir. İster bir yazılım geliştiricisi, ister bir sunum tasarımcısı olun, **add text to table** hücrelerine metin ekleyin ve ana paragrafların etrafına çerçeveler çizin, böylece slaytlarınız öne çıksın. Bu öğreticide, tabloya nasıl metin ekleyeceğinizi, hizalayacağınızı ve metnin etrafına nasıl çerçeve çizeceğinizi Aspose.Slides for Java ile adım adım göreceksiniz. Sonunda, doğru bilgiyi doğru zamanda vurgulayan cilalı sunumlar oluşturabileceksiniz.

Sunumlarınızı dönüştürmeye hazır mısınız? Hadi başlayalım!

## Quick Answers
- **“add text to table” ne anlama geliyor?** Programatik olarak bireysel tablo hücrelerinin metin içeriğini eklemek veya güncellemek anlamına gelir.  
- **Dosyayı kaydeden yöntem hangisidir?** `pres.save("output.pptx", SaveFormat.Pptx)` – bu **save presentation as pptx** adımı değişikliklerinizi sonlandırır.  
- **Bir şeklin içindeki metni nasıl hizalarım?** `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)` üzerinden `TextAlignment.Left` (veya Center/Right) kullanın.  
- **Bir paragrafın etrafına dikdörtgen çizebilir miyim?** Evet – paragraflar üzerinde döngü kurun, sınırlayıcı dikdörtgeni alın ve dolgu olmayan, siyah bir çizgiye sahip bir `IAutoShape` ekleyin.  
- **Lisans gerekir mi?** Değerlendirme için geçici bir lisans yeterlidir; üretim kullanımı için tam lisans gereklidir.

## Prerequisites

### Required Libraries
Aspose.Slides for Java'a ihtiyacınız var. Maven veya Gradle kullanarak nasıl ekleyeceğinizi aşağıda bulabilirsiniz:

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

### Environment Setup
Java Development Kit (JDK) yüklü olduğundan emin olun, tercihen JDK 16 veya daha yeni bir sürüm, çünkü bu örnek `jdk16` sınıflandırıcısını kullanıyor.

### Knowledge Prerequisites
- Java programlamaya temel bir anlayış.  
- PowerPoint gibi sunum yazılımlarına aşinalık.  
- IntelliJ IDEA veya Eclipse gibi bir Entegre Geliştirme Ortamı (IDE) kullanma deneyimi.

## Setting Up Aspose.Slides for Java

Aspose.Slides'ı kullanmaya başlamak için şu adımları izleyin:

1. **Install the Library**: Bağımlılıkları yönetmek için Maven veya Gradle kullanın, ya da doğrudan [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

2. **License Acquisition**:
   - Ücretsiz deneme olarak [Temporary License](https://purchase.aspose.com/temporary-license/) adresinden geçici bir lisans indirerek başlayın.
   - Tam erişim için [Purchase Aspose.Slides](https://purchase.aspose.com/buy) adresinden lisans satın almayı düşünün.

3. **Basic Initialization**:
Sunum ortamınızı aşağıdaki kod parçacığıyla başlatın:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Why add text to table and draw frames?

Tabloya metin eklemek, yapılandırılmış verileri net bir şekilde sunmanızı sağlar; paragrafların veya belirli bölümlerin (ör. **'0'** karakterini içeren) etrafına çerçeve çizmek ise izleyicinin dikkatini önemli değerlere çeker. Bu kombinasyon, finansal raporlar, gösterge panelleri veya ana sayıları karmaşa olmadan vurgulamanız gereken her slayt için mükemmeldir.

## How to add text to table in Aspose.Slides for Java

### Feature 1: Create Table and Add Text to Cells

#### Overview
Bu özellik, **how to create table** nasıl yapılır, ardından **add text to table** hücrelerine metin eklenir ve son olarak **save presentation as pptx** nasıl kaydedilir gösterir.

#### Steps

**1. Create a Table**  
İlk olarak, sunumunuzu başlatın ve (50, 50) konumunda, belirtilen sütun genişlikleri ve satır yükseklikleriyle bir tablo ekleyin.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
Paragraflar oluşturun, metin bölümleri ekleyin ve bunları belirli bir hücreye yerleştirin.
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

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Feature 2: Add TextFrame to AutoShape and Set Alignment

#### Overview
Bir auto shape'e belirli hizalama ayarlarıyla bir metin çerçevesi eklemeyi öğrenin—bu, **set text alignment java** örneğidir.

#### Steps

**1. Add an AutoShape**  
(400, 100) konumunda, belirtilen boyutlarda bir dikdörtgen AutoShape ekleyin.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
Metni “Text in shape” olarak ayarlayın ve sola hizalayın.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Feature 3: Draw Frames around Paragraphs and Portions in Table Cells

#### Overview
Bu özellik, **draw frames around text** ve **draw rectangle around paragraph** işlemlerini, ‘0’ karakterini içeren bölümler için nasıl yapacağınızı gösterir.

#### Steps

**1. Create a Table**  
“Create Table and Add Text to Cells” kodunu başlangıç ayarı olarak yeniden kullanın.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
Önceki özelliğin paragraf oluşturma kodunu yeniden kullanın.
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

**3. Draw Frames**  
Paragraflar ve bölümler üzerinde döngü kurarak çerçeveler çizin.
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

**4. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Conclusion
Bu kılavuzu izleyerek **add text to table** yapabilir, şekillerin içindeki metni hizalayabilir ve **draw frames around text** ile önemli bilgileri vurgulayabilirsiniz. Bu teknikleri ustalıkla kullanmak, Aspose.Slides for Java ile son derece cilalı, veri odaklı sunumlar oluşturmanızı sağlar. Daha ileri keşifler için bu özellikleri grafikler, animasyonlar veya PDF’ye dışa aktarma ile birleştirmeyi deneyin.

## Frequently Asked Questions

**Q: Can I use these APIs with older JDK versions?**  
A: Kütüphane JDK 8 ve üzerini destekler, ancak `jdk16` sınıflandırıcısı yeni çalışma zamanlarında en iyi performansı sağlar.

**Q: How do I change the frame color?**  
A: Çizgi formatının dolgu rengini değiştirin, ör. `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: Evet—`pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` kullanın ve ardından bayt dizisini kaydedin.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: `cell.getTextFrame().getParagraphs()` içinde döngü yapın, “Total” kelimesini içeren bölümü bulun ve o bölümün sınırlayıcı kutusunun etrafına bir dikdörtgen çizin.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: API veri akışı sağlar ve `pres.dispose()` çağrıldığında kaynakları serbest bırakır; bu, büyük dosyalar için bellek yönetimine yardımcı olur.

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}