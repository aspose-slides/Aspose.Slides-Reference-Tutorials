---
title: تطبيق تأثير التدوير ثلاثي الأبعاد على الأشكال في برنامج PowerPoint
linktitle: تطبيق تأثير التدوير ثلاثي الأبعاد على الأشكال في برنامج PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تطبيق تأثيرات التدوير ثلاثي الأبعاد على الأشكال في PowerPoint باستخدام Aspose.Slides لـ Java من خلال هذا البرنامج التعليمي الشامل خطوة بخطوة.
weight: 12
url: /ar/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تطبيق تأثير التدوير ثلاثي الأبعاد على الأشكال في برنامج PowerPoint

## مقدمة
هل أنت مستعد للارتقاء بعروض PowerPoint التقديمية إلى المستوى التالي؟ يمكن أن تؤدي إضافة تأثيرات التدوير ثلاثية الأبعاد إلى جعل شرائحك أكثر ديناميكية وجاذبية. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيوضح لك هذا البرنامج التعليمي خطوة بخطوة كيفية تطبيق تأثيرات التدوير ثلاثي الأبعاد على الأشكال في PowerPoint باستخدام Aspose.Slides لـ Java. دعونا نتعمق في الأمر!
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر ما يلي:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: قم بتنزيل أحدث إصدار من Aspose.Slides for Java من[رابط التحميل](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم IDE مثل IntelliJ IDEA أو Eclipse للبرمجة.
4.  ترخيص صالح: إذا لم يكن لديك ترخيص، يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) لتجربة الميزات.
## حزم الاستيراد
أولاً، لنستورد الحزم الضرورية في مشروع Java الخاص بك. ستساعدك هذه الواردات في التعامل مع العروض التقديمية والأشكال باستخدام Aspose.Slides.
```java
import com.aspose.slides.*;

```
## الخطوة 1: قم بإعداد مشروعك
قبل الغوص في التعليمات البرمجية، قم بإعداد بيئة مشروعك. تأكد من إضافة Aspose.Slides for Java إلى تبعيات مشروعك.
أضف Aspose.Slides إلى مشروعك:
1.  قم بتنزيل ملفات Aspose.Slides JAR من ملف[صفحة التحميل](https://releases.aspose.com/slides/java/).
2. أضف ملفات JAR هذه إلى مسار بناء مشروعك.
## الخطوة 2: إنشاء عرض تقديمي جديد لـ PowerPoint
في هذه الخطوة، سنقوم بإنشاء عرض PowerPoint تقديمي جديد.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation pres = new Presentation();
```
يقوم مقتطف التعليمات البرمجية هذا بتهيئة كائن عرض تقديمي جديد حيث سنضيف أشكالنا.
## الخطوة 3: إضافة شكل مستطيل
بعد ذلك، دعونا نضيف شكل مستطيل إلى الشريحة الأولى.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
يضيف هذا الرمز شكلاً مستطيلاً في الموضع والحجم المحددين في الشريحة الأولى.
## الخطوة 4: تطبيق التدوير ثلاثي الأبعاد على المستطيل
الآن، دعونا نطبق تأثير التدوير ثلاثي الأبعاد على الشكل المستطيل.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
هنا، قمنا بتعيين العمق وزوايا دوران الكاميرا ونوع الكاميرا ونوع الإضاءة لإعطاء المستطيل مظهرًا ثلاثي الأبعاد.
## الخطوة 5: إضافة شكل خط
دعونا نضيف شكلاً آخر، هذه المرة خطًا، إلى الشريحة.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
يضع هذا الرمز شكل خط على الشريحة.
## الخطوة 6: تطبيق التدوير ثلاثي الأبعاد على الخط
وأخيرا، سوف نقوم بتطبيق تأثير دوران ثلاثي الأبعاد على شكل الخط.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
على غرار المستطيل، قمنا بتعيين الخصائص ثلاثية الأبعاد لشكل الخط.
## الخطوة 7: احفظ العرض التقديمي
بعد إضافة الأشكال وتكوينها، احفظ العرض التقديمي.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
يحفظ هذا الرمز العرض التقديمي الخاص بك باسم الملف المحدد بالتنسيق المطلوب.
## خاتمة
 تهانينا! لقد نجحت في تطبيق تأثيرات التدوير ثلاثي الأبعاد على الأشكال في عرض PowerPoint التقديمي باستخدام Aspose.Slides لـ Java. باتباع هذه الخطوات، يمكنك إنشاء عروض تقديمية جذابة وديناميكية. لمزيد من التخصيص والمزيد من الميزات المتقدمة، راجع[Aspose.Slides الوثائق](https://reference.aspose.com/slides/java/).
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لإنشاء عروض PowerPoint التقديمية وتعديلها ومعالجتها برمجيًا.
### هل يمكنني تجربة Aspose.Slides لـ Java مجانًا؟
 نعم يمكنك الحصول على[تجربة مجانية](https://releases.aspose.com/) أو أ[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) لاختبار الميزات.
### ما أنواع الأشكال التي يمكنني إضافة تأثيرات ثلاثية الأبعاد إليها في Aspose.Slides؟
يمكنك إضافة تأثيرات ثلاثية الأبعاد إلى أشكال مختلفة مثل المستطيلات والخطوط وعلامات الحذف والأشكال المخصصة.
### كيف يمكنني الحصول على دعم Aspose.Slides لـ Java؟
 يمكنك زيارة[منتدى الدعم](https://forum.aspose.com/c/slides/11) للمساعدة ومناقشة أي قضايا.
### هل يمكنني استخدام Aspose.Slides لـ Java في المشاريع التجارية؟
 نعم، ولكن عليك شراء ترخيص. يمكنك شراء واحدة من[صفحة الشراء](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
