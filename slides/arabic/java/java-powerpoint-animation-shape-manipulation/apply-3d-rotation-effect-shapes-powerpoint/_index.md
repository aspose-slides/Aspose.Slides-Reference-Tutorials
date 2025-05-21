---
"description": "تعرف على كيفية تطبيق تأثيرات الدوران ثلاثية الأبعاد على الأشكال في PowerPoint باستخدام Aspose.Slides for Java من خلال هذا البرنامج التعليمي الشامل خطوة بخطوة."
"linktitle": "تطبيق تأثير الدوران ثلاثي الأبعاد على الأشكال في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تطبيق تأثير الدوران ثلاثي الأبعاد على الأشكال في PowerPoint"
"url": "/ar/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تطبيق تأثير الدوران ثلاثي الأبعاد على الأشكال في PowerPoint

## مقدمة
هل أنت مستعد للارتقاء بعروض PowerPoint التقديمية إلى مستوى جديد؟ إضافة تأثيرات الدوران ثلاثية الأبعاد تجعل شرائحك أكثر ديناميكية وتفاعلية. سواء كنت مطورًا محترفًا أو مبتدئًا، سيوضح لك هذا البرنامج التعليمي خطوة بخطوة كيفية تطبيق تأثيرات الدوران ثلاثية الأبعاد على الأشكال في PowerPoint باستخدام Aspose.Slides لجافا. هيا بنا!
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من [موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides for Java: قم بتنزيل أحدث إصدار من Aspose.Slides for Java من [رابط التحميل](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم بيئة التطوير المتكاملة مثل IntelliJ IDEA أو Eclipse للترميز.
4. رخصة صالحة: إذا لم يكن لديك ترخيص، يمكنك الحصول على [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) لتجربة الميزات.
## استيراد الحزم
أولاً، لنستورد الحزم اللازمة لمشروع جافا. ستساعدك هذه الحزم على التعامل مع العروض التقديمية والأشكال باستخدام Aspose.Slides.
```java
import com.aspose.slides.*;

```
## الخطوة 1: إعداد مشروعك
قبل البدء في البرمجة، قم بإعداد بيئة مشروعك. تأكد من إضافة Aspose.Slides لجافا إلى تبعيات مشروعك.
أضف Aspose.Slides إلى مشروعك:
1. قم بتنزيل ملفات Aspose.Slides JAR من [صفحة التحميل](https://releases.aspose.com/slides/java/).
2. أضف ملفات JAR هذه إلى مسار بناء مشروعك.
## الخطوة 2: إنشاء عرض تقديمي جديد في PowerPoint
في هذه الخطوة سوف نقوم بإنشاء عرض تقديمي جديد في PowerPoint.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation pres = new Presentation();
```
يقوم مقتطف التعليمات البرمجية هذا بتهيئة كائن عرض تقديمي جديد حيث سنضيف الأشكال الخاصة بنا.
## الخطوة 3: إضافة شكل مستطيل
الآن، دعونا نضيف شكل مستطيل إلى الشريحة الأولى.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
يضيف هذا الكود شكل مستطيل في الموضع والحجم المحددين على الشريحة الأولى.
## الخطوة 4: تطبيق الدوران ثلاثي الأبعاد على المستطيل
الآن، دعنا نطبق تأثير الدوران ثلاثي الأبعاد على شكل المستطيل.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
هنا، قمنا بتعيين العمق، وزوايا دوران الكاميرا، ونوع الكاميرا، ونوع الإضاءة لإعطاء المستطيل مظهرًا ثلاثي الأبعاد.
## الخطوة 5: إضافة شكل خط
دعونا نضيف شكلًا آخر، هذه المرة خطًا، إلى الشريحة.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
يضع هذا الكود شكل خط على الشريحة.
## الخطوة 6: تطبيق الدوران ثلاثي الأبعاد على الخط
وأخيرًا، سنطبق تأثير الدوران ثلاثي الأبعاد على شكل الخط.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
على غرار المستطيل، قمنا بتعيين خصائص ثلاثية الأبعاد لشكل الخط.
## الخطوة 7: حفظ العرض التقديمي
بعد إضافة الأشكال وتكوينها، احفظ العرض التقديمي.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
يحفظ هذا الكود العرض التقديمي الخاص بك باسم الملف المحدد بالتنسيق المطلوب.
## خاتمة
تهانينا! لقد نجحت في تطبيق تأثيرات الدوران ثلاثية الأبعاد على الأشكال في عرض تقديمي لبرنامج PowerPoint باستخدام Aspose.Slides لجافا. باتباع هذه الخطوات، يمكنك إنشاء عروض تقديمية جذابة وديناميكية. لمزيد من التخصيص والميزات المتقدمة، راجع [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/).
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لإنشاء عروض PowerPoint وتعديلها والتلاعب بها برمجيًا.
### هل يمكنني تجربة Aspose.Slides لـJava مجانًا؟
نعم يمكنك الحصول على [نسخة تجريبية مجانية](https://releases.aspose.com/) أو أ [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) لاختبار الميزات.
### ما هي أنواع الأشكال التي يمكنني إضافة تأثيرات ثلاثية الأبعاد إليها في Aspose.Slides؟
يمكنك إضافة تأثيرات ثلاثية الأبعاد إلى أشكال مختلفة مثل المستطيلات والخطوط والقطع الناقصة والأشكال المخصصة.
### كيف أحصل على الدعم لـ Aspose.Slides لـ Java؟
يمكنك زيارة [منتدى الدعم](https://forum.aspose.com/c/slides/11) للحصول على المساعدة ومناقشة أي مشاكل.
### هل يمكنني استخدام Aspose.Slides لـ Java في المشاريع التجارية؟
نعم، ولكن عليك شراء ترخيص. يمكنك شراء ترخيص من [صفحة الشراء](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}