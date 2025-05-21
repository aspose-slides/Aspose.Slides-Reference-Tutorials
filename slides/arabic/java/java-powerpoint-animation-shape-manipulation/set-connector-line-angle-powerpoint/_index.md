---
"description": "تعرّف على كيفية ضبط زوايا خطوط التوصيل في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. خصّص شرائحك بدقة."
"linktitle": "تعيين زاوية خط الموصل في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين زاوية خط الموصل في PowerPoint"
"url": "/ar/java/java-powerpoint-animation-shape-manipulation/set-connector-line-angle-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين زاوية خط الموصل في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية ضبط زاوية خطوط التوصيل في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. تُعد خطوط التوصيل أساسية لتوضيح العلاقات والتدفقات بين الأشكال في شرائحك. بضبط زواياها، تضمن أن تنقل عروضك التقديمية رسالتك بوضوح وفعالية.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت JDK (Java Development Kit) على نظامك.
- تم تنزيل مكتبة Aspose.Slides لجافا وإضافتها إلى مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## استيراد الحزم
للبدء، استورد الحزم اللازمة إلى مشروع جافا. تأكد من تضمين مكتبة Aspose.Slides للوصول إلى وظائف PowerPoint.
```java
import com.aspose.slides.*;

```
## الخطوة 1: تهيئة كائن العرض التقديمي
ابدأ بتهيئة كائن العرض التقديمي لتحميل ملف PowerPoint الخاص بك.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
## الخطوة 2: الوصول إلى الشرائح والأشكال
قم بالوصول إلى الشريحة وأشكالها لتحديد خطوط التوصيل.
```java
Slide slide = (Slide) pres.getSlides().get_Item(0);
Shape shape;
```
## الخطوة 3: التكرار عبر الأشكال
قم بالتكرار عبر كل شكل على الشريحة لتحديد خطوط التوصيل وخصائصها.
```java
for (int i = 0; i < slide.getShapes().size(); i++) {
    double dir = 0.0;
    shape = (Shape) slide.getShapes().get_Item(i);
    if (shape instanceof AutoShape) {
        AutoShape ashp = (AutoShape) shape;
        if (ashp.getShapeType() == ShapeType.Line) {
            // شكل خط المقبض
            dir = getDirection(ashp.getWidth(), ashp.getHeight(), ashp.getFrame().getFlipH() != 0, ashp.getFrame().getFlipV() != 0);
        }
    } else if (shape instanceof Connector) {
        // شكل موصل المقبض
        Connector ashp = (Connector) shape;
        dir = getDirection(ashp.getWidth(), ashp.getHeight(), ashp.getFrame().getFlipH() != 0, ashp.getFrame().getFlipV() != 0);
    }
    System.out.println(dir);
}
```
## الخطوة 4: حساب الزاوية
قم بتنفيذ طريقة getDirection لحساب زاوية خط الموصل.
```java
public static double getDirection(float w, float h, boolean flipH, boolean flipV) {
    float endLineX = w * (flipH ? -1 : 1);
    float endLineY = h * (flipV ? -1 : 1);
    float endYAxisX = 0;
    float endYAxisY = h;
    double angle = (Math.atan2(endYAxisY, endYAxisX) - Math.atan2(endLineY, endLineX));
    if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية التحكم بزوايا خطوط التوصيل في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. باتباع هذه الخطوات، يمكنك تخصيص شرائحك بفعالية لعرض بياناتك ومفاهيمك بصريًا بدقة.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java مع مكتبات Java الأخرى؟
بالتأكيد! يتكامل Aspose.Slides for Java بسلاسة مع مكتبات Java الأخرى لتحسين تجربة إنشاء وإدارة العروض التقديمية.
### هل برنامج Aspose.Slides مناسب لمهام PowerPoint البسيطة والمعقدة؟
نعم، يوفر Aspose.Slides مجموعة واسعة من الوظائف التي تلبي متطلبات PowerPoint المختلفة، بدءًا من معالجة الشرائح الأساسية وحتى مهام التنسيق والرسوم المتحركة المتقدمة.
### هل يدعم Aspose.Slides كافة ميزات PowerPoint؟
يسعى Aspose.Slides جاهدًا لدعم معظم ميزات PowerPoint. مع ذلك، للحصول على وظائف محددة أو متقدمة، يُنصح بالاطلاع على الوثائق أو التواصل مع دعم Aspose.
### هل يمكنني تخصيص أنماط خطوط الموصل باستخدام Aspose.Slides؟
بالتأكيد! يوفر Aspose.Slides خيارات شاملة لتخصيص خطوط التوصيل، بما في ذلك الأنماط والسمك ونقاط النهاية، مما يتيح لك إنشاء عروض تقديمية جذابة بصريًا.
### أين يمكنني العثور على الدعم للاستعلامات المتعلقة بـ Aspose.Slides؟
يمكنك زيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على المساعدة بشأن أي استفسارات أو مشكلات تواجهها أثناء عملية التطوير.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}