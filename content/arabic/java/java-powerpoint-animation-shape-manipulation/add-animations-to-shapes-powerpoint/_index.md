---
title: إضافة الرسوم المتحركة إلى الأشكال في PowerPoint
linktitle: إضافة الرسوم المتحركة إلى الأشكال في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة رسوم متحركة إلى الأشكال في PowerPoint باستخدام Aspose.Slides لـ Java من خلال هذا البرنامج التعليمي المفصل. مثالية لإنشاء عروض تقديمية جذابة.
type: docs
weight: 10
url: /ar/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/
---
## مقدمة
غالبًا ما يتطلب إنشاء عروض تقديمية جذابة إضافة رسوم متحركة إلى الأشكال والنصوص. يمكن أن تجعل الرسوم المتحركة شرائحك أكثر ديناميكية وجاذبية، مما يضمن بقاء جمهورك مهتمًا. في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة الرسوم المتحركة إلى الأشكال في عرض PowerPoint التقديمي باستخدام Aspose.Slides لـ Java. بحلول نهاية هذه المقالة، ستكون قادرًا على إنشاء رسوم متحركة احترافية دون عناء.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، دعونا نتأكد من أن لديك كل ما تحتاجه:
1.  Aspose.Slides لمكتبة Java: تحتاج إلى تثبيت مكتبة Aspose.Slides لـ Java. أنت تستطيع[قم بتنزيله هنا](https://releases.aspose.com/slides/java/).
2. Java Development Kit (JDK): تأكد من تثبيت JDK على جهازك.
3. بيئة التطوير المتكاملة (IDE): استخدم أي Java IDE مثل IntelliJ IDEA أو Eclipse أو NetBeans.
4. المعرفة الأساسية لـ Java: يفترض هذا البرنامج التعليمي أن لديك فهمًا أساسيًا لبرمجة Java.
## حزم الاستيراد
للبدء، ستحتاج إلى استيراد الحزم اللازمة لـ Aspose.Slides وفئات Java الأخرى المطلوبة.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## الخطوة 1: قم بإعداد دليل المشروع الخاص بك
أولاً، قم بإنشاء دليل لملفات مشروعك.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## الخطوة 2: تهيئة كائن العرض التقديمي
 بعد ذلك، قم بإنشاء مثيل`Presentation` فئة لتمثيل ملف PowerPoint الخاص بك.
```java
// إنشاء فئة العرض التقديمي التي تمثل PPTX
Presentation pres = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة الأولى
الآن، قم بالوصول إلى الشريحة الأولى في العرض التقديمي حيث ستضيف الرسوم المتحركة.
```java
// الوصول إلى الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
```
## الخطوة 4: إضافة شكل إلى الشريحة
أضف شكلاً مستطيلاً إلى الشريحة وأدخل بعض النص فيه.
```java
// أضف شكل مستطيل إلى الشريحة
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.addTextFrame("Animated TextBox");
```
## الخطوة 5: تطبيق تأثير الرسوم المتحركة
قم بتطبيق تأثير الرسوم المتحركة "PathFootball" على الشكل.
```java
// إضافة تأثير الرسوم المتحركة PathFootBall
pres.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(ashp, EffectType.PathFootball,
        EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## الخطوة 6: إنشاء مشغل تفاعلي
قم بإنشاء شكل زر يؤدي إلى تشغيل الرسوم المتحركة عند النقر عليه.
```java
// قم بإنشاء شكل "زر" لتشغيل الرسوم المتحركة
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## الخطوة 7: تحديد التسلسل التفاعلي
تحديد سلسلة من التأثيرات للزر.
```java
// قم بإنشاء سلسلة من التأثيرات للزر
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## الخطوة 8: إضافة مسار مستخدم مخصص
أضف رسمًا متحركًا مخصصًا لمسار المستخدم إلى الشكل.
```java
// إضافة تأثير الرسوم المتحركة لمسار المستخدم المخصص
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// إنشاء تأثير الحركة
IMotionEffect motionBhv = ((IMotionEffect) fxUserPath.getBehaviors().get_Item(0));
// تحديد نقاط المسار
Point2D.Float[] pts = (Point2D.Float[]) Array.newInstance(Point2D.Float.class, 1);
pts[0] = new Point2D.Float(0.076f, 0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new Point2D.Float(-0.076f, -0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.getPath().add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
```
## الخطوة 9: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي في الموقع الذي تريده.
```java
// احفظ العرض التقديمي كملف PPTX
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// تخلص من كائن العرض التقديمي
if (pres != null) pres.dispose();
```
## خاتمة
وهناك لديك! لقد نجحت في إضافة الرسوم المتحركة إلى الأشكال في عرض PowerPoint التقديمي باستخدام Aspose.Slides لـ Java. تسهل هذه المكتبة القوية تحسين عروضك التقديمية باستخدام التأثيرات الديناميكية، مما يضمن استمرار تفاعل جمهورك. تذكر أن الممارسة تؤدي إلى الكمال، لذا استمر في تجربة التأثيرات والمحفزات المختلفة لمعرفة ما يناسب احتياجاتك بشكل أفضل.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لإنشاء عروض PowerPoint التقديمية وتعديلها ومعالجتها برمجيًا.
### هل يمكنني استخدام Aspose.Slides مجانًا؟
 يمكنك تجربة Aspose.Slides مجانًا باستخدام ملف[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/). لمواصلة الاستخدام، مطلوب ترخيص مدفوع.
### ما هي إصدارات Java المتوافقة مع Aspose.Slides؟
يدعم Aspose.Slides الإصدار Java SE 6 والإصدارات الأحدث.
### كيف يمكنني إضافة رسوم متحركة مختلفة إلى أشكال متعددة؟
يمكنك إضافة رسوم متحركة مختلفة إلى أشكال متعددة عن طريق تكرار الخطوات لكل شكل وتحديد تأثيرات مختلفة حسب الحاجة.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
 تفحص ال[توثيق](https://reference.aspose.com/slides/java/) و[منتدى الدعم](https://forum.aspose.com/c/slides/11) لمزيد من الأمثلة والمساعدة.