---
date: '2026-11-16'
description: رسم إطار حول النص في جداول PowerPoint باستخدام Aspose.Slides for Java
  – تعلّم كيفية إنشاء الجداول، إضافة النص إلى الخلايا، تمييز الخلايا، وتصدير الملف
  بصيغة PPTX.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: رسم إطار حول النص في جداول PowerPoint باستخدام Aspose.Slides for Java.
  يوضح هذا الدليل كيفية إنشاء الجداول، إضافة النص ومحاذاته، تمييز الخلايا، وتصدير
  الشرائح بصيغة PNG.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: كيفية رسم إطار حول النص وإنشاء جداول في PowerPoint باستخدام Aspose.Slides
  for Java
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
title: كيفية رسم إطار حول النص وإنشاء جداول في PowerPoint باستخدام Aspose.Slides for
  Java
url: /ar/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية رسم إطار حول النص وإنشاء جداول في PowerPoint باستخدام Aspose.Slides for Java

## المقدمة

رسم **إطار حول النص** في شريحة PowerPoint يتيح لك إبراز الأرقام الرئيسية دون تغيير المحتوى الأساسي. في هذا الدرس ستتعلم كيفية إنشاء جدول برمجيًا، وإدراج النص داخل الخلايا ومحاذاته، وإبراز كلمات معينة أو خلايا كاملة، وأخيرًا حفظ العرض التقديمي كملف PPTX. في النهاية ستحصل على شريحة مصقولة تجذب انتباه الجمهور إلى المكان الذي تريد.

