---
"description": "تعرف على كيفية إزالة الأجزاء من الأشكال الهندسية في PowerPoint باستخدام Aspose.Slides لـ Java من خلال دليلنا المفصل خطوة بخطوة."
"linktitle": "إزالة جزء من شكل هندسي في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إزالة جزء من شكل هندسي في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-formatting-geometry/remove-segment-geometry-shape-powerpoint/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إزالة جزء من شكل هندسي في PowerPoint

## مقدمة
هل ترغب في معالجة الأشكال في عروض PowerPoint التقديمية باستخدام Java؟ أنت في المكان المناسب! Aspose.Slides for Java هي واجهة برمجة تطبيقات قوية تُمكّنك من إنشاء الشرائح وتعديلها وإدارتها في عروضك التقديمية بسهولة. في هذا البرنامج التعليمي، سنشرح لك عملية إزالة مقطع من شكل هندسي في PowerPoint. سواء كنت مطورًا محترفًا أو مبتدئًا، سيقدم لك هذا الدليل نهجًا خطوة بخطوة لإتقان هذه المهمة. هل أنت مستعد للبدء؟ هيا بنا!
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من [موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides لـ Java: قم بتنزيل مكتبة Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم بيئة التطوير المتكاملة مثل IntelliJ IDEA أو Eclipse لكتابة وتشغيل كود Java الخاص بك.
4. المعرفة الأساسية بلغة جافا: إن الفهم الأساسي لبرمجة جافا سوف يساعدك على متابعة هذا البرنامج التعليمي.
## استيراد الحزم
للبدء، نحتاج إلى استيراد الحزم اللازمة من مكتبة Aspose.Slides. إليك الطريقة:
```java
import com.aspose.slides.*;

```
دعونا نقسم عملية إزالة جزء من شكل هندسي في شريحة PowerPoint إلى خطوات متعددة.
## الخطوة 1: إنشاء عرض تقديمي جديد
أولاً، علينا إنشاء كائن عرض تقديمي جديد. سيُستخدم هذا الكائن كحاوية للشرائح والأشكال.
```java
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة شكل هندسي إلى الشريحة
بعد ذلك، أضف شكلًا هندسيًا إلى الشريحة. في هذا المثال، سنستخدم شكل قلب.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Heart, 100, 100, 300, 300);
```
## الخطوة 3: استرداد مسار الهندسة للشكل
بعد إضافة الشكل، نحتاج إلى استرجاع مساره الهندسي. يحتوي هذا المسار على الأجزاء التي تُعرّف الشكل.
```java
IGeometryPath path = shape.getGeometryPaths()[0];
```
## الخطوة 4: إزالة جزء من مسار الهندسة
الآن، سنحذف مقطعًا محددًا من مسار الهندسة. في هذا المثال، سنحذف المقطع عند الفهرس ٢.
```java
path.removeAt(2);
```
## الخطوة 5: تعيين مسار الهندسة الجديد
بعد إزالة القطعة، قم بإرجاع مسار الهندسة المعدلة إلى الشكل.
```java
shape.setGeometryPath(path);
```
## الخطوة 6: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل في ملف.
```java
String resultPath = "Your Output Directory" + "GeometryShapeRemoveSegment.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## الخطوة 7: تنظيف الموارد
تأكد دائمًا من تنظيف الموارد لمنع تسرب الذاكرة.
```java
if (pres != null) pres.dispose();
```
## خاتمة
وهذا كل ما في الأمر! مع Aspose.Slides لجافا، أصبح التعامل مع الأشكال في عروض PowerPoint التقديمية سهلًا وفعالًا. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة إزالة أجزاء من الأشكال الهندسية، مما يمنحك تحكمًا أكبر في تصميم ووظائف شرائحك. برمجة ممتعة!
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لإنشاء عروض PowerPoint وتعديلها وإدارتها برمجيًا.
### هل يمكنني استخدام Aspose.Slides لـ Java مع أشكال أخرى بالإضافة إلى شكل القلب؟
بالتأكيد! يدعم Aspose.Slides لـ Java مجموعة واسعة من الأشكال التي يمكنك التعامل معها.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لنظام Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### هل أحتاج إلى ترخيص لاستخدام Aspose.Slides لـ Java؟
نعم، تحتاج إلى ترخيص للاستفادة من جميع الوظائف. يمكنك شراء ترخيص. [هنا](https://purchase.aspose.com/buy) أو الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
التوثيق الشامل متاح [هنا](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}