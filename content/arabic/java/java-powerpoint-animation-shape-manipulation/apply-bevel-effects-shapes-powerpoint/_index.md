---
title: تطبيق تأثيرات شطبة على الأشكال في PowerPoint
linktitle: تطبيق تأثيرات شطبة على الأشكال في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تطبيق التأثيرات المائلة على الأشكال في PowerPoint باستخدام Aspose.Slides لـ Java من خلال دليلنا خطوة بخطوة. تعزيز العروض التقديمية الخاصة بك.
type: docs
weight: 13
url: /ar/java/java-powerpoint-animation-shape-manipulation/apply-bevel-effects-shapes-powerpoint/
---
## مقدمة
يعد إنشاء عروض تقديمية جذابة بصريًا أمرًا بالغ الأهمية لجذب انتباه جمهورك والحفاظ عليه. يمكن أن تؤدي إضافة تأثيرات مشطوفة إلى الأشكال إلى تحسين الجماليات العامة لشرائحك، مما يجعل عرضك التقديمي مميزًا. في هذا البرنامج التعليمي، سنرشدك خلال عملية تطبيق التأثيرات المجسمة المائلة على الأشكال في PowerPoint باستخدام Aspose.Slides for Java. سواء كنت مطورًا يتطلع إلى أتمتة عملية إنشاء العروض التقديمية أو مجرد شخص يحب إجراء تعديلات على التصميم، فإن هذا الدليل يوفر لك كل ما تحتاجه.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Java Development Kit (JDK): تأكد من تثبيت JDK. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides لمكتبة Java: قم بتنزيل المكتبة من[Aspose.Slides لجافا](https://releases.aspose.com/slides/java/).
- IDE (بيئة التطوير المتكاملة): استخدم أي IDE من اختيارك، مثل IntelliJ IDEA أو Eclipse أو NetBeans.
-  ترخيص Aspose: لاستخدام Aspose.Slides دون قيود، احصل على ترخيص من[Aspose الشراء](https://purchase.aspose.com/buy) أو الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) للتقييم.
## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم اللازمة للعمل مع Aspose.Slides في مشروع Java الخاص بك. وإليك كيف يمكنك القيام بذلك:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
```
## الخطوة 1: قم بإعداد مشروعك
 قبل أن تتمكن من البدء في البرمجة، تأكد من إعداد مشروعك بشكل صحيح. قم بتضمين مكتبة Aspose.Slides في مسار إنشاء مشروعك. إذا كنت تستخدم Maven، فأضف التبعية التالية إلى ملفك`pom.xml` ملف:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>23.6</version>
</dependency>
```
## الخطوة 2: إنشاء عرض تقديمي
 لبدء العمل مع Aspose.Slides، تحتاج إلى إنشاء مثيل لـ`Presentation` فصل. تمثل هذه الفئة ملف PowerPoint.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation pres = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة الأولى
بعد إنشاء عرض تقديمي، قم بالوصول إلى الشريحة الأولى حيث ستضيف الأشكال وتعامل معها.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## الخطوة 4: إضافة شكل إلى الشريحة
الآن، قم بإضافة شكل إلى الشريحة. في هذا المثال، سوف نقوم بإضافة القطع الناقص.
```java
// إضافة شكل على الشريحة
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.getFillFormat().setFillType(FillType.Solid);
shape.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
ILineFillFormat format = shape.getLineFormat().getFillFormat();
format.setFillType(FillType.Solid);
format.getSolidFillColor().setColor(Color.ORANGE);
shape.getLineFormat().setWidth(2.0);
```
## الخطوة 5: تطبيق التأثيرات المجسمة على الشكل
بعد ذلك، قم بتطبيق التأثيرات المائلة على الشكل لمنحه مظهرًا ثلاثي الأبعاد.
```java
// قم بتعيين خصائص ThreeDFormat للشكل
shape.getThreeDFormat().setDepth((short) 4);
shape.getThreeDFormat().getBevelTop().setBevelType(BevelPresetType.Circle);
shape.getThreeDFormat().getBevelTop().setHeight(6);
shape.getThreeDFormat().getBevelTop().setWidth(6);
shape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.OrthographicFront);
shape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.ThreePt);
shape.getThreeDFormat().getLightRig().setDirection(LightingDirection.Top);
```
## الخطوة 6: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي كملف PPTX في الدليل المحدد لديك.
```java
// قم بكتابة العرض التقديمي كملف PPTX
pres.save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
## الخطوة 7: التخلص من كائن العرض التقديمي
 لتحرير الموارد، تأكد دائمًا من أن`Presentation` يتم التخلص من الكائن بشكل صحيح.
```java
if (pres != null) pres.dispose();
```
## خاتمة
 يعد تطبيق التأثيرات المائلة على الأشكال في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java عملية مباشرة يمكنها تحسين المظهر المرئي لشرائحك بشكل كبير. باتباع الخطوات الموضحة في هذا الدليل، يمكنك بسهولة إنشاء عروض تقديمية احترافية وجذابة. تذكر أن تستكشف[Aspose.Slides الوثائق](https://reference.aspose.com/slides/java/) لمزيد من المعلومات التفصيلية والميزات المتقدمة.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية تتيح للمطورين إنشاء عروض PowerPoint التقديمية وتعديلها وإدارتها برمجيًا.
### هل يمكنني استخدام Aspose.Slides لـ Java مجانًا؟
 يقدم Aspose.Slides نسخة تجريبية مجانية يمكنك التنزيل منها[هنا](https://releases.aspose.com/). للحصول على الميزات الكاملة، تحتاج إلى شراء ترخيص.
### ما أنواع الأشكال التي يمكنني إضافتها إلى شرائحي؟
يمكنك إضافة أشكال مختلفة مثل المستطيلات وعلامات الحذف والخطوط والأشكال المخصصة باستخدام Aspose.Slides for Java.
### هل من الممكن تطبيق تأثيرات ثلاثية الأبعاد أخرى إلى جانب الشطب؟
نعم، يتيح لك Aspose.Slides for Java تطبيق تأثيرات ثلاثية الأبعاد متنوعة، بما في ذلك تأثيرات العمق والإضاءة والكاميرا.
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على الدعم من مجتمع Aspose وفريق الدعم على موقعهم[منتدى الدعم](https://forum.aspose.com/c/slides/11).