---
title: إزالة الجزء من الشكل الهندسي في PowerPoint
linktitle: إزالة الجزء من الشكل الهندسي في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إزالة الأجزاء من الأشكال الهندسية في PowerPoint باستخدام Aspose.Slides لـ Java من خلال دليلنا التفصيلي خطوة بخطوة.
weight: 22
url: /ar/java/java-powerpoint-shape-formatting-geometry/remove-segment-geometry-shape-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
هل تتطلع إلى التعامل مع الأشكال في عروض PowerPoint التقديمية باستخدام Java؟ لقد جئت إلى المكان المناسب! Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية تسمح لك بإنشاء الشرائح وتعديلها وإدارتها في عروضك التقديمية دون عناء. في هذا البرنامج التعليمي، سنرشدك خلال عملية إزالة جزء من شكل هندسي في PowerPoint. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيوفر لك هذا الدليل منهجًا خطوة بخطوة لإتقان هذه المهمة. على استعداد للغوص في؟ هيا بنا نبدأ!
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: قم بتنزيل مكتبة Aspose.Slides for Java من[هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم IDE مثل IntelliJ IDEA أو Eclipse لكتابة تعليمات Java البرمجية وتشغيلها.
4. المعرفة الأساسية لـ Java: سيساعدك الفهم الأساسي لبرمجة Java على متابعة هذا البرنامج التعليمي.
## حزم الاستيراد
للبدء، نحتاج إلى استيراد الحزم الضرورية من مكتبة Aspose.Slides. إليك كيفية القيام بذلك:
```java
import com.aspose.slides.*;

```
دعونا نقسم عملية إزالة مقطع من شكل هندسي في شريحة PowerPoint إلى خطوات متعددة.
## الخطوة 1: إنشاء عرض تقديمي جديد
أولاً، نحتاج إلى إنشاء كائن عرض تقديمي جديد. سيكون هذا الكائن بمثابة حاوية لشرائحنا وأشكالنا.
```java
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة شكل هندسي إلى الشريحة
بعد ذلك، قم بإضافة شكل هندسي إلى الشريحة. في هذا المثال، سوف نستخدم شكل قلب.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Heart, 100, 100, 300, 300);
```
## الخطوة 3: استرداد المسار الهندسي للشكل
بمجرد إضافة الشكل، نحتاج إلى استرداد المسار الهندسي الخاص به. يحتوي مسار الشكل الهندسي على الأجزاء التي تحدد الشكل.
```java
IGeometryPath path = shape.getGeometryPaths()[0];
```
## الخطوة 4: إزالة جزء من المسار الهندسي
الآن، سنقوم بإزالة جزء معين من المسار الهندسي. في هذا المثال، نقوم بإزالة المقطع الموجود في الفهرس 2.
```java
path.removeAt(2);
```
## الخطوة 5: قم بتعيين المسار الهندسي الجديد
بعد إزالة المقطع، قم بتعيين المسار الهندسي المعدل مرة أخرى إلى الشكل.
```java
shape.setGeometryPath(path);
```
## الخطوة 6: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدل في ملف.
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
وهناك لديك! باستخدام Aspose.Slides for Java، أصبح التعامل مع الأشكال في عروض PowerPoint التقديمية أمرًا مباشرًا وفعالاً. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة إزالة الأجزاء من الأشكال الهندسية، مما يمنحك تحكمًا أكبر في تصميم الشرائح ووظائفها. ترميز سعيد!
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لإنشاء عروض PowerPoint التقديمية وتعديلها وإدارتها برمجيًا.
### هل يمكنني استخدام Aspose.Slides لـ Java مع أشكال أخرى إلى جانب شكل القلب؟
قطعاً! يدعم Aspose.Slides for Java مجموعة واسعة من الأشكال التي يمكنك التعامل معها.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ Java؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### هل أحتاج إلى ترخيص لاستخدام Aspose.Slides لـ Java؟
 نعم، أنت بحاجة إلى ترخيص للحصول على الوظائف الكاملة. يمكنك شراء واحدة[هنا](https://purchase.aspose.com/buy) أو الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
 الوثائق الشاملة متاحة[هنا](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
