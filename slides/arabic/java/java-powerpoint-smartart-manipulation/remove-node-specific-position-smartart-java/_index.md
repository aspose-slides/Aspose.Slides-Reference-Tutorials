---
"description": "تعرّف على كيفية إزالة عقدة من موضع محدد في SmartArt باستخدام Aspose.Slides لـ Java. حسّن تخصيص العرض التقديمي بسهولة."
"linktitle": "إزالة العقدة في موضع محدد في SmartArt"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إزالة العقدة في موضع محدد في SmartArt"
"url": "/ar/java/java-powerpoint-smartart-manipulation/remove-node-specific-position-smartart-java/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إزالة العقدة في موضع محدد في SmartArt

## مقدمة
في مجال تطوير جافا، تبرز Aspose.Slides كأداة فعّالة لمعالجة العروض التقديمية برمجيًا. سواءً كان الأمر يتعلق بإنشاء شرائح أو تعديلها أو إدارتها، يوفر Aspose.Slides لجافا مجموعةً فعّالة من الميزات لتبسيط هذه المهام بكفاءة. ومن هذه العمليات الشائعة إزالة عقدة من موضع محدد داخل كائن SmartArt. يشرح هذا البرنامج التعليمي خطوة بخطوة عملية إنجاز ذلك باستخدام Aspose.Slides لجافا.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من إعداد المتطلبات الأساسية التالية:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من [هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides لجافا: احصل على مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هذا الرابط](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): قم بتثبيت IDE مثل IntelliJ IDEA أو Eclipse لكتابة وتنفيذ كود Java بسلاسة.

## استيراد الحزم
في مشروع Java الخاص بك، قم بتضمين الحزم الضرورية للاستفادة من وظائف Aspose.Slides:
```java
import com.aspose.slides.*;
```
## الخطوة 1: تحميل العرض التقديمي
ابدأ بتحميل ملف العرض التقديمي الذي يوجد به كائن SmartArt:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "RemoveNodeSpecificPosition.pptx");
```
## الخطوة 2: التنقل عبر أشكال SmartArt
انتقل عبر كل شكل في العرض التقديمي لتحديد كائنات SmartArt:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes()) {
    if (shape instanceof ISmartArt) {
        ISmartArt smart = (ISmartArt) shape;
```
## الخطوة 3: الوصول إلى عقدة SmartArt
قم بالوصول إلى عقدة SmartArt في الموضع المطلوب:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## الخطوة 4: إزالة العقدة الفرعية
إزالة العقدة الفرعية في الموضع المحدد:
```java
((ISmartArtNodeCollection) node.getChildNodes()).removeNode(1);
```
## الخطوة 5: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل:
```java
pres.save(dataDir + "RemoveSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## خاتمة
مع Aspose.Slides لجافا، أصبح التعامل مع كائنات SmartArt ضمن العروض التقديمية أمرًا سهلاً. باتباع الخطوات الموضحة، يمكنك إزالة العقد بسلاسة من مواقع محددة، مما يُحسّن من إمكانيات تخصيص عرضك التقديمي.
## الأسئلة الشائعة
### هل استخدام Aspose.Slides لـ Java مجاني؟
Aspose.Slides لجافا هي مكتبة تجارية، ولكن يمكنك استكشاف وظائفها من خلال نسخة تجريبية مجانية. تفضل بزيارة [هذا الرابط](https://releases.aspose.com/) للبدء.
### أين يمكنني العثور على الدعم للاستعلامات المتعلقة بـ Aspose.Slides؟
لأي مساعدة أو استفسارات، يمكنك زيارة منتدى Aspose.Slides [هنا](https://forum.aspose.com/c/slides/11).
### هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
نعم يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/) لأغراض التقييم.
### كيف يمكنني شراء Aspose.Slides لـ Java؟
لشراء Aspose.Slides لـ Java، تفضل بزيارة صفحة الشراء [هنا](https://purchase.aspose.com/buy).
### أين يمكنني العثور على وثائق مفصلة لـ Aspose.Slides لـ Java؟
يمكنك الوصول إلى الوثائق الشاملة [هنا](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}