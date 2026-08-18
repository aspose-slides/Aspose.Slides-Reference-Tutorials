---
date: '2026-06-23'
description: تعلم كيفية إنشاء جدول في PowerPoint، إضافة نص إلى خلايا الجدول، رسم إطارات
  حول النص، وحفظ العرض التقديمي كملف pptx باستخدام Aspose.Slides for Java.
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
title: كيفية إنشاء جدول في PowerPoint ورسم إطارات باستخدام Aspose.Slides for Java
url: /ar/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء جدول في PowerPoint ورسم إطارات باستخدام Aspose.Slides for Java

## مقدمة

إنشاء **create table in PowerPoint** برمجياً يمكن أن يوفر لك ساعات من التنسيق اليدوي، خاصة عندما تحتاج إلى إبراز الأرقام الرئيسية أو إضافة ملاحظات توضيحية. في هذا الدرس ستكتشف كيفية إضافة نص إلى خلايا الجدول، رسم إطارات حول فقرات محددة، ضبط محاذاة النص بدقة، وأخيراً **save presentation as pptx** – كل ذلك باستخدام واجهة برمجة التطبيقات القوية Aspose.Slides for Java. في النهاية ستحصل على شريحة تبدو مصقولة، سهلة القراءة، وتلفت انتباه الجمهور فوراً إلى أهم البيانات.

## إجابات سريعة
- **What does “add text to table” mean?** يعني إدراج أو تحديث المحتوى النصي لخلايا الجدول الفردية برمجياً.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – هذه الخطوة **save presentation as pptx** تُنهي تغييراتك.  
- **How can I align text inside a shape?** استخدم `TextAlignment.Left` (أو Center/Right) عبر `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** نعم – قم بالتكرار عبر الفقرات، احصل على المستطيل المحيط بها، وأضف `IAutoShape` بدون تعبئة وخط أسود.  
- **Do I need a license?** ترخيص مؤقت يعمل للتقييم؛ ترخيص كامل مطلوب للاستخدام الإنتاجي.  

## لماذا رسم إطارات حول النص؟

رسم إطار (أو مستطيل) حول فقرة أو جزء محدد—مثل أي نص يحتوي على الحرف **'0'**—يجذب انتباه الجمهور فوراً إلى ذلك المحتوى. يوفر إشارة بصرية واضحة دون تعديل النص الأساسي، مما يجعله مثالياً لإبراز الأرقام الرئيسية، التحذيرات، أو فصل الأقسام داخل الشريحة.

## المتطلبات المسبقة

قبل الغوص في الكود، تأكد من وجود ما يلي:

### المكتبات المطلوبة
ستحتاج إلى Aspose.Slides for Java. إليك كيفية تضمينه باستخدام Maven أو Gradle:

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

### إعداد البيئة
تأكد من تثبيت مجموعة تطوير جافا (JDK)، ويفضل JDK 16 أو أحدث، حيث يستخدم هذا المثال المصنف `jdk16`.

### المتطلبات المعرفية
- فهم أساسي لبرمجة Java.  
- الإلمام ببرامج العروض التقديمية مثل PowerPoint.  
- خبرة في استخدام بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## إعداد Aspose.Slides for Java

`Presentation` هي الفئة الأساسية في Aspose.Slides التي تمثل ملف PowerPoint في الذاكرة وتوفر الوصول إلى الشرائح، الأشكال، والجداول. لبدء استخدام Aspose.Slides، اتبع الخطوات التالية:

1. **Install the Library**: استخدم Maven أو Gradle لإدارة التبعيات، أو قم بتنزيله مباشرة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - ابدأ بتجربة مجانية عن طريق تنزيل ترخيص مؤقت من [Temporary License](https://purchase.aspose.com/temporary-license/).
   - للحصول على وصول كامل، فكر في شراء ترخيص عبر [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:  
   قم بتهيئة بيئة العرض التقديمي الخاصة بك باستخدام مقتطف الشيفرة التالي:  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## كيفية إضافة نص إلى جدول في Aspose.Slides for Java؟

حمّل `Presentation` جديدًا، أنشئ جدولًا عند الإحداثيات المطلوبة، املأ الخلايا بكائنات `TextFrame`، وأخيرًا استدعِ `pres.save("output.pptx", SaveFormat.Pptx)`. هذه السلسلة تنشئ **create table in PowerPoint**، وتضيف نصًا مخصصًا إلى كل خلية، وتكتب النتيجة إلى ملف PPTX في سير عمل واحد وفعّال.

### الميزة 1: إنشاء جدول وإضافة نص إلى الخلايا

#### نظرة عامة
تُظهر هذه الميزة كيفية **create table**، ثم **add text to table** الخلايا، ثم لاحقًا **save presentation as pptx**.

#### الخطوات

**1. Create a Table**  
أولاً، قم بتهيئة العرض التقديمي الخاص بك وأضف جدولًا في الموضع (50, 50) مع عرض الأعمدة وارتفاع الصفوف المحدد.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Text to Cells**  
أنشئ فقرات مع أجزاء من النص وأضفها إلى خلية محددة.  
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

### الميزة 2: إضافة TextFrame إلى AutoShape وتعيين المحاذاة

#### نظرة عامة
تعلم كيفية إضافة إطار نص مع محاذاة محددة إلى شكل تلقائي—مثال على **set text alignment java**.

#### الخطوات

AutoShape هو شكل يمكنه احتواء النص والرسومات.

**1. Add an AutoShape**  
أضف مستطيلًا كـ AutoShape في الموضع (400, 100) بالأبعاد المحددة.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` enum يحدد خيارات المحاذاة الأفقية للنص داخل الشكل.