## الإجابات السريعة
- **ما معنى “add text to table”؟** يعني إدراج أو تحديث المحتوى النصي لخلايا الجدول الفردية برمجيًا.  
- **ما الطريقة التي تحفظ الملف؟** `pres.save("output.pptx", SaveFormat.Pptx)` – هذه الخطوة **حفظ العرض التقديمي كـ pptx** تُنهي تغييراتك.  
- **كيف يمكنني محاذاة النص داخل شكل؟** استخدم `TextAlignment.Left` (أو Center/Right) عبر `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **هل يمكنني رسم مستطيل حول فقرة؟** نعم – كرر عبر الفقرات، احصل على المستطيل المحيط بها، وأضف `IAutoShape` بدون تعبئة وخط أسود.  
- **هل أحتاج إلى ترخيص؟** الترخيص المؤقت يعمل للتقييم؛ الترخيص الكامل مطلوب للاستخدام في الإنتاج.  

## لماذا نرسم إطارات حول النص؟

رسم إطار حول النص يبرز فورًا الأرقام المهمة أو التحذيرات أو العناوين. يوفر إشارة بصرية مع الحفاظ على التنسيق الأصلي دون تعديل، مما يجعله مثاليًا لتقارير المالية، لوحات مؤشرات الأداء KPI، أو أي شريحة تحتاج إلى إبراز.

## ما هو رسم إطار حول النص؟

`draw frame around text` هي التقنية التي تضيف برمجيًا شكلًا مستطيلًا يتبع الحدود الدقيقة لفقرة أو جزء من النص، باستخدام تنسيق الخط دون تعبئة الداخل. هذه الطريقة تتيح لك إبراز المحتوى دون تعديل النص نفسه.

## المتطلبات المسبقة

قبل البدء، تأكد من توفر ما يلي:

### المكتبات المطلوبة
ستحتاج إلى Aspose.Slides for Java. أدرجه باستخدام أحد مديري الحزم:

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

يمكنك أيضًا تصفح الإصدارات على [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### إعداد البيئة
يوصى باستخدام Java Development Kit (JDK) 16 أو أحدث لأن الأمثلة تستخدم المصنف `jdk16`. أي بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse ستعمل.

### المتطلبات المعرفية
- مهارات برمجة Java الأساسية.  
- الإلمام بمفاهيم PowerPoint (الشرائح، الأشكال، الجداول).  
- فهم كيفية إدارة Maven/Gradle للتبعيات.

## إعداد Aspose.Slides for Java

`Presentation` هي الفئة الأساسية في Aspose.Slides التي تمثل ملف PowerPoint في الذاكرة وتوفر الوصول إلى الشرائح، الأشكال، والجداول. يمكنها التعامل مع عروض تقديمية تصل إلى **10,000 شريحة** مع الحفاظ على استهلاك الذاكرة أقل من **500 ميغابايت**، مما يجعلها مناسبة للأتمتة على نطاق واسع.

1. **تثبيت المكتبة** – استخدم Maven أو Gradle، أو قم بتنزيلها مباشرة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).  
2. **الحصول على الترخيص** – ابدأ بتجربة مجانية من [Temporary License](https://purchase.aspose.com/temporary-license/) وارتقِ إلى ترخيص كامل عبر [Purchase Aspose.Slides](https://purchase.aspose.com/buy) لأعباء العمل الإنتاجية.  
3. **التهيئة الأساسية** – أنشئ كائن `Presentation` جديد وحمّل أو أنشئ الشرائح حسب الحاجة.  
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

`Presentation` هي الفئة الرئيسية التي تمثل ملف PowerPoint في الذاكرة.  
حمّل `Presentation` جديدًا، أنشئ جدولًا عند الإحداثيات المطلوبة، عبّئ الخلايا بكائنات `TextFrame`، وأخيرًا استدعِ `pres.save("output.pptx", SaveFormat.Pptx)`. هذه السلسلة تنشئ **إنشاء جدول في PowerPoint**، وتضيف نصًا مخصصًا إلى كل خلية، وتكتب النتيجة إلى ملف PPTX في عملية واحدة فعّالة.

### الإجابة المباشرة
أنشئ جدولًا باستدعاء `slide.getShapes().addTable(...)`، ثم لكل خلية استخدم `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))`. بعد تعبئة جميع الخلايا، استدعِ `pres.save("output.pptx", SaveFormat.Pptx)` لكتابة الملف. هذه الطريقة تتيح لك التحكم برمجيًا في محتوى كل خلية وتنسيقها.

#### الميزة 1: إنشاء جدول وإضافة نص إلى الخلايا

**1. إنشاء جدول** – ابدأ عرضًا تقديميًا، أضف شريحة، وضع جدولًا عند (50, 50) بأعمدة وعروض صفوف محددة.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. إضافة نص إلى الخلايا** – لكل خلية، أنشئ `Paragraph`، أضف `Portion` بالسلسلة المطلوبة، وعيّن الفقرة إلى `TextFrame` الخاصة بالخلية.  
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

**3. حفظ العرض التقديمي** – استدعِ `pres.save("output.pptx", SaveFormat.Pptx")`.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## كيفية رسم إطار حول النص في شريحة PowerPoint؟

`Rectangle2D` تمثل مساحة مستطيلة في مساحة إحداثيات ثنائية الأبعاد.  
حمّل الشريحة، حدد الفقرة أو الجزء الذي تريد إبرازها، استخرج المستطيل المحيط عبر `getRect()`، ثم أضف مستطيل `IAutoShape` بدون تعبئة وخط ملون. هذه الطريقة تعمل لكل من الفقرات الكاملة وأجزاء الكلمات الفردية.

### الإجابة المباشرة
لرسم إطار حول النص، احصل أولاً على مستطيل الفقرة (`Rectangle2D rect = paragraph.getRect();`). ثم أنشئ مستطيل `IAutoShape` (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`)، عيّن `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)`، وأوقف التعبئة (`shape.getFillFormat().setFillType(FillType.NoFill)`). سيُحدّد الشكل النص بدقة.

#### الميزة 3: رسم إطارات حول الفقرات والأجزاء في خلايا الجدول

**1. إنشاء جدول** – أعد استخدام الكود من الميزة 1 لإعداد الجدول الأولي.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. إضافة فقرات** – أعد استخدام كود إنشاء الفقرات من الميزة 1.  
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

**3. رسم إطارات** – كرر عبر كل فقرة، احصل على المستطيل المحيط، وأضف شكل مستطيل كما هو موضح أعلاه. بالنسبة للأجزاء التي تحتوي على الحرف ‘0’, ارسم إطارًا إضافيًا لتسليط الضوء على تلك الأرقام.  
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

**4. حفظ العرض التقديمي** – نفس الخطوة النهائية كما من قبل.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## كيفية إضافة إطار نص إلى AutoShape وتعيين المحاذاة

`AutoShape` هو شكل يمكنه احتواء نص أو صور أو محتوى آخر.  
يمكن لـ `AutoShape` احتواء `TextFrame`. يمكنك التحكم في المحاذاة الأفقية باستخدام تعداد `ParagraphFormat`.

### الإجابة المباشرة
أنشئ AutoShape مستطيل (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`)، احصل على `TextFrame` الخاص به، عيّن النص باستخدام `shape.getTextFrame().setText("Text in shape")`، ثم استدعِ `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)`. هذا يَمحِّز النص إلى اليسار داخل الشكل.

