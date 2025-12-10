---
date: '2025-12-10'
description: تعرّف على كيفية إضافة النص إلى جدول ورسم إطارات حول النص في PowerPoint
  باستخدام Aspose.Slides للغة Java. يغطي هذا الدليل إنشاء الجداول، وضبط محاذاة النص،
  وإطار المحتوى.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides for Java – إضافة نص إلى الجدول وتعديل الإطار
url: /ar/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان معالجة الجداول والإطارات في العروض التقديمية باستخدام Aspose.Slides for Java

## المقدمة

قد يكون عرض البيانات بفعالية تحديًا في PowerPoint. سواء كنت مطور برمجيات أو مصمم عروض تقديمية، **add text to table** الخلايا وارسم إطارات حول الفقرات الرئيسية لجعل الشرائح أكثر بروزًا. في هذا الدرس ستتعرف بالضبط على كيفية إضافة نص إلى جدول، محاذاته، ورسم إطارات حول النص — كل ذلك باستخدام Aspose.Slides for Java. في النهاية، ستكون قادرًا على إنشاء عروض مصقولة تُبرز المعلومات الصحيحة في الوقت المناسب.

هل أنت مستعد لتحويل عروضك التقديمية؟ هيا نبدأ!

## إجابات سريعة
- **What does “add text to table” mean?** يعني ذلك إدراج أو تحديث المحتوى النصي لخلايا الجدول الفردية برمجيًا.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – هذه خطوة **save presentation as pptx** التي تُنهي تغييراتك.  
- **How can I align text inside a shape?** استخدم `TextAlignment.Left` (أو Center/Right) عبر `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** نعم – قم بالتكرار عبر الفقرات، احصل على المستطيل المحيط بها، وأضف `IAutoShape` بدون تعبئة وخط أسود.  
- **Do I need a license?** الترخيص المؤقت يكفي للتقييم؛ الترخيص الكامل مطلوب للاستخدام في الإنتاج.

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
تأكد من تثبيت مجموعة تطوير جافا (JDK)، ويفضل أن تكون JDK 16 أو أحدث، لأن هذا المثال يستخدم المصنف `jdk16`.

### المتطلبات المعرفية
- فهم أساسي لبرمجة Java.  
- الإلمام ببرامج العروض التقديمية مثل PowerPoint.  
- خبرة في استخدام بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## إعداد Aspose.Slides for Java

لبدء استخدام Aspose.Slides، اتبع الخطوات التالية:

1. **Install the Library**: استخدم Maven أو Gradle لإدارة التبعيات، أو قم بتنزيله مباشرة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - ابدأ بتجربة مجانية عن طريق تنزيل ترخيص مؤقت من [Temporary License](https://purchase.aspose.com/temporary-license/).
   - للوصول الكامل، فكر في شراء ترخيص من [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**: قم بتهيئة بيئة العرض الخاصة بك باستخدام مقتطف الكود التالي:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## لماذا إضافة نص إلى جدول ورسم إطارات؟

إضافة نص إلى جدول يتيح لك عرض البيانات المهيكلة بوضوح، بينما رسم إطارات حول الفقرات أو أجزاء محددة (مثل تلك التي تحتوي على الحرف **'0'**) يجذب انتباه الجمهور إلى القيم المهمة. هذا الجمع مثالي للتقارير المالية، لوحات التحكم، أو أي شريحة تحتاج إلى إبراز أرقام رئيسية دون فوضى.

## كيفية إضافة نص إلى جدول في Aspose.Slides for Java

### الميزة 1: إنشاء جدول وإضافة نص إلى الخلايا

#### نظرة عامة
توضح هذه الميزة كيفية **how to create table**، ثم **add text to table** الخلايا وبعد ذلك **save presentation as pptx**.

#### الخطوات

**1. Create a Table**  
أولاً، قم بتهيئة العرض الخاص بك وأضف جدولًا في الموضع (50, 50) مع تحديد عرض الأعمدة وارتفاع الصفوف.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
أنشئ فقرات تحتوي على أجزاء من النص وأضفها إلى خلية محددة.
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

**1. Add an AutoShape**  
أضف مستطيلًا كـ AutoShape في الموضع (400, 100) مع الأبعاد المحددة.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
عيّن النص إلى “Text in shape” وقم بمحاذاته إلى اليسار.
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
تركز هذه الميزة على **draw frames around text** وحتى **draw rectangle around paragraph** للأجزاء التي تحتوي على الحرف ‘0’.

#### الخطوات

**1. Create a Table**  
أعد استخدام الكود من “Create Table and Add Text to Cells” للإعداد الأولي.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
أعد استخدام كود إنشاء الفقرات من الميزة السابقة.
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

## الخلاصة
باتباع هذا الدليل، يمكنك **add text to table**، محاذاة النص داخل الأشكال، و**draw frames around text** لتسليط الضوء على المعلومات الهامة. إتقان هذه التقنيات يتيح لك إنشاء عروض تقديمية عالية الجودة، مدفوعة بالبيانات، باستخدام Aspose.Slides for Java. لاستكشاف المزيد، جرّب دمج هذه الميزات مع المخططات، الرسوم المتحركة، أو التصدير إلى PDF.

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذه الـ APIs مع إصدارات JDK أقدم؟**  
ج: المكتبة تدعم JDK 8 وما فوق، لكن المصنف `jdk16` يقدم أفضل أداء على بيئات التشغيل الأحدث.

**س: كيف يمكنني تغيير لون الإطار؟**  
ج: عدّل لون تعبئة تنسيق الخط، مثال: `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**س: هل يمكن تصدير الشريحة النهائية كصورة؟**  
ج: نعم—استخدم `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` ثم احفظ مصفوفة البايتات.

**س: ماذا لو أردت تمييز كلمة “Total” فقط داخل خلية؟**  
ج: قم بالتكرار عبر `cell.getTextFrame().getParagraphs()`، ابحث عن الجزء الذي يحتوي على “Total”، وارسم مستطيلًا حول صندوق حد ذلك الجزء.

**س: هل يتعامل Aspose.Slides بفعالية مع العروض الكبيرة؟**  
ج: الـ API يبث البيانات ويحرّر الموارد عند استدعاء `pres.dispose()`، مما يساعد في إدارة الذاكرة للملفات الكبيرة.

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}