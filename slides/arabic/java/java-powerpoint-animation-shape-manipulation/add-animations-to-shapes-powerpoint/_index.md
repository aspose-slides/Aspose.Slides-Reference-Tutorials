---
"description": "تعرّف على كيفية إضافة رسوم متحركة إلى الأشكال في PowerPoint باستخدام Aspose.Slides لجافا من خلال هذا البرنامج التعليمي المفصل. مثالي لإنشاء عروض تقديمية جذابة."
"linktitle": "إضافة الرسوم المتحركة إلى الأشكال في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة الرسوم المتحركة إلى الأشكال في PowerPoint"
"url": "/ar/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة الرسوم المتحركة إلى الأشكال في PowerPoint

## مقدمة
غالبًا ما يتطلب إنشاء عروض تقديمية جذابة إضافة رسوم متحركة للأشكال والنصوص. تُضفي الرسوم المتحركة على شرائحك حيويةً وجاذبيةً، مما يضمن استمرار اهتمام جمهورك. في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة الرسوم المتحركة للأشكال في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. بنهاية هذه المقالة، ستتمكن من إنشاء رسوم متحركة احترافية بكل سهولة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، دعنا نتأكد من أن لديك كل ما تحتاجه:
1. مكتبة Aspose.Slides لجافا: يجب تثبيت مكتبة Aspose.Slides لجافا. يمكنك [قم بتحميله هنا](https://releases.aspose.com/slides/java/).
2. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK على جهازك.
3. بيئة التطوير المتكاملة (IDE): استخدم أي بيئة تطوير متكاملة لـ Java مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.
4. المعرفة الأساسية بلغة جافا: يفترض هذا البرنامج التعليمي أن لديك فهمًا أساسيًا لبرمجة جافا.
## استيراد الحزم
للبدء، ستحتاج إلى استيراد الحزم اللازمة لـ Aspose.Slides وفئات Java الأخرى المطلوبة.
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## الخطوة 1: إعداد دليل المشروع الخاص بك
أولاً، قم بإنشاء دليل لملفات مشروعك.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## الخطوة 2: تهيئة كائن العرض التقديمي
بعد ذلك، قم بإنشاء مثيل `Presentation` الفئة لتمثيل ملف PowerPoint الخاص بك.
```java
// إنشاء فئة عرض تقديمي تمثل PPTX
Presentation pres = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة الأولى
الآن، قم بالوصول إلى الشريحة الأولى في العرض التقديمي حيث ستضيف الرسوم المتحركة.
```java
// الوصول إلى الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
```
## الخطوة 4: إضافة شكل إلى الشريحة
أضف شكل مستطيل إلى الشريحة وأدرج بعض النص فيه.
```java
// إضافة شكل مستطيل إلى الشريحة
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
## الخطوة 6: إنشاء مُحفِّز تفاعلي
قم بإنشاء شكل زر سيؤدي إلى تشغيل الرسوم المتحركة عند النقر فوقه.
```java
// إنشاء شكل "زر" لتشغيل الرسوم المتحركة
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## الخطوة 7: تحديد التسلسل التفاعلي
قم بتحديد سلسلة من التأثيرات للزر.
```java
// إنشاء سلسلة من التأثيرات للزر
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## الخطوة 8: إضافة مسار مستخدم مخصص
أضف رسمًا متحركًا لمسار المستخدم المخصص إلى الشكل.
```java
// إضافة تأثير رسوم متحركة لمسار المستخدم المخصص
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
## الخطوة 9: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي في الموقع المطلوب.
```java
// حفظ العرض التقديمي كملف PPTX
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// التخلص من كائن العرض
if (pres != null) pres.dispose();
```
## خاتمة
وها قد انتهيت! لقد نجحت في إضافة رسوم متحركة إلى الأشكال في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. تُسهّل هذه المكتبة القوية تحسين عروضك التقديمية بتأثيرات ديناميكية، مما يضمن تفاعل جمهورك. تذكر، الممارسة تصنع الإتقان، لذا استمر في تجربة تأثيرات ومحفزات مختلفة لمعرفة ما يناسب احتياجاتك.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لإنشاء عروض PowerPoint وتعديلها والتلاعب بها برمجيًا.
### هل يمكنني استخدام Aspose.Slides مجانًا؟
يمكنك تجربة Aspose.Slides مجانًا باستخدام [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/). للاستمرار في الاستخدام، يلزم الحصول على ترخيص مدفوع.
### ما هي إصدارات Java المتوافقة مع Aspose.Slides؟
يدعم Aspose.Slides Java SE 6 والإصدارات الأحدث.
### كيف أضيف رسوم متحركة مختلفة إلى أشكال متعددة؟
يمكنك إضافة رسوم متحركة مختلفة إلى أشكال متعددة عن طريق تكرار الخطوات لكل شكل وتحديد تأثيرات مختلفة حسب الحاجة.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
تحقق من [التوثيق](https://reference.aspose.com/slides/java/) و [منتدى الدعم](https://forum.aspose.com/c/slides/11) لمزيد من الأمثلة والمساعدة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}