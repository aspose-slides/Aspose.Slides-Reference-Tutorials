---
title: تعيين زاوية خط الموصل في PowerPoint
linktitle: تعيين زاوية خط الموصل في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين زوايا خط الموصل في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. قم بتخصيص الشرائح الخاصة بك بدقة.
type: docs
weight: 17
url: /ar/java/java-powerpoint-animation-shape-manipulation/set-connector-line-angle-powerpoint/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية تعيين زاوية خطوط الموصل في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java. تعتبر خطوط الموصل ضرورية لتوضيح العلاقات والتدفقات بين الأشكال في شرائحك. ومن خلال ضبط زواياها، يمكنك التأكد من أن عروضك التقديمية تنقل رسالتك بوضوح وفعالية.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- JDK (Java Development Kit) مثبت على نظامك.
-  تم تنزيل Aspose.Slides لمكتبة Java وإضافتها إلى مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك. تأكد من تضمين مكتبة Aspose.Slides للوصول إلى وظائف PowerPoint.
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
قم بالوصول إلى الشريحة وأشكالها لتحديد خطوط الموصل.
```java
Slide slide = (Slide) pres.getSlides().get_Item(0);
Shape shape;
```
## الخطوة 3: التكرار من خلال الأشكال
كرر كل شكل على الشريحة لتحديد خطوط الموصل وخصائصها.
```java
for (int i = 0; i < slide.getShapes().size(); i++) {
    double dir = 0.0;
    shape = (Shape) slide.getShapes().get_Item(i);
    if (shape instanceof AutoShape) {
        AutoShape ashp = (AutoShape) shape;
        if (ashp.getShapeType() == ShapeType.Line) {
            // التعامل مع شكل الخط
            dir = getDirection(ashp.getWidth(), ashp.getHeight(), ashp.getFrame().getFlipH() != 0, ashp.getFrame().getFlipV() != 0);
        }
    } else if (shape instanceof Connector) {
        // التعامل مع شكل الموصل
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
في هذا البرنامج التعليمي، تعلمنا كيفية التعامل مع زوايا خطوط الموصل في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java. باتباع هذه الخطوات، يمكنك تخصيص شرائحك بشكل فعال لتمثيل بياناتك ومفاهيمك بشكل مرئي بدقة.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java مع مكتبات Java الأخرى؟
قطعاً! يتكامل Aspose.Slides for Java بسلاسة مع مكتبات Java الأخرى لتحسين تجربة إنشاء العرض التقديمي وإدارته.
### هل Aspose.Slides مناسب لمهام PowerPoint البسيطة والمعقدة؟
نعم، يقدم Aspose.Slides مجموعة واسعة من الوظائف التي تلبي متطلبات PowerPoint المختلفة، بدءًا من معالجة الشرائح الأساسية وحتى التنسيق المتقدم ومهام الرسوم المتحركة.
### هل يدعم Aspose.Slides جميع ميزات PowerPoint؟
يسعى Aspose.Slides جاهداً لدعم معظم ميزات PowerPoint. ومع ذلك، بالنسبة لوظائف محددة أو متقدمة، يوصى بمراجعة الوثائق أو التواصل مع دعم Aspose.
### هل يمكنني تخصيص أنماط خطوط الموصل باستخدام Aspose.Slides؟
بالتأكيد! يوفر Aspose.Slides خيارات شاملة لتخصيص خطوط الموصل، بما في ذلك الأنماط والسمك ونقاط النهاية، مما يسمح لك بإنشاء عروض تقديمية جذابة بصريًا.
### أين يمكنني العثور على الدعم للاستفسارات المتعلقة بـ Aspose.Slides؟
 يمكنك زيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للمساعدة في أي استفسارات أو مشكلات تواجهها أثناء عملية التطوير.