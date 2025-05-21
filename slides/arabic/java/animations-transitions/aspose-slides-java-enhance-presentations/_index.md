---
"date": "2025-04-18"
"description": "تعلّم كيفية تحسين عروضك التقديمية بإتقان التعامل مع الجداول والإطارات باستخدام Aspose.Slides لجافا. يغطي هذا الدليل إنشاء الجداول، وإضافة إطارات النصوص، ورسم الإطارات حول محتوى محدد."
"title": "Aspose.Slides لجافا - إتقان التعامل مع الجداول والإطارات في العروض التقديمية"
"url": "/ar/java/animations-transitions/aspose-slides-java-enhance-presentations/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان التعامل مع الجداول والإطارات في العروض التقديمية باستخدام Aspose.Slides لـ Java

## مقدمة

قد يكون عرض البيانات بفعالية في PowerPoint أمرًا صعبًا. سواء كنت مطور برامج أو مصمم عروض تقديمية، فإن استخدام جداول جذابة بصريًا وإضافة إطارات نصية يجعل شرائحك أكثر جاذبية. يستكشف هذا البرنامج التعليمي كيفية استخدام Aspose.Slides لجافا لإضافة نص إلى خلايا الجدول ورسم إطارات حول الفقرات والأجزاء التي تحتوي على أحرف معينة مثل "0". بإتقان هذه التقنيات، ستُحسّن عروضك التقديمية بدقة وأناقة.

### ما سوف تتعلمه:
- إنشاء الجداول في الشرائح وملئها بالنص.
- محاذاة النص داخل الأشكال التلقائية لتقديم أفضل.
- رسم إطارات حول الفقرات والأجزاء للتأكيد على المحتوى.
- التطبيقات العملية لهذه الميزات في سيناريوهات العالم الحقيقي.

هل أنت مستعد لتحويل عروضك التقديمية؟ هيا بنا!

## المتطلبات الأساسية

قبل الغوص في الكود، تأكد من أن لديك ما يلي:

### المكتبات المطلوبة
ستحتاج إلى Aspose.Slides لجافا. إليك كيفية تضمينه باستخدام Maven أو Gradle:

**مافن:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**جرادل:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### إعداد البيئة
تأكد من تثبيت Java Development Kit (JDK)، ويفضل JDK 16 أو إصدار أحدث، حيث يستخدم هذا المثال `jdk16` مصنف.

### متطلبات المعرفة
- فهم أساسيات برمجة جافا.
- -الإلمام ببرامج العروض التقديمية مثل PowerPoint.
- خبرة في استخدام بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## إعداد Aspose.Slides لـ Java

لبدء استخدام Aspose.Slides، اتبع الخطوات التالية:

1. **تثبيت المكتبة**:استخدم Maven أو Gradle لإدارة التبعيات، أو قم بتنزيله مباشرة من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

2. **الحصول على الترخيص**:
   - ابدأ بفترة تجريبية مجانية عن طريق تنزيل ترخيص مؤقت من [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/).
   - للحصول على إمكانية الوصول الكاملة، فكر في شراء ترخيص من [شراء Aspose.Slides](https://purchase.aspose.com/buy).

3. **التهيئة الأساسية**:
قم بتهيئة بيئة العرض التقديمي الخاصة بك باستخدام مقتطف التعليمات البرمجية التالي:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // الكود الخاص بك هنا
} finally {
    if (pres != null) pres.dispose();
}
```

## دليل التنفيذ

يغطي هذا القسم الميزات المختلفة التي يمكنك تنفيذها باستخدام Aspose.Slides لـ Java.

### الميزة 1: إنشاء جدول وإضافة نص إلى الخلايا

#### ملخص
توضح هذه الميزة كيفية إنشاء جدول في الشريحة الأولى وملء خلايا محددة بالنص. 

##### خطوات:
**1. إنشاء جدول**
أولاً، قم بتهيئة العرض التقديمي الخاص بك وأضف جدولاً في الموضع (50، 50) بعرض أعمدة محدد وارتفاع صفوف محددين.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2. إضافة نص إلى الخلايا**
إنشاء فقرات تحتوي على أجزاء من النص وإضافتها إلى خلية محددة.
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
**3. احفظ العرض التقديمي**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### الميزة 2: إضافة إطار نصي إلى الشكل التلقائي وتعيين المحاذاة

#### ملخص
تعرف على كيفية إضافة إطار نص بمحاذاة محددة إلى شكل تلقائي.

##### خطوات:
**1. إضافة شكل تلقائي**
أضف مستطيلاً كشكل تلقائي في الموضع (400، 100) بأبعاد محددة.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```
**2. ضبط محاذاة النص**
اضبط النص على "نص في الشكل" وقم بمحاذاته إلى اليسار.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
**3. احفظ العرض التقديمي**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### الميزة 3: رسم إطارات حول الفقرات والأجزاء في خلايا الجدول

#### ملخص
ترتكز هذه الميزة على رسم الإطارات حول الفقرات والأجزاء التي تحتوي على "0" داخل خلايا الجدول.

##### خطوات:
**1. إنشاء جدول**
أعد استخدام الكود من "إنشاء جدول وإضافة نص إلى الخلايا" للإعداد الأولي.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2. إضافة فقرات**
إعادة استخدام كود إنشاء الفقرات من الميزة السابقة.
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
**3. ارسم الإطارات**
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
**4. احفظ العرض التقديمي**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## خاتمة
باتباع هذا الدليل، يمكنك تحسين عروضك التقديمية بفعالية باستخدام Aspose.Slides لجافا. إتقان التعامل مع الجداول والإطارات يتيح لك إنشاء شرائح أكثر جاذبية وجمالاً. لمزيد من الاستكشاف، فكّر في التعمق في ميزات Aspose.Slides الإضافية أو دمجها مع تطبيقات جافا أخرى.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}