**2. Set Text Alignment**  
عيّن النص إلى “Text in shape” وامحاه إلى اليسار.  
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

### الميزة 3: رسم إطارات حول الفقرات والأجزاء في خلايا الجدول

#### نظرة عامة
تركّز هذه الميزة على **draw frames around text** وحتى **draw rectangle around paragraph** للأجزاء التي تحتوي على الحرف ‘0’.

#### الخطوات

`IAutoShape` يمثل كائن شكل يمكن رسمه على شريحة، مثل المستطيلات المستخدمة للإطارات.

**1. Create a Table**  
أعد استخدام الشيفرة من “Create Table and Add Text to Cells” للإعداد الأولي.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Paragraphs**  
أعد استخدام شيفرة إنشاء الفقرات من الميزة السابقة.  
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
قم بالتكرار عبر الفقرات والأجزاء لرسم إطارات حولها.  
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

## الأخطاء الشائعة والنصائح

- **Null checks** – احرص دائمًا على تغليف استخدام `Presentation` داخل كتلة try‑finally لضمان تشغيل `pres.dispose()` وتحرير الموارد الأصلية.  
- **Bounding rectangle accuracy** – المستطيل الذي تُعيده `para.getRect()` يعكس التخطيط الحالي؛ إذا غيرت حجم الخط أو الهوامش، أعد حساب المستطيل قبل رسم الإطار.  
- **Performance** – عند التعامل مع جداول كبيرة جدًا، فكر في تجميع إضافات الأشكال أو إعادة استخدام كائن `IAutoShape` واحد مع تحديث الهندسة لتقليل استهلاك الذاكرة.  

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذه الـ APIs مع إصدارات JDK القديمة؟**  
ج: المكتبة تدعم JDK 8 وما فوق، لكن المصنف `jdk16` يقدم أفضل أداء على أوقات التشغيل الأحدث.

**س: كيف أغيّر لون الإطار؟**  
ج: عدّل لون تعبئة خط الشكل، على سبيل المثال `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**س: هل يمكن تصدير الشريحة النهائية كصورة؟**  
ج: نعم—استخدم `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` ثم احفظ مصفوفة البايت.

**س: ماذا لو أردت إبراز كلمة “Total” فقط داخل خلية؟**  
ج: قم بالتكرار عبر `cell.getTextFrame().getParagraphs()`, ابحث عن الجزء الذي يحتوي على “Total”، وارسم مستطيلًا حول صندوق الحد الخاص بذلك الجزء.

**س: هل يتعامل Aspose.Slides مع العروض الكبيرة بكفاءة؟**  
ج: الـ API يبث البيانات ويحرّر الموارد عند استدعاء `pres.dispose()`، مما يساعد في إدارة الذاكرة للملفات الكبيرة.

---

**آخر تحديث:** 2026-06-23  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [Aspose.Slides for Java&#58; إتقان جداول PPTX ومعالجة النص في عروض PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [كيفية إنشاء إطارات نص ديناميكية في PowerPoint باستخدام Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [إضافة أعمدة في إطار النص باستخدام Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}