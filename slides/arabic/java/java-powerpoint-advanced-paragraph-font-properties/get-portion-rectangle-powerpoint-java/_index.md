---
"description": "تعلّم كيفية الحصول على مستطيل الجزء في PowerPoint باستخدام Aspose.Slides لجافا من خلال هذا البرنامج التعليمي المفصل خطوة بخطوة. مثالي لمطوري جافا."
"linktitle": "الحصول على مستطيل الجزء في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "الحصول على مستطيل الجزء في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# الحصول على مستطيل الجزء في PowerPoint باستخدام Java

## مقدمة
إنشاء عروض تقديمية ديناميكية بلغة جافا سهل للغاية مع Aspose.Slides لجافا. في هذا البرنامج التعليمي، سنتعمق في تفاصيل الحصول على مستطيل الجزء في PowerPoint باستخدام Aspose.Slides. سنغطي كل شيء، من إعداد بيئة العمل إلى شرح الكود خطوة بخطوة. هيا بنا نبدأ!
## المتطلبات الأساسية
قبل أن ننتقل إلى الكود، دعنا نتأكد من أن لديك كل ما تحتاجه لمتابعة الأمر بسلاسة:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK 8 أو أعلى على جهازك.
2. Aspose.Slides لـ Java: قم بتنزيل الإصدار الأحدث من [هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): Eclipse، أو IntelliJ IDEA، أو أي بيئة تطوير متكاملة Java أخرى من اختيارك.
4. المعرفة الأساسية بلغة جافا: يعد فهم برمجة جافا أمرًا ضروريًا.
## استيراد الحزم
أولاً، لنستورد الحزم اللازمة. سيتضمن ذلك Aspose.Slides وبعض الحزم الأخرى لإدارة مهمتنا بكفاءة.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## الخطوة 1: إعداد العرض التقديمي
الخطوة الأولى هي إنشاء عرض تقديمي جديد. سيكون هذا هو لوحتنا للعمل عليه.
```java
Presentation pres = new Presentation();
```
## الخطوة 2: إنشاء جدول
الآن، لنُضِف جدولًا إلى الشريحة الأولى من عرضنا التقديمي. سيحتوي هذا الجدول على الخلايا التي سنضيف إليها النص.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## الخطوة 3: إضافة فقرات إلى الخلايا
بعد ذلك، سننشئ فقرات ونضيفها إلى خلية محددة في الجدول. يتضمن ذلك مسح أي نص موجود ثم إضافة فقرات جديدة.
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
لجعل عرضنا التقديمي أكثر ديناميكية، سنضيف إطار نص إلى الشكل التلقائي ونحدد محاذاته.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## الخطوة 5: حساب الإحداثيات
نحتاج إلى الحصول على إحداثيات الزاوية العلوية اليسرى لخلية الجدول. سيساعدنا هذا في تحديد موضع الأشكال بدقة.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## الخطوة 6: إضافة إطارات إلى الفقرات والأجزاء
باستخدام `IParagraph.getRect()` و `IPortion.getRect()` باستخدام أساليبنا، يمكننا إضافة إطارات إلى فقراتنا وأجزائنا. يتضمن ذلك التكرار خلال الفقرات والأجزائها، وإنشاء أشكال حولها، وتخصيص مظهرها.
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
وبنفس الطريقة، سنضيف إطارات إلى الفقرات في الشكل التلقائي لدينا، مما يعزز من الجاذبية البصرية للعرض التقديمي.
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
وأخيرًا، سنقوم بحفظ عرضنا التقديمي في المسار المحدد.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## الخطوة 9: التنظيف
من الجيد التخلص من كائن العرض لتحرير الموارد.
```java
if (pres != null) pres.dispose();
```
## خاتمة
تهانينا! لقد نجحت في تعلم كيفية الحصول على مستطيل الجزء في PowerPoint باستخدام Aspose.Slides لجافا. تتيح لك هذه المكتبة القوية عالمًا واسعًا من الإمكانيات لإنشاء عروض تقديمية ديناميكية وجذابة بصريًا برمجيًا. تعمق في Aspose.Slides واستكشف المزيد من الميزات لتحسين عروضك التقديمية بشكل أكبر.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint وتعديلها والتلاعب بها برمجيًا.
### هل يمكنني استخدام Aspose.Slides لـ Java في المشاريع التجارية؟
نعم، يُمكن استخدام Aspose.Slides لجافا في المشاريع التجارية. يُمكنك شراء ترخيص من [هنا](https://purchase.aspose.com/buy).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لنظام Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟
الوثائق متاحة [هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
يمكنك الحصول على الدعم من منتدى Aspose [هنا](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}