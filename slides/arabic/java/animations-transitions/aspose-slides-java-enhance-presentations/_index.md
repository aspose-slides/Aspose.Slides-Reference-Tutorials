---
date: '2026-02-09'
description: تعلم كيفية رسم إطارات حول النص وإضافة نص إلى خلايا الجداول في PowerPoint
  باستخدام Aspose.Slides for Java. يغطي هذا الدرس إنشاء الجداول، وضبط محاذاة النص،
  وحفظ العرض التقديمي بصيغة pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: كيفية رسم الإطارات وإضافة نص إلى جدول باستخدام Aspose.Slides for Java
url: /ar/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية رسم إطارات وإضافة نص إلى جدول في العروض التقديمية باستخدام Aspose.Slides for Java

## المقدمة

عرض البيانات بوضوح في PowerPoint يمكن أن يكون تحديًا حقيقيًا، خاصة عندما تحتاج إلى **إضافة نص إلى جدول** الخلايا وتبرز القيم المهمة باستخدام إشارات بصرية. في هذا الدليل ستتعلم **كيفية رسم إطارات** حول فقرات محددة، وضبط محاذاة النص داخل الأشكال، وأخيرًا **حفظ العرض التقديمي كملف pptx**—كل ذلك باستخدام Aspose.Slides for Java. في النهاية ستحصل على مجموعة شرائح مصقولة تجذب انتباه الجمهور إلى المكان الذي تريد.

هل أنت مستعد لجعل شرائحك تبرز؟ دعنا نتبع العملية خطوة بخطوة.

## إجابات سريعة
- **ماذا يعني “إضافة نص إلى جدول”؟** يعني إدراج أو تحديث المحتوى النصي لخلايا الجدول الفردية برمجيًا.  
- **أي طريقة تحفظ الملف؟** `pres.save("output.pptx", SaveFormat.Pptx)` – هذه الخطوة **حفظ العرض التقديمي كملف pptx** تُنهي التغييرات.  
- **كيف يمكنني محاذاة النص داخل شكل؟** استخدم `TextAlignment.Left` (أو Center/Right) عبر `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **هل يمكنني رسم مستطيل حول فقرة؟** نعم – قم بالتكرار على الفقرات، احصل على المستطيل المحيط بها، وأضف `IAutoShape` بدون تعبئة وبخط أسود.  
- **هل أحتاج إلى ترخيص؟** الترخيص المؤقت يعمل للتقييم؛ الترخيص الكامل مطلوب للاستخدام الإنتاجي.  

## لماذا نرسم إطارات حول النص؟

رسم إطار (أو مستطيل) حول فقرة أو جزء محدد (مثلاً أي نص يحتوي على الحرف **'0'**) يجذب الانتباه فورًا. هذه التقنية مثالية لـ:

- تمييز الأرقام المالية الرئيسية في جدول.  
- تأكيد التحذيرات أو الملاحظات المهمة في شريحة.  
- إنشاء فواصل بصرية دون إضافة أشكال إضافية يدويًا.

## المتطلبات المسبقة

قبل الغوص في الشيفرة، تأكد من توفر ما يلي:

### المكتبات المطلوبة
ستحتاج إلى Aspose.Slides for Java. إليك طريقة تضمينه باستخدام Maven أو Gradle:

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

لبدء استخدام Aspose.Slides، اتبع الخطوات التالية:

1. **تثبيت المكتبة**: استخدم Maven أو Gradle لإدارة التبعيات، أو قم بتحميلها مباشرة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **الحصول على الترخيص**:
   - ابدأ بتجربة مجانية بتحميل ترخيص مؤقت من [Temporary License](https://purchase.aspose.com/temporary-license/).
   - للحصول على وصول كامل، فكر في شراء ترخيص عبر [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **التهيئة الأساسية**:
   قم بتهيئة بيئة العرض التقديمي باستخدام مقتطف الشيفرة التالي:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## كيفية إضافة نص إلى جدول في Aspose.Slides for Java

### الميزة 1: إنشاء جدول وإضافة نص إلى الخلايا

#### نظرة عامة
توضح هذه الميزة كيفية **إنشاء جدول**، ثم **إضافة نص إلى جدول** الخلايا وأخيرًا **حفظ العرض التقديمي كملف pptx**.

#### الخطوات

**1. إنشاء جدول**  
أولاً، قم بتهيئة العرض التقديمي وأضف جدولًا في الموضع (50, 50) مع تحديد عرض الأعمدة وارتفاع الصفوف.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. إضافة نص إلى الخلايا**  
أنشئ فقرات مع أجزاء نصية وأضفها إلى خلية محددة.
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

**3. حفظ العرض التقديمي**  
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

**1. إضافة AutoShape**  
أضف مستطيلًا كـ AutoShape في الموضع (400, 100) مع الأبعاد المحددة.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. تعيين محاذاة النص**  
عيّن النص إلى “Text in shape” وقم بمحاذاته إلى اليسار.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. حفظ العرض التقديمي**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### الميزة 3: رسم إطارات حول الفقرات والأجزاء في خلايا الجدول

#### نظرة عامة
تركز هذه الميزة على **رسم إطارات حول النص** وحتى **رسم مستطيل حول الفقرة** للأجزاء التي تحتوي على الحرف ‘0’.

#### الخطوات

**1. إنشاء جدول**  
أعد استخدام الشيفرة من “إنشاء جدول وإضافة نص إلى الخلايا” للإعداد الأولي.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. إضافة فقرات**  
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

**3. رسم إطارات**  
قم بالتكرار على الفقرات والأجزاء لرسم إطارات حولها.
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

**4. حفظ العرض التقديمي**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## المشكلات الشائعة والنصائح

- **فحوصات Null** – احرص دائمًا على تغليف استخدام `Presentation` داخل كتلة try‑finally لضمان تنفيذ `pres.dispose()` وتحرير الموارد الأصلية.  
- **دقة المستطيل المحيط** – المستطيل الذي تُعيده `para.getRect()` يعكس التخطيط الحالي؛ إذا غيرت حجم الخط أو الهوامش، أعد حساب المستطيل قبل رسم الإطار.  
- **الأداء** – عند التعامل مع جداول كبيرة جدًا، فكر في تجميع إضافات الأشكال أو إعادة استخدام كائن `IAutoShape` واحد مع تحديث الهندسة لتقليل استهلاك الذاكرة.

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذه الـ APIs مع إصدارات JDK أقدم؟**  
ج: تدعم المكتبة JDK 8 فما فوق، لكن المصنف `jdk16` يقدم أفضل أداء على بيئات التشغيل الأحدث.

**س: كيف أغيّر لون الإطار؟**  
ج: عدّل لون تعبئة خط الإطار، مثال: `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**س: هل يمكن تصدير الشريحة النهائية كصورة؟**  
ج: نعم—استخدم `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` ثم احفظ مصفوفة البايتات.

**س: ماذا لو أردت تمييز كلمة “Total” فقط داخل خلية؟**  
ج: قم بالتكرار عبر `cell.getTextFrame().getParagraphs()`، ابحث عن الجزء الذي يحتوي على “Total”، وارسم مستطيلًا حول صندوق الحد الخاص بذلك الجزء.

**س: هل يتعامل Aspose.Slides مع العروض الكبيرة بكفاءة؟**  
ج: تقوم الـ API ببث البيانات وتحرير الموارد عند استدعاء `pres.dispose()`، مما يساعد في إدارة الذاكرة للملفات الكبيرة.

**آخر تحديث:** 2026-02-09  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