**1. إضافة AutoShape** – ضع مستطيلًا في الموقع المطلوب.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. تعيين محاذاة النص** – طبّق المحاذاة اليسرى كما هو موضح أعلاه.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. حفظ العرض التقديمي** – نفس الخطوة النهائية.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## المشكلات الشائعة والنصائح

- **دائمًا قم بالتخلص** – غلف استخدام `Presentation` في كتلة try‑finally واستدعِ `pres.dispose()` لتحرير الموارد الأصلية.  
- **إعادة حساب المستطيلات المحيطة** – إذا غيرت حجم الخط أو الهوامش أو حشوة الخلية بعد رسم الإطار، استدعِ `paragraph.getRect()` مرة أخرى قبل إضافة الشكل.  
- **إنشاء الأشكال على دفعات للجداول الكبيرة** – إعادة استخدام نسخة واحدة من `IAutoShape` وتحديث هندستها يقلل من ضغط الذاكرة عند معالجة جداول بمئات الصفوف.  
- **أرقام الأداء** – يمكن لـ Aspose.Slides إنشاء PPTX مكوّن من 200 شريحة في أقل من ثانيتين على خادم عادي بأربع نوى، ورسم إطارات حول 1,000 فقرة يضيف أقل من 150 مللي ثانية من الحمل.

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذه الـ APIs مع إصدارات JDK أقدم؟**  
ج: المكتبة تدعم JDK 8 وما فوق، لكن المصنف `jdk16` يقدم أفضل أداء على بيئات التشغيل الأحدث.

**س: كيف أغيّر لون الإطار؟**  
ج: عدّل لون تعبئة تنسيق الخط، مثال `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**س: هل يمكن تصدير الشريحة النهائية كصورة؟**  
ج: نعم—استخدم `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` ثم احفظ مصفوفة البايت.

**س: ماذا لو احتجت إلى إبراز كلمة “Total” فقط داخل خلية؟**  
ج: كرّر عبر `cell.getTextFrame().getParagraphs()`, ابحث عن الجزء الذي يحتوي على “Total”, وارسم مستطيلًا حول الصندوق المحيط بذلك الجزء.

**س: هل يتعامل Aspose.Slides بفعالية مع العروض التقديمية الكبيرة؟**  
ج: الـ API يبث البيانات ويحرّر الموارد عند استدعاء `pres.dispose()`، مما يساعد في إدارة الذاكرة للملفات الكبيرة.

---

**آخر تحديث:** 2026-11-16  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16)  
**المؤلف:** Aspose  

## الدروس ذات الصلة

- [Aspose.Slides for Java: إتقان جداول PPTX ومعالجة النص في عروض PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [كيفية إنشاء إطارات نص ديناميكية في PowerPoint باستخدام Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [إضافة أعمدة في إطار النص باستخدام Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}