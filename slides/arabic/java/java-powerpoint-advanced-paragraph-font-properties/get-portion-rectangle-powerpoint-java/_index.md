---
title: الحصول على مستطيل الجزء في PowerPoint باستخدام Java
linktitle: الحصول على مستطيل الجزء في PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية الحصول على الجزء المستطيل في PowerPoint باستخدام Aspose.Slides لـ Java من خلال هذا البرنامج التعليمي التفصيلي خطوة بخطوة. مثالية لمطوري جافا.
type: docs
weight: 12
url: /ar/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---
## مقدمة
أصبح إنشاء عروض تقديمية ديناميكية في Java أمرًا سهلاً مع Aspose.Slides for Java. في هذا البرنامج التعليمي، سوف نتعمق في التفاصيل الدقيقة للحصول على الجزء المستطيل في PowerPoint باستخدام Aspose.Slides. سنغطي كل شيء بدءًا من إعداد بيئتك وحتى تحليل التعليمات البرمجية خطوة بخطوة. اذا هيا بنا نبدأ!
## المتطلبات الأساسية
قبل أن ننتقل إلى الكود، دعنا نتأكد من أن لديك كل ما تحتاجه للمتابعة بسلاسة:
1. Java Development Kit (JDK): تأكد من تثبيت JDK 8 أو إصدار أحدث على جهازك.
2.  Aspose.Slides لـ Java: قم بتنزيل أحدث إصدار من[هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): Eclipse أو IntelliJ IDEA أو أي Java IDE آخر من اختيارك.
4. المعرفة الأساسية بـ Java: يعد فهم برمجة Java أمرًا ضروريًا.
## حزم الاستيراد
أول الأشياء أولاً، فلنستورد الحزم الضرورية. وسيشمل ذلك Aspose.Slides وعدد قليل من الآخرين للتعامل مع مهمتنا بكفاءة.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## الخطوة 1: إعداد العرض التقديمي
الخطوة الأولى هي إنشاء عرض تقديمي جديد. ستكون هذه هي اللوحة القماشية التي سنعمل عليها.
```java
Presentation pres = new Presentation();
```
## الخطوة 2: إنشاء جدول
الآن، دعونا نضيف جدولاً إلى الشريحة الأولى من العرض التقديمي. سيحتوي هذا الجدول على الخلايا التي سنضيف فيها النص.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## الخطوة 3: إضافة فقرات إلى الخلايا
بعد ذلك، سنقوم بإنشاء فقرات وإضافتها إلى خلية معينة في الجدول. يتضمن ذلك مسح أي نص موجود ثم إضافة فقرات جديدة.
```java
// إنشاء فقرات
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// إضافة نص إلى خلية الجدول
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## الخطوة 4: إضافة إطار نص إلى شكل تلقائي
لجعل عرضنا التقديمي أكثر ديناميكية، سنقوم بإضافة إطار نص إلى الشكل التلقائي وتعيين محاذاته.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## الخطوة 5: حساب الإحداثيات
نحتاج إلى الحصول على إحداثيات الزاوية العلوية اليسرى لخلية الجدول. وهذا سوف يساعدنا على وضع الأشكال بدقة.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## الخطوة 6: إضافة إطارات إلى الفقرات والأجزاء
 باستخدام`IParagraph.getRect()` و`IPortion.getRect()`بالطرق، يمكننا إضافة إطارات إلى فقراتنا وأجزاءنا. يتضمن ذلك تكرار الفقرات والأجزاء وإنشاء أشكال حولها وتخصيص مظهرها.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## الخطوة 7: إضافة إطارات إلى فقرات الشكل التلقائي
وبالمثل، سنقوم بإضافة إطارات إلى الفقرات في الشكل التلقائي الخاص بنا، مما يعزز المظهر المرئي للعرض التقديمي.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## الخطوة 8: حفظ العرض التقديمي
وأخيرًا، سنقوم بحفظ العرض التقديمي الخاص بنا في المسار المحدد.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## الخطوة 9: التنظيف
من الممارسات الجيدة التخلص من كائن العرض التقديمي لتحرير الموارد.
```java
if (pres != null) pres.dispose();
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية الحصول على الجزء المستطيل في PowerPoint باستخدام Aspose.Slides لـ Java. تفتح هذه المكتبة القوية عالمًا من الإمكانيات لإنشاء عروض تقديمية ديناميكية وجذابة بصريًا برمجيًا. تعمق أكثر في Aspose.Slides واستكشف المزيد من الميزات لتحسين عروضك التقديمية بشكل أكبر.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية وتعديلها ومعالجتها برمجياً.
### هل يمكنني استخدام Aspose.Slides لـ Java في المشاريع التجارية؟
 نعم، يمكن استخدام Aspose.Slides for Java في المشاريع التجارية. يمكنك شراء ترخيص من[هنا](https://purchase.aspose.com/buy).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ Java؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟
 الوثائق متاحة[هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على الدعم من منتدى Aspose[هنا](https://forum.aspose.com/c/slides/11